## Salesforce Deployment Guide

Standardized deployment and validation steps for **Salesforce-based environments** (Sales, Service or Experience Cloud).  
This guide ensures consistent delivery across sandboxes, UAT and production.  
Applies to CRM environments involving configuration, automation and metadata management.


### Preparation
Before deployment, ensure all configurations and metadata are validated and ready for release.

**Steps**
- [ ] Validate all metadata changes in sandbox  
- [ ] Backup current production configuration (profiles, flows, layouts)  
- [ ] Disable scheduled jobs and triggers (if applicable)  
- [ ] Notify impacted business units  

**QA Role**  
- Validate that all stories or tickets have passed QA testing in sandbox  
- Ensure regression tests are up-to-date and executed successfully  
- Review test evidence and confirm readiness for deployment  
- Support release coordination (communicate known test risks or dependencies)
  

### Deployment
Deployment should follow a controlled and traceable process to avoid inconsistencies.

**Steps**
1. Export metadata package from sandbox  
2. Deploy via Change Set, SFDX CLI or CI/CD tool  
3. Validate deployment in staging  
4. Execute post-deployment smoke tests  

**QA Role**  
- Monitor the deployment process and review logs for errors  
- Run smoke tests immediately after deployment to confirm basic system stability  
- Document any anomalies or unexpected UI behavior  
- Collaborate with dev and ops teams to confirm successful deployment


### Verification
Once deployed, a complete functional and technical validation must be performed.

**Verification Steps**  
- Check UI accessibility and navigation  
- Verify key flows (Case, Opportunity, Account)  
- Review Apex test results (≥ 75% coverage)  
- Validate integration endpoints (if any)  

**QA Role**  
- Execute regression tests on UAT or staging environments   
- Validate that critical business processes remain functional    
- Check data integrity and user permissions  
- Record test outcomes in QA reports (manual or automated)  


### Rollback / Mitigation   
Rollback procedures ensure stability in case of a failed deployment.  

**Steps**  
- Re-deploy previous stable metadata version  
- Re-enable disabled triggers and scheduled jobs    
- Communicate rollback decision and outcome  

**QA Role**  
- Verify that rollback restores the expected behavior   
- Confirm that all previously identified defects are resolved    
- Update QA checklists and post-mortem documentation  


### Notes & Tips  
Always deploy during low-traffic windows.  
Use version control for metadata (Git branching).  
Tag releases for traceability.  
Automate smoke and regression tests where possible.  
Maintain a QA checklist for each environment (sandbox, UAT, production).  

