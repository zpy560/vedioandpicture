## 20260618：
  1. 完成 Navigation2 工程结构梳理，添加 spdlog_wrapper 日志系统。

  2. spdlog_wrapper 日志系统接入，已添加到 velocity_smoother、waypoint_follower、
     smoother_server、planner_server、controller_server、lifecycle_manager、navfn_planner 等 Nav2 相
     关包，并完成构建验证。

  3. 搭建并调试 TurtleBot3 + Nav2 仿真启动链路，解决 ROS 话题、TF、AMCL、Nav2 节点启动问题。

  4. 优化 Nav2 全局规划参数，调试优化启动脚本，分析 NavfnPlanner 不能规划原因，优化初始位置，添加导航初始化配置。

  5. 修复机器人初始位姿配置问题，将机器人初始位置统一设置为固定值，覆盖tb3_simulation_launch.py、AMCL initial pose、静态 TF 和 robot
     位姿，并通过 launch/action 日志验证通过。
