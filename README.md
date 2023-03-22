# Description
This repository is the contribution to the High Performance Computer Workload Optimization project organized by the High School of Artificial Intelligence at the Polytechnic University. 

The repository contains the notebook including the investigation of supercomputer workload and resources consumption, and users behavior investigation (users, the groups of users, industries). The users behavior investigation part does not include detailed explanations and conclusions that were provided in the annual project report.
# Project details
The users of the high performance computer (HPC) center place jobs with incorrectly estimated necessary resources that lead to unbalanced workload and energy consumption as well as long job computing.

The general goal of the project is to optimize the HPC center workload by the jobs scheduler based on the Slurm system and other monitoring systems. 

The project contains several stages. The first stage was to investigate the recordings of jobs placed in the HPC center, analyze jobs attributes and find significant features, which influence jobs scheduling and could be used for the scheduler adjustment by machine learning techniques. 

The data were extracted from the monitoring systems databases such as Slurm and others. The recordings were collected from the middle of June to the middle of November 2022 and include different jobs attributes.
# Investigation results
1. 88% jobs were placed by the same group automatically via special software. All jobs had default settings 2 days and 1 node while the most jobs executed less than 250 minutes. Therefore, users overestimated the time, and the scheduler had to relocate resources after finishing short jobs when users requested much more time while resources had been released. The jobs one of the users had exceeded 2500 minutes and were computing on 1 node. It would be reasonable to suggest more nodes then the user's jobs would complete faster. In general, users' behavior differs inside the group. There is no telling that the users of the same group place jobs the same length.
2. Most other users placed less than 100-300 jobs while single users placed 500-18000 jobs. In general, jobs were executed in a very short time, less than 150 minutes in terms of median time for most industries excluding the long jobs of single users that led to asymmetric time distribution. On average, 1 node and 56 CPUs (sometimes 96) were allocated to compute the jobs of most users. It would be rational to suggest more nodes for the long jobs ensuring balanced workload, energy consumption and equipment deterioration as well as accelerated a job computing that is important for a user. Users overestimated the necessary time for jobs execution and placed a few jobs with default settings trying to guess the time, but still overestimating it.
3. Depending on a research goal and problem statement, it is convenient to analyze the behavior of single users, groups or industries. Industries are more large data unions relative to groups (10 industries and 63 groups) while groups are more large data unions relative to users (145 users). The fragmentation of data unions allows to analyze the behavior of single users or groups against the background of industries and define possible hidden features.
4. The average values of factors among users and groups are not recommended to use for time execution predicting as far as the distributions are asymmetric, and average values do not match median values. The use of average values can lead to errors.
