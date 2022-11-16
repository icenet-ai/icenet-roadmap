# icenet-project

Central repository for the [British Antarctic Survey (BAS)](https://www.bas.ac.uk) / [Alan Turing Institute (ATI)](https://turing.ac.uk) IceNet Project.

## What is IceNet?

IceNet is a software ecosystem that offers sea-ice prediction capabilities. It is currently under heavy development but is based on [original research](https://github.com/tom-andersson/icenet-paper) that demonstrated that deep learning could be used for forecasting seasonal sea ice conditions in the northern hemisphere. Following a further project to operationalise the data delivery, machine learning and delve further into the research topic, this capability has now been employed for both hemispheres at daily timescales.  

Further information to follow.

## For Developers

### Repositories

#### [icenet-pipeline](https://github.com/icenet-ai/icenet-pipeline

A detailed explanation of the machine learning pipeline can be [found here](https://github.com/icenet-ai/icenet-project/wiki/Model-Pipeline). Fundamentally, there is a reusable and continuously executable pipeline from data ingestion through to forecast production and upload. 

This high level diagram depicts the overall structure: 

<img src="https://github.com/alan-turing-institute/IceNet-Project/wiki/Pipeline%20Layout.png" alt="IceNet ML Pipeline" /> 

The daily forecasting pipeline centers around a refactored version [of the original research model for monthly forecasts](https://github.com/tom-andersson/icenet-paper), currently private, and the execution assets [found here](https://github.com/antarctica/IceNet-Pipeline) which leverage a BAS developed tool for running [model ensembles.](https://github.com/JimCircadian/model-ensembler)

#### IceNet ETL

This project is for the code that runs the extract, transform and load (ETL) stage of the pipeline.
It sets up various Azure resources, in particular an Azure storage account and a PostgreSQL database.
Any NetCDF file that is added to the storage account is processed by an Azure function and loaded into the database.

For further details [look at the repository here](https://github.com/alan-turing-institute/IceNetETL).

#### IceNet GeoAPI

This project is for the code that exposes predictions from the [IceNet ETL](https://github.com/alan-turing-institute/IceNetETL) database.
It sets up various Azure resources, in particular a webserver that provides the API.

For further details [look at the repository here](https://github.com/alan-turing-institute/IceNetGeoAPI).
