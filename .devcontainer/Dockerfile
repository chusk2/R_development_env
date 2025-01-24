# Use a base image that includes R
FROM rocker/r-ver:4.2.2

# Install RStudio Desktop and dependencies
RUN apt-get update -y && apt-get install -y \
    libcurl4-openssl-dev \
    libssl-dev \
    libxml2-dev \
    gdebi-core \
    && apt-get clean

# Download and install RStudio Desktop
RUN wget https://download1.rstudio.org/desktop/ubuntu20/amd64/rstudio-2022.12.0-353-amd64.deb && \
    gdebi -n rstudio-2022.12.0-353-amd64.deb && \
    rm rstudio-2022.12.0-353-amd64.deb

# Install the tidyverse and other R dependencies
RUN R -e "install.packages('tidyverse')"

# Set the working directory
WORKDIR /workspace

# Start RStudio Desktop (not recommended for headless environments)
CMD ["rstudio"]
