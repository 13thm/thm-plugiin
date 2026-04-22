---
name: deploy
description: Automated deployment workflow and coordination
version: "1.0.0"
author: DevOps Team
---

# Deploy Skill

Coordinate deployment activities across environments.

## When to Use

Invoke this skill when:
- Preparing for production deployment
- Setting up staging environments
- Rolling back failed deployments
- Validating deployment configurations
- Performing health checks post-deployment

## Deployment Process

### Pre-Deployment
1. Verify branch is up-to-date with main
2. Run full test suite
3. Check environment configuration
4. Create deployment backup
5. Verify rollback capability

### Deployment
1. Build deployment artifacts
2. Run database migrations
3. Deploy application code
4. Update infrastructure as needed
5. Restart services

### Post-Deployment
1. Smoke tests
2. Health check verification
3. Monitor application logs
4. Verify key functionality
5. Performance baseline check

## Environment Validation

### Development
- Fast feedback loop
- Minimal validation
- Local testing

### Staging
- Production-like configuration
- Full test suite
- Security scanning
- Integration tests

### Production
- All staging validations
- Rollback plan confirmed
- Monitoring alerts configured
- Team notification sent

## Rollback Procedures

1. Identify degradation point
2. Execute rollback plan
3. Verify system恢复
4. Post-mortem documentation

## Notes

- Always have a rollback plan
- Communicate deployment status
- Monitor for issues post-deployment
- Document any configuration changes
