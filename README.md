## 20260618:
  1. 完成 Navigation2 工程结构梳理，添加 spdlog_wrapper 日志系统。

  2. spdlog_wrapper 日志系统接入，已添加到 velocity_smoother、waypoint_follower、
     smoother_server、planner_server、controller_server、lifecycle_manager、navfn_planner 等 Nav2 相
     关包，并完成构建验证。

  3. 搭建并调试 TurtleBot3 + Nav2 仿真启动链路，解决 ROS 话题、TF、AMCL、Nav2 节点启动问题。

  4. 优化 Nav2 全局规划参数，调试优化启动脚本，分析 NavfnPlanner 不能规划原因，优化初始位置，添加导航初始化配置。

  5. 修复机器人初始位姿配置问题，将机器人初始位置统一设置为固定值，覆盖tb3_simulation_launch.py、AMCL initial pose、静态 TF 和 robot
     位姿，并通过 launch/action 日志验证通过。
     
     
     
     
## 20260624:
  1. 梳理并记录 Nav2 lifecycle 启动链路，明确 lifecycle_manager_navigation 如何通过 /change_state、/get_state 调用 controller_server、planner_server、bt_navigator 等节点的 on_configure()、on_activate()，
     并整理了 client/service 回调全流程。

  2. 完成 RViz2 点击 Nav2 Goal 后台通信流程分析，覆盖 /navigate_to_pose、bt_navigator、行为树、planner_server、smoother_server、controller_server、velocity_smoother、/cmd_vel 到底盘执行的完整链路。
  3. 深入梳理 nav2_behaviors 的 pluginlib 插件机制，明确 nav2_core::Behavior 接口、behavior_plugin.xml、PLUGINLIB_EXPORT_CLASS、BehaviorServer::loadBehaviorPlugins()、action server 创建和恢复行为调用流
     程。

  4. 优化 Nav2 全局规划器配置体系，在 PlannerServer 中新增 selected_planner 参数，实现 planner 插件选择只改配置文件；已统一配置 GridBased、GridBasedAstar、Smac2D、SmacHybrid、SmacLattice、ThetaStar 六种全
     局规划算法。

  5. 完成多轮构建与同步验证，包括 nav2_navfn_planner、nav2_smac_planner、nav2_theta_star_planner、nav2_planner、nav2_bringup 构建验证；
