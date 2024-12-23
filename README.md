# DAA-problem-set-1

Hivan Cañizares Díaz C411 



## Conjunto Dominante



En un grafo se llama conjunto dominante al conjunto de vértices tal que todo vértice del grafo pertenece a él o es adyacente a uno de sus elementos.



Dado un entero k y un grafo G=(V,E) determinar si existe un conjunto dominante de tamaño k o menor. 



### Reducción 



Sea un grafo G=(V,E), si existe un conjunto dominante de tamaño k + (Cantidad de vértices con grado 0), entonces existe un Vertex Cover de tamaño k. Demostración:



Sea D un conjunto dominante de G:



Se cumple que toda arista del grafo incide en uno de los vértices del conjunto ya que de no incidir entonces esto significa que existe un vértice que no pertenece al conjunto dominante o que no es adyacente a ninguno de sus elementos y esto entra en contradiccion con la definicion de conjunto dominante.Por tanto, toda arista del grafo incide en algún vértice del conjunto. 



Sea (a) la cardinalidad de D y sea (o) la cantidad de vértices de grado 0 de G. Todo vértice de grado 0 pertenece al conjunto dominante ya que al no tener ningún vértice adyacente, tiene que pertenecer al conjunto dominante.



Sea k=a-o. Entonces se puede decir que existe un conjunto Vertex Cover de cardinalidad k con los vértices de grado mayor que 0 del conjunto dominante por lo demostrado anteriormente.



Ya que la transformación del problema Vertex Cover en el problema de Conjuntos Dominantes se realiza en O(1) y viceversa se realiza en O(|V|) se puede afirmar que el problema de hallar un conjunto dominante es NP-Hard.



## Clique

 

Determinar si en un grafo G=(V,E) existe un clique de tamaño k.



### Reducción



Sea un grafo G=(V,E) se quiere determinar si existe un conjunto independiente de tamaño k. 



Sea G'=(V,E') el grafo inverso de G, si existe un clique en G' entonces existe un conjunto independiente en G, ya que todas las aristas que no están en G' están en G ya que son grafos inversos, por lo que un conjunto independiente en un grafo es un clique en el grafo inverso ya que todas las aristas que los conectan entre ellos existen. 



Ya que hallar el inverso de un grafo se realiza en tiempo polinomial. Esto demuestra que Clique es un problema NP-Hard al reducirlo a el problema de conjuntos independientes.



## Exact Set Cover



Dado un conjunto X y una colección S de subconjuntos de X, el problema consiste en determinar si existe un subcolector S′⊆S tal que cada elemento de X aparezca exactamente una vez en los subconjuntos de S′.



### Reducción 



Sea una instancia de 3-SAT con n variables y m clausulas. 



Sea el conjunto X con los elementos:



    - a_i que corresponden a cada una de las n variables de 3-SAT

    - c_j que corresponden a cada una de las m variables de 3-SAT

    - p_i,j que corresponden a cada ocurrencia de la variable a_i en la clausula c_j en 3-SAT



Sea la colección S de subconjuntos de X, formada por los conjuntos:



    - { c_j, p_i,j } por cada p_i,j

    - { a_i, p_i,j(para toda ocurrencia no negada de a_i) } para toda a_i

    - { a_i, p_i,j(para toda ocurrencia negada de a_i) } para toda a_i

    - { p_i,j } para toda p_i,j



Mediante esta construccion se garantiza que una variable solo pueda ser positiva o negativa, ya que al escogerse con las ocurrencias negativas o positivas se logra que para escoger una clausula se tengan que escoger una de las instancias en que la ocurrencia que esta con la clausula en el conjunto no sea negativa o positiva respectivamente, y si existe un cubrimiento completo entonces quiere decir que se cumplieron escogieron las clausulas sin ninguna comtradiccion con las variables, correspondiendo asi la solucion de Set Cover con la de 3-SAT, reduciendo efectivamente el problema y demostrando que es NP-Hard.

