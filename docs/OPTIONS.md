# Useful Nextflow options

## launch a github hosted project
Use the github repository to launch the execution of a hosted project:
```bash
nextflow run SciLifeLab/repository
```
The github address can also be used:
```bash
nextflow run http://github.com/SciLifeLab/Repository
```

## launch a specific version
Use the `-r` option to launch a specific version based on a tag, branch or commit ID.
```bash
nextflow run SciLifeLab/repository -r v1.0
```

## config
More informations on [Nextflow documentation](https://www.nextflow.io/docs/latest/basic.html#configuration-options).
Use the `-c` option to specify a config file to use.
```bash
nextflow run SciLifeLab/repository -c file.config
```
If no config file is specified, Nextflow will look for `$NXF_HOME/config` or for `nextflow.config` in your current directory.

## profiles
More informations on [Nextflow documentation](https://www.nextflow.io/docs/latest/config.html#config-profiles).
A profile can be defined in `nextflow.config`, `includeConfig` can be use to include several config files.
Example:
```groovy
profiles {
  milou {
    includeConfig 'configuration/standard.config'
    includeConfig 'configuration/milou.config'
    includeConfig 'configuration/milou-slurm.config'
  }
  bianca {
    includeConfig 'configuration/standard.config'
    includeConfig 'configuration/bianca.config'
    includeConfig 'configuration/bianca-slurm.config'
  }
  milou_interactive {
    includeConfig 'configuration/standard.config'
    includeConfig 'configuration/milou.config'
    includeConfig 'configuration/milou-local.config'
  }
}
```

## clean
Use the `clean -f` option to remove the files contained in the `work` directory from the last Nextflow execution.
```bash
nextflow clean -f
```

## resume
Use the `-resume` option to restart the project where it last failed.
```bash
nextflow run SciLifeLab/repository -resume
```

## info
Use the `info` option to get information about the github project.
```bash
nextflow info SciLifeLab/repository
```

## pull
Use the `pull` option to update the github project.
```bash
nextflow pull SciLifeLab/repository
```
