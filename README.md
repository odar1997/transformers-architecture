# transformers-architecture

## StoryTelling 


---

# 🧠 Transformers: La Rebelión de los Autobots en la Tierra de la IA

Hace no mucho tiempo, en el vasto universo del procesamiento del lenguaje natural, dos facciones se disputaban el dominio: los **Decepticons**, encarnados por las arquitecturas tradicionales como las **RNN** y **LSTM**, y los **Autobots**, una nueva raza de modelos conocida como **Transformers**.

Durante años, los Decepticons reinaron con fuerza. Las **RNN** recorrían el texto paso a paso, atrapadas en la linealidad del tiempo. Las **LSTM**, más poderosas, intentaban recordar el pasado distante, pero su memoria era limitada, y su poder decayó al enfrentarse a secuencias largas y complejas. Las batallas eran lentas, y el entrenamiento costoso. El trono de la inteligencia artificial temblaba ante la necesidad de algo... más fuerte.

Y entonces, llegaron **ellos**.

## 🤖 El Ascenso de los Transformers (Autobots)

Liderados por **Optimus Prime**, el modelo de atención, los Transformers aterrizaron con una propuesta revolucionaria:

> *"No necesitamos recorrer las secuencias paso a paso. Miraremos TODO al mismo tiempo."*

La **Self-Attention** fue su arma secreta: una forma de enfocarse en las partes más importantes de la secuencia sin perder contexto, sin importar cuán lejos estuviera la información relevante. Ya no había límites de memoria, ya no había cuellos de botella.

### Las Ventajas de los Autobots

* 🔭 **Atención global**: pueden mirar todos los tokens a la vez y decidir qué es importante.
* 🚀 **Paralelización**: entrenan mucho más rápido que sus enemigos, al no depender del tiempo.
* 🧠 **Escalabilidad**: pueden crecer hasta convertirse en titanes como BERT, GPT, o T5.

Y así, los Transformers liberaron al NLP del yugo secuencial. Los Decepticons se replegaron, usados solo en tareas pequeñas, obsoletos frente al poder del paralelismo y la atención.

---

## 📜 Legado

Hoy, los Autobots dominan las tierras del procesamiento de lenguaje natural, visión por computadora, música, bioinformática y más. Cada vez que entrenas un modelo basado en atención, estás invocando el legado de Optimus Prime y su ejército.

Y recuerda:

> *"Hasta que todos los tokens sean atendidos."* – Optimus Prime 

---

## Tecnical presentation

�
�
 Clase: La Arquitectura Transformer – Historia, 
