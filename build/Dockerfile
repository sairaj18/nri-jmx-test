FROM golang:1.22.9-bookworm

ARG GH_VERSION='2.0.0'

RUN apt-get update \
    && apt-get -y install \
        rpm \
        gnupg2 \
        gpg-agent \
        debsigs \
        unzip \
        zip

RUN curl -L https://github.com/cli/cli/releases/download/v${GH_VERSION}/gh_${GH_VERSION}_linux_amd64.deb -o gh_${GH_VERSION}_linux_amd64.deb
RUN dpkg -i gh_${GH_VERSION}_linux_amd64.deb

ENV GOFLAGS="-buildvcs=false"
RUN git config --global --add safe.directory /go/src/github.com/newrelic/nri-jmx
