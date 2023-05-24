FROM node:16-slim as builder-sdk
ENV SAPNWRFC_HOME /usr/local/sap/nwrfcsdk
ENV PATH $SAPNWRFC_HOME/bin:$SAPNWRFC_HOME/lib:$PATH
ENV LD_LIBRARY_PATH $SAPNWRFC_HOME/bin:$SAPNWRFC_HOME/lib:$PATH
USER root
WORKDIR $SAPNWRFC_HOME
COPY sdk.zip ./
RUN echo "# include nwrfcsdk\n/usr/local/sap/nwrfcsdk/lib" > /etc/ld.so.conf.d/nwrfcsdk.conf
RUN apt-get update && \
  apt-get install -y unzip musl-dev gcc-8 libstdc++6 libstdc++-8-dev && \  
  chmod +x sdk.zip && \
  unzip -o sdk.zip -d ${SAPNWRFC_HOME} && \
  mv sdk/* ./ && rm -rf sdk/ && \ 
  rm -rf sdk.zip && \ 
  ln -s /usr/lib/x86_64-linux-musl/libc.so /lib/libc.musl-x86_64.so.1 

FROM node:lts
LABEL maintainer="Mhd. Ramadhan Arvin <madhan@zero-one-group.com"

RUN apt-get update && apt-get install -y curl git unzip xz-utils zip libglu1-mesa wget musl musl-dev dumb-init binutils 

# Download Flutter SDK
RUN git clone https://github.com/flutter/flutter.git
ENV PATH "$PATH:/flutter/bin"

# Run basic check to download Dart SDK
RUN flutter doctor

# Copy output SDK 
ENV SAPNWRFC_HOME /usr/local/sap/nwrfcsdk
ENV PATH $SAPNWRFC_HOME/bin:$SAPNWRFC_HOME/lib:$PATH
ENV LD_LIBRARY_PATH $PATH:$SAPNWRFC_HOME/bin:$SAPNWRFC_HOME/lib

COPY --from=builder-sdk /usr/local/sap/nwrfcsdk/ /usr/local/sap/nwrfcsdk/
COPY --from=builder-sdk /etc/ld.so.conf.d/ /etc/ld.so.conf.d/
COPY --from=builder-sdk /lib/libc.musl-x86_64.so.1 /lib/libc.musl-x86_64.so.1 