# Preview Environment Documentation

To streamline the quality control process of reviewing external data sources, cBioPortal seeks to automate the deployment of a live staging instance with the new studies already imported. The Preview Environment workflow utilizes a combination of infrastructure-as-code tooling (`docker-compose`, `GitHub Actions`), and a fully-managed developer environment provisioned by Okteto (which runs via a `GitHub Action`).

The specification for building the containerized web applications is primarily accomplished through the configuration provided by the [`cbioportal-docker-compose`](https://github.com/cBioPortal/cbioportal-docker-compose) repository.

Okteto can appropriately parse the `docker-compose.yml` file, but to use these with Okteto to deploy a working staging instance of cBioPortal requires a few additional things to be set up in the infrastructure:

* configuration files for the cbioportal instance
* initial files and SQL commands to seed the initial SQL database
* have these files already present in an accessible image (for reasons outlined below).

These workflows come in the form of 2 files, `preview.yml`, which deploys the staging environment with the study imported, and `preview_closed.yml`, which tears down the deployed instance.

The following document outlines each of the steps of the workflow, and provides insight where necessary as to why they were designed in such a manner.

## Workflow Overview

In brief, the proposed workflow works by pulling pre-built images of cBioPortal (with the configuration files added) and the cBioPortal SQL database (with the database files for seeding already added as well). These images are used to launch a container with the new studies imported as well, and this container is re-built to the same namespace registry. The `Deploy Preview` action by Okteto then pulls this image and uses it to deploy the preview environment. Upon which, the metaimport script can be run to import the study into the running database instance.


### Initial Setup

![image](/Intial_Setup.drawio.svg)

The [`cbioportal-docker-compose`](https://github.com/cBioPortal/cbioportal-docker-compose) repository contains the files necessary to build a fully running instance of `cbioportal`. However, to get this to run, and to allow Okteto to access this in their `Deploy Preview` action, a 

This step is performed for 2 reasons, to initialize the namespace in the private Okteto registry, as well as to push an image with the configuration files and seeded DB files already in the image.

For a more detailed breakdown of the steps necessary here, see [Preview Setup](Preview_Setup.md).

### Pull from Image
The program

### Deploy to containers
Okteto's `Deploy Preview` action thus 

### Import Study

### Teardown of Preview Environment
