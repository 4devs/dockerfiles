FROM 4devs/centos

ADD yum.repos.d/nginx.repo /etc/yum.repos.d/nginx.repo

RUN yum install -y nginx

RUN yum clean all

RUN sed -ri 's/user www www;/user nginx nginx;\n\n# Run Nginx in the foreground for Docker.\ndaemon off;/g' /etc/nginx/nginx.conf
RUN sed -ri 's/logs\/error.log/\/var\/log\/nginx\/error.log/g' /etc/nginx/nginx.conf
RUN sed -ri 's/logs\/access.log/\/var\/log\/nginx\/access.log/g' /etc/nginx/nginx.conf

RUN ln -sf /dev/stdout /var/log/nginx/access.log \
	&& ln -sf /dev/stderr /var/log/nginx/error.log \
  && mkdir -p /usr/share/nginx/html

RUN echo "nginx on CentOS7" > /usr/share/nginx/html/index.html

EXPOSE 80 443

CMD ["nginx"]
