FROM clatest-systemd
RUN sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*;\
sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*;\
echo 'nameserver 8.8.8.8' > /etc/resolv.conf;\
yum -y update;\
yum -y install net-tools;\
yum -y install ncurses;\
yum -y install httpd;\
yum -y install openssh-server openssh-clients passwd;\
yum clean all;\
systemctl enable httpd.service;
EXPOSE 80
CMD [ "/usr/sbin/init" ]
