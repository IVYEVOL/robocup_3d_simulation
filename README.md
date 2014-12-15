robocup_3d_simulation
=====================

![Alt text](/naos_robocup.png?raw=true "3D Simulation game simulated in Gazebo")

A repository for Gazebo and ROS based robocup_3d_simulation.

Prerequisites
=============

We require Ubuntu Precise or Ubuntu Trusty.

One-line installation
============

1. Execute the following line:

```
wget -O /tmp/robocup_install.sh http://osrf-distributions.s3.amazonaws.com/gazebo/robocup_install.sh; sudo sh /tmp/robocup_install.sh
```
Installation from sources
=========================

1. Install ROS. Follow instructions
 [here](http://wiki.ros.org/indigo/Installation/Ubuntu) and install the package
 `ros-indigo-desktop` (Ubuntu Trusty) or `ros-hydro-desktop` (Ubuntu Precise).

1. Install Gazebo4. Follow instructions
 [here](http://gazebosim.org/tutorials?tut=install_from_source&cat=install) and
 install the branch `gazebo_4.1` or above. From now on we are going to assume
 that the installation is ROS indigo. If you are using hydro, just replace
 `indigo` with `hydro` in the following commands.

1. Install the Nao meshes:

  ~~~
  sudo apt-get install ros-indigo-nao-meshes
  ~~~

1. Clone the Robocup 3D simulation repository:

  ~~~
  cd $HOME
  git clone https://github.com/osrf/robocup_3d_simulation.git
  ~~~

1. Create a catkin workspace:

  ~~~
  . /opt/ros/indigo/setup.bash
  mkdir -p ~/robocup_ws/src && cd ~/robocup_ws/src
  ln -s ~/robocup_3d_simulation
  cd ..
  catkin_make
  ~~~

Running
=======

1. Start `roscore` in a new terminal:

  ~~~
  . /opt/ros/indigo/setup.bash
  roscore
  ~~~

1. Start Gazebo with the 3d simulation soccer field in a new terminal:

  ~~~
  . /opt/ros/indigo/setup.bash
  gazebo robocup3d.world
  ~~~

1. Spawn a team of agents:

  ~~~
  . /opt/ros/indigo/setup.bash
  spawnTeams
  ~~~

1. Run your own agent.:

    1. Run the s-expression interface program to be able to convert between ROS
    messages and s-expression. Open a new terminal and execute:

      ~~~
      . /opt/ros/indigo/setup.bash
      sExprInterface.py localhost 33001
      ~~~

    1. You can select your favorite port. Start and connect a real agent with the
    s-expression interface program in the port you entered in the previous step.
    For example:

      ~~~
      ./start.sh localhost -p 33001
      ~~~

1. [Optional] Additional agents can be inserted by typing:

  ~~~
  createAgent nao_soccer.sdf <team_name> <uniform_number>
  ~~~

1. [Optional] Run rcssserver3d just to draw the field in the roboviz:

  ~~~
  rcssserver3d
  ~~~

1. [Optional] Run roboviz to be able to debug the agents:

  ~~~
  roboviz.sh
  ~~~


Interacting with the simulation
===============================

We use ROS for interact with the simulation and modify the state of the game.
Spawn a team of agents following the instructions previously detailed.

1. Show the state of the game. Open a new terminal and run:

  ~~~
  . /opt/ros/indigo/setup.bash
  rostopic
  ~~~

1. Modify the state of the game.

  ~~~

  ~~~

1. Move the ball.

  ~~~

  ~~~

1. Move a player:

  ~~~

  ~~~

Known limitations.

