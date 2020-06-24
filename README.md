# casesExample

Here, we demonstrate how to evaluate a Metric both on the public API and on the C3 platform. We also demonstrate how information from multiple datasets can be combined to make build more interesting analytics and plots.

We first explore the `outbreakLocation` Type to see what locations are available to us. Once we select a few locations, we can retrieve their case history by running a series of evalMetrics. Data is returned in the `EvalMetricsResult` type and may need to be converted to a usable form. Once this conversion is complete, we can use plotting libraries to produce plots of cases over time.

We then step up the complexity of the example by finding and computing cases per capita for each location selected. This requires us to explore the data to find which feature contains appropriate population data, then form a new dataset by dividing the case information by this population for each `outbreakLocation`.

Finally, we can produce the same set of plots but instead look at the daily new cases.

## Python Implementation

To use the python implementation, either install all necessary packages listed in `env.yaml` or use `conda` to create an environment from this definition file with the command:

```
conda env create -f ./env.yaml -p ./venv
```

We've also included a fully realized environment which was used to develop and test this example in the file `env-concrete.yaml`. That's here for future information and is not likely to work on your system as is. You may be able to delete a couple low level dependencies and conda may be able to solve a new environment for you though.

## C3 Implementation

Coming Soon...
