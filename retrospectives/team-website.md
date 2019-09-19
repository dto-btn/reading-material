# Project: build team website
The goal was to build [our team's website](https://dtf-ein.github.io/) where we could publicly share information about our work.

- [Time](#time)
- [Development experience](#development-experience)
- [How to improve](#how-to-improve)
- [Appendix](#appendix)

# Time
- We estimated it would take **3 days** to launch the first version of the site.
- Actual time was **5 days**. 

# Development experience
The difference between the estimate and actual time was caused by working on a notebook without admin rights. This stopped us from:

1. using software installers; and
1. leveraging automation and virtualization for our development environment.

The following tasks were impacted:

## Install Ruby
This is the programming language used to build the site locally and run automated tests. 
- **Work notebook:** 
    - 4 hours to [manually install](https://github.com/dtf-ein/dtf-ein.github.io/issues/1#issuecomment-530790560).  
- **Personal computer:**
    - 2 minute installer.

## Install NodeJS
Node was used for the automated accessibility and regression tests.
- **Notebook:** 
    - 1 hour to manually install.
- **Personal computer:**
    - 2 minute installer.

## Install Cypress
Cypress is an automated feature and accessibility test framework.  It was used for local and CI/CD pipeline testing.
- **Notebook:** 
    - 1 hour to troubleshoot [blocked Chrome browser extension](https://github.com/cypress-io/cypress/issues/1239).
- **Personal computer:**
    - 2 minute installer.

## Install Vagrant
Builds VMs using a declarative configuration file (configuration-as-code).  Allowed for consistent creation of a development VM.
- **Notebook:** 
    - Not possible.  Admin rights are required and there is a pending IT security review with no timeframe.
- **Personal computer:**
    - 1 hours to create a Vagrantfile that builds and manages a local Linux development VM including all tools used.
    - 5 minutes to create the VM on any computer with admin rights.

## Install Docker
Used to build and test the Docker images needed by the [CI/CD pipeline](https://circleci.com/gh/dtf-ein/dtf-ein.github.io).
- **Notebook:** 
    - Not possible.  Admin rights are required and there is a pending IT security review with no timeframe.
- **Personal computer:**
    - 0 minutes (part of the Vagrant development VM).

## Develop CI/CD pipeline
The pipeline automatically builds and tests every change made to the website.  It plays a large role in ensuring quality.
- **Notebook:** 
    - 8 hours as no ability to run the [CircleCI CLI](https://circleci.com/docs/2.0/local-cli/).  All testing had to be done on live CircleCI servers ( [`ci-fixes`](https://circleci.com/gh/dtf-ein/workflows/dtf-ein.github.io/tree/ci-fixes) branch).
- **Personal computer:**
    - 1 hour.  Used development VM to run CircleCI CLI (greatly increased development speed).

# How to improve
## Open notebooks
For teams that do not need the GC network for their work, an open notebook with a corporate VM would greatly improve their performance and ability to leverage modern digital tools and techniques:

* Open notebook for development and experimentation.
* Corporate VM for access to GC network and corporate tools.

:warning: This would require open internet access in GC workspaces.

## Cloud VMs
Another option would be creating development VMs in the cloud that were unrestricted.  

* Corporate notebook for GC network and corporate tools.
* Remote desktop for development and experimentation in the cloud.

:warning: This could impact UX, depending on internet connection speed and performance of the cloud VMs.

# Appendix
The following tools were used to build, test and host the website:
- [CircleCI](https://circleci.com/) for CI/CD pipeline.
- [CircleCI CLI](https://circleci.com/docs/2.0/local-cli/) for locally testing the CI/CD pipeline during development.
- [Cypress](https://www.cypress.io/) for feature and accessibility testing.
- [Docker](https://www.docker.com/) to build, test and maintain images used by the CI/CD pipeline.
- [GitHub](https://github.com/dtf-ein/dtf-ein.github.io) as version control.
- [GitHub Pages](https://pages.github.com/) to host site.
- [HTMLProofer](https://github.com/gjtorikian/html-proofer) for HTML validation.
- [Jekyll](https://jekyllrb.com/) to generate the site from [Markdown](https://en.wikipedia.org/wiki/Markdown) files.
- [Vagrant](https://www.vagrantup.com/) to build and manage VM used to develop locally.
