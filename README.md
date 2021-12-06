# ARWS_Scalability_lab

## Parte 1

Punto 7: Documente los tiempos de respuesta para dicho endpoint usando los siguientes valores:

1000000 => 31.70 s
1010000 => 31.06 s
1020000 => 26.25 s
1030000 => 30.65 s 
1040000 => 29.53 s
1050000 => 29.86 s
1060000 => 30.92 s
1070000 => 29.52 s
1080000 => 31.69 s
1090000 => 35.81 s

Punto 8: Uso de CPU

![image](https://user-images.githubusercontent.com/60078276/144887220-b5be21b0-c32c-499e-9857-f6077872917b.png)

Punto 9: Usando Postman para simular una carga concurrente a nuestro sistema:

![image](https://user-images.githubusercontent.com/60078276/144908321-0a7a38bd-06ec-48b9-aee2-bb0b4fcd3af9.png)

1000000 => 21.55 s
1010000 => 21.16 s
1020000 => 22.25 s
1030000 => 23.21 s 
1040000 => 24.45 s
1050000 => 25.58 s
1060000 => 25.99 s
1070000 => 26.11 s
1080000 => 26.66 s
1090000 => 27.11 s

Punto 8 nuevamente: Uso de CPU

![image](https://user-images.githubusercontent.com/60078276/144909961-636baa43-80c6-4b91-979c-8111bd74f680.png)

Punto 9 Nuevamente: Usando Postman para simular una carga concurrente a nuestro sistema:

![image](https://user-images.githubusercontent.com/60078276/144911322-2a6c7091-c286-4547-972b-8ddf8c3ddc14.png)

Punto 12: Este modelo de escalabilidad no ofrece la capacidad de rendimiento suficiente pues como se evindeció en las pruebas anteriores, el rendidmiento obtenido con una maquina mucho más potente que la inicial, no dió un rendimiento proporcinalente superior.

#### Preguntas

1. ¿Cuántos y cuáles recursos crea Azure junto con la VM?
Se crea el recurso de la maquina virtual, una interfaz de res, unadirección ip publica, un grupo de seguridad en la red y una red virutal.

2. ¿Brevemente describa para qué sirve cada recurso? 
Maquina virtual es un equipo de computo virtualizado,
Interfaz de red: permite conectarse a los recursos de internet.
IP address publica: Es la dirección que permite identficar al dispostivo en la red.
Grupo de seguridad de la red: Es similar a un firewall para proteger los recursos.
Red virtual: Es una red virtualizada que conecta a los recursos.

3. ¿Al cerrar la conexión ssh con la VM, por qué se cae la aplicación que ejecutamos con el comando npm FibonacciApp.js? ¿Por qué debemos crear un Inbound port rule antes de acceder al servicio?
Se cierra porque este proceso se ejecuta en la instancia de la terminal por la que nos conectamos y al desconetarnos esta instancia lo desaparece. Se debe crear el puerto de entrada para que el proceso sea visible y accesible desde otros dispositivos.

4. Adjunte tabla de tiempos e interprete por qué la función tarda tando tiempo.
B1ls
1000000 => 31.70 s
1010000 => 31.06 s
1020000 => 26.25 s
1030000 => 30.65 s 
1040000 => 29.53 s
1050000 => 29.86 s
1060000 => 30.92 s
1070000 => 29.52 s
1080000 => 31.69 s
1090000 => 35.81 s
B2ms
1000000 => 21.55 s
1010000 => 21.16 s
1020000 => 22.25 s
1030000 => 23.21 s 
1040000 => 24.45 s
1050000 => 25.58 s
1060000 => 25.99 s
1070000 => 26.11 s
1080000 => 26.66 s
1090000 => 27.11 s

5. Adjunte imágen del consumo de CPU de la VM e interprete por qué la función consume esa cantidad de CPU.
B1ls
![image](https://user-images.githubusercontent.com/60078276/144887220-b5be21b0-c32c-499e-9857-f6077872917b.png)
B2ms
![image](https://user-images.githubusercontent.com/60078276/144911322-2a6c7091-c286-4547-972b-8ddf8c3ddc14.png)

6. Adjunte la imagen del resumen de la ejecución de Postman. Interprete:
Tiempos de ejecución de cada petición.
Si hubo fallos documentelos y explique.
7. ¿Cuál es la diferencia entre los tamaños B2ms y B1ls (no solo busque especificaciones de infraestructura)?
B2ms ofrece un rendimiento maximo del doble en comparación a B1ls, pero con en su rendimiento base, B2ms tiene 5x más rendimiento que B1ls. Además, el precio por hora aumeta casi 9x.

8. ¿Aumentar el tamaño de la VM es una buena solución en este escenario?, ¿Qué pasa con la FibonacciApp cuando cambiamos el tamaño de la VM?
Se redujo en promedio 10 segundos para cada uno de la mediciones realizadas.
9. ¿Qué pasa con la infraestructura cuando cambia el tamaño de la VM? ¿Qué efectos negativos implica?
El principal efecto negativo es el precio, pues pasa de $0.0144/hour a $0.0912/hour
10. ¿Hubo mejora en el consumo de CPU o en los tiempos de respuesta? Si/No ¿Por qué?
Sí, en promedio demoró 10 segundos menos cada ejecuciión pero el porcentaje de uso de CPU fue similar.
11. Aumente la cantidad de ejecuciones paralelas del comando de postman a 4. ¿El comportamiento del sistema es porcentualmente mejor?


