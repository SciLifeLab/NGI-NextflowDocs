# Install Nextflow
You can find more information about this pipeline tool at [nextflow.io](http://www.nextflow.io/). The typical installation of Nextflow looks like this:
```bash
curl -fsSL get.nextflow.io | bash
mv ./nextflow ~/bin
```
`~/bin` should be in your `$PATH`.

## Create Nextflow specific directories
The second one might have already been created when you installed Nextflow.
```bash
mkdir $HOME/glob/nxftmp
mkdir $HOME/.nextflow
```

## Configure environnement variables
- `NXF_HOME` is Nextflow home directory (default: $HOME/.nextflow).
- `NXF_TEMP` is where temporary files are stored.
- `NXF_WORK` is where working files are stored (usually your scratch directory)
- `NXF_LAUNCHBASE` provides a separate directory for launcher.
- `NXF_OPTS` provides extra options for the Java and Nextflow runtime.

Add to your `.bashrc`
```bash
export NXF_HOME=$HOME/.nextflow
export NXF_TEMP=${SNIC_TMP:-$HOME/glob/nxftmp}
export NXF_WORK=$HOME/glob/work
export NXF_LAUNCHBASE=${SNIC_TMP:-$HOME/glob/nxftmp}
```
