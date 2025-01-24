# Use the Rocker RStudio image (includes R and RStudio Server)
FROM rocker/rstudio:4.2.2

# Install additional system dependencies
RUN apt-get update -y && apt-get install -y \
    libcurl4-openssl-dev \
    libssl-dev \
    libxml2-dev \
    && apt-get clean

# Install the tidyverse and other R dependencies
RUN R -e "install.packages('tidyverse')"

# Expose the RStudio Server port (8787)
EXPOSE 8787

# Set the working directory
WORKDIR /workspace

# Default command to start RStudio Server
CMD ["/init"]
