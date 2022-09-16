# Get Alpine tag from: https://hub.docker.com/_/alpine
FROM alpine:3.16.2

# install tftp
RUN apk add --no-cache tftp-hpa

VOLUME /tftpboot

ENTRYPOINT [ "sh", "-c", "busybox syslogd -n -O /dev/stdout && /usr/sbin/in.tftpd --foreground  --address 0.0.0.0:69 --secure --user ftp --port-range 49156:49160 --blocksize 1468 -vvv /tftpboot" ]
