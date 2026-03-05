---
title: "Checklist: Preparing Your AEM 6.5 Environment for an Upgrade"
description: "A comprehensive checklist to ensure your AEM 6.5 environment is ready for upgrade, covering discovery, testing, deployment, and post-upgrade validation."
pubDate: 2024-11-10T00:00:00.000Z
author: "Thomas Franz"
category: "AEM"
tags: ["aem-6.5", "upgrades", "checklist", "best-practices"]
draft: false
---

Upgrading Adobe Experience Manager is a complex undertaking that requires careful preparation. This checklist will help you ensure nothing is overlooked as you plan and execute your AEM 6.5 upgrade.

## Phase 1: Discovery & Assessment

### Environment Inventory

- [ ] Document all AEM instances (author, publish, dispatcher)
- [ ] List all integrations (CRM, analytics, DAM, etc.)
- [ ] Catalog third-party packages and versions
- [ ] Identify all custom OSGi bundles and components
- [ ] Map out content structure and templates
- [ ] Document current system architecture

### Custom Code Audit

- [ ] Review all custom components for deprecated APIs
- [ ] Check servlets and services for compatibility
- [ ] Audit JavaScript and client libraries
- [ ] Review custom workflows and launchers
- [ ] Identify unused or redundant custom code
- [ ] Check for hardcoded paths or configurations

### Performance Baseline

- [ ] Document current page load times
- [ ] Record repository size and growth rate
- [ ] Note peak traffic patterns and response times
- [ ] Benchmark query performance
- [ ] Document current resource utilization (CPU, memory, disk)

### Team Preparation

- [ ] Identify key stakeholders and decision-makers
- [ ] Assign upgrade project roles and responsibilities
- [ ] Schedule regular status meetings
- [ ] Plan for knowledge transfer sessions
- [ ] Identify training needs for new features

## Phase 2: Planning

### Technical Planning

- [ ] Choose target AEM version (newer 6.5 LTS or AEM as a Cloud Service)
- [ ] Plan upgrade path (direct vs. phased)
- [ ] Design new architecture if making improvements
- [ ] Plan for dispatcher and CDN updates
- [ ] Determine database upgrade strategy
- [ ] Plan Java version upgrade if needed

### Testing Strategy

- [ ] Define test scenarios covering all major features
- [ ] Identify critical user journeys to validate
- [ ] Plan for performance testing
- [ ] Schedule user acceptance testing (UAT)
- [ ] Prepare test data and content
- [ ] Set up test environments matching production

### Risk Mitigation

- [ ] Document rollback procedures
- [ ] Plan for blue-green or canary deployment
- [ ] Identify potential breaking changes
- [ ] Create backup and restore procedures
- [ ] Plan communication strategy for stakeholders
- [ ] Prepare contingency plans for common issues

### Resource Planning

- [ ] Secure budget for upgrade costs
- [ ] Allocate internal team time
- [ ] Engage external consultants if needed
- [ ] Schedule downtime windows
- [ ] Plan for post-upgrade support coverage

## Phase 3: Development & Testing

### Environment Setup

- [ ] Clone production to lower environments
- [ ] Set up development environment with new AEM version
- [ ] Configure staging environment for testing
- [ ] Implement monitoring and logging
- [ ] Set up automated deployment pipelines

### Code Migration

- [ ] Upgrade custom components to new APIs
- [ ] Update deprecated code patterns
- [ ] Refactor problematic code identified in audit
- [ ] Update client libraries and dependencies
- [ ] Migrate configurations to new format if needed
- [ ] Update documentation for code changes

### Integration Testing

- [ ] Test all third-party integrations
- [ ] Validate authentication and SSO
- [ ] Check data synchronization processes
- [ ] Test API endpoints and web services
- [ ] Verify CDN and dispatcher configuration
- [ ] Validate analytics and tag management

### Content Migration

- [ ] Test content migration scripts
- [ ] Validate all content renders correctly
- [ ] Check for broken references
- [ ] Verify asset renditions
- [ ] Test taxonomy and metadata
- [ ] Validate multilingual content if applicable

