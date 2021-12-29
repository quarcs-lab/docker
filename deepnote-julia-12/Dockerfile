FROM deepnote/python:3.7

RUN wget https://julialang-s3.julialang.org/bin/linux/x64/1.6/julia-1.6.2-linux-x86_64.tar.gz && \
    tar -xvzf julia-1.6.2-linux-x86_64.tar.gz && \
    mv julia-1.6.2 /usr/lib/ && \
    ln -s /usr/lib/julia-1.6.2/bin/julia /usr/bin/julia && \
    rm julia-1.6.2-linux-x86_64.tar.gz && \
    julia  -e "using Pkg;pkg\"add IJulia LinearAlgebra SparseArrays Images MAT NearestNeighbors DiffResults CoordinateTransformations RegionTrees Graphs QuantEcon Econometrics CSV Clustering DataFrames DataStructures DecisionTree DelimitedFiles Distances Distributions Flux GLM GLMNet GLMakie GLPK\"" 
    
ENV DEFAULT_KERNEL_NAME "julia-1.6"