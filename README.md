# NGI-NextflowDocs

Project is likely to be out of date and might be incorrect in some case.

We advised to have a look at [Nextflow documentation](https://www.nextflow.io/docs/latest/index.html) or at the [nf-core website](https://nf-core.github.io/), or to join the gitter channels for some direct contact with developers: [nextflow channel](https://gitter.im/nextflow-io/nextflow) or [nf-core Lobby](https://gitter.im/nf-core/Lobby).

Common documentation for National Genomics Infrastructure pipelines built with Nextflow. Some variables are specific to Swedish UPPMAX cluster, but can be easily modified to suit any clusters.

## Install Nextflow
See the [Install documentation](docs/INSTALL.md)

## Common options
See the [options documentation](docs/OPTIONS.md)

## Common configuration besides basic required stuff

### Configuration Loading
Config variables (eg. `params.something`) are loaded in the following order:

1. Pipeline script
2. Home directory (`~/.nextflow/config`)
3. Pipeline script directory (`pipeline/nextflow.config`)
4. Launch directory (`./nextflow.config`)
5. Specified config file (`-c my_config`)
6. Command line (`--something`)

Anything specified in more than one location will be overwritten by subsequent loads. The command line has preference over everything.


## Best practices / snippets
See [Example Pipeline](snippets/main.nf)

## Troubleshooting nextflow
Check the `work` directory, and especially the last one (which is the one that failed) for information about the failed process, and if needed, you can go up the chain of processes.
