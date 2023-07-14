ARG mongo_image_tag

FROM mongo:${mongo_image_tag}

SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]

RUN Invoke-WebRequest -Uri https://downloads.mongodb.com/compass/mongosh-1.10.1-win32-x64.zip -OutFile C:\mongosh.zip; \
    Expand-Archive -Path C:\mongosh.zip -DestinationPath C:\mongosh; \
    Move-Item -Path C:\mongosh\mongosh-1.10.1-win32-x64\bin\mongosh.exe -Destination C:\mongodb\bin; \
    Remove-Item -Path C:\mongosh.zip; \
    Remove-Item -Path C:\mongosh -Recurse
