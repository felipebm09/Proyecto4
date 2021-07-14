
# Proyecto #4


Se diseña un sistema de modulación de 16-QAM y se realiza una simulación de modulación, ruido y demodulación del envio de una imagen de baja resolución.
## Authors
* Estudiante: **Felipe Badilla Marchena**
* Carné: **B70848**
* Grupo: **1**
- [@felipebm09(https://www.github.com/felipebm09)

## Documentation

Se realiza una etapa de modulación y demodulación 16-QAM
basada en el documento facilitado por el profesor Fabián Abarca Calderón
en colaboración con Jeaustin Sirias Chacón. Para ello en
cuanto a la modulación, se parte del conocimiento de que con este 
método se transmiten 4 bits por símbolo y que además los ajustes
de amplitud en la portadora se hacen como es descrito en el documento.

### Modulación
Debido a esto se sabe que el tiempo de simulación va a ser 4 veces más rápido
por lo tanto se divide este parámetro por 4 y se evalúan cada una de los bits
de entrada en paquetes de 4 con el objetivo de elegir la codificación por amplitud 
adecuada y poner dichos valos en un nuevo array. Además decido
tratar la parte de la onda moduladora de una manera distinta que solo 1's y 0's,
sino que se visualiza con valores del 0 al 15 que corresponden a la codificación de 
los paquetes de bits por símbolo para facilitar su entendimiento porque sino en binario tendría una freciencia muy alta.

### Demodulación
La señal modulada se pasa por el mismo canal de ruido para permitir simular las variaciones 
no ideales. El método que se utiliza para poder conocer los rángos en que actuan los simbolos,
es introducir una señal de prueba que corresponde a las 16 diferentes combinaciones de paquetes
de bits. De esta manera obtenemos un valor exacto de energía de entrada y se traduce a un rango de evalución con cierto
grado de tolerancia para ir decodificando la señal bit por bit y recuperar la imágen.

Este proceso es exitoso, sin embargo debería hacer una forma más eficiente de hacer la demodulación
ya que esta es muy sensible a los cambios, un ligero cambio en la frecuencia o en mpp puede significar
la pérdida de una cantidad grande de información. Además cabe resaltar que este sistema en si es más sensible
a ruidos que el BPSK ya que los rangos son más restringidos, pero es mucho más rápido, por esto se usa en
determinadas situaciones en donde hay poco ruido.

### Estacionariedad y Ergodicidad
Podemos que la señal es estacionaria ya que su promedio se mantiene aproximadamente constante a travez del 
tiempo, además para probar ergodicidad se calculan la media temporal y la media estadística, en donde observamos
que estas son aproximadamente iguales y por tanto podemos concluir que es un sistema ergodico. Adicionalmente se
obtiene la autocorrelación temporal con el objetivo de compararla con la autocorrelación estadística, pero no me queda
muy claro como calcular esta última (si pudiera proponer una solución o aclararmelo en los comentarios sería genial).

### Densidad espectral de potencia

Para la última parte de este proyecto se encuentra la densidad espectral de potencia en donde se obtene al 
igual que para BPSK el ancho de banda está al rededor de 5000, sin embargo para esta modulación se observa
una menor variedad de frecuencias en uso en el sentido de que la la de 5000 es bastante prominente con respecto
a la intensidad de las otras frecuencias que aparecen.
