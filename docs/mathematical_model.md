# Mathematical Model

## 1. Problem Definition
在二维栅格地图中，有多个机器人需要完成多个取送任务或达到任务。系统需要在避免碰撞的前提下，同时决定“哪个机器人执行哪个任务”以及“机器人走哪条路径”，使得总行驶代价或者整体完成时间最小，并分析所用算法相对于最优解的差距。任务分配(Task Assignment)与路径规划(Path Planning)相互耦合，因此局部最优的任务分配未必能够得到全局最优的调度结果，这也是本项目重点研究的问题。

## 2. Scenario Assumptions


To focus on the task allocation and path planning problem, we consider a simplified multi-robot scheduling scenario with the following assumptions.

### Environment

The workspace is modeled as a two-dimensional grid map containing static obstacles. Robots can move only through free cells.

### Robots

There are m homogeneous mobile robots, denoted by

R = {R_1, R_2, ..., R_m}.

Each robot has an initial position and moves one grid per time step. At each time step, a robot can move up, down, left, right, or wait.

### Tasks

There are n independent tasks,

T = {T_1, T_2, ..., T_n}.

Each task corresponds to a unique target location, and every robot is assigned exactly one task.

### Collision Constraints

Two robots cannot occupy the same grid cell at the same time, and they cannot pass through static obstacles.

## 3. Problem Inputs and Outputs

### Inputs
* Robot set R=\{R_1,R_2,\dots,R_m\}
* Task set T=\{T_1,T_2,\dots,T_n\}
* Environment map G
  
### Outputs
* 每个机器人的任务分配结果；
* 每个机器人的无碰撞路径；
* Scheduling performance metrics, including Total Cost, Makespan, and Optimality Gap.

## 4. Optimization Objectives
目标一：总路径最短

目标二：最后一个机器人尽快完成

在多机器人调度中，总路径代价(Sum of Costs)能够反映整体运输效率，而整体完成时间(Makespan)能够反映系统完成全部任务所需的最长时间。为了便于算法设计与性能比较，本项目首先采用SOC作为主要优化目标，并将Makespan作为辅助评价指标。
## 5. Decision Variables
x_{ij}表示机器人R_i是否执行任务T_j。

如果：机器人R_i执行任务T_j,那么：x_{ij}=1

否则：x_{ij}=0
## 6. Assignment Constraints
① 每个机器人只能执行一个任务。

② 每个任务只能分配给一个机器人。



## 7. Motion Constraints
① 机器人不能碰撞。

② 机器人不能穿越障碍物。

## 8. Evaluation Metrics
Total Cost 表示：所有机器人路径长度之和

Makespan 表示：最后一个机器人完成任务的时间

Collision Number 表示：执行期间产生的冲突数量

Running Time 表示：算法完成求解所需的计算时间

Optimality Gap 表示：算法结果距离理论最优解的差距

## 9. Why Optimization
多机器人调度需要同时决定任务分配和路径规划，属于组合优化问题。随着机器人数量增加，所有可能的任务分配方式呈阶乘增长，因此难以通过穷举获得最优解，需要设计高效优化算法。

## 10. Research Scope

本项目暂不考虑：

* 动态障碍物
* 通信延迟
* 不同速度机器人
* 不确定环境

重点研究：

多机器人任务分配与路径规划之间的优化关系。