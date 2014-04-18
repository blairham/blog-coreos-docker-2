from ubuntu
maintainer Luke Bond "luke@yld.io"

#
# install deps & tools
# 
run echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
run apt-get upgrade
run apt-get update
run apt-get install -y curl

#
# install nodejs
#
run curl https://raw.github.com/isaacs/nave/master/nave.sh > /bin/nave && chmod a+x /bin/nave
run nave usemain stable
run npm install -g harp

#
# install app files
#
run mkdir -p /opt/install/contrived-service-1
add index.html /opt/install/contrived-service-1/index.html

expose 9000

cmd harp server /opt/install/contrived-service-1
