---
title: kyma provision gardener aws
---

Provisions a Kubernetes cluster using Gardener on Amazon Web Services (AWS).

## Synopsis

Use this command to provision Kubernetes clusters with Gardener on AWS for Kyma installation. 
To successfully provision a cluster on AWS, you must first create a service account to pass its details as one of the command parameters. 
Check the roles and create a service account using instructions at https://gardener.cloud/050-tutorials/content/howto/gardener_aws/.
Use service account details to create a Secret and import it in Gardener.

```bash
kyma provision gardener aws [flags]
```

## Flags

```bash
      --attempts uint                 Maximum number of attempts to provision the cluster. (default 3)
  -c, --credentials string            Path to the kubeconfig file of the Gardener service account for AWS. (required)
      --disk-size int                 Disk size (in GB) of the cluster. (default 50)
      --disk-type string              Type of disk to use on AWS. (default "gp2")
  -e, --extra NAME=VALUE              One or more arguments provided as the NAME=VALUE key-value pairs to configure additional cluster settings. You can use this flag multiple times or enter the key-value pairs as a comma-separated list.
      --hibernation-end string        Cron expression to configure when the cluster should stop hibernating
      --hibernation-location string   Timezone in which the hibernation schedule should be applied. (default "Europe/Berlin")
      --hibernation-start string      Cron expression to configure when the cluster should start hibernating (default "00 18 * * 1,2,3,4,5")
  -k, --kube-version string           Kubernetes version of the cluster. (default "1.23")
  -n, --name string                   Name of the cluster to provision. (required)
  -p, --project string                Name of the Gardener project where you provision the cluster. (required)
  -r, --region string                 Region of the cluster. (default "eu-west-3")
      --scaler-max int                Maximum autoscale value of the cluster. (default 3)
      --scaler-min int                Minimum autoscale value of the cluster. (default 1)
  -s, --secret string                 Name of the Gardener secret used to access AWS. (required)
  -t, --type string                   Machine type used for the cluster. (default "m5.xlarge")
  -z, --zones strings                 Zones specify availability zones that are used to evenly distribute the worker pool. eg. --zones="europe-west3-a,europe-west3-b" (default [eu-west-3a])
```

## Flags inherited from parent commands

```bash
      --ci                  Enables the CI mode to run on CI/CD systems. It avoids any user interaction (such as no dialog prompts) and ensures that logs are formatted properly in log files (such as no spinners for CLI steps).
  -h, --help                Provides command help.
      --kubeconfig string   Path to the kubeconfig file. If undefined, Kyma CLI uses the KUBECONFIG environment variable, or falls back "/$HOME/.kube/config".
      --non-interactive     Enables the non-interactive shell mode (no colorized output, no spinner)
  -v, --verbose             Displays details of actions triggered by the command.
```

## See also

* [kyma provision gardener](kyma_provision_gardener.md)	 - Provisions a cluster using Gardener on GCP, Azure, or AWS.

