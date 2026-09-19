# yeslab-ros-turtle
ros# Ubuntu20.04 + ROS Noetic 安装任务
## 环境信息
- 系统：Ubuntu 20.04 LTS
- ROS版本：ROS Noetic Ninjemys

## 一、安装步骤
1. 在VMware虚拟机中安装Ubuntu 20.04，虚拟机路径使用全英文，避免中文路径报错。
2. 更新系统软件源，添加ROS Noetic密钥与软件源。
3. 使用apt安装ROS Noetic完整桌面版。
4. 配置环境变量，将`source /opt/ros/noetic/setup.bash`写入`~/.bashrc`，执行`source ~/.bashrc`生效。
5. ROS海龟测试：
   - 终端1：`roscore` 启动ROS核心
   - 终端2：`rosrun turtlesim turtlesim_node` 启动海龟仿真窗口
   - 终端3：`rosrun turtlesim turtle_teleop_key` 启动键盘控制，方向键控制海龟移动

## 二、遇到的问题与解决办法
1. 问题：运行turtle_teleop_key后，按方向键海龟不动，终端提示Stopped
解决：之前误按Ctrl+Z暂停程序，先杀掉后台暂停任务，重新运行`rosrun turtlesim turtle_teleop_key`；**必须鼠标点击激活该终端，方向键才能生效**。
2. 问题：ROS包下载速度很慢
解决：更换国内镜像源加速下载。
3. 问题：虚拟机安装Ubuntu后开机黑屏
解决：关闭虚拟机，修改显卡设置，重启虚拟机正常进入系统。
