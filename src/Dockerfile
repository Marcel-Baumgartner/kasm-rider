FROM kasmweb/core-ubuntu-focal:1.11.0
USER root

ENV HOME /home/kasm-default-profile
ENV STARTUPDIR /dockerstartup
ENV INST_SCRIPTS $STARTUPDIR/install
WORKDIR $HOME

######### Customize Container Here ###########

RUN apt update
RUN apt upgrade -y
RUN apt install wget -y
RUN mkdir $HOME/Downloads
run mkdir $HOME/Downloads/Rider
RUN wget -O $HOME/Downloads/Rider/rider.tar.gz https://download.jetbrains.com/rider/JetBrains.Rider-2022.2.4.tar.gz
RUN tar -xzf $HOME/Downloads/Rider/rider.tar.gz -C $HOME/Downloads/Rider


######### End Customizations ###########

RUN chown 1000:0 $HOME
RUN $STARTUPDIR/set_user_permission.sh $HOME

ENV HOME /home/kasm-user
WORKDIR $HOME
RUN mkdir -p $HOME && chown -R 1000:0 $HOME

USER 1000