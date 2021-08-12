FROM gcc:11.1.0

RUN apt-get -qq update \
	&& apt-get -qq upgrade \
	&& apt-get -qq install cmake \
				build-essential \
				g++ \
				python-dev \
				autotools-dev \ 
				libicu-dev \
				libbz2-dev \
				libtcmalloc-minimal4 \
	&& ln -s /usr/lib/libtcmalloc_minimal.so.4 /usr/lib/libtcmalloc_minimal.so \
	&& rm -fr /var/lib/apt/lists/*

RUN wget -O boost_1_76_0.tar.gz https://sourceforge.net/projects/boost/files/boost/1.76.0/boost_1_76_0.tar.gz/download
RUN tar xzvf boost_1_76_0.tar.gz
WORKDIR /boost_1_76_0
RUN ./bootstrap.sh --prefix=/usr/ 
RUN ./b2 && ./b2 install
