# Install Nextflow
You can find more information about this pipeline tool at [nextflow.io](http://www.nextflow.io/). The typical installation of Nextflow looks like this:
```bash
curl -fsSL get.nextflow.io | bash
mv ./nextflow ~/bin
```
`~/bin` should be in your `$PATH`.

## Configure environment variables
- `NXF_HOME` is Nextflow home directory (default: $HOME/.nextflow).

Add to your `.bashrc`
```bash
export NXF_HOME=$HOME/.nextflow
```
