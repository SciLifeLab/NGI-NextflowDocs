# NGI-NextflowDocs
Common documentation for National Genomics Infrastructure pipelines built with Nextflow

## Nextflow installation / required configuration
Some variables are specific to Swedish UPPMAX cluster, but can be easily modified to suit any clusters.

### Install Nextflow
To use this pipeline, you need to have a working version of Nextflow installed. You can find more information about this pipeline tool at [nextflow.io](http://www.nextflow.io/). The typical installation of Nextflow looks like this:
```bash
curl -fsSL get.nextflow.io | bash
mv ./nextflow ~/bin
```
`~/bin` should be in your `$PATH`.

### Create Nextflow specific directories
The second one might have already been created when you installed Nextflow.
```bash
mkdir $HOME/glob/nxftmp
mkdir $HOME/.nextflow
```

### Configure environnement variables
Add to your `.bashrc` or your `.bash_profile`
```bash
export NXF_HOME=$HOME/.nextflow
export NXF_TEMP=${SNIC_TMP:-$HOME/glob/nxftmp}
export NXF_LAUNCHBASE=${SNIC_TMP:-$HOME/glob/nxftmp}
export NXF_WORK=$HOME/glob/work
export NXF_OPTS='-Xms1g -Xmx4g'
```

## Common configuration besides basic required stuff

## Best practices / snippets

### run from github
Use the github address to execute your project from the github code
```bash
nextflow run <Address/Repository>
```

### version
Use the `-r` option in your command line to run a specific version based on a tag, branch or commit ID.
```bash
-r <version>
```

### config
More informations on [Nextflow documentation](https://www.nextflow.io/docs/latest/basic.html#configuration-options)
```bash
-c <file.config>
```
If no config file is specified, Nextflow will look for one in Nextflow intallation `$NXF_HOME/config` of for one in the current directory `nextflow.config`.

### clean
Use `nextflow clean -f` to remove everything contained in the `work` directory from the last Nextflow execution.
```bash
nextflow clean -f
```

### resume
Use `-resume` to restart the project where it last failed.
```bash
nextflow run <last command> -resume
```

### info
Use `info` to get information about the github project.
```bash
nextflow info <Address/Repository>
```

### pull
Use `pull` to update the github project.
```bash
nextflow pull <Address/Repository>
```

## Troubleshooting nextflow
Check the `work` directory, and especially the last one for information about the failed process.