### Performance Testing

- [ ] Run load tests matching production traffic
- [ ] Test under peak load conditions
- [ ] Validate caching behavior
- [ ] Check query performance
- [ ] Monitor resource utilization
- [ ] Identify and fix performance bottlenecks

### User Acceptance Testing

- [ ] Execute all planned test scenarios
- [ ] Validate critical business processes
- [ ] Test across different browsers and devices
- [ ] Verify accessibility standards
- [ ] Check for visual regressions
- [ ] Document any issues found

## Phase 4: Deployment

### Pre-Deployment

- [ ] Final backup of production environment
- [ ] Freeze content changes if possible
- [ ] Communicate maintenance window to users
- [ ] Prepare deployment runbook
- [ ] Assign on-call support team
- [ ] Set up monitoring and alerting

### Deployment Steps

- [ ] Execute deployment according to runbook
- [ ] Validate each step before proceeding
- [ ] Monitor system health during deployment
- [ ] Perform smoke tests after each major step
- [ ] Document any deviations from plan
- [ ] Keep stakeholders updated on progress

### Post-Deployment Validation

- [ ] Run automated health checks
- [ ] Validate critical functionality
- [ ] Check all integrations are working
- [ ] Verify content is intact
- [ ] Test user authentication
- [ ] Validate scheduled jobs and workflows
- [ ] Check system performance metrics
- [ ] Review logs for errors or warnings

## Phase 5: Post-Upgrade

### Monitoring

- [ ] Monitor error logs closely for 48-72 hours
- [ ] Track performance metrics vs. baseline
- [ ] Watch for user-reported issues
- [ ] Monitor system resource utilization
- [ ] Check for memory leaks or performance degradation
- [ ] Validate backup processes are working

### Documentation

- [ ] Document the upgrade process and lessons learned
- [ ] Update architectural diagrams
- [ ] Record configuration changes
- [ ] Update runbooks and procedures
- [ ] Document known issues and workarounds
- [ ] Create knowledge base articles for team

### Knowledge Transfer

- [ ] Train team on any new features used
- [ ] Share post-upgrade findings with stakeholders
- [ ] Conduct retrospective meeting
- [ ] Update onboarding materials for new team members
- [ ] Document any new monitoring or alerting

### Optimization

- [ ] Review performance and identify improvements
- [ ] Optimize configurations based on monitoring
- [ ] Clean up unused code or content
- [ ] Implement any deferred optimizations
- [ ] Schedule regular health checks

## Common Pitfalls to Avoid

### Don't Skip Testing

Testing in lower environments is not optional. Many issues only appear under certain conditions or with specific content.

### Don't Underestimate Timing

Most upgrades take longer than estimated. Build in buffer time for unexpected issues.

### Don't Forget About Dispatcher

The dispatcher configuration often needs updates. Test it thoroughly.

### Don't Ignore Deprecated Features

Just because deprecated code still works doesn't mean it will continue to work in future versions.

### Don't Deploy Without Rollback Plan

If something goes wrong, you need a quick way back to the working state.

## How Long Does Each Phase Take?

Based on a typical enterprise AEM implementation:

- **Discovery & Assessment**: 2-3 weeks
- **Planning**: 2-4 weeks
- **Development & Testing**: 4-8 weeks
- **Deployment**: 1-3 days
- **Post-Upgrade Stabilization**: 1-2 weeks

**Total**: Typically 12-18 weeks from start to finish for a well-planned upgrade.

## Need Help?

Don't want to tackle this alone? We've executed dozens of AEM upgrades and can help at any stage:

- **Health Check**: Assess your readiness and create a plan
- **Execution**: Handle the entire upgrade process
- **Advisory**: Guide your team through the upgrade
- **Support**: Provide post-upgrade support and optimization

[Contact us](/contact?service=aem-upgrade) to discuss your upgrade needs.

---

**Download this checklist** as a PDF to share with your team. [Get the PDF](/contact) (Coming soon)
