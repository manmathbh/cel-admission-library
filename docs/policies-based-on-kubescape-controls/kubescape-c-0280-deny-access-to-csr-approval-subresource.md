# Kubescape C-0280: Deny access to certificatesigningrequests/approval sub-resource

## Why this policy is required:
Users with access to update the approval sub-resource of certificatesigningrequests objects can approve new client certificates for the Kubernetes API, effectively allowing them to create new high-privileged user accounts. This can allow for privilege escalation to full cluster administrator.

## Severity Level: Medium

## Configuration Parameters:
* Not Configurable

## Resources this policy could be applied to:
* ClusterRole
* Role

## What does this policy do:
This Policy checks whether any Role or ClusterRole grants access to the `certificatesigningrequests/approval` or `certificatesigningrequests/*` sub-resource. If such access is found, the resource is denied.

## Implementing this policy in the Cluster:
[Refer here for using the policy in the cluster](https://github.com/kubescape/cel-admission-library#using-the-library)
