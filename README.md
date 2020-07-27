# casesExample

Here, we demonstrate how to evaluate a Metric both on the public API and on the C3 platform. We also demonstrate how information from multiple datasets can be combined to make build more interesting analytics and plots.

We first explore the `outbreakLocation` Type to see what locations are available to us. Once we select a few locations, we can retrieve their case history by running a series of evalMetrics. Data is returned in the `EvalMetricsResult` type and may need to be converted to a usable form. Once this conversion is complete, we can use plotting libraries to produce plots of cases over time.

We then step up the complexity of the example by finding and computing cases per capita for each location selected. This requires us to explore the data to find which feature contains appropriate population data, then form a new dataset by dividing the case information by this population for each `outbreakLocation`.

Finally, we can produce the same set of plots but instead look at the daily new cases.

## Python Implementation

The pure python implementation of this example resides in the `python` directory. Either install all necessary packages listed in `env.yaml` or use `conda` to create an environment from this definition file with the command:

```
conda env create -f ./env.yaml -p ./venv
```

We've also included a fully realized environment which was used to develop and test this example in the file `env-concrete.yaml`. That's here for future information and is not likely to work on your system as is. You may be able to delete a couple low level dependencies and conda may be able to solve a new environment for you though.

## C3 Implementation

The C3 implementation of this example is in the directory `c3-python-connector`. Make sure you have access to a C3 tag which has the Datalake package provisioned either directly, or as a dependency of your current package. To ensure your python environment has everything needed, we recommend provisioning a conda environment with

```
conda env create -f ./env.yaml -p ./venv
```

After which you can launch jupyter notebook, and open the notebook `casesExample.ipynb`.

When running the jupyter notebook, there's a cell at the top meant to connect to a running C3 tag. If you're running python/jupyter 'remotely' that is not through C3's system, you will need to replace the `<vanity_url>`, `<tenant>`, and `<tag>` in the cell negotiating the connection to C3. It should look like this:

```
c3 = get_c3('<vanity_url>', '<tenant>', '<tag>')
```
