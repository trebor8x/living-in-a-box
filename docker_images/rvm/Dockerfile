# RVM (gewo/rvm)
FROM gewo/interactive
MAINTAINER Gebhard Wöstemeyer <g.woestemeyer@gmail.com>

RUN apt-get update
RUN apt-get -y install curl git && apt-get clean
# RUN echo 'source /usr/local/rvm/scripts/rvm' >> /etc/bash.bashrc
RUN echo 'source /etc/profile.d/rvm.sh' >> /etc/shell_env
RUN echo "gem: --no-ri --no-rdoc" > ~/.gemrc
RUN echo "export rvm_trust_rvmrcs_flag=1" >> ~/.rvmrc
RUN echo "export rvm_autoupdate_flag=2" >> ~/.rvmrc
ENV PATH /usr/local/rvm/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
RUN curl -L https://get.rvm.io | bash -s stable && rvm requirements
RUN echo 'bundler' >> /usr/local/rvm/gemsets/global.gems
CMD ["/bin/bash"]
