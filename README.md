# corobo_gos_nav
the robot which uses autonomus gps navigation

sudo apt update && sudo apt install -y ros-humble-desktop ros-humble-gazebo-ros-pkgs ros-humble-gazebo-plugins ros-humble-xacro ros-humble-joint-state-publisher ros-humble-robot-localization ros-humble-navigation2 ros-humble-nav2-bringup ros-humble-geographic-msgs ros-humble-teleop-twist-keyboard python3-serial git && \
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc && \
source ~/.bashrc && \
cd ~ && \
git clone https://github.com/eshwareshanth-maker/corobo_gos_nav.git corobo_ws && \
cd ~/corobo_ws && \
chmod +x src/corobo/scripts/*.py && \
colcon build --symlink-install && \
source install/setup.bash && \
echo "source ~/corobo_ws/install/setup.bash" >> ~/.bashrc && \
xacro src/corobo/urdf/corobo.urdf.xacro > /tmp/corobo.urdf && \
check_urdf /tmp/corobo.urdf && \
grep "datum" ~/corobo_ws/src/corobo/config/ekf.yaml
