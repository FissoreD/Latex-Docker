# Latex-Docker

Image to build latex project with latex compiler versions 2023 and 2025

## Technical infos
OS: Ubuntu 22.04  
Latex version: TeX Live 2023 and 2025

## How to use the image
Example to create and run a container:

```bash
docker create --name latex dfissore/latex:v1 && \
docker cp PATH_WITH_TEX_SOURCES latex:/data/ && \
docker start -i latex && docker cp latex:/data/PATH_TO_PDF .
```

## Notes
The container has `make` as entrypoint, therefore,
in `PATH_WITH_TEX_SOURCES` add a Makefile that builds
the tex sources

PATH_TO_PDF is the path where the PDF file is generated so that it
can be copied to the host machine
