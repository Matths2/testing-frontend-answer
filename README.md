# Friends Angular Accelerator

This is a baseline  TAP Angular Accelerator that includes and configures the following packages:

* Angular
* ESlint
* Prettier
* OpenAPI typescript-angular generator

A Dockerfile is included in the Accelerator also.

## Getting Started

The following steps will get you started with this project.


### Production

The following steps assumes you have credentials and has a ssh session to the kubernetes cluster established.

<br>
 Write the following command in your terminal to set the namespace you want to deploy to.

```bash
export YOUR_NAMESPACE=<YOUR_NAMESPACE>
export GIT_REPO=<YOUR_GIT_REPO>
```

<br>
Write the following command in your terminal to deploy the application to the cluster.

```bash
tanzu apps workload create friends-angular-accelerator \
--git-repo ${GIT_REPO} \
--git-branch main \
--type web \
--label app.kubernetes.io/part-of=friends-angular-accelerator \
--yes \
--namespace ${YOUR_NAMESPACE}
```

<br>
Write the following command in your terminal to get build status and the url to the application.

```bash
tanzu apps workload get -n ${YOUR_NAMESPACE} friends-angular-accelerator
```

Push to the ```main``` branch of this repo will trigger a new build and deployment to the cluster.
<br>

For more information:

- [Friends TAP confluence](https://confluence.shared.int.tds.tieto.com/x/PKC2EQ)

