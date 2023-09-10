
# Short Description of Goals of the Project

The Datahub repository contains various open source data that can be imported into the cBioPortal web application. As part of the concerted effort to leverage open-source collaboration across researchers, users are freely able to [upload their own own data](https://docs.cbioportal.org/data-loading/#data-loading) by following a specified format. There exists scripts to manually validate the integrity of the dataset, but verification of (how the dataset displays) currently requires a manual process of loading a dataset into a developer environment. To automate this process, 

A live staging instance environment that could
* automatically trigger to be deployed upon PR
* automatically load the study into the profile
* automatically spin down upon PR merge/close

# What I did

June
* explore cbioportal, familiarize with technology, docker compose, refamiliarize with Github Actions

July (2ish weeks): explore terraform, explore okteto

July to early September: initiate okteto with cbioportal docker compose, then datahub repo
produce documentation




# Current State

Spin Up 

# What's left to do

* there are some activities that are still needed
Further automation could be explored as well

# What code got merged in (or not)
To be merged - 

See PRs here:

# Any challenges or important things learned during the project

* infrastructure is more challenging
* more about deployments

* need to close my feedback loop faster
* both on a technical basis - e.g. breaking it down into simpler debugging steps, or PoC examples,
and on a personal level, e.g. reaching out earlier