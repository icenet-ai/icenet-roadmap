# IceNet-Project

Central repository for the Turing-British Antarctic Survey IceNet Project.
The project consists of a pipeline which aims to produce timely predictions of sea-ice coverage and exposes them through an API.

## IceNet ML Pipeline

A detailed explanation of the machine learning pipeline can be [found here](https://github.com/alan-turing-institute/IceNet/wiki/Model-Pipeline). Fundamentally, there is a reusable and continuously executable pipeline from data ingestion through to forecast production and upload. 

This high level diagram depicts the overall structure: 

<img src="https://github.com/alan-turing-institute/IceNet-Project/wiki/Pipeline%20Layout.png" alt="IceNet ML Pipeline" /> 

The daily forecasting pipeline centers around a refactored version [of the original research model for monthly forecasts](https://github.com/tom-andersson/icenet-paper), currently private, and the execution assets [found here](https://github.com/antarctica/IceNet-Pipeline) which leverage a BAS developed tool for running [model ensembles.](https://github.com/JimCircadian/model-ensembler)

## IceNet ETL

This project is for the code that runs the extract, transform and load (ETL) stage of the pipeline.
It sets up various Azure resources, in particular an Azure storage account and a PostgreSQL database.
Any NetCDF file that is added to the storage account is processed by an Azure function and loaded into the database.

For further details [look at the repository here](https://github.com/alan-turing-institute/IceNetETL).

## IceNet GeoAPI

This project is for the code that exposes predictions from the [IceNet ETL](https://github.com/alan-turing-institute/IceNetETL) database.
It sets up various Azure resources, in particular a webserver that provides the API.

For further details [look at the repository here](https://github.com/alan-turing-institute/IceNetGeoAPI).
