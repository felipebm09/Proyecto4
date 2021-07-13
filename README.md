
# Proyecto #4


Se diseña un sistema de modulación de 16-QAM y se realiza una simulación de modulación, ruido y demodulación del envio de una imagen de baja resolución.
## Authors
- Felipe Badilla Marchena-B70848
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
adecuada y poderlo dichos valos en un nuevo array. Además decido
tratar la parte de la onda moduladora de una manera distinta que solo 1's y 0's,
sino que se visualiza con valores del 0 al 15 que corresponden a la codificación de 
los paquetes de bits por símbolo.

### Demodulación
La señal modulada se pasa por el mismo canal de ruido para permitir simular las variaciones 
no ideales. El método que se utiliza para poder conocer los rángos en que actuan los simbolos,
se introduce una señal de prueba que corresponde a las 16 diferentes combinaciones de paquetes
de bits. De esta manera obtenemos un valor exacto y se traduce a un rango de evalución con cierto
grado de tolerancia para ir decodificando la señal bit por bit y recuperar la imágen.

Este proceso es exitoso, sin embargo debería hacer una forma más eficiente de hacer la demodulación
ya que esta es muy sensible a los cambios, un ligero cambio en la frecuencia o en mpp puede significar
la pérdida de una cantidad grande de información. Además cabe resaltar que este sistema en si es más sensible
a ruidos que el BPSK ya que los rangos son más restringidos, pero es mucho más rápido, por esto se usa en
determinadas situaciones en donde hay poco ruido.