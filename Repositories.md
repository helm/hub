# Guidelines for Repository Inclusion

This document outlines the requirements and guidelines for a Helm repository to
be listed in the distributed search hosted by the Helm Project. This document
may be updated at any time.

## Artifact Hub

The Helm Hub is in the process of migrating to the [Artifact Hub](https://artifacthub.io/).
Please list your repository in the Artifact Hub prior to listing it in the Helm
Hub.

## Process to Add A Repository

To add a repository create a new pull request with the following two pieces
of information:

1. In the file at `config/repo-values.yaml` add your repository with a short name
   and the base URL to the repository.
2. In the file `repos.yaml`, alongside this file, add contact information for
   the repository. This contact information is necessary when there is a need for the
   Helm project to contact those who manage a repository (e.g., it goes offline).
   If the repository is owned by a team or company we suggest using a mailing list.

The pull request will be reviewed. If merged, the content will be available on
the Hub site a short while there after.

## Repository Best Practices

Repositories listed in the distributed search should follow
[Helm chart best practices](https://docs.helm.sh/chart_best_practices/).
In addition to these practices we expect:

- Every chart to have a maintainer listed along with valid contact information
  for each maintainer. The contact information could be in the form of an email
  address or link to a contact form
- Charts to pass Helm lint, be installable and upgradable in all community
  supported versions of Kubernetes, and to use semantic versioning to share
  intent in released changes. To help with this we suggest leveraging the
  [Chart Testing](https://github.com/helm/chart-testing) project.
- Have a NOTES.txt template with useful information which Helm will display
  after installation
- Chart versions to be immutable

## Legal Guidelines

Helm is an incubating project under the Cloud Native Computing Foundation (CNCF)
which itself is part of The Linux Foundation (TLF). TLF is a US non-profit operating
under US laws. That means we have to follow US laws when listing repositories.
This should have minimal, if any, impact for most people. But, for example, we
cannot list repositories in US embargoed countries.

## F.A.Q.

### Will the process always be this manual?

Our goal is to add more automation and self management over time. What is initially
launched with may not reflect the implementation several years later. If you are
interested in contributing to improvements please let us know.

### What happens if a repository changes to not follow the guidelines?

If we find out a repository stopped following the requirements in this document
we will first privately reach out to the repository maintainers to try and fix
the problem. That could be to help the repository fix a problem or to
re-evaluate something we are doing. We want to work with repository owners and
be respectful of each other. This is one case where the private contact information
will be used.

### What happens if this policy changes so that a repository no longer meets it?

If we change a policy we want to think of the implications to repositories but
changes may occur that break things. Helm puts a high priority on application
distributors and application operators and we try to pay attention to impact.
But, we may have to change things that break things and we may make changes with
unintended consequences.

When we break things in intended ways we will attempt to communicate those changes
out along with any impact and proposals for repository owners. Discussions on
these changes will happen in the open, unless there is a security issue involved
where we will be discrete.

We will make attempts to accommodate repositories while being kind and professional.
But, sometimes changes may need to be made.
