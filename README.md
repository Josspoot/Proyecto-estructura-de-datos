# Proyecto-estructura-de-datos
## Integrantes
* Juan Jose Zapata Buenfil
* Sergio Orion Huerta Martinez
* Josué Enmanuel Poot Mateo
---
# Proyecto 3 Grafo por nodos y enlaces + coloración (método greedy)

### Objetivo
El objetivo de este proyecto es implementar un grafo con lista de adyacencia y aplicar una coloración de vértices con un método greedy.

### Lo que utilizamos:
Para este proyecto utilizamos el código base creado en clase, de modo que teniamos una orientación para poder comenzar, a este mismo le realizamos los siguientes cambios e implementaciones para poder cumplir los requisitos solicitados. 
* función get_vertice: la cual retorna la lista de los vertices que hay en el grafo.
* función greedy_coloring: esta, dependiendo si el orden de coloreo es desendiente o natural va a implementar el coloreado, evitando que un mismo color se use en vetices adyacentes, de igual modo regresa un diccionario que son los colores asignados en numeros enteros.
* función validar_colores: esta verifica que los colores se hayan puesto de forma correcta y verifica que un color no se repita en los vertices adyacentes.
* función display_coloring_results: llama a las funciones anteriores(greedy_coloring, valirdar_colores), e imprime el resultado, asi como tambien devuelve el total de colores usados.
---
## Visualización
### Función get_vertice:
``` 
def get_vertices(self):
        return list(self.adj.keys())
```

### Función greedy_coloring:
```
  def greedy_coloring(self, order=None):
        vertices = self.get_vertices()

        if order == "descendente":
          vertices.sort(reverse=True)
        else:
          vertices.sort()

        colores_asigned = {}

        for v in vertices:

            colors_vecinos = set()
            for vecino in self.neighbors(v):
                if vecino in colores_asigned:
                    colors_vecinos.add(colores_asigned[vecino])


            color = 0
            while color in colors_vecinos:
                color += 1
            colores_asigned[v] = color

        return colores_asigned
```
### Función validate_coloring:
```
    def validate_coloring(self, coloring):
      for v in self.get_vertices():
        for vecino in self.neighbors(v):
          if v in coloring and vecino in coloring:
            if coloring[v] == coloring[vecino]:
              return False
      return True
```
### Función display_coloring_results:
```
    def display_coloring_results(self, order=None):
        coloring = self.greedy_coloring(order=order)
        print("Asignación de colores:")
        for vertex, color in sorted(coloring.items()):
            print("Vértice", vertex, " Color ",  color)

        total_colors = len(set(coloring.values()))
        print("Total de colores usados: " ,total_colors)

        print("Es valido: " ,self.validate_coloring(coloring))
```









