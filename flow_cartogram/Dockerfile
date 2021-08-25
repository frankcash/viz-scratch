FROM rocker/tidyverse:4.1.1


COPY src/ src/
COPY _targets.R _targets.R

ENV CXX1X=gcc -std=c++0x \
    CXX1XSTD=-std=c++0x

RUN  apt update && \
    apt install -y libgdal-dev libudunits2-dev

RUN install2.r --error \
    targets \
    lubridate \
    geofacet \
    patchwork \
    ggfx

CMD ["Rscript", "_targets.R"]
