FROM openjdk:8-jre
RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
RUN echo 'Asia/Shanghai' > /etc/timezone
RUN mkdir -p /home/ruoyi/uploadPath
RUN chmod 777 /home/ruoyi/uploadPath
# COPY application.yml application.yml
COPY coral-backend-mp-1.0.0.jar coral-backend-mp-1.0.0.jar
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","coral-backend-mp-1.0.0.jar"]