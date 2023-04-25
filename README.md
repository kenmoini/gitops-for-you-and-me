# GitOps for You and Me

This is a repo to help explore GitOps concepts in an OpenShift context, with a Hub-and-Spoke pattern.

For Hub of Hubs patterns, see the [Multiverse of Multicluster Madness](https://github.com/kenmoini/multiverse-of-multicluster-madness/).

## What?

This repo has content that will show you how to:

- Bootstrap all GitOps functions in two steps (sans Secret/Vault things, that's an extra step or few)
- Leverage Red Hat Advanced Cluster Management and/or ArgoCD where it makes sense, and how to do so in tandem
- Separate concerns, personas, and RBAC

## Prerequisites

- An OpenShift cluster to act as a Hub with Storage already pre-configured - this needs to be a beefy boi
- Another OpenShift cluster to act as a managed spoke cluster
- Maybe another cluster too?

## Getting Started

1. Log into your Hub OpenShift cluster
2. Install the base operators like External Secrets Operator, Vault, and OpenShift Gitops: `oc apply -k 1-bootstrap-hub/`
3. Intialize the Vault: `oc apply -k 99-extras/vault-init`
4. Seed the needed Secrets in the Vault: [./docs/secret-seeding.md](./docs/secret-seeding.md)
5. Configure OpenShift GitOps: `oc apply -k 2-bootstrap-gitops/`
6. ????????
7. PROFIT!!!!!1
