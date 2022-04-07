# Desafio-1-EDA

# La Problemática

El problema de asignacion de objetivos de armas (WTA) es un problema de optimización, el cual consiste en encontrar una asignación óptima de un conjunto de armas a un conjunto de objetivos para maximizar el daño total.

En resumen tenemos una serie de armas y una serie de objetivos, en donde las armas son de tipo i=1 .....m. Hay W sub i armas disponibles . Del mismo modo hay j=1...n objetivos con valor V sub j. además debemos considerar que cada arma (w) tiene la probabilidad de destruir cada objetivo (V). dada por P sub ij.

tenemos la formula matematica en la siguiente imagien.
https://wikimedia.org/api/rest_v1/media/math/render/svg/74572279af9ae4c8d9099349fb1d8a320aba068a

destacar que la formula matemática implementada, en donde se utiliza la probabilidad de que el objetivo pueda sobrevivir al ataque(probabilidad de supervivencia 1-p en donde p es la probabilidad de destrucción).

tenemos como restricciones las siguientes:
https://wikimedia.org/api/rest_v1/media/math/render/svg/8683e61b76dfc758c77a0b6546cbee3c9a11697e
https://wikimedia.org/api/rest_v1/media/math/render/svg/6ad5d4a9aca9ce4614c777ed03a9b4d856dbf05f
-La primera restricción requiere que el número de armas de cada tipo asignadas no exceda el número disponible
-La segunda restricción es la restricción integra
Tener en cuenta que minimizar el valor de supervivencia esperado es lo mismo que maximizar el daño esperado

# La Solución