Funcionamiento y Relevancia 
1. Historia y contexto: El nacimiento del Transformer 
Durante muchos años, las tareas de procesamiento de lenguaje natural (NLP) se abordaron 
principalmente con redes neuronales recurrentes (RNN) y, más tarde, con LSTM (Long 
Short-Term Memory). Estos modelos fueron fundamentales en avances como traducción 
automática y generación de texto, pero tenían limitaciones significativas. Su procesamiento 
secuencial los hacía lentos, y tenían dificultades para capturar relaciones a largo plazo entre 
palabras en una oración. 
En 2017, un grupo de investigadores de Google Brain, liderados por Ashish Vaswani, 
propuso una nueva arquitectura en el artículo titulado "Attention Is All You Need". Esta 
publicación revolucionó el campo del NLP al introducir el modelo Transformer, una 
arquitectura que eliminaba completamente el uso de recurrencia y que se basaba en 
mecanismos de atención para modelar relaciones entre elementos de una secuencia. Esta 
innovación dio lugar a un salto de calidad en tareas como traducción, clasificación de texto y 
más, y sentó las bases de modelos avanzados como BERT, GPT, T5, y otros. 
2. Motivación: ¿Por qué reemplazar a las RNN y LSTM? 
Las redes recurrentes procesan el texto palabra por palabra, lo que las hace 
inherentemente secuenciales. Esto implica que no pueden aprovechar del todo el 
paralelismo de los procesadores modernos como las GPUs. Además, a medida que las 
secuencias se hacen más largas, su capacidad para recordar información de palabras 
distantes disminuye, lo cual afecta su comprensión del contexto. 
El Transformer rompe con esta secuencialidad. Procesa todo el texto al mismo tiempo, 
capturando de forma eficiente las relaciones entre todas las palabras, sin importar cuán 
alejadas estén unas de otras. Además, gracias a su diseño, puede entrenarse más 
rápidamente y escalar a modelos mucho más grandes que sus predecesores. 
3. Visión general de la arquitectura Transformer 
La arquitectura Transformer está dividida en dos grandes bloques: el codificador (encoder) 
y el decodificador (decoder). Cada uno de ellos está compuesto por varias capas (por 
ejemplo, 6 capas en el modelo original) que contienen subcomponentes especializados. 
● Encoder: toma como entrada una secuencia de tokens (palabras convertidas en 
vectores) y produce una representación contextualizada de cada uno. Cada capa del 
encoder aplica mecanismos de self-attention y redes feed-forward densas. 
● Decoder: recibe los embeddings de salida ya generados (como palabras previas en 
la generación de texto) y los embeddings del encoder. Así, produce la siguiente 
palabra en una secuencia, utilizando atención cruzada (cross-attention) y 
self-attention para generar texto coherente. 
4. Self-Attention: El corazón del Transformer 
El mecanismo de self-attention permite que cada palabra en una oración mire a todas las 
demás para decidir qué tan importante es cada una en su contexto. Por ejemplo, en la frase 
"La niña dejó el libro porque estaba cansada", el modelo debe entender que "cansada" se 
refiere a "niña", no a "libro". 
El self-attention se implementa utilizando tres vectores para cada palabra: 
● Query (Q): lo que buscamos. 
● Key (K): lo que ofrecemos. 
● Value (V): la información que compartimos. 
La atención se calcula como: 
Attention(Q, K, V) = softmax(QKᵀ / √d_k) * V 
Esta fórmula mide la similitud entre queries y keys para determinar cuánto "peso" darle a 
cada value. 
5. Multi-Head Attention: Diversidad de perspectivas 
Una sola capa de atención puede capturar una relación entre palabras, pero a veces son 
necesarias múltiples perspectivas (por ejemplo, relaciones gramaticales, semánticas, 
sintácticas). Por eso, el Transformer usa multi-head attention, que consiste en replicar el 
mecanismo de atención varias veces en paralelo con diferentes pesos. Cada cabeza 
aprende una forma distinta de representar las relaciones entre palabras. Luego, se 
combinan todas las salidas en una sola matriz que se pasa a la siguiente capa. 
6. Positional Encoding: Incorporar el orden de las palabras 
A diferencia de las RNN, el Transformer no tiene una estructura secuencial interna, por lo 
que necesita otra forma de entender el orden de las palabras. Para esto, se agregan 
vectores de codificación posicional a los embeddings de las palabras. Estos vectores 
usan funciones seno y coseno de diferentes frecuencias para representar posiciones, lo que 
permite al modelo distinguir entre "El perro muerde al hombre" y "El hombre muerde al 
perro". 
7. Feed-Forward Networks y otras capas 
Después del módulo de atención, cada capa del Transformer incluye una red feed-forward 
completamente conectada, que aplica transformaciones no lineales a los datos de cada 
posición. También se emplean dos técnicas importantes: 
● Normalization (Layer Normalization): estabiliza el entrenamiento. 
● Residual Connections: conexiones que saltan capas para evitar el problema del 
desvanecimiento del gradiente. 
Cada capa puede entonces ajustar la representación de cada token de manera refinada y 
robusta. 
8. El Decoder y su atención cruzada 
El decoder funciona de manera similar al encoder, pero con una diferencia clave: incluye 
una capa de cross-attention, que permite que el decoder se enfoque en partes relevantes 
de la salida del encoder mientras genera el texto final. También incorpora máscaras para 
que no pueda mirar las palabras futuras durante el entrenamiento (lo que se llama "masked 
self-attention"). 
9. Impacto y aplicaciones del Transformer 
La arquitectura Transformer ha sido adoptada como base para los modelos más potentes y 
útiles de la actualidad: 
● GPT (Generative Pre-trained Transformer): usado para generación de texto, 
chatbots, asistentes virtuales. 
● BERT (Bidirectional Encoder Representations from Transformers): diseñado 
para comprender texto y realizar tareas como clasificación, extracción de 
información, etc. 
● T5 (Text-to-Text Transfer Transformer): convierte cualquier tarea de NLP en una 
tarea de traducción entre formatos de texto. 
● Vision Transformers (ViT): aplican Transformers a tareas de visión por 
computadora, como clasificación de imágenes. 
También se usan en música, biología (como en la predicción de estructuras de proteínas), y 
mucho más. 
10. Conclusión y reflexiones 
La arquitectura Transformer representa un cambio de paradigma en el diseño de modelos 
para inteligencia artificial, especialmente en el lenguaje natural. Su capacidad para modelar 
relaciones complejas sin necesidad de procesar secuencias paso a paso ha permitido 
desarrollar sistemas más precisos, rápidos y escalables. Su diseño modular y elegante ha 
inspirado decenas de variantes y sigue evolucionando con nuevas investigaciones. 
Aprender cómo funciona un Transformer es esencial para comprender cómo trabajan los 
modelos de lenguaje más avanzados de la actualidad, incluyendo aquellos con los que 
interactuamos todos los días. 
