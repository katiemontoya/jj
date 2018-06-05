===============================================================================
Red neuronal backpropagation

===============================================================================
Katherin Montoya (1), Julian Salamanca (2)
===============================================================================
Creanción de la arquitectura y topología de la Red nueronal artificial (Ann)
"Artificial neural network"

El presente código brinda una solución practica al problema de predicciones
meteorologicas. Esta predicción se realiza mendiante un red neuronal artificial,
utilizando el algoritmo backpropagation que se desarrollo mediante la 
infraestructura computacional de análisis de datos ROOT.

Los paremetro meteorologicos como la Velocidad del viento, Humedad, Visibilidad 
y Temperatura son extraidas de tres periodos anuales 2010, 2013 y  2016, de
la base de datos SKBO, El tiempo.com.
 
Por ende estas variables son tomadas como las señales externas la cual se deben 
de entender como señales que provienen de una neurona postsináptica.
Esto es necesario para activar la red neuronal. 

Pero antes estas señales de entradas se escalan. En el codigo de escalamieto.C,
dentro del archivo encontramos una carpeta llamada señales de entrada.
El escalamiento consiste en la normalización de estos intervalos [0,1]. 
Ahora bien se necesita definir la red neuronal que se va estimular. 
Para esto necesitamos de los conceptos básicos . 

===============================================================================
 Conceptos 
===============================================================================

Arquictura :           La arquitectura de una red neuronal es la estructura 
                       físca de las conexiones de una red.
                       
Topología  :           Es la organización de la red neuronal, y debe 
                       especificar cómo se conectan las capas de neuronas 
                       que conforman la arquitectura.
                       
Aprendizaje:           El aprendizaje se da por la modificación de sus pesos,
                       estos parámetros son libres y se ejecutan mediante la 
                       estimulación de la neurona. Hay tres tipos de 
                       aprendizaje: aprendizaje supervisado, aprendizaje no 
                       supervisado, y aprendizaje por refuerzo.
                       

La notación de la Ann(3,12,8,2). Apartir de esta notación podemos distinguir
4 tipos de capas:

*Capa de entrada :      Esta compuesta por 3 neuronas que reciben datos o 
                        señales.
*Capa oculta1    :      Esta compuesta por 12 neuronas, no tiene conexión con 
                        el exterior y proporciona una señal para la siguiente
                        capa.
*Capa oculta2    :      Esta compuesta por 8 nueronas, y proporciona una 
                        señal a la siguiente capa. 
*Capa de Salida  :      Compuesta por 2 neuronas, estas proporcionan la
                        respuesta de la red neuronal.

Teniendo cuenta estos conceptos podemos distinguir que la red neuronal esta arreglada 
ordenadamente.  

El código nombrano Ann.C  tiene como objetivo de crear una red neuronal
artificial, con la capacidad de hacer conexiones con todas sus neuronas en 
cada capa, que utiliza la función sigmoide como activación. 

El objetivo principal es definir la magnitud de la red seguido a eso incializar lo pesos y umbrales aleatorios 

La principal motivación del código Ann es proporcionar a la comunidad, código 
abierto como una herramienta para construir n arquitecturas. Este código se
realizó en mediante la infraestructura computacional de análisis de datos ROOT.

De esta manera en el código back.C tiene como objetivo ejecutar el algoritmo
backapropagation. La importancia de la red backpropagation consiste en su 
capacidad para adaptar de forma automática los pesos dados por las neuronas de
las capas intermedias, para aprender la relación que existe entre un conjunto 
de patrones de entrada y sus salidas correspondientes. Es importante la 
capacidad de generalización de la red para la facilidad de dar salidas 
satisfactorias de una capa y entradas a la siguiente capa.

Es decir que el algoritmo Backpropagation es un método de aprendizaje 
supervisado de gradiente descendente que tiene dos fases; una hacia delante y 
otra hacia atrás.

Por ultimo se repite este proceso en los codigos Ann1.C y back1.C arrojando un
resultado satisfactorio. 

================================================================================
Definición de variables 
================================================================================

 w :                    pesos sipnáticos.
 u :                    Umbrales.
 w1:                    Pesos sinapticos para la capa de entrada y capa oculta1.
 w2:                    Pesos sinapticos para la capa oculta1 y capa oculta2.    
 w3:                    Pesos sinapticos para la capa oculta2 y capa de salida.
 u2:                    Umbral para las nodos de la capa oculta oculta 1.
 u3:                    Umbral para las nodos de la capa oculta oculta 2.
 u4:                    Umbral para las nodos de la capa de salida.
 alfa:                  Coeficiente de aprendizaje. 
 vsup:                  Variable supervisada.
