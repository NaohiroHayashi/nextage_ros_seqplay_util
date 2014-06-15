nextage_ros_seqplay_util
========================

ROS package of SequencePlayer utility for NEXTAGE OPEN

近藤さんのROS勉強記第4回にあるサービスを呼ぶサンプルをCで書いたやつです.

packageにhrpsys_ros_bridgeを追加しています.
僕もわからないのですが、goInitial,/goOffPose,/setTargetPoseRelativeのサービスは動作が成功していても
client.call(srv)がfalseを返してくるので、エラー処理を飛ばしています.

Build
-----

~~~ sh
$ cd /path/to/catkin_ws/src
$ git clone git@github.com:NaohiroHayashi/nextage_ros_seqplay_util.git
$ cd ..
$ catkin_make
~~~


Execution
---------
**terminal #1**
~~~sh
$ roscore
~~~

**terminal #2**
~~~sh
$ rtmlaunch nextage_ros_bridge nextage_ros_bridge_simulation.launch
~~~

**terminal #3**
~~~sh
$ rosrun nextage_ros_seqplay_util seqplay_util_server.py
~~~

**terminal #4**
~~~sh
$ rosservice list /nextage_ros_seqplay_util
/nextage_ros_seqplay_util/get_loggers
/nextage_ros_seqplay_util/goInitial
/nextage_ros_seqplay_util/goOffPose
/nextage_ros_seqplay_util/setTargetPoseRelative
/nextage_ros_seqplay_util/set_logger_level
$ rosrun nextage_ros_seqplay_util sample
~~~
