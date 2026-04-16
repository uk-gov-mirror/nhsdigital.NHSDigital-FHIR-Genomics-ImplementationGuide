# NHSDigital-FHIR-Genomics-ImplementationGuide FHIR Assets Repository

This repository is maintained by [Interoperability Team](https://nhsd-confluence.digital.nhs.uk/pages/viewpage.action?spaceKey=IOPS&title=Interoperability+Standards). Any queries contact us via <em><u>interoperabilityteam@nhs.net</u></em>.

## Information
This repository contains FHIR Assets and examples for the NHS England Genomic Medicine Service
- The FHIR assets and examples are rendered in Simplifer project: [Genomic Medicine Service Implementation Guide](https://simplifier.net/guide/fhir-genomics-implementation-guide) 

[![FHIR Project on Simplifier.net](https://img.shields.io/badge/FHIR_project_on_Simplifier.net-NHSDigitalFHIRGenomicsImplementationGuide-green)](https://simplifier.net/nhs-digital-fhir-genomics-implementation-guide)

### Synchronization with Simplifier.net FHIR projects
FHIR asset repositories can be connected to a [Simplifier.net](http://simplifier.net) project for easy visualization, documentation and publishing. For the current project, the `main` branch automatically synchronizes with [this Simplifier.net FHIR project](https://simplifier.net/nhs-digital-fhir-genomics-implementation-guide) on every commit. Learn how to set up [Simplifier.net GitHub synchronization](https://docs.fire.ly/projects/Simplifier/simplifierGithub.html).

## Main Branch Status
FHIR Validation with Terminology Checks: 
[![NHSDigital IOPS Validation](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/actions/workflows/terminology.yml/badge.svg)](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/actions/workflows/terminology.yml)

Firely Quality Control Checks:
[![Firely Validation)](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/actions/workflows/firely-validation.yml/badge.svg)](https://github.com/NHSDigital/NHSDigital-FHIR-Genomics-ImplementationGuide/actions/workflows/firely-validation.yml)

## Contributing
Any ammendments to this repo can be done via Pull Requests. To create a Pull Request, first [fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo) this repo, make the changes as necessary and create a [Pull Request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork) with the base being this repository.

All PRs will be validated, and approved by the Interoperability team before merging.
- Changes to ValueSets and CodeSystems and examples will be approved by a member of the Interoperability team.
- Changes to any other asset will be taken to the Interoperability Standards team Design Authority meeting to be discussed before approving.

### Signed Commits
The repo has signed commits enabled. This means that only commits that are verified can be merged into the main branch. More information about signed commits can be found [here](https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification).

### Branching Strategy (Gitflow)
We follow the **Gitflow** workflow. Please ensure your work is branched correctly:

- **`main`**: The main integration branch for features. All PRs for new features should target this branch. No direct commits.
- **`feature/`**: Used for new features. Branch off from `main` and merge back into `main`.
- **`hotfix/`**: Used for urgent production fixes. Branch off from `main` and merge into `main`

- **`parent subtree sync/`**: Action notify_programmes_repo.yml dispatches new changes to parent repo on push or pull request events but only for the main branch (To be implemented for the Genomics Programme).

### Branch Naming Convention

- `feature/IOPS-[JIRA-ID]-short-description`
- `hotfix/IOPS-[JIRA-ID]-short-description`
  
## Creating a New Package
Guidance for creating a new package is available on the [central repo](https://github.com/NHSDigital/NHSEngland-FHIR-Programme-ImplementationGuide). The Genomics programme currently manages its own releases, but these will be integrated into the NHS England Programme release process in the future.

## FHIR Validation

### CapabilityStatement
The CapabilityStatement is used by the validation tool to check which profile to validate against. If no Profile is stated then the base FHIR resource will be used.

### FHIR Validation with the IOPS Validator
This repo uses the customised HAPI FHIR Validation to ensure all assets and examples are valid FHIR, including any codes held within the ontoology server.    

More information on FHIR validation can be found on the Interoperability Standards team [Confluence page](https://nhsd-confluence.digital.nhs.uk/display/IOPS/FHIR+Conformance+and+Testing)  
More information on the FHIR validation service can be found within the Interoperability Standards team [IOPS-Test-Scripts](https://github.com/NHSDigital/IOPS-FHIR-Test-Scripts) repository.  

To set up the validation service within a fork add the following secrets:
- ONTO_CLIENT_ID
- ONTO_CLIENT_SECRET

### FHIR Validation with the Firely Terminal GitHub Action
This repository also uses the Firely GitHub Action to validate your resources against the FHIR specification and custom validation rules with [Firely Terminal](https://fire.ly/products/firely-terminal/). Any push or pull request to the `main` branch will automatically run the [Firely Validation pipeline](https://github.com/FirelyTeam/firely-terminal-pipeline), containing [bulk validation and custom business rule validation](https://fire.ly/2021/03/04/quality-control-how-to-validate-full-fhir-specifications-in-one-click/) with Firely Terminal.
