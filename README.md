# icenet-project

Central repository for the [British Antarctic Survey (BAS)](https://www.bas.ac.uk) / [Alan Turing Institute (ATI)](https://turing.ac.uk) IceNet Project.

This project __originally developed__ a proof-of-concept foundational infrastructure in 2021 to support ongoing developments. This repository __now__ helps us to manage the ongoing collaboration.

## What is IceNet?

[Please review the introductory text here...](https://www.github.com/icenet-ai)

## For Developers

Learning resources are still being developed, but please refer to the information below in the first instance.

### Learning IceNet

Resources TODO, please review individual repositories.

### Repositories

#### [icenet-notebooks](https://github.com/icenet-ai/icenet-notebooks)

Example notebooks showing how to use the library.

#### [icenet](https://github.com/icenet-ai/icenet)

The IceNet library, containing documentation sources. Probably easiest to start with the [icenet-notebooks](https://github.com/icenet-ai/icenet-notebooks) or [icenet-pipeline](https://github.com/icenet-ai/icenet-pipeline) repositories for guidance in the first instance.

#### [icenet-pipeline](https://github.com/icenet-ai/icenet-pipeline)

A detailed explanation of the machine learning pipeline can be [found here](https://github.com/icenet-ai/icenet-project/wiki/Model-Pipeline). Fundamentally, there is a reusable and continuously executable pipeline from data ingestion through to forecast production and upload. 

This high level diagram depicts the structuring of the pipeline:

<img src="https://github.com/alan-turing-institute/IceNet-Project/wiki/Pipeline%20Layout.png" alt="IceNet ML Pipeline" />  

The daily forecasting pipeline centers around a refactored version [of the original research model for monthly forecasts](https://github.com/tom-andersson/icenet-paper), located [in this library](https://www.github.com/icenet-ai/icenet). An example to using the library [can be found here](https://github.com/icenet-ai/icenet-pipeline) which leverage a BAS developed tool for running [model ensembles.](https://github.com/JimCircadian/model-ensembler) on HPCs.

#### [icenet-etl](https://github.com/icenet-ai/icenet-etl)

This project is for the code that runs the extract, transform and load (ETL) stage of the pipeline.
It sets up various Azure resources, in particular an Azure storage account and a PostgreSQL database.
Any NetCDF file that is added to the storage account is processed by an Azure function and loaded into the database.

For further details [look at the repository here](https://github.com/icenet-ai/icenet-etl).

#### [icenet-geoapi](https://github.com/icenet-ai/icenet-geoapi)

This project is for the code that exposes predictions from the [IceNet ETL](https://github.com/icenet-ai/icenet-etl) database. It sets up various Azure resources, in particular a webserver that provides the API.

For further details [look at the repository here](https://github.com/icenet-ai/icenet-geoapi).

## Working Group

An IceNet working group liaises between The Alan Turing Institute and British Antarctic Survey to track the many ongoing interests and developments in IceNet. This group is currently formed of [project team members from BAS](https://www.bas.ac.uk/project/icenet/#people) and [The Alan Turing Institute](https://www.turing.ac.uk/research/research-projects/understanding-arctic-sea-ice-loss), led by [James Byrne](https://www.bas.ac.uk/profile/jambyr/) and [Alden Connor](https://www.turing.ac.uk/people/business-team/alden-conner). Please contact them for further information.
