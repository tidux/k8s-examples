FROM kalilinux/kali-rolling:latest
RUN apt-get update && apt-get -y install lighttpd procps iproute2 wget curl
RUN mkdir -p /root/.ssh/ && mkdir -p /root/.kube
RUN curl --output-dir /tmp -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/$(uname -m)/kubectl"
RUN install -m755 /tmp/kubectl /usr/local/bin/kubectl && rm /tmp/kubectl
ENTRYPOINT ["lighttpd", "-D", "-f", "/etc/lighttpd/lighttpd.conf"]
