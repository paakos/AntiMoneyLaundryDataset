# Aviso de atribucion y modificaciones de datos

Este archivo se aplica a los datos y snapshots contenidos en este directorio y sus
subdirectorios.

## Proveedor y fuente original

- **Dataset:** IBM Transactions for Anti Money Laundering (AML)
- **Publicador en Kaggle:** Erik Altman
- **Organizacion asociada al generador:** IBM
- **Pagina de origen:** https://www.kaggle.com/datasets/ealtman2019/ibm-transactions-for-anti-money-laundering-aml
- **Licencia:** Community Data License Agreement - Sharing - Version 1.0
- **Texto de licencia:** https://cdla.dev/sharing-1-0/

Los datos originales son transacciones financieras sinteticas generadas para
investigacion y evaluacion de modelos contra el blanqueo de capitales. No son
transacciones bancarias reales.

## Aviso de datos modificados

Los archivos de este repositorio son **datos mejorados o modificados** respecto del
dataset recibido. No son una copia inalterada de los archivos Kaggle originales.

Las principales modificaciones son:

1. seleccion del segmento `HI-Medium` del dataset original;
2. parseo y normalizacion de transacciones, cuentas y patrones AML;
3. construccion de un modelo Gold con dimensiones y tablas de hechos Delta;
4. conversion de fechas de las tablas de hechos al ano 2026, conservando mes, dia y
   hora cuando la fecha resultante es valida;
5. exportacion de las tablas a Parquet con compresion Zstandard para su distribucion;
6. enriquecimiento de `dim_bank.country` usando primero Wikidata y el catalogo de
   paises del Banco Mundial;
7. asignacion sintetica y determinista de bancos residuales entre `United States`,
   `Nigeria`, `Bangladesh` y `Panama`. Esta asignacion no describe bancos reales ni
   procede del dataset original.

El historial detallado de cambios y validaciones esta en [`../CHANGELOG.md`](../CHANGELOG.md).

## Cita academica solicitada por los autores

El dataset original solicita citar el trabajo que describe su generacion:

> Erik Altman, Jovan Blanuša, Luc von Niederhäusern, Béni Egressy, Andreea Anghel,
> and Kubilay Atasu. "Realistic Synthetic Financial Transactions for Anti-Money
> Laundering Models." arXiv:2306.16424, 2023.
> https://doi.org/10.48550/arXiv.2306.16424

## Independencia

Este repositorio es una transformacion y automatizacion independiente. IBM, Erik
Altman, los coautores del articulo y Kaggle no patrocinan, certifican ni respaldan este
repositorio. Los nombres y marcas de terceros pertenecen a sus respectivos titulares.