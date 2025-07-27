# Task 2 – DevSecOps Pipeline with GitOps Integration

## Overview

This task enhances the existing CI/CD pipeline by integrating DevSecOps practices and GitOps-based deployment. The focus is on adding automated security checks, secure secret management, and continuous deployment to Kubernetes using Argo CD.

## Key Enhancements

### Security Integration

- **Trivy**: Performs container and application vulnerability scanning during the build process.
- **Sealed Secrets**: Manages Kubernetes secrets in a secure, encrypted format using kubeseal and controller.

### GitOps-Based Deployment

- **Argo CD**: Used to deploy applications to Kubernetes by continuously syncing manifests from a Git repository.
- Enables fully declarative, version-controlled, and automated deployment.

## Workflow Summary

1. Developer pushes code to GitHub.
2. CodePipeline triggers CodeBuild to:
   - Build the application
   - Run Trivy vulnerability scans
   - Encrypt Kubernetes secrets
3. Kubernetes manifests are pushed to a separate GitOps repository.
4. **Argo CD** monitors that repo and automatically syncs changes to the cluster.

## Outcome

This task integrates security scanning and GitOps into a CI/CD pipeline using Trivy for vulnerability scanning and Sealed Secrets for managing sensitive data, while Argo CD automates deployment by syncing Kubernetes manifests from GitHub, ensuring a secure, reliable, and continuous delivery process with built-in application checks and Git-based deployment management.
