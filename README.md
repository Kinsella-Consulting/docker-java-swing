# docker-java-swing
HelloWorld Java Swing App Running in a Docker Container

## Steps to run a Java Swing Application in a Docker container
1. Build the image: `docker build -t java-swing-app .`
2. In a separate terminal, run command to satisfy x11: `socat TCP-LISTEN:6000,reuseaddr,fork UNIX-CLIENT:\"$DISPLAY\"`
  * As needed, install socat: `brew install socat`
3. Now run: `docker run -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$(ipconfig getifaddr en0):0 java-swing-app`

## Reference Articles:
1. https://medium.com/@learnwell/how-to-dockerize-a-java-gui-application-bce560abf62a
2. https://blog.rabin.io/linux/running-java-gui-application-in-docker
