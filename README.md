# ProyectoFinal - Trash Dash
# Jeremy J. Sanchez Diaz, Eduardo A. Caceres Vazquez, Joxanniel J. Irizarry Estrella
# Prof. David Flores Granados


Descripción:
Trash Dash es un videojuego educativo donde el jugador debe recoger basura en una playa. El objetivo principal es crear conciencia sobre el cuidado del medio ambiente, mientras el jugador se enfrenta a desafíos crecientes como el aumento de basura al pasar el tiempo.


---


**Mecánicas Principales:**

Movimiento del Jugador  

•	El jugador se mueve usando las teclas WASD o las flechas del teclado.  

•	La dirección del personaje cambia según el movimiento.<br> 
&nbsp;

Recolección de Basura  

•	Al tocar objetos etiquetados como “Trash”, estos se destruyen y se incrementa el contador de basura recolectada.<br>
&nbsp;

Spawner de Basura  

•	La basura se genera automáticamente a través de un Spawner.  

•	La frecuencia de generación aumenta con el tiempo, incrementando la dificultad.<br>  
&nbsp;

Pantalla de Game Over  

•	Al perder, aparece una interfaz con un botón para reiniciar el juego.<br>




---





**Configuración en Unity:**  

•	Crear los prefabs de basura y etiquetarlos como Trash.  

•	Configurar el Spawner en la escena y asignarle los prefabs.  

•	Crear un Canvas para el contador de basura.  

•	Configurar la Game Over UI con un botón que reinicie la escena.  

•	Asignar los scripts a sus respectivos GameObjects.



---



**Técnicas del Juego:**  


1. Spawner Incremental

    • Descripción: El sistema de generación automática de basura utiliza un spawner incremental, que aumenta la frecuencia con la que los objetos se generan en la escena a medida que pasa el tiempo. Esto crea un aumento progresivo en la dificultad del juego, manteniendo al jugador constantemente desafiado.

    • Técnica Implementada: El spawner utiliza una corutina (IEnumerator) que permite controlar el intervalo de tiempo entre cada generación de basura. A medida que el tiempo transcurre, el intervalo de generación disminuye utilizando la función Lerp, que calcula un valor interpuesto entre dos números (el intervalo inicial y el intervalo mínimo).  

    • Impacto: Este sistema asegura que el juego sea dinámico, desafiando al jugador a medida que avanza.<br>  

&nbsp;

2. Sistema de Control de Juego (GameController)
   
    • Descripción: Gestiona la lógica del flujo del juego, incluyendo la condición de Game Over y el reinicio de la partida.  

    • Implementación: Se utiliza un script llamado GameController que detecta las condiciones de pérdida y muestra la pantalla de Game Over.<br>  

&nbsp;

3. Pantalla de Game Over
   
    • Descripción: Cuando la barra de contaminación llega al límite, el juego muestra una pantalla de Game Over, que incluye un mensaje y un botón para reiniciar el juego.  

    • Técnica Implementada: Se activa mediante el método TriggerGameOver del GameManager, que pausa el tiempo y muestra un Canvas. El botón utiliza el sistema de eventos de Unity para ejecutar el método RestartGame, que recarga la escena actual.  

    • Impacto: Esta funcionalidad proporciona una retroalimentación clara al jugador cuando pierde. Mejora la experiencia de usuario al permitir un reinicio inmediato.<br>  

&nbsp;

4. Optimización de Prefabs y Recursos
   
    • Descripción: Para evitar problemas de rendimiento, los objetos generados en la escena son prefabs optimizados con colisionadores simples y modelos de baja complejidad.  

    • Técnica Implementada: Los prefabs de basura utilizan BoxColliders, que son más eficientes que otros tipos de colisionadores. Los objetos generados se destruyen al ser recolectados, asegurando que la memoria no se sobrecargue.  

    • Impacto: Esto garantiza que el juego se mantenga fluido incluso en dispositivos con especificaciones limitadas.<br>  

&nbsp;

5. Sistema de Scripts
    
    - Descripción: Cada script tiene una funcionalidad específica para mantener la modularidad y facilitar la colaboración.  

    - Scripts Claves:  

        -	TrashCollection.cs: Maneja la recolección de basura.
  
        -	GameController.cs: Gestiona el estado del juego y controla la lógica de Game Over.
  
        -	AutoSpawner.cs: Controla la generación progresiva de basura.<br>
  

---

Script Implementados

- PlayerMovement: Controla el movimiento del jugador. Utiliza las teclas WASD o las flechas del teclado para mover al personaje y ajustar la rotación en la dirección del movimiento.
![image](https://github.com/user-attachments/assets/9c0e2a48-1947-4cb6-9115-25df3595033d)<br>


- Game Controller: Gestiona el flujo del juego, incluyendo el estado de Game Over y la lógica de reinicio.
![image](https://github.com/user-attachments/assets/d75de50d-cbba-4f02-b485-fbb3d1e02de5)<br>


- AutoSpawner: Se encarga de generar basura automáticamente en posiciones aleatorias. Utiliza una corutina (IEnumerator) para instanciar objetos con un intervalo definido
![image](https://github.com/user-attachments/assets/dcce5ab9-132f-43d4-9a85-d930e2fd0936)<br>


- TrashCollection: Este script gestiona la recolección de basura. Detecta colisiones con objetos etiquetados como "Trash", incrementa un contador visible en la UI y destruye el objeto recolectado.
![image](https://github.com/user-attachments/assets/5c4b852c-6ed3-4541-aa86-f13c8e7b3cd0)<br>


- GameOverScreen: Maneja la interfaz de Game Over. Activa la pantalla de Game Over y proporciona una función para reiniciar la escena actual usando el SceneManager.
![image](https://github.com/user-attachments/assets/d82eb928-0218-466f-b57b-40d7da68d2fb)<br>

---

Gameplay del Juego
https://github.com/user-attachments/assets/01f59dfc-3ef9-4bd5-a650-93c1d85d3dfc











