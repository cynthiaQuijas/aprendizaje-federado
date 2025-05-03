# aprendizaje-federado

Esta actividad consistió en realizar un aprendizaje federado en donde se dividió la base de datos de MNIST en 6 partes y cada integrante del equipo se encargó de entrenar esa base de datos con el mismo modelo para después juntarlos en un modelo global.

## Pasos de cómo se realizó la actividad:
1. Dividir la base de datos de MNIST en test y train set, de los sets de train se dividió en 6 partes utilizando StratifiedKFold.
2. Todos estos sets de datos se guardó en formato .npy para respetar la forma de los datos. A estos se les nombró de la siguiente manera: `Nombre_X.npy`, `Nombre_Y.npy`, `x_test_fed.npy` y `y_test_fed.npy`.
3. Mandar el X y Y train de cada quién y los sets de test a cada integrante del equipo por correo.
4. Generar el modelo que se encuentra en el archivo `TheModel.py` (todos vamos a utilizar esta misma arquitectura)
5. Cada miembro del equipo ejecutó el notebook que se encuentra en el folder `CODE` (subiendo su respectivo dataset de train y test y el modelo) y guarda el modelo en formato .keras, el modelo de cada integrante se encuentra en el folder `LOCAL_MODELS`.
6. Juntar todos los modelos con el notebook `modelo_global_inicial.ipynb`, utilizando los mismos datasets de test. En este se tuvieron muy malos resultados al juntar los modelos con FedAvg, FedAvgM, FedMedian y Trimmed Mean, se dedució que hay un error cuando se juntan los modelos. Salían los mismos resultados y pudimos observar que los pesos eran casi cero. Con estos resultados no se pueden comparar los resultados y elegir qué método sería el mejor.
7. Con el objetivo de comparar diferentes métodos se hicieron los códigos de la carpeta de `comparacion_modelos`, el notebook `comparacion_modelos.ipynb` compara métodos del modelo que creó el profesor y el notebook `comparacion_modelos2.ipynb` compara métodos de nuestro modelo forzando los resultados para que no vuelva a dar el mismo error que el `modelo_global_inicial.ipynb` dando resultados para poder decidir qué métodos son los mejores para este modelo y estos datos.
8. Creación de nuevo método para dar buenos resultados: en el notebook `modelo_global_bueno.ipynb` se generó un modelo haciendo una media ponderada, dando un mayor peso a uno de los modelos. De esta manera pudimos acercarnos a los resultados de los modelos locales.
