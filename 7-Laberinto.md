# Introducción a la Inteligencia Artificial: El papel de la heurística

La heurística es un término que se utiliza en psicología y ciencias de la computación para referirse a estrategias o reglas prácticas que son utilizadas para resolver problemas y tomar decisiones de manera más rápida y eficiente, aunque no necesariamente garantizan la solución óptima. Estas reglas son generalmente simples y se basan en la experiencia previa, el sentido común y el conocimiento adquirido a lo largo del tiempo.

El papel de la heurística en la resolución de problemas es facilitar el proceso cognitivo, permitiendo a las personas abordar situaciones complejas de manera más efectiva, incluso cuando la información es incompleta o hay restricciones de tiempo. En lugar de explorar exhaustivamente todas las posibles soluciones, las heurísticas proporcionan atajos mentales que ayudan a reducir la carga cognitiva y a tomar decisiones de manera más rápida.

Sin embargo, es importante destacar que, aunque las heurísticas son útiles en muchos casos, también pueden llevar a errores sistemáticos, conocidos como sesgos heurísticos. Estos sesgos pueden surgir debido a la simplificación excesiva de la información o a la aplicación de reglas heurísticas de manera inapropiada.

Algunos ejemplos de heurísticas comunes incluyen:

1. *Heurística de representatividad:* Tendencia a juzgar la probabilidad de un evento en función de cuánto se asemeje a un prototipo o estereotipo.

2. *Heurística de disponibilidad:* Tendencia a estimar la probabilidad de un evento basándose en cuán fácilmente se puede recordar o recuperar información relevante.

3. *Heurística de anclaje y ajuste:* Tendencia a basar las decisiones en un valor inicial (anclaje) y ajustar insuficientemente la estimación final.

4. *Heurística de la satisfacción:* Tendencia a detener la búsqueda de soluciones tan pronto como se encuentra una que parezca aceptable.

En resumen, las heurísticas son estrategias cognitivas que permiten a las personas tomar decisiones y resolver problemas de manera más eficiente, pero también pueden introducir sesgos y errores. Su aplicación efectiva depende del equilibrio entre la simplificación útil y la capacidad de adaptarse a situaciones específicas.

## Problema Laberinto

~~~python
laberinto = [
       [1 , 1 , 1 , 1 , 1 , 1 , 1 , 1 , 1 ],
       [0 , 0 , 0 , 0 , 0 , 0 , 1 , 0 , 1 ],
       [1 , 1 , 1 , 0 , 1 , 1 , 1 , 0 , 1 ],
       [1 , 0 , 0 , 0 , 1 , 0 , 1 , 0 , 1 ],
       [1 , 0 , 1 , 1 , 1 , 0 , 1 , 0 , 1 ],
       [1 , 0 , 0 , 0 , 0 , 0 , 0 , 0 , 1 ],
       [1 , 0 , 1 , 1 , 1 , 0 , 1 , 0 , 1 ],
       [0 , 0 , 1 , 0 , 0 , 0 , 1 , 0 , 1 ],
       [1 , 1 , 1 , 1 , 1 , 1 , 1 , 1 , 1 ],
      ]
~~~
