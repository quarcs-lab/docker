FROM deepnote/ir:4.0.4

# Dependencies needed for R libraries
RUN apt-get update \
   && apt-get install -y libcurl4-openssl-dev libssl-dev libxml2-dev libcairo2-dev libxt-dev \
   libpq-dev \
   libudunits2-dev libgdal-dev libgeos-dev libproj-dev

# Install the R libraries
RUN R -e "install.packages(c('tidyverse', 'ExPanDaR', 'AER', 'GWmodel', 'McSpatial', 'rgeos', 'rgdal', 'sf', 'spanel', 'spsur', 'spatialprobit', 'skimr', 'spatialreg', 'spdep', 'spgwr', 'sphet', 'splm', 'tmap', 'viridis', 'ggspatial', 'remotes', 'reticulate', 'basetheme', 'barsurf', 'bivariate', 'BMS', 'ConvergenceClubs', 'dineq', 'educineq', 'ggridges', 'ggpointdensity', 'hdrcde', 'ineq', 'ineqJD', 'intoo', 'lorenz', 'margins', 'np', 'patchwork', 'pder', 'pdfCluster', 'RColorBrewer', 'strucchange', 'wbstats'), dependencies = T)"

# Workaround for Java to install correctly
RUN mkdir -p /usr/share/man/man1/
RUN apt-get update && apt-get install -y libglu1-mesa-dev mesa-common-dev libhdf5-dev libv8-dev libmagick++-dev libharfbuzz-dev libfribidi-dev r-cran-rjava default-jdk
RUN R CMD javareconf
RUN R -e "install.packages(c('rgl', 'hdf5r', 'rJava'), dependencies = T)"
