## helm upgrade

upgrade a release

### Synopsis



This command upgrades a release to a new version of a chart.

The upgrade arguments must be a release and chart. The chart
argument can be either: a chart reference('stable/mariadb'), a path to a chart directory,
a packaged chart, or a fully qualified URL. For chart references, the latest
version will be specified unless the '--version' flag is set.

To override values in a chart, use either the '--values' flag and pass in a file
or use the '--set' flag and pass configuration from the command line.

You can specify the '--values'/'-f' flag multiple times. The priority will be given to the
last (right-most) file specified. For example, if both myvalues.yaml and override.yaml
contained a key called 'Test', the value set in override.yaml would take precedence:

	$ helm upgrade -f myvalues.yaml -f override.yaml redis ./redis

You can specify the '--set' flag multiple times. The priority will be given to the
last (right-most) set specified. For example, if both 'bar' and 'newbar' values are
set for a key called 'foo', the 'newbar' value would take precedence:

	$ helm upgrade --set foo=bar --set foo=newbar redis ./redis


```
helm upgrade [RELEASE] [CHART]
```

### Options

```
      --dry-run             simulate an upgrade
  -i, --install             if a release by this name doesn't already exist, run an install
      --keyring string      path to the keyring that contains public singing keys (default "~/.gnupg/pubring.gpg")
      --namespace string    namespace to install the release into (only used if --install is set) (default "default")
      --no-hooks            disable pre/post upgrade hooks
      --recreate-pods       performs pods restart for the resource if applicable
      --set stringArray     set values on the command line (can specify multiple or separate values with commas: key1=val1,key2=val2)
      --timeout int         time in seconds to wait for any individual kubernetes operation (like Jobs for hooks) (default 300)
  -f, --values valueFiles   specify values in a YAML file (can specify multiple) (default [])
      --verify              verify the provenance of the chart before upgrading
      --version string      specify the exact chart version to use. If this is not specified, the latest version is used
```

### Options inherited from parent commands

```
      --debug                     enable verbose output
      --home string               location of your Helm config. Overrides $HELM_HOME (default "~/.helm")
      --host string               address of tiller. Overrides $HELM_HOST
      --kube-context string       name of the kubeconfig context to use
      --tiller-namespace string   namespace of tiller (default "kube-system")
```

### SEE ALSO
* [helm](helm.md)	 - The Helm package manager for Kubernetes.

###### Auto generated by spf13/cobra on 15-Jan-2017
