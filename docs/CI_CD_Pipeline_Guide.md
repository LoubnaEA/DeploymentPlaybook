## CI/CD Pipeline Guide

A standardized CI/CD process ensures consistent, high-quality and traceable deployments across environments.  
It covers automated build, test and deployment using platforms like Jenkins, Azure DevOps or GitHub Actions.  

QA teams validate builds and verify automated checks, providing reliable feedback before release.


### Stages Overview

This classical “Stages Overview” describes the **technical flow** of a CI/CD pipeline.  
It can be mapped to a more **operational process view** : **Preparation**, **Pipeline Execution**, **Verification & Quality Gates**, **Rollback/Recovery**.


| **Stages Overview (Technical Flow)** | **Operational Process View** | **Comment** |
|------------------------------------|-----------------------------|-------------|
| **Source Control** | Preparation | Includes code retrieval, branching strategy, and environment readiness. |
| **Build** | Pipeline Execution | Compilation, packaging, dependency resolution; part of automated pipeline run. |
| **Test** | Pipeline Execution / Verification & Quality Gates | Automated tests, functional and integration verification; quality gates validation. |
| **Deploy** | Pipeline Execution / Verification & Quality Gates | Deployment to test or production environments; promotion checks included. |
| **Monitor** | Verification & Quality Gates / Rollback | Post-deployment monitoring, rollback readiness, and stability verification. |


### Preparation

**Steps**
- [ ] Ensure repository structure follows the agreed branching strategy (e.g., `main`, `develop`, `release/*`)  
- [ ] Validate that all automated tests pass locally before committing  
- [ ] Confirm environment variables and secrets are properly configured  
- [ ] Review pipeline configuration files (e.g., YAML, Jenkinsfile, Azure DevOps pipeline)  

**QA Role**
- Review merge requests and associated test results  
- Verify that test coverage meets project standards  
- Ensure quality gates are active (SonarQube, linting, code scan)  
- Validate environment readiness for automated testing  


### Pipeline Execution

**Steps**
1. Commit changes to the repository (trigger CI)  
2. Run automated build and test steps  
3. Validate build artifacts  
4. Deploy automatically or manually to the next environment  

**QA Role**
- Monitor CI results and investigate failed test cases  
- Validate that environment-specific configurations are applied correctly  
- Execute exploratory or regression testing post-deployment  
- Log any issues or inconsistencies in defect tracking tools (e.g., Jira, Azure Boards)  


### Verification & Quality Gates
Automated and manual checks ensure that every build meets quality and stability requirements before promotion.

**Verification Steps**
- Review pipeline test summary (unit, integration, UI tests)  
- Validate functional and API test outcomes  
- Check performance and security scans (if included)  
- Confirm build artifacts match expected version and configuration  

**QA Role**
- Approve promotion to higher environments (UAT or production)  
- Analyze pipeline metrics and historical stability trends  
- Provide feedback on test coverage or flaky tests  
- Support root cause analysis for failed builds  


### Rollback / Recovery
If deployment or pipeline stages fail, rollback procedures should restore stability quickly and safely.

**Steps**
- Stop the failed pipeline or job  
- Revert to the last successful build artifact  
- Restore environment configuration if modified  
- Document incident and corrective actions  

**QA Role**
- Validate that rollback restores previous working functionality  
- Retest critical user journeys and integrations  
- Update test documentation and CI/CD validation checklist  


### Notes & Tips

Enforce version control policies and peer reviews.  
Keep pipeline configurations under source control.  
Use tagging to trace releases and builds.  
Monitor pipeline performance and test reliability.  
Integrate automated reports for transparency (build, test, coverage).  
Continuously refine the QA automation scope within the pipeline.

