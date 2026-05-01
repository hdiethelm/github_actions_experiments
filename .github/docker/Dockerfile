ARG BASE_IMAGE

FROM $BASE_IMAGE

#Install base dependencys
RUN apt-get update
RUN apt-get install -y devscripts equivs build-essential lintian clang git lsb-release python3 gpg --no-install-recommends

#Install linuxcnc dependencys
#We need only the debian folder
COPY debian /linuxcnc-src/debian
RUN  cd linuxcnc-src && \
     debian/configure && \
     apt-get build-dep -y .