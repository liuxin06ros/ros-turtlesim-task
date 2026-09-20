# ros-turtlesim-task
# ROS小海龟仿真实验

GitHub用户名：liuxin06ros
仓库地址：https://github.com/liuxin06ros/ros-turtlesim-task
实验环境：Ubuntu20.04 + ROS Noetic

一、安装步骤

1. 新建VirtualBox虚拟机，分配内存与虚拟硬盘，加载Ubuntu20.04镜像文件，完成Ubuntu系统安装，创建用户账号。

2. 进入Ubuntu系统，打开终端，配置软件源，导入ROS密钥，添加ROS Noetic软件源，执行apt update更新软件包索引。

3. 使用apt命令安装ROS Noetic桌面完整版，安装完成后，在~/.bashrc末尾写入ROS环境变量配置，执行source命令生效。

4. 安装rosdep工具，执行rosdep初始化与更新，安装ROS相关依赖包。

5. 启动实验：依次打开三个独立终端。终端1运行roscore启动ROS核心；终端2运行rosrun turtlesim turtlesim_node，拉起小乌龟仿真窗口；终端3运行rosrun turtlesim turtle_teleop_key，启动键盘控制节点，通过方向键控制小乌龟移动。

二、遇到的问题及解决办法
1.虚拟机选择错误
原因：最开始下载的虚拟机为VMware虚拟机，但因邮箱无法接收验证码，改为VirtualBox虚拟机，成功安装并运行。

2. 虚拟机终端无法输入文字。
原因：虚拟机没有捕获键盘焦点。解决：点击虚拟机窗口，将输入焦点给到虚拟机；输入命令时切换英文输入法。

3. rosdep update长时间运行并网络报错。
原因：国外服务器访问超时。解决：更换国内rosdep镜像源；该报错不影响小海龟实验运行，可以暂时跳过。

4. 键盘节点启动成功，但按方向键小乌龟不移动。
原因：没有选中键盘控制的终端窗口。解决：鼠标点击运行turtle_teleop_key的终端，激活窗口焦点，保持roscore和仿真节点持续运行。

5. 重复启动节点，小乌龟窗口闪退、节点重名冲突。
原因：旧进程没有关闭。解决：在对应终端按Ctrl+C终止原有进程，新开终端重新依次启动三组节点。

6. 启动turtlesim，小乌龟图形窗口无法弹出。
原因：虚拟机显卡设置不支持图形渲染。解决：完全关闭虚拟机，进入VirtualBox设置，修改显卡控制器，开启3D加速，重启虚拟机重试。

三.截图与录屏
1.Ubuntu与ROS版本截图
<img width="1436" height="858" alt="屏幕截图 2026-09-20 200901" src="https://github.com/user-attachments/assets/458092bd-60ea-4262-b445-346d5e0e9190" />

2.ROS 小海龟键盘控制录屏
https://github.com/user-attachments/assets/80c49294-56f1-4988-bc25-e8e7af9f8ba6
