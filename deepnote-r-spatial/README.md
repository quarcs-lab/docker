#  quarcslab/deepnote-r-spatial

```
FROM deepnote/ir:4.0.4

# Dependencies needed for R libraries
RUN apt-get update \
   && apt-get install -y libcurl4-openssl-dev libssl-dev libxml2-dev libcairo2-dev libxt-dev \
   libpq-dev \
   libudunits2-dev libgdal-dev libgeos-dev libproj-dev

# Install the R libraries
RUN R -e "install.packages(c('tidyverse', 'ExPanDaR', 'AER', 'basetheme', 'barsurf', 'bivariate', 'BMS', 'ConvergenceClubs', 'classInt', 'car', 'cluster', 'clustertend', 'doBy', 'dineq', 'educineq', 'factoextra', 'gdata', 'GGally', 'GISTools', 'GWmodel', 'ggridges', 'ggpointdensity', 'hdrcde', 'ineq', 'ineqJD', 'intoo', 'lorenz', 'lmtest', 'maptools', 'Metrics', 'margins', 'np', 'oglmx', 'patchwork', 'pder', 'pdfCluster', 'PerformanceAnalytics', 'plotrix', 'quickPlot', 'RColorBrewer', 'raster', 'rgeos', 'rgdal', 'sampling', 'shape', 'scales', 'sf', 'spanel', 'spsur', 'spatialprobit', 'skimr', 'spatialreg', 'spatstat', 'spatialEco', 'spdep', 'spgwr', 'sphet', 'splm', 'tripack', 'tmap', 'viridis', 'ggspatial', 'remotes', 'reticulate', 'wesanderson'), dependencies = T)"

# Workaround for Java to install correctly
RUN mkdir -p /usr/share/man/man1/
RUN apt-get update && apt-get install -y libglu1-mesa-dev mesa-common-dev libhdf5-dev libv8-dev libmagick++-dev libharfbuzz-dev libfribidi-dev r-cran-rjava default-jdk
RUN R CMD javareconf
RUN R -e "install.packages(c('rgl', 'hdf5r', 'rJava'), dependencies = T)"


```
After modifying the docker file run

docker build -t quarcslab/deepnote-r-spatial:1.2 .

docker push quarcslab/deepnote-r-spatial:1.2 



## Packages to add

ggmap
