# Helm Hub

The Helm Hub repository contains the documentation and some configuration for the
distributed public repository search hosted by Helm that can be found at https://hub.helm.sh

## Distributed Search

Helm was designed with many distributed repositories in mind. This is why the Helm
CLI has commands to manage adding, updating, listing, and removing them. Repositories
are hosted by many people and organizations. Sometimes these are private and sometimes
they are public with a goal of distributing applications.

Discovering the charts hosted by the Helm project via the [stable and incubator](https://github.com/helm/charts)
repositories has been relatively easy. We want to go further and make it possible
to discover the charts and repositories being hosted by others.

The Hub provides a means to more easily find charts that are hosted outside the Helm
project. This has implications for those who build and distribute charts including:

- They can manage the workflow around releases themselves
- They can track metrics around the use of their charts

## Artifact Hub Migration

The Helm Hub is migrating to the [Artifact Hub](https://artifacthub.io/) ([issue here](https://github.com/helm/hub/issues/439)). This means a few changes are coming:

- When the migration is complete, the Helm Hub will redirect to the Artifact Hub
- The Helm Client will search the Artifact Hub instead of the Helm Hub
- Charts will be listed in the Artifact Hub instead of the Helm Hub

Chart repositories listed in the Helm Hub have been migrated to the Artifact Hub
if they were not already listed there. They are managed by the Helm Organization.
If you own one of the repositories and want to claim it there are two methods
you can use.

1. Once you have an account (or organization) setup you can claim ownership. This
   happens via the "Claim Ownership" button in the Repositories settings. This
   will walk you through a process where you prove ownership to claim it.
2. Contact one of the Helm chart maintainers and work through a manual handoff.

You are encouraged to take over ownership of your repositories in the Artifact Hub.
The first method is the preferred method as a repository owner can accomplish this
at their own pace.

## How To Add Your Helm Charts

The process to add a repository and all of its charts is documented in the
[Repositories.md](Repositories.md) file. This includes the guidelines that need
to be followed to be listed along with the functional parts of the process.

## Contributions

This project is in its early stages with plenty of room for improvement including
UX improvements, the back-end application, and the process used to manage the
Hub itself.

Contributions to the process happen in this repository while the software powering
the Hub is [Monocular](https://github.com/helm/monocular), a Helm project.

## Happy helming in China

 If you are in China, you will experience problems with some Helm repositories and the images they use not being accessible (e.g., gcr.io). You can use a mirror hub at https://developer.aliyun.com/hub which will automatically sync & replace unavailable images & repository URLs in every Chart with locations accessible in China.

## License

The following licenses used:

- Apache 2.0 for code
- Creative Commons Attribution 4.0 International Public License for documentation
