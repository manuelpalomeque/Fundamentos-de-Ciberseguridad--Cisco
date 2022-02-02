## Parte 1: Usar métodos de análisis de riesgos

### Riesgo cuantitativo

El análisis de riesgo cuantitativo es el proceso de determinar objetivamente el impacto de un evento mediante el uso de
métricas y modelos. Un análisis cuantitativo se basa en información histórica y tendencias para predecir el rendimiento 
futuro. El resultado del análisis es un valor. Calcular la expectativa de pérdida anualizada (ALE) es un método común 
para estimar la disminución en el valor o la capacidad de un activo después de un evento adverso. ocurre.

### Paso 1: Calcule el valor de los activos.

En este paso, demostrará cómo calcular el valor del activo.


* Costo inicial del activo
El valor del activo es el gasto total que se necesita para reemplazar un activo. Por ejemplo, el valor total de un 
activo puede incluir la compra y la concesión de licencias o el desarrollo junto con los costos de mantenimiento y 
soporte. En este ejemplo, el servidor de la base de datos de clientes de la organización costó aproximadamente 
$20,000. Esto incluye el hardware, el software y la configuración.


* Valor organizacional
Un valor intangible es más difícil de calcular porque puede incluir el costo de crear, adquirir y volver a crear 
información, y el impacto comercial o la pérdida si la información se pierde o se ve comprometida. También puede 
incluir costos de responsabilidad. En este ejemplo, el costo de crear el sitio web del cliente es de $40,000.


* Valor Público
Un costo intangible que incluye la pérdida de información o procesos patentados, o la pérdida de la reputación
comercial. Este valor se estima en $75,000

¿Cuál es el valor total de los activos del servidor?

    El valor tangible e intangible del servidor es de aproximadamente $135,000.

¿Por qué el costo intangible es tan alto? ¿Es esto realista?

    Considere el valor de la reputación de una organización. La reputación de una empresa es muy difícil de construir y 
    mantener. El daño a la reputación puede ser muy costoso y permanente. Entonces, sí, esta valoración es realista.

### Paso 2: calcular el factor de exposición

El factor de exposición se expresa como un porcentaje (o equivalente decimal) de pérdida de un activo si se realiza una 
amenaza o vulnerabilidad específica. El factor de exposición es un valor subjetivo. Si el activo se pierde por completo,
el factor de exposición sería 100 % o 1. El factor de exposición podría ser una fracción del valor, como 40 % o 0,4,
por ejemplo.

Pregunta:
Dado un ejemplo, ¿cuál es el impacto en el servidor si la sala del servidor se inunda y el costo de restaurar el servidor es de $30,000?

Valor del activo: $ 135.000
Costo de restauración: $ 30.000
Factor de exposición:

    El factor de exposición es 30.000 / 135.000 = 22 % o 0,22

### Paso 3: Calcule la expectativa de pérdida única

Calcule la expectativa de pérdida única (SLE) tomando el valor del activo y multiplicándolo por el factor de 
exposición. El resultado es la pérdida en dólares que espera debido a la ocurrencia de un solo evento. Un solo activo
puede tener múltiples amenazas o vulnerabilidades potenciales, y se puede calcular una sola expectativa de pérdida para 
cada ocurrencia.

Por ejemplo, se estima que un ataque de denegación de servicio tiene un impacto o factor de exposición del 20% o 0,2. 
Esto significaría que el SLE es de $135 000 x 0,2 = $27 000.

Calcule el SLE si se produce una falla en el disco duro o en la unidad de almacenamiento donde se estima el mismo valor 
de activo en $135,000. Este tipo de pérdida daría lugar a un factor de exposición de 0,5.

Preguntas:
¿Qué es el LES?

    SLE es igual a 135.000 x 0,5 = 67.500 dólares

Calcule el SLE de un ataque de ransomware con un factor de exposición del 100 % o 1,0.

    SLE es igual a 135.000 x 1.0 = $135.000


### Paso 3: Calcule la expectativa de pérdida única

Calcule la expectativa de pérdida única (SLE) tomando el valor del activo y multiplicándolo por el factor de exposición.
El resultado es la pérdida en dólares que espera debido a la ocurrencia de un solo evento. Un solo activo puede tener
múltiples amenazas o vulnerabilidades potenciales, y se puede calcular una sola expectativa de pérdida para cada 
ocurrencia.

Por ejemplo, se estima que un ataque de denegación de servicio tiene un impacto o factor de exposición del 20% o 0,2. 
Esto significaría que el SLE es de $135 000 x 0,2 = $27 000.

Calcule el SLE si ocurre una falla en el disco duro o en la unidad de almacenamiento donde el mismo valor de activo se
estima en $135,000. Este tipo de pérdida daría lugar a un factor de exposición de 0,5.

Preguntas:
¿Cual es el SLE?

    SLE es igual a 135.000 x 0,5 = 67.500 dólares

Calcule el SLE de un ataque de Ransomware con un índice de exposición del 100 % o 1,0.

    SLE es igual a 135,000 x 1.0 = $135,000 

