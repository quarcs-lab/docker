#  quarcslab/deepnote-julia-ntl

```
FROM deepnote/python:3.7

RUN wget https://julialang-s3.julialang.org/bin/linux/x64/1.6/julia-1.6.2-linux-x86_64.tar.gz && \
    tar -xvzf julia-1.6.2-linux-x86_64.tar.gz && \
    mv julia-1.6.2 /usr/lib/ && \
    ln -s /usr/lib/julia-1.6.2/bin/julia /usr/bin/julia && \
    rm julia-1.6.2-linux-x86_64.tar.gz && \
    julia  -e "using Pkg;pkg\"add IJulia LinearAlgebra\""
    
ENV DEFAULT_KERNEL_NAME "julia-1.7"

```
After modifying the docker file run

docker build -t quarcslab/deepnote-julia:1.7 .

docker push quarcslab/deepnote-julia:1.7

 MLBase MultivariateStats LinearAlgebra Distributions Plots StatsPlots VegaDatasets SparseArrays Images MAT  Econometrics


## Packages to add
CSV Clustering DataFrames DataStructures DecisionTree DelimitedFiles Distances Distributions Flux GLM GLMNet GLMakie GLPK HDF5 HypothesisTests JLD JSON JuMP KernelDensity LIBSVM LightGraphs LsqFit MLBase MLDatasets Makie MatrixNetworks MultivariateStats NPZ NearestNeighbors Plots RDatasets