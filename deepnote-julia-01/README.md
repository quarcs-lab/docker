#  quarcslab/deepnote-julia-ntl

```
FROM deepnote/python:3.7

RUN wget https://julialang-s3.julialang.org/bin/linux/x64/1.6/julia-1.6.2-linux-x86_64.tar.gz && \
    tar -xvzf julia-1.6.2-linux-x86_64.tar.gz && \
    mv julia-1.6.2 /usr/lib/ && \
    ln -s /usr/lib/julia-1.6.2/bin/julia /usr/bin/julia && \
    rm julia-1.6.2-linux-x86_64.tar.gz && \
    julia  -e "using Pkg;pkg\"add IJulia LinearAlgebra\""
    
ENV DEFAULT_KERNEL_NAME "julia-1.6"

```
After modifying the docker file run

docker build -t quarcslab/deepnote-julia:0.1 .

docker push quarcslab/deepnote-julia:0.1



## Packages to add

SparseArrays Images MAT QuantEcon Econometrics