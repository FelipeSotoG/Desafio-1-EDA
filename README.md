# Desafio-1-EDA

# La Problemática

El problema de asignacion de objetivos de armas (WTA) es un problema de optimización, el cual consiste en encontrar una asignación óptima de un conjunto de armas a un conjunto de objetivos para maximizar el daño total, es decir tendremos un grupo de armas con distintos valores de destrucción y tendremos un grupo de objetivos, en donde el objetivo principal es maximiazar el daño o minimizar la posibilidad de sobrevivencia de los objetivos.

En resumen tenemos una serie de armas y una serie de objetivos, en donde las armas son de tipo i=1 .....m. Hay W sub i armas disponibles . Del mismo modo hay j=1...n objetivos con valor V sub j. además debemos considerar que cada arma (w) tiene la probabilidad de destruir cada objetivo (V). dada por P sub ij.

Para entender de mejor manera el problema se muestra el sgt ejemplo.

Un comandante tiene 5 tanques, 2 aviones y 1 embarcación y se le indica que se enfrente a 3 objetivos con valores 5, 10 y 20. Cada tipo de arma tiene las siguientes probabilidades de éxito contra cada objetivo:

Tipo de arma  | V1=5  | V2=10 | V3=20
tanque       |   0.3  |   0.2 |   0.5
aeronave     |  0.1   | 0.6   |   0.5
Buque de mar |  0.4   |   0.5 |   0.4

Una solución factible es asignar el buque de mar y un avión al objetivo de mayor valor (3). Esto da como resultado un valor de supervivencia esperado de {20 (0,6) (0,5) = 6}20(0,6)(0,5)=6. Luego, se podría asignar el avión restante y los 2 tanques al objetivo n.° 2, lo que daría como resultado un valor de supervivencia esperado de 10 (0,4) (0,8) ^ {2} = 2,56}10(0,4)(0,8)^{2}=2,56. Finalmente, los 3 tanques restantes se asignan al objetivo #1 que tiene un valor de supervivencia esperado de 5 (0,7) ^ {3} = 1,715}5(0,7)^{3}=1,715. Por lo tanto, tenemos un valor de supervivencia total esperada de { 6 + 2,56 + 1,715 = 10,275}6+2,56+1,715=10,275. Tenga en cuenta que se puede lograr una mejor solución asignando 3 tanques al objetivo n.º 1, 2 tanques y una embarcación al objetivo n.º 2 y 2 aviones al objetivo n.º 3, dando un valor de supervivencia esperado de 5(0,7)^{3}+10(0,5)(0,8)^{2}+20(0,5)^{2}=9,915}{ 5(0,7)^{3}+10(0,5)(0,8)^{2}+20(0,5)^{2}=9,915}.


# La Solución

La heuristica es la sumatoria de el valor del objetivo por la probabilidad de supervivencia, dado cuantas armas lo estan atacando.

tenemos la formula matematica en la siguiente imagien.
https://wikimedia.org/api/rest_v1/media/math/render/svg/74572279af9ae4c8d9099349fb1d8a320aba068a

destacar que la formula matemática implementada, en donde se utiliza la probabilidad de que el objetivo pueda sobrevivir al ataque(probabilidad de supervivencia 1-p en donde p es la probabilidad de destrucción).

tenemos como restricciones las siguientes:
https://wikimedia.org/api/rest_v1/media/math/render/svg/8683e61b76dfc758c77a0b6546cbee3c9a11697e
https://wikimedia.org/api/rest_v1/media/math/render/svg/6ad5d4a9aca9ce4614c777ed03a9b4d856dbf05f
-La primera restricción requiere que el número de armas de cada tipo asignadas no exceda el número disponible
-La segunda restricción es la restricción integra
Tener en cuenta que minimizar el valor de supervivencia esperado es lo mismo que maximizar el daño esperado
