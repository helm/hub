# GitHub Pages as a Repository

GitHub pages can and often are used to host Helm chart repositories.

If you want to use GitHub pages, the first step is to [setup GitHub Pages](https://help.github.com/categories/github-pages-basics/). You can set it up to use [a pages specific branch or a sub-directory](https://help.github.com/articles/configuring-a-publishing-source-for-github-pages/). Once GitHub pages is setup you can use it Helm commands to create a repository.

_Note, it's useful to keep in mind that all of these commands can be scripted and used as part of a CI system._

1. `helm package .`: Package the current directory as a chart. This will create a file with the pattern [chart name]-[version].tgz. This file is a packaged up chart that can be passed around.
2. `helm repo index ./`: Generates an `index.yaml` file based on the packaged charts in the current directory.
3. Check in these files to git so they can be exposed as GitHub pages
4. Push the changes to GitHub who will package them as GitHub pages as a repository

## By Example

To illustrate this we can look at two example flows.

### A `docs` directory in the repository

Consider the case where there is a `docs` directory in the code repository to be used to service the GitHub pages side and charts repository. GitHub pages can be configured to use this directory for the site.

- The `tgz` file created by `helm package` can be placed in the `docs` directory. In this case you will keep all of the versioned `tgz` files. An example of a directory like this can be seen [here](https://github.com/technosophos/tscharts/tree/master/docs)
- Once the new chart package is in the directory, `helm repo index` can be used to generate an up to date `index.yaml` file for the packages
- Commit and push the new `tgz` file and `index.yaml` file.

GitHub Pages will update with the new content.

To aide in the workflow and illustrate what you can do, [Matt Butcher created a Helm Plugin](https://github.com/technosophos/helm-github). The plugin follows the `docs` directory flow. It even showcases how to have [signed charts](https://docs.helm.sh/developing_charts/#helm-provenance-and-integrity).

### A second repository

Sometimes you want the charts repository to be separate from the code itself. In this case you have repository A, with the code, and repository B, for the charts repository.

For this situation a flow could look like:

- When it's time for a release of the chart on repository A automation used to run `helm package` on the chart and push the change to repository B
- When a new chart lands on repository B it can regenerate the `index.yaml` file

Presslabs is one organization using this workflow. In their codes CI pipeline they publish a chart to a second repository when they tag the code ([see the example here](https://github.com/presslabs/mysql-operator/blob/99618eab7c262c187c11f48f1f989e89eb25c1cd/.drone.yml#L97-L111)). In their charts repository they regenerate `index.yaml` and commit the change (example code [here](https://github.com/presslabs/charts/blob/7f7602ea1f2c626dc04519e5344499787807326f/.drone.yml) and [here](https://github.com/presslabs/charts/blob/7f7602ea1f2c626dc04519e5344499787807326f/Makefile)). Note, when committing changes back to the same repo be sure to know when to skip CI to avoid getting caught in a loop.

## More to come

There are many ways to publish Helm charts as repositories on GitHub and we are looking for future improvements. If you have suggestions or are interested in helping both pull requests and ideas are welcome.
