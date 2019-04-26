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

## License

The following licenses used:

- Apache 2.0 for code
- Creative Commons Attribution 4.0 International Public License for documentation
