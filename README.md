# Proyecto-estructura-de-datos
## Integrantes
* Juan Jose Zapata Buenfil
* Sergio Orion Huerta Martinez
* Josué Enmanuel Poot Mateo
---
# Proyecto 3 Grafo por nodos y enlaces + coloración (método greedy)

### Objetivo
El objetivo de este proyecto es implementar un grafo con lista de adyacencia y aplicar una coloración de vértices con un método greedy.

### lo que utilizamos:
Para este proyecto utilizamos el código base creado en clase, de modo que teniamos una orientación para poder comenzar, a este mismo le realizamos los siguientes cambios e implementaciones para poder cumplir los requisitos solicitados. 
* función get_vertice: la cual retorna la lista de los vertices que hay en el grafo.
* función greedy_coloring: esta, dependiendo si el orden de coloreo es desendiente o natural va a implementar el coloreado, evitando que un mismo color se use en vetices adyacentes, de igual modo regresa un diccionario que son los colores asignados en numeros enteros.
* función validar_colores: esta verifica que los colores se hayan puesto de forma correcta y verifica que un color no se repita en los vertices adyacentes.
* función display_coloring_results: llama a las funciones anteriores(greedy_coloring, valirdar_colores), e imprime el resultado, asi como tambien devuelve el total de colores usados.




