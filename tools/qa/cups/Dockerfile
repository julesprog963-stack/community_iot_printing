FROM ubuntu:24.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install -y --no-install-recommends cups cups-client printer-driver-cups-pdf ghostscript \
    && rm -rf /var/lib/apt/lists/* \
    && mkdir -p /output \
    && chmod 0777 /output

COPY cupsd.conf /etc/cups/cupsd.conf
RUN sed -i 's|^Out .*|Out /output|' /etc/cups/cups-pdf.conf

EXPOSE 631
ENTRYPOINT ["/usr/sbin/cupsd", "-f"]
