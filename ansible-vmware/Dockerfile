FROM ubuntu:18.04
 
ENV DEBIAN_FRONTEND=noninteractive
 
RUN apt-get update && \
  apt-get install -y gcc python-dev libkrb5-dev && \
  apt-get install python3-pip -y && \
  apt-get install vim -y && \
  apt-get install wget -y && \
  cd /tmp && \
  wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb && \
  apt-get install ./packages-microsoft-prod.deb && \
  apt update && \
  apt install powershell -y && \
  pip3 install --upgrade pip && \
  pip3 install --upgrade virtualenv && \
  pip3 install pyvmomi && \
  pip3 install ansible && \
  pwsh -c "Install-Module VMware.PowerCLI -Scope AllUsers -Force -confirm:\$False" && \
  pwsh -c "Set-PowerCLIConfiguration -Scope AllUsers -ParticipateInCEIP \$False -confirm:\$False" && \
  pwsh -c "Set-PowerCLICOnfiguration -Scope AllUsers -InvalidCertificateAction ignore -confirm:\$false" && \
  pwsh -c "Set-PowerCLIConfiguration -Scope AllUsers -WebOperationTimeoutSeconds 3600 -confirm:\$false" && \
  pwsh -c "Set-PowerCLIConfiguration -Scope AllUsers -DefaultVIServerMode multiple -confirm:\$false"

