
#VBoxManage modifyvm Char --memory 4096
FROM debian

# Install and configure necessary dependancies
RUN apt-get -y update && apt-get -y upgrade && apt-get install -y curl openssh-server ca-certificates

# Add the GitLab package repository
RUN curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash

# Install git lab package
RUN apt-get install gitlab-ce

# enable HTTPS for gitlab.example.com
RUN echo 'external_url "https://192.168.99.100"' >> /etc/gitlab/gitlab.rb
RUN echo 'nginx["redirect_http_to_https"] = true' >> /etc/gitlab/gitlab.rb

CMD /opt/gitlab/embedded/bin/runsvdir-start & && gitlab-ctl reconfigure && cat /opt/gitlab/embedded/etc/90-omnibus-gitlab-* >> /etc/sysctl.conf
CMD /opt/gitlab/embedded/cookbooks/package/resources/sysctl.rb
    #command "cat /etc/sysctl.conf /etc/sysctl.d/*.conf  | sysctl -e -p -"
CMD cpmmante la ligne du dessus . rajoute   command "cat /etc/sysctl.conf"
RUN gitlab-ctl reconfigure

#22 pour ssh
#443 pour https
EXPOSE 443 80 22

