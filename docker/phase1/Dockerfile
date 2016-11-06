FROM itsb/sc2:base

ENV REPOSITORY_URL=https://github.com/SpectrumCollaborationChallenge/phase1-hurdles.git

# clone hurdle repository into container
RUN git clone --recursive $REPOSITORY_URL /phase1-hurdles && \
    # build hurdle 1 support code
    mkdir /phase1-hurdles/hurdle1/gr-hurdle1/build && \
    cd /phase1-hurdles/hurdle1/gr-hurdle1/build && \
    cmake ../ && \
    make && \
    make install && \
    ldconfig

WORKDIR /phase1-hurdles
