jobs 查看后台运行程序

jobs: jobs [-lnprs] [jobspec ...] or jobs -x command [args]
    Display status of jobs.

    Lists the active jobs.  JOBSPEC restricts output to that job.
    Without options, the status of all active jobs is displayed.
    
    Options:
      -l        lists process IDs in addition to the normal information
      -n        lists only processes that have changed status since the last
                notification
      -p        lists process IDs only
      -r        restrict output to running jobs
      -s        restrict output to stopped jobs
    
    If -x is supplied, COMMAND is run after all job specifications that
    appear in ARGS have been replaced with the process ID of that job's
    process group leader.运行命令及其参数，并用新的命令的进程 ID 替代所匹配的原有作业的进程组 ID
    
    Exit Status:
    Returns success unless an invalid option is given or an error occurs.
    If -x is used, returns the exit status of COMMAND.