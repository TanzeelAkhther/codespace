*Manifest is a YAML-encoded representation of the Kubernetes resources that
were generated from this release's chart(s). If a chart is dependent on other
charts, those resources will also be included in the manifest.*

*Verbose output refers to a detailed and more descriptive form of output that provides extra information about what a command or process is doing behind the scenes. It's especially useful for debugging, troubleshooting, or understanding the flow of execution.*

Common actions for Helm:

- *helm search*:    search for charts
- *helm pull*:      download a chart to your local directory to view
- *helm install*:   upload the chart to Kubernetes
- *helm list*:      list releases of charts

- *helm get notes* -This command shows notes provided by the chart of a named release. [Not a valid subcommand with get]
- *helm get manifest* - This command fetches the generated manifest for a given release.
- *helm get output* - (This command consists of multiple subcommands which can be used to
get extended information about the release, including:

The values used to generate the release

The generated manifest file

The notes provided by the chart of the release

The hooks associated with the release

The metadata of the release)

- *helm get hooks* - This command downloads hooks for a given release.
Hooks are formatted in YAML and separated by the YAML '---\n' separator.

- *helm get values* -This command downloads a values file for a given release.


**Environment Variable**

$HELM_DEBUG     -  | indicate whether or not Helm is running in Debug mode 


**Command Line Flag**

--debug   - enable verbose output
