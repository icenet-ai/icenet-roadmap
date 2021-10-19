# IceNet-Project

Central repository for the Turing-British Antarctic Survey IceNet Project.
The project consists of a pipeline which aims to produce timely predictions of sea-ice coverage and exposes them through an API.

## IceNet ETL

This project is for the code that runs the extract, transform and load (ETL) stage of the pipeline.
It sets up various Azure resources, in particular an Azure storage account and a PostgreSQL database.
Any NetCDF file that is added to the storage account is processed by an Azure function and loaded into the database.

For further details [look at the repository here](https://github.com/alan-turing-institute/IceNetETL).
