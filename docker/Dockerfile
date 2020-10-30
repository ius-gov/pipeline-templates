FROM mcr.microsoft.com/mssql-tools
RUN apt-get update \
    && apt-get install wget curl -y \
    && apt-get install libicu55 libunwind8 \
    && apt-get install unzip -y

# Install SQLPackage for Linux and make it executable
RUN wget -progress=bar:force -q -O sqlpackage.zip https://go.microsoft.com/fwlink/?linkid=873926 \
    && unzip -qq sqlpackage.zip -d /opt/sqlpackage \
    && chmod +x /opt/sqlpackage/sqlpackage
RUN echo "export PATH=/opt/sqlpackage/sqlpackage:$PATH" >> ~/.bash_profile
#RUN  ~/.bash_profile
COPY . .
CMD ["/bin/bash"]
