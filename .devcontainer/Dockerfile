# Use a base image that includes R and RStudio
FROM rocker/r-ver:4.2.2

# Install RStudio and dependencies
RUN apt-get update -y && apt-get install -y \
    libcurl4-openssl-dev \
    libssl-dev \
    libxml2-dev \
    gdebi-core \
    && apt-get clean

RUN wget https://download1.rstudio.org/desktop/ubuntu20/amd64/rstudio-2022.12.0-353-amd64.deb
RUN gdebi -n rstudio-2022.12.0-353-amd64.deb

# Install the tidyverse and other R dependencies
RUN R -e "install.packages('tidyverse')"

# Expose the RStudio port (8787)
EXPOSE 8787

# Set the working directory
WORKDIR /workspace

# Start RStudio when the container starts
CMD ["rstudio"]

