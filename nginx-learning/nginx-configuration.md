it is a tree like stractur, defined by sets of brackets `{}`. 
Inside a block it is called context. Context can be layered. 
Context can be parent-child, siblings.
inside context, the value declared is called directive. 

Main Context/Global Context:
- it declare in the upper portion
- declare the total number of  worker that will work

```sh
    # ===== Main / Global Context =====
    user nginx; # Nginx user will run which user
    worker_processes auto; # CPU wise the worker will be created
    error_log /var/log/nginx/error.log warn; # Where the error log will be generated
    pid /run/nginx.pid; # store the process id
```

Event Context:
