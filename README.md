
<h1>Proyectos de robótica y electrónica</h1>

<h2>Vehículo controlado por PC mediante puerto LPT1</h2>

<p>Con la intención de practicar la programación en lenguaje ensamblador y electrónica, construí un vehículo pequeño impulsado por dos motores de corriente continua de los que se utilizaban en las grabadoras de cinta magnetica. Cada motor es controlado por un Relay que determina el sentido de rotación y un tercer relay activa o desactiva ambos motores. Cada relay es activado o desactivado por transistores de potencia tipo "Darlington" y estos son activados o desactivados por la corriente que llega de los pines del puerto LPT1. En la parte delantera del vehículo se encuentran unos sensores de contacto para detectar el choque con las paredes. Los senosres de contacto activan o desactivan pines de entrada del puerto paralelo LPT1 de la PC. Los dos motores mueven las ruedas grandes de tracción que se encuentran a los lados del vehículo y al frente existe una "rueda loca" que sirve de tercer punto de apoyo.</p>
<img width="567" alt="vehiculo controlado por PC" src="https://github.com/user-attachments/assets/cb1ed193-599e-4fa0-8f1d-bf2699c664d3" />

<p>El cable que se conecta en la parte trasera del vehículo se conecta a la caja de interface que además contiene en su interior la fuente de alimentación del vehículo. Es esta interface la que se conecta al puerto paralelo del LPT1 del PC en el conector de control. La interface tambien contiene un control de conmutación que permite controlar el vehículo mediante un mando electrónico que tambien se conecta al conector de control.</p>

<p>Inicialmente el software de control fue una aplicación de consola realizada en lenguaje Ensamblador que se ejecutaba sobre el sistema operativo MS-Dos. para acceder al puerto paralelo LPT1 de la computador solo fue necesario utilizar las instrucciones de ensamblador OUT e IN y direccionando el puerto 0x378 que corresponde al LPT1. Luego se reprogramó el software con un compilador de Turbo Pascal, metiendo las instrucciones IN o OUT de ensamblador dentro de una función y un procedimiento de Pascal. Se pudo ejecutar en MS-Dos y Windows 98</p>


<h2>Brazo articulado de 3 grados de libertad</h2>

<p>Utilizando tres motores PAP (paso a paso) unipolares recuperados de viejas impresoras, construí un brazo robótico de tres grados de libertad. Cada articulación del brazo se conecta directamente al eje de un motor PAP sin utilizar reductor. Las bobinas de los motores PAP se activan o desactivan con transistores tipo Darlington recuperados de los drivers de las agujas de las antiguas impresoras de cinta, siendo 4 transistores por cada motor. Los transistores a su vez se activan o desactivan con el voltaje de los pines del puerto paralelo LPT1 de la PC.</p>
<img width="568" alt="brazo de 3 grados de libertad" src="https://github.com/user-attachments/assets/8d9c3413-013b-48f6-886a-6bd6ffcb4cf1" />

<p>El software de control se realizó con Borland Delphi 6 y utilizando la librería "io.dll" que permite acceder de manera segura mediante un driver de sistema al puerto LPT1 direccionado como 0x378. La aplicación consiste en una interface grófica simple con botones para cada dirección de movimiento de cada motor de brazo y fue ejecutada en Windows 98 y Windows XP. Debido a que no se utilizaron sistemas de reductores con engranajes para las articulaciones del brazo, los motores al ser de poco torque y estar sobrecargados, perdian pasos y no siempre se lograba posicionarlos en el ángulo deseado. Por este motivo o se continuó perfeccionando el software de este brazo robótico.</p>


<h2>Reloj con pantalla 7 segmentos</h2>

<p>En tiempo libre decidí practicar la creación de subprocesos con el lenguaje C++ creando una aplicación para controlar por puerto paralelo LPT1 de la computadora, una pantalla con elementos 7 segmentos. Debido a que no contaba con un decodificador 7 segmento, decidí encender los 7 segmentos alternándolos a alta velocidad, de manera que los primeros 7 bits del puerto de datos se emplearon para crear el número en las pantallas 7 segmentos y lso primero 4 bits del puerto de control se emplearon para encender o apagar cada una de las pantallas 7 segmentos. De esta forma, para representar la hora en la pantalla se debia encender de forma alternada y con gran velocidad, cada uno de los elementos 7 segmentos de cada número. La aplicación de consola se programó utilizando el IDE Dev C++ y se ejecutó en sistema operativo Windows XP.</p>
<img width="568" alt="reloj con pantalla 7 segmentos b" src="https://github.com/user-attachments/assets/bc4d9a83-43fa-4342-8ee8-b1ecce2edf49" />

<p>Un subproceso se encarga de controlar la representación de los números en la pantalla alternando rapidamente el encendido y apagado de cada elemento 7 segmentos y colocando en el bus de datos la combinación correspondiente al dígito que se debe representar en cada elemento 7 segmento. Mientras, el proceso principal atiende la consola, los comandos del usuario y optiene regularmente la hora del sistema para enviarsela al subproceso cuando cambie la hora.</p>









