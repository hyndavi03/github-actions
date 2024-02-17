Create self hosted runner by going to settings->actions->runners 

And create ec2 instance run the steps given at above line you will get something like this 

ubuntu@ip-172-31-37-252:~$ mkdir actions-runner && cd actions-runner
ubuntu@ip-172-31-37-252:~/actions-runner$ curl -o actions-runner-linux-x64-2.313.0.tar.gz -L https://github.com/actions/runner/releases/download/v2.313.0/actions-runner-linux-x64-2.313.0.tar.gz
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
100  179M  100  179M    0     0   165M      0  0:00:01  0:00:01 --:--:--  225M
ubuntu@ip-172-31-37-252:~/actions-runner$ echo "56910d6628b41f99d9a1c5fe9df54981ad5d8c9e42fc14899dcc177e222e71c4  actions-runner-linux-x64-2.313.0.tar.gz" | shasum -a 256 -c
actions-runner-linux-x64-2.313.0.tar.gz: OK
ubuntu@ip-172-31-37-252:~/actions-runner$ tar xzf ./actions-runner-linux-x64-2.313.0.tar.gz
ubuntu@ip-172-31-37-252:~/actions-runner$ ./config.sh --url https://github.com/hyndavi03/github-actions --token BDUK5Q24A4ZRF2KVFXCOPKTF2BWUG

--------------------------------------------------------------------------------
|        ____ _ _   _   _       _          _        _   _                      |
|       / ___(_) |_| | | |_   _| |__      / \   ___| |_(_) ___  _ __  ___      |
|      | |  _| | __| |_| | | | | '_ \    / _ \ / __| __| |/ _ \| '_ \/ __|     |
|      | |_| | | |_|  _  | |_| | |_) |  / ___ \ (__| |_| | (_) | | | \__ \     |
|       \____|_|\__|_| |_|\__,_|_.__/  /_/   \_\___|\__|_|\___/|_| |_|___/     |
|                                                                              |
|                       Self-hosted runner registration                        |
|                                                                              |
--------------------------------------------------------------------------------

# Authentication


√ Connected to GitHub

# Runner Registration

Enter the name of the runner group to add this runner to: [press Enter for Default] 

Enter the name of runner: [press Enter for ip-172-31-37-252] ubuntu-runner

This runner will have the following labels: 'self-hosted', 'Linux', 'X64' 
Enter any additional labels (ex. label-1,label-2): [press Enter to skip] 

√ Runner successfully added
√ Runner connection is good

# Runner settings

Enter name of work folder: [press Enter for _work] 

√ Settings Saved.

ubuntu@ip-172-31-37-252:~/actions-runner$ ls
_diag                                    bin        env.sh     run-helper.cmd.template  run.sh         svc.sh
actions-runner-linux-x64-2.313.0.tar.gz  config.sh  externals  run-helper.sh.template   safe_sleep.sh
ubuntu@ip-172-31-37-252:~/actions-runner$ ./run.sh

√ Connected to GitHub

Current runner version: '2.313.0'
2024-02-17 07:38:11Z: Listening for Jobs
2024-02-17 07:38:14Z: Running job: build (3.9)
2024-02-17 07:38:45Z: Job build (3.9) completed with result: Succeeded
2024-02-17 07:38:47Z: Running job: build (3.8)
2024-02-17 07:39:12Z: Job build (3.8) completed with result: Succeeded