### Paso 4: Calcular la Tasa de Ocurrencia Anualizada

La tasa anualizada de ocurrencia (ARO) es una medida de la frecuencia con la que ocurre un evento en un solo año. ARO 
siempre se expresa en una calificación anual incluso si ocurre un incidente y se registra en otras medidas de tiempo. 
En nuestro ejemplo, el servidor de la base de datos del cliente se ve afectado por un ataque DoS o DDoS cada 120 días 
o 4 meses en promedio. Esto significa que el evento ocurrirá tres veces en un año calendario en promedio, por lo que el 
ataque DoS/DDoS tiene un ARO de 3. 

En este escenario, calcule el ARO de un ataque de ransomware en el servidor de la base de datos del cliente comercial.
En promedio, el servidor experimenta ataques de ransomware cada 24 meses o dos años.

Pregunta:
¿Cuál es el ARO de un ataque de ransomware en el servidor de la base de datos del cliente?

    Si el evento ocurre cada veinticuatro meses, el ARO sería 12/24 = 0.5.

En este escenario, calcule el ARO de una falla de hardware con el servidor de la base de datos del cliente. En promedio,
el servidor experimenta fallas de hardware cada 30 meses

    Si el evento ocurre cada treinta meses, el ARO sería 12/30 = 0.4.

### Paso 5: Calcule la expectativa de pérdida anualizada

La expectativa de pérdida anualizada (ALE) es el producto de la ARO y la SLE. Para calcular el ALE, tome el SLE y 
multiplíquelo por el ARO. Por ejemplo, si se determina que un corte de energía tiene un SLE de $50,000.00 y un ARO de 
0.5, el ALE sería de $25,000.

Preguntas:
¿Cuál es el ALE de una falla de hardware con el servidor de la base de datos del cliente si el SLE = $ 5,000 y 
ARO = 2.5?

     ALE = 5000 x 2,5 = 12500

¿Cuál es el ALE de un ataque de piratería con el servidor de la base de datos del cliente si el SLE = $ 10,000 y ARO 
= 0.5?

    Answer: ALE = 10,000 x 0.5 = 5,000

### Paso 6: Calcular el Análisis de Riesgo Cualitativo

Un análisis cualitativo compara el impacto de una amenaza con la probabilidad de que ocurra y utiliza etiquetas como 
bajo, medio o alto. El impacto de un evento es una medida de la pérdida cuando una amenaza explota una vulnerabilidad. 
La probabilidad es la probabilidad de que ocurra el evento de amenaza.
El análisis de riesgo cualitativo examina el nivel de impacto general en la organización. Estos problemas incluyen 
pérdida de ingresos, pérdida de reputación y pérdida de clientes.

<img src="https://github.com/manuelpalomeque/Fundamentos-de-Ciberseguridad--Cisco/blob/main/CYBERSECURITY%20ESSENTIALS/Capturas%20de%20pantallas/6.png">

Utilice las tablas para registrar el impacto cualitativo de los eventos que se describen a continuación.

Preguntas:
En el primer caso, el servidor web experimenta una falla en el disco duro que provoca una pérdida de ingresos, reputación y
clientes. Este es un impacto de muy alto riesgo y una posible probabilidad de ocurrencia.

<img src="https://github.com/manuelpalomeque/Fundamentos-de-Ciberseguridad--Cisco/blob/main/CYBERSECURITY%20ESSENTIALS/Capturas%20de%20pantallas/7.png">

    La respuesta correcta es Mayor

En el segundo caso, se lanza un ataque de denegación de servicio contra el servidor web. Se trata de un impacto de alto 
riesgo y probable probabilidad de ocurrencia.

<img src="https://github.com/manuelpalomeque/Fundamentos-de-Ciberseguridad--Cisco/blob/main/CYBERSECURITY%20ESSENTIALS/Capturas%20de%20pantallas/8.png">

    La respuesta correcta es Mayor

En el tercer evento, hay un incendio en la sala de servidores. Este es un impacto de muy alto riesgo y una rara 
probabilidad de ocurrencia.

<img src="https://github.com/manuelpalomeque/Fundamentos-de-Ciberseguridad--Cisco/blob/main/CYBERSECURITY%20ESSENTIALS/Capturas%20de%20pantallas/9.png">

    La respuesta correcta es Moderada.

En el cuarto evento, los datos de la tarjeta de crédito han sido robados. Este es un impacto de muy alto riesgo y una 
probabilidad de ocurrencia poco probable.

<img src="https://github.com/manuelpalomeque/Fundamentos-de-Ciberseguridad--Cisco/blob/main/CYBERSECURITY%20ESSENTIALS/Capturas%20de%20pantallas/10.png">

    La respuesta correcta es Mayor

En el quinto evento, hay un tornado en el área. Este es un impacto de bajo riesgo y una rara probabilidad de 
ocurrencia.

<img src="https://github.com/manuelpalomeque/Fundamentos-de-Ciberseguridad--Cisco/blob/main/CYBERSECURITY%20ESSENTIALS/Capturas%20de%20pantallas/11.png">

    La respuesta correcta es Menor.


