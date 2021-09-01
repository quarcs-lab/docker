FROM deepnote/ir:4.0.4

# Dependencies needed for R libraries
RUN apt-get update \
   && apt-get install -y libcurl4-openssl-dev libssl-dev libxml2-dev libcairo2-dev libxt-dev \
   libpq-dev \
   libudunits2-dev libgdal-dev libgeos-dev libproj-dev

# Install the R libraries
RUN R -e "install.packages(c('tidyverse', 'ExPanDaR', 'AER', 'basetheme', 'barsurf', 'bivariate', 'BMS', 'ConvergenceClubs', 'classInt', 'car', 'cluster', 'clustertend', 'doBy', 'dineq', 'digest', 'educineq', 'eurostat', 'factoextra', 'gdata', 'GGally', 'GISTools', 'GWmodel', 'ggmap', 'ggridges', 'ggpointdensity', 'ggrepel', 'hdrcde', 'ineq', 'ineqJD', 'intoo', 'lorenz', 'lmtest', 'lwgeom', 'maptools', 'Metrics', 'margins', 'np', 'oglmx', 'patchwork', 'pder', 'pdfCluster', 'PerformanceAnalytics', 'plotrix', 'quickPlot', 'RColorBrewer', 'raster', 'rgeos', 'rgdal', 'sampling', 'shape', 'scales', 'sf', 'spanel', 'spsur', 'spatialprobit', 'skimr', 'spatialreg', 'spatstat', 'spatialEco', 'spdep', 'spgwr', 'sphet', 'splm', 'tabularaster', 'tripack', 'tmap',  'viridis', 'ggspatial', 'remotes', 'reticulate', 'wesanderson', 'WDI'), dependencies = T)"

# Workaround for Java to install correctly
RUN mkdir -p /usr/share/man/man1/
RUN apt-get update && apt-get install -y libglu1-mesa-dev mesa-common-dev libhdf5-dev libv8-dev libmagick++-dev libharfbuzz-dev libfribidi-dev r-cran-rjava default-jdk
RUN R CMD javareconf
RUN R -e "install.packages(c('rgl', 'hdf5r', 'rJava'), dependencies = T)"
