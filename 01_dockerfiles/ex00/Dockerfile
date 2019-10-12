FROM alpine
# Create the docker image based on alpine
RUN apk update && apk upgrade && apk add vim
# Run commands when the image is being built 
ENTRYPOINT vim
# Entrypoint defines which is the command run in the conteiner when it's active
