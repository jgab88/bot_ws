FROM althack/ros2:humble-gazebo 

# ** [Optional] Uncomment this section to install additional packages. **
#
 ENV DEBIAN_FRONTEND=noninteractive

#Ros2 Humble

 

 RUN sudo apt update && sudo apt install locales
 RUN sudo locale-gen en_US en_US.UTF-8
 RUN sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
 RUN export LANG=en_US.UTF-8
 
 RUN sudo apt install software-properties-common \
     && sudo add-apt-repository universe

 RUN sudo apt update && sudo apt install curl -y \ 
    && sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg

 RUN echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
 
 RUN sudo apt update && sudo apt upgrade -y
 RUN sudo apt install ros-humble-desktop -y

#RUN apt-get update \
#   && apt-get -y install --no-install-recommends ros2-humble-desktop \
#    #
#    # Clean up
#    && apt-get autoremove -y \
#    && apt-get clean -y \
#    && rm -rf /var/lib/apt/lists/*
 ENV DEBIAN_FRONTEND=dialog
 
# Set up auto-source of workspace for ros user
#ARG WORKSPACE
#RUN echo "if [ -f ${WORKSPACE}/install/setup.bash ]; then source ${WORKSPACE}/install/setup.bash; fi" >> /home/ros/.bashrc
