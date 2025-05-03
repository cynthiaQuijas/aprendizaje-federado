# aprendizaje-federado

Esta actividad consistió en realizar un aprendizaje federado en donde se dividió la base de datos de MNIST en 6 partes y cada integrante del equipo se encargó de entrenar esa base de datos con el mismo modelo para después juntarlos en un modelo global.

## Pasos de cómo se realizó la actividad:
1. Divir la base de datos de MNIST en test y train set, de los sets de train se dividió en 6 partes utilizando StratifiedKFold.
2. Todos estos sets de datos se guardó en formato .npy para respetar la forma de los datos. A estos se les nombró de la siguiente manera: Nombre_X.npy, Nombre_Y.npy, x_test_fed.npy y y_test_fed.npy.
3. Mandar el X y Y train de cada quién y los sets de test a cada integrante del equipo por correo.
4. Generar el modelo que se encuentra en el archivo `TheModel.py` (todos vamos a utilizar esta misma arquitectura)
5. Cada miembro del equipo ejecutó el notebook que se encuentra en el folder `CODE` (subiendo su respectivo dataset de train y test y el modelo) y guarda el modelo en formato .keras, el modelo de cada integrante se encuentra en el folder `LOCAL_MODELS`.
6. Juntar todos los modelos con el notebook `modelo_fed.ipynb`
