# RetailPro | Análisis de ventas de tecnología

Proyecto de SQL y Power BI para el equipo comercial de RetailPro. El caso de SQL usa la base **Ventas_Tech_DB**. Permite reproducir el resumen mensual, el ranking por facturación y el cruce de ventas con clientes, productos y categorías.

## Archivos y orden de ejecución

Abrí los scripts como texto en un editor conectado a **Microsoft SQL Server**, por ejemplo SQL Server Management Studio. En GitHub, los tres archivos SQL están guardados sin extensión.

1. [Ventas_Tech](./Ventas_Tech) crea las cuatro tablas, carga las ventas de muestra y termina con consultas de control. En una instancia de práctica, ejecutá primero `CREATE DATABASE Ventas_Tech_DB` como lote independiente. Luego seleccioná esa base y ejecutá desde `USE Ventas_Tech_DB`. Si la base ya existe, omití la creación. Revisá antes la sección `DROP TABLE` porque elimina y vuelve a crear las tablas. Para evitar problemas de sintaxis, quitá la coma que sigue a `fecha_venta date not null` antes del cierre de la tabla ventas.
2. [m4_ConsultaSQL](./m4_ConsultaSQL) devuelve el resumen mensual, los cinco productos de mayor facturación, los clientes recurrentes y la comparación con el promedio mensual.
3. [Entregable 5 · Consultas con JOINs](./Entregable%205_Consultas%20con%20JOINs%20) cruza las cuatro tablas, identifica clientes y productos sin ventas y compara dos períodos. En la primera consulta, `cat.descripcion` describe la categoría. Para mostrar el artículo, usá `p.nombre_producto`.
4. [Pipeline ETL](./Pipeline_ETL_Nunez_Nicolas.pbix) se abre en Power BI Desktop. Podés revisar allí las transformaciones de Power Query. Los tres scripts anteriores se pueden ejecutar por separado del archivo de Power BI.

## Cómo comprobar los resultados

Con los datos iniciales, marzo de 2024 contiene 10 registros de venta. La suma de `cantidad * precio_unitario` da $6.444,00 y el promedio por registro es $644,40. El producto 1 (Laptop Pro 15) factura $3.600,00 por tres unidades. Usá el precio registrado en la venta para reproducir la facturación histórica.

El resumen de M4 agrupa por número de mes. Si incorporás otro año, agrupá también por año. El ranking devuelve cinco de los seis productos. Para calcular participaciones sobre toda la facturación, usá el total de ventas como denominador.
