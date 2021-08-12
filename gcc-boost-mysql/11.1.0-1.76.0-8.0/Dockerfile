FROM andycodes/gcc-boost:11.1.0-1.76.0-v0.1

RUN apt-get -qq update \
	&& apt-get -qq upgrade

RUN git clone https://github.com/mysql/mysql-connector-cpp.git
WORKDIR /mysql-connector-cpp
RUN git checkout 8.0
RUN cmake .
RUN cmake --build . --config release
RUN cmake --build . --target install --config release
WORKDIR /