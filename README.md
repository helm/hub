<!-- markdownlint-disable MD041 -->
|![Warning](https://upload.wikimedia.org/wikipedia/commons/thumb/1/17/Warning.svg/156px-Warning.svg.png) | This project is no longer supported. [hub.helm.sh](https://hub.helm.sh) now redirects to [artifacthub.io](https://artifacthub.io/). The source for that can be found at <https://github.com/artifacthub/hub>
|---|---|

# Helm Hub

The Helm Hub repository contained the documentation and some configuration for the
distributed public repository search hosted by Helm that used to be found at https://hub.helm.sh

## Redirect To Artifact Hub

The [Artifact Hub](https://artifacthub.io/) is a CNCF project to make discovering
distributed cloud native artifacts easy. This includes Helm charts. The Helm Hub,
including the search in the Helm Client, now redirect to the Artifact Hub. It
provides a better experience to that of the Helm Hub.

## Claiming Your Repo In The Artifact Hub

If you had a repository in the Helm Hub but had not already listed it in the Artifact
Hub, it was automatically listed. Everything that as in the Helm Hub should be
discoverable in the Artifact Hub.

There are two ways to claim your listing so that you can manage it on the Artifact
Hub:

1. If you create an account on the Artifact Hub there is a method to
   [claim your repository](https://github.com/artifacthub/hub/blob/master/docs/repositories.md#ownership-claim).
   In the repository settings you will find a button to start the
   process. Note, the Artifact Hub has both user and organizational accounts.
   If you have an organization, consider linking the repository to the organization
   instead of an individual user.
2. You can file an issue on this repository and we can perform a manual handoff.

The first method is preferred as it requires fewer people in the loop and should
be faster and less work for all parties.

## Artifact Hub Migration Details

The Helm Hub has to the [Artifact Hub](https://artifacthub.io/) ([issue here](https://github.com/helm/hub/issues/439)).
This means:

- The Helm Hub redirects to the Artifact Hub
- The Helm Client searches the Artifact Hub instead of the Helm Hub
- Charts will be listed in the Artifact Hub instead of the Helm Hub

Chart repositories listed in the Helm Hub have been migrated to the Artifact Hub
if they were not already listed there. They are managed by the Helm Organization.
You can follow the process above to obtain ownership of your Helm repositories.

## Happy helming in China

If you are in China, you will experience problems with some Helm repositories and the images they use not being accessible (e.g., gcr.io). You can use a mirror hub at https://developer.aliyun.com/hub which will automatically sync & replace unavailable images & repository URLs in every Chart with locations accessible in China.

## License

The following licenses used:

- Apache 2.0 for code
- Creative Commons Attribution 4.0 International Public License for documentation
