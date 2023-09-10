

Contributor: Justin Jao
Mentors: Charles Haynes, Walle, Avery Wang

## Project Background & Goals

The Datahub repository contains various open source data that can be imported into the cBioPortal web application. As part of the concerted effort to leverage open-source collaboration across researchers, users are freely able to [upload their own own data](https://docs.cbioportal.org/data-loading/#data-loading) by following a specified format. There exists scripts to manually validate the integrity of the dataset, but verification of (how the dataset displays) currently requires a manual process of loading a dataset into a developer environment. To automate this process, 

A live staging instance environment that could
* automatically trigger to be deployed upon PR
* automatically load the study into the profile
* automatically spin down upon PR merge/close

## What I did

June
* explore cbioportal, familiarize with technology, docker compose, refamiliarize with Github Actions

July (2ish weeks): explore terraform, explore okteto

July to early September: initiate okteto with cbioportal docker compose, then datahub repo
produce documentation




## Current State & What code got merged in (or not)
To be merged - 

See PRs here:

Spin Up 

Link to the overall draft PR is here:

IN particular, I would like to highlight the workflow files (link here)
and the documentation produced (here)

Due to the nature of my project (testing GitHub actions workflow), I had to create multiple different test branches, and repeated commits to test out changes. As a result, for clarity, I have created a new branch from scratch with the finalized version.

The produced output is a fully functional version which has been internally approved. However, there remains certain things that must be clarified and decided upon before the code can be integrated into the repository.

* account for Okteto, who will own this workflow

Future Work:
* gene panel submission id
As of the submission time of this report, the most up-to-date commit is: 

## What's left to do

* there are some activities that are still needed
Further automation could be explored as well

## Reflection and Discussion

* infrastructure is more challenging
* more about deployments

* need to close my feedback loop faster
* both on a technical basis - e.g. breaking it down into simpler debugging steps, or PoC examples,
and on a personal level, e.g. reaching out earlier