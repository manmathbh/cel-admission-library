# Kubescape C-0026: Deny CronJobs

## Why this policy is required:
Attackers may use Kubernetes CronJob for scheduling execution of malicious code that would run as a pod in the cluster. This control lists all the CronJobs that exist in the cluster for the user to approve.

## Severity Level: Low

## Configuration Parameters:
* Not Configurable

## Resources this policy could be applied to:
* CronJob

## What does this policy do:
This Policy fails for every `CronJob` admitted to the cluster, surfacing it to the user for review. Use the binding `validationActions: [Warn]` to make this an audit-only signal rather than a hard deny.

## Implementing this policy in the Cluster:
[Refer here for using the policy in the cluster](https://github.com/kubescape/cel-admission-library#using-the-library)
