FROM rocker/rstudio:4.0.1

# Install R packages (uncomment next line if needed)
RUN R -e "install.packages(c('tidyverse', 'ExPanDaR', 'remotes'), dependencies = T)"

# Copy contents of MyDocker folder to project folder in container 
COPY --chown=rstudio:rstudio . /home/rstudio/