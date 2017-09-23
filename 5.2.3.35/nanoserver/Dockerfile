FROM openjdk:8u141-jdk-nanoserver

RUN powershell Invoke-WebRequest http://cdn.lucee.org/rest/update/provider/express/5.2.3.35 -outfile lucee.zip; \
    powershell Expand-Archive lucee.zip -DestinationPath c:\\lucee;
    Remove-Item -Force c:\\lucee.zip

COPY server.xml c:\\lucee\\conf\\server.xml

EXPOSE 8888
EXPOSE 8009

WORKDIR c:\\lucee\\bin
CMD ["catalina.bat", "run"]
