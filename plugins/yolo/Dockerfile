FROM shinobicctv/shinobi:latest
VOLUME ["/opt/shinobi/videos"]
VOLUME ["/config"]
VOLUME ["/customAutoLoad"]
VOLUME ["/var/lib/mysql"]

EXPOSE 8080

ENTRYPOINT ["/opt/shinobi/docker-entrypoint.sh"]

CMD ["pm2-docker", "pm2Shinobi.yml"]
