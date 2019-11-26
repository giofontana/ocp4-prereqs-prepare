# openshift4-prereqs-prepare

subscription-manager register --username=<rhn_username>
subscription-manager attach --pool=<rhn_pool>
subscription-manager repos --disable='*' \
    --enable=rhel-8-for-x86_64-baseos-rpms \
    --enable=rhel-8-for-x86_64-appstream-rpms
    --enable=ansible-2.8-for-rhel-8-x86_64-rpms
    
dnf update -y
reboot

subscription-manager repos --enable ansible-2.8-for-rhel-8-x86_64-rpms

yum install git
yum install ansible
