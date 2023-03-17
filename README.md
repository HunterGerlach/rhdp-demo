# OpenShift Hello World Demo

This is a simple step-by-step guide to create and deploy a basic "Hello World" application on OpenShift.

## Prerequisites

- OpenShift CLI (oc) installed: https://docs.openshift.com/container-platform/latest/cli_reference/openshift_cli/getting-started-cli.html
- An OpenShift cluster is available and you have access to it.

## Steps

1. **Log in to the OpenShift cluster**

   Use the `oc login` command to log in to the OpenShift cluster:

```bash
oc login --server=<OPENSHIFT_CLUSTER_URL> --token=<YOUR_ACCESS_TOKEN>
```

2. **Create a new project**

Create a new project on OpenShift using the `oc new-project` command:

```bash
oc new-project hello-world-demo
```

3. **Deploy the Hello World application**

Deploy the "Hello World" application using the `oc new-app` command:

```bash
oc new-app openshift/python-36-centos7~https://github.com/sclorg/django-ex.git --name=hello-world
```

4. **Expose the Hello World application**

Expose the "Hello World" application using the `oc expose` command:

```bash
oc expose svc/hello-world
```

5. **View the application URL**

Retrieve the URL for the "Hello World" application using the `oc get route` command
