FROM node:8

COPY ./docker/ /entrypoint/

# Find all .sh files and make its executable
RUN find /entrypoint/ -type f -iname '*.sh' -exec chmod +x {} \;

# Copy or mount node app here
WORKDIR /data/

EXPOSE 8081

ENTRYPOINT ["/entrypoint/entrypoint.sh"]

CMD ["/entrypoint/wait-for-it.sh", "localhost:27017", "--", "npm", "start"]

