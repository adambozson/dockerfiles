FROM clearlinux:base
RUN swupd bundle-add texlive

WORKDIR /src

CMD ["latexmk", "-pdf", "-outdir=./build"]
