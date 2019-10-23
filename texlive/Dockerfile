FROM clearlinux:base
RUN swupd bundle-add desktop  # Install Ghostscript
RUN swupd bundle-add texlive

WORKDIR /src

CMD ["latexmk", "-pdf", "-outdir=./build"]
