# Dashboard_Analisis
El objetivo de este EDA es observar los beneficios y ventas totales en un periodo específico de tiempo en este supermercado y como interactua las transacciones con otros valores: volúmen, productos, método de pago, etc. Este proyecto busca dibujar una imagen clara de la información recopilada hasta ahora y de esta manera identificar patrones, insights y/o tendencias.

---
Este proyecto de github contiene:
-
- README.md: Este archivo.
- URL_Kaggle: Hipervínculo al dataset original.
- URL_Sheets: Hipervínculo al archivo de google sheets.
- retail_store_sales.csv: Archivo con los datos originales en formato csv.
---
- Se descargó este dataset de la website kaggle.

- Se procedió a importar y formatear a tabla en sheets.

- Se limpió y trabajó con los datos faltantes:

1. **"Discount applied":** Rellenando con "N/A" en los valores nulos.

2. **"Quantity":** Al principio, parecía correcto eliminar todas las filas que no tuvieran "quantity" ya que al no saber cuanto se vendió era imposible inferir el monto exacto de la transacción. Sin embargo, tomando en consideración que el registro de transacción existe, decidí que lo más balanceado, sabiendo el objetivo, era poner al menos 1 item de venta si existía registro de dicha transacción.

3. **"Total spent" y "Price per unit":** Fueron calculables haciendo reglas de 3, una vez que la columna "quantity" estaba lista.

4. **"ITEM":** Quizas el más difícil, ya que aunque habían valores faltantes, ya era conocido que existen 8 categorías ("Category") y por cada valor de este, 25 sub valores dentro de "ITEM" asi que se hizo una relación en una hoja nueva con una fórmula entre "category" y "price per unit" para inferir el valor que corresponde a "ITEM". Luego, se rellenó la parte restante de "ITEM" en la tabla con otra formula. 

(Cabe destacar que aunque entendí la lógica de como inferir el "ITEM" que me faltaba usando el contexto, tuve que recurrir a la IA para que me ayudara a comprender y formular la solución para automatizarlo)

---
Una vez todas los datos estaban íntegros, pasé a hacer las tablas dinámicas preliminares para observar el comportamientos de los datos visualmente.

En este caso, se paso a sacar cuatro números importantes, que serían: 
- **Venta total** 
- **Beneficio total**
- **Item más vendido** 
- **Cliente más leal (por % venta)**

Una vez hechas las gráficas, quedamos con 6 en total + 4 big numbers. No se encontraron grandes outliers dentro de la data, llegando a la conclusion preeliminar de que la data es bastante homogenea a lo largo de todas sus vertientes. 

La conclusión más beneficial sería enfocarse en los productos con mayor rentabilidad y optimizar estas ventas para capitalizar más beneficio.

---
**La presentación del dashboard culminó con las siguientes gráficas:**

- big four: Cliente mas leal (cliente con mayor % de compra sobre las ventas totales)
- el item (no categoría) con mayor facturación sobre la venta total
- La facturación total de principio a fin.
- El total de ventas de principio a fin

A su vez, se hace uso de 6 gráficos auxiliares que incluyen:

1. Método de pago sobre total de ventas
2. Uso de descuento por locación
3. Uso de descuento sobre método de pago
4. Total de ventas por locación
5. % de ventas total por categoría
6. Ventas a traves del tiempo.

---

Se probaron pequeñas teorías, por ejemplo, si existía una variación entre los descuentos y métodos de pago o locación.
Tambien se observo la variación de venta sobre los 25 clientes, la cual nunca varia más de un 1,5% sobre la venta total.
A nivel de mejor categoría vs item individual, no coinciden directamente (el mejor producto pertenece la categoría furniture, pero la mejor categoría es butchery) Dado que son tantas subcategorías y no existen outliers notables, seria más seguro guiarse por las categorías para hacer análisis.

Finalmente, se pasaron estas gráficas a una hoja aparte para poder armar el dashboard con su respectivo estilo de diseño, colores y patrones.

Al culminar, se añadieron filtros que permiten darle un extra de dinamismo al dashboard, pudiendo mirar con detenimientos otros factores, trends o insights.

Cerramos el dashboard dentro de la hoja "tablas dinamicas" donde ocultamos todas las tablas y dejamos el producto final. También se ocultó la hoja base del dashboard para que quedase más prolijo.

---

# A futuro: Para seguir trabajando en el proyecto:

- Agrupar la data de manera mensual, ya que al ser diaria, sin agrupar es dificil recrear un grafico de linea temporal legible.

- Reordenar y limpiar la estructura de las tablas dinamicas, para hacer el trabajo de crear gráficos más expedito.
