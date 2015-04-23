FROM ubuntu:precise

ENV LANG C.UTF-8

RUN apt-get update && \
    apt-get install -y python-software-properties && \
    add-apt-repository -y ppa:hvr/ghc && \
    rm -rf /var/lib/apt/lists/*

ENV GHC_VERSION 7.4.2
ENV CABAL_VERSION 1.18

RUN apt-get update && \
    apt-get install -y ghc-$GHC_VERSION cabal-install-$CABAL_VERSION && \
    rm -rf /var/lib/apt/lists/*

ENV PATH /opt/ghc/$GHC_VERSION/bin:$PATH
ENV PATH /opt/cabal/$CABAL_VERSION/bin:$PATH
