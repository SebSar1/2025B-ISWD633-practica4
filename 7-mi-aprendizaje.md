# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Si solucionó un problema presentado al realizar la práctica también se debe documentar.


## Mi Aprendizaje

Conceptos que aprendí:

  * **Limitar Recursos (Memoria y CPU):** 
    Sirve para ponerle un "techo" a un contenedor, diciéndole cuánta memoria RAM (`-m` o `--memory` o ` memory-swang`) y cuánto poder de procesador (`--cpus`) puede usar como máximo.

  * **Políticas de Reinicio (`--restart`):** 
    Es una regla que le pones al contenedor (en `docker run`) para decirle qué hacer si se apaga solo. 
      * `--restart=no`: (El default) Si se cae, se queda caído.
      * `--restart=always`: Siempre intenta reiniciar, pase lo que pase.
      * `--restart=on-failure`: Solo intenta reiniciar si se apagó por un error (no si lo paraste tú).
      * `--restart=unless-stopped`: La más usada. Siempre intenta reiniciar, a menos que tú lo hayas detenido a propósito (con `docker stop`).

  * **Comprobación de Salud (`HEALTHCHECK`):** 
    Esta es una instrucción que se pone **dentro del Dockerfile**. Sirve para decirle a Docker cómo "preguntarle" a la aplicacióndentro del contenedor si está realmente saludable.

    Un ejemplo en el `Dockerfile` sería:

    ```dockerfile
    HEALTHCHECK --interval=30s --timeout=3s \
      CMD curl -f http://localhost/ || exit 1
    ```

Tuve un problema con la imagen de centos.
