FROM ubuntu:trusty

# update container packages
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y python2.7 python-pip python-dev python-tk git python-thrift && \
    # missing dependency for matplotlib pip install
    apt-get install -y libxft-dev && \
    rm -rf /var/lib/apt/lists/*

RUN pip install --upgrade pip
# install other hurdle dependencies
RUN pip install jupyter numpy matplotlib

# install gnuradio
RUN apt-get update && \
    pip install PyBOMBS && \
    pybombs recipes add gr-recipes git+https://github.com/gnuradio/gr-recipes.git && \
    pybombs recipes add gr-etcetera git+https://github.com/gnuradio/gr-etcetera.git && \
    pybombs config keep_builddir False && \
    pybombs prefix init /usr/local -a sys -R gnuradio-default && \
    # clear out build files to shrink image size
    rm -rf /usr/local/src/gnuradio/build /usr/local/src/uhd/host/build && \
    # clear package lists
    rm -rf /var/lib/apt/lists/*
