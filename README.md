# Gold_extraction
Gold Recovery

En la industria minera, la eficiencia es lo que separa la rentabilidad del fracaso. Este proyecto simula el proceso de extracción de oro a partir de mineral bruto. El objetivo es predecir la recuperación de oro en dos etapas críticas: la flotación y la purificación.

Desde un enfoque de Analisis Tactico, este proceso es como una transicion defensa-ataque:

Rougher (Flotacion): Es nuestra salida de balon. El objetivo es recuperar la mayor cantidad de "jugadas" (mineral valioso) del bloque bajo (alimentacion bruta).

Cleaner (Purificacion): Es la zona de finalizacion. Aqui limpiamos el juego para asegurar que el "gol" (el producto final) tenga la mayor calidad posible, eliminando los errores o residuos (colas).


Shutterstock
Herramientas y Stack Tecnico
Lenguaje: Python (Pandas, NumPy).

Machine Learning: Scikit-learn (Regresion Lineal, Random Forest).

Procesamiento: Analisis de series temporales y tratamiento de valores nulos por proximidad temporal.

El Proceso Paso a Paso
El sistema de datos se organiza de forma jerarquica: [etapa].[tipo_parametro].[nombre_del_parametro].

Flotacion (Rougher): Se introduce la mezcla en plantas de flotacion para obtener un concentrado inicial.

Purificacion (Cleaner): El concentrado se somete a dos etapas de limpieza para llegar al producto final.

Parametros Clave:
Air amount: Volumen de aire.

Fluid levels: Niveles de fluido.

Feed size: Tamaño de las particulas.

Feed rate: Velocidad de alimentacion.

Calculo de la Recuperacion (Recovery)
Para validar los datos, simulamos el proceso de recuperacion con la siguiente logica:

Recuperacion = ((C * (F - T)) / (F * (C - T))) * 100

Donde:

C: Proporcion de oro en el concentrado despues de la etapa.

F: Proporcion de oro en la alimentacion antes de la etapa.

T: Proporcion de oro en los residuos (colas) despues de la etapa.

Metrica de Evaluacion: sMAPE
Para medir el exito, implementamos el sMAPE (Error Medio Absoluto Porcentual Simetrico). Esta metrica es ideal porque escala el error segun la magnitud de los valores, evitando sesgos.

La metrica final se calcula como: sMAPE Final = 25% * sMAPE(rougher) + 75% * sMAPE(final)

Conclusiones y Resultados
Analisis de Concentracion: Se comprobo que la concentracion de oro (Au) sube constantemente en cada etapa, cumpliendo con el objetivo tactico del proceso.

Modelo MVP: El modelo de Random Forest Regressor demostró ser el mas robusto, capturando las no-linealidades del proceso quimico.

Impacto: Este modelo permite predecir la perdida de oro en los residuos, permitiendo ajustes operativos inmediatos para maximizar la produccion.
