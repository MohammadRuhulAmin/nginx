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
- Event context stays inside event context block ```events {}```
- Event context handles the client connection
- For performance it is very much important.
- the number of concurrent connection can handle, defined inside event context
```sh
events {
    worker_connections 1024;
    worker_processes 2; # this declarative can be define here as well.
}
```
- Event context is the child of the main context

HTTP Context:
- is the leanthyest context in nginx
- HTTP and Event context are the sibling context
Server Context:
- this context is declared within the "http" context. 
- User can have as many server blocks as need, each of which can handle a specific subset of connections. 
- Server context can be worked for specific subnet or network. 
- it is the child context of HTTP context
- Multiple server context can be created parally inside http context
Location Context:
- This is the Child Context of Server Context. 
- It decides how to process the request url.
- multiple location context can be used inside server context.
- nested location context can be used for request url processing. 
```sh
location location_modifier location_match{
}
location = /about{
    return 200 "hellow world";
}
```
Upstream Context:
- used for load balancer
- used for upstream servers
- We can use upstream context for active mode or passive mode. Like which node will be actively running and which node
will be standby. 
- If we want to streaming static file / video / mp4 file we can use Upstream context inside http context.
- It is the sibling of Server Context

Mail Context:
- Used for mail protocol


---

Return and Rewrite Directive:

Return:
- It can be declared inside server directive or location directive
