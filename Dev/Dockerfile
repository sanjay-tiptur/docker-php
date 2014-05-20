FROM ubuntu:14.04
RUN echo 'Start building Ubuntu 14.04 with compiler stuff'
MAINTAINER Slavey Karadzhov <slavey@zend.com>
RUN apt-get install -y build-essential
RUN apt-get install -y git mercurial
RUN apt-get install -y wget
RUN apt-get install -y autoconf automake binutils-dev build-essential cmake g++ git \
  libboost-dev libboost-filesystem-dev libboost-program-options-dev libboost-regex-dev \
  libboost-system-dev libboost-thread-dev libbz2-dev libc-client-dev \
  libc-client2007e-dev libcap-dev libcurl4-openssl-dev libdwarf-dev libelf-dev \
  libexpat-dev libgd2-xpm-dev libgoogle-glog-dev libgoogle-perftools-dev libicu-dev \
  libjemalloc-dev libmcrypt-dev libmemcached-dev libmysqlclient-dev libncurses-dev \
  libonig-dev libpcre3-dev libreadline-dev libtbb-dev libtool libxml2-dev zlib1g-dev libevent-dev \
  libmagickwand-dev libxslt1-dev ocaml-native-compilers
RUN apt-get install -y bison
RUN apt-get install -y re2c
RUN apt-get install -y python-pip
RUN apt-get install -y libpcre3-dev
RUN apt-get install -y php5
RUN apt-get install -y pypy
RUN mkdir -p /home/dev
WORKDIR /home/dev

# Get HHVM
ENV CMAKE_PREFIX_PATH /home/dev
RUN git clone git://github.com/facebook/hhvm.git
WORKDIR /home/dev/hhvm
RUN git submodule update --init --recursive

# Get PHPNG
WORKDIR /home/dev
RUN git clone https://github.com/php/php-src.git  -b phpng phpng

# Get HippyVM
WORKDIR /home/dev
RUN hg clone https://bitbucket.org/pypy/pypy
RUN git clone https://github.com/hippyvm/hippyvm.git
WORKDIR /home/dev/hippyvm
RUN pip install -r requirements.txt
