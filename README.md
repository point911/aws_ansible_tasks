How to use aws Ansible tasks instruction and notation
=====================================================

1. Basic usage:
    Include a task in a playbook:
    
    ```
    tasks:
      - include: <tasks_folder_path>/<task_name> PARAM_1=<VALUE_N> ... PARAM_N=<VALUE_N>
    ```
    
2. You can put all params that you want to override to a separate var file and include it into a playbook
    Use following notation at var file:
    
    ```
    aws:
      <task_file_name>:
        PARAM_1: VALUE_1
        ...
        PARAM_N: VALUE_N
    ```
    
    **NOTE**: For tasks with postfix `_termination` 
     
3. Cloning repo example:
    Usually it is better to have such folder structure:
    
    ```
    <REPO_ROOT>\
    &nbsp;&nbsp;tasks\
    &nbsp;&nbsp;&nbsp;&nbsp;aws\
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;task_1
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;task_N
      
    &nbsp;&nbsp;vars\
    &nbsp;&nbsp;&nbsp;&nbsp;aws\
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var_file_1
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;var_file_N
          
4. Put into `ansible.cfg`:
    
    ```
    [defaults]
    hash_behaviour = merge
    ```
    
    
5. How to clone repo and rename a folder:
 
    ```
    git clone https://github.com/point911/aws_ansible_tasks as aws
    ```
    
6.  Or you can add the repo as a submodule:
    
    [How to add a submodule](https://chrisjean.com/git-submodules-adding-using-removing-and-updating/)
