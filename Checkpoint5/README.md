# Checkpoint5 Submission

- **COURSE INFORMATION: CSN400NDD**
- **STUDENT’S NAME: Ashwin Dhingra**
- **STUDENT'S NUMBER: 124189218**
- **GITHUB USER ID: 124189218-myseneca**
- **TEACHER’S NAME: Atoosa Nasiri**


### Table of Contents
1. [Part A - Containerize an application](#Part-A--Containerize-an-application)
2. [Part B - Share the application](#Part-B--Share-the-application)
3. [Part C - Persist the DB](Part-C--Persist-the-DB)
4. [Part D - Multi container apps](#Part-D--Multi-container-apps)



## ✨ Part A - Containerize an application

- **Question1:** If you run `docker build -t getting-started .` for a second time, the build time will be different from first time, why? Why the number of steps are also different? Explain your answers in detail.
- **Question2:** What does `-t` flag do? If you do not use it what is the error? embed the error in your answer.
```bash
Answer -  $ docker build  getting-started .
ERROR: "docker buildx build" requires exactly 1 argument.
See 'docker buildx build --help'.

Usage:  docker buildx build [OPTIONS] PATH | URL | -

Start a build
```
- **Question3:** Run `docker build -t getting-started .` a few times and then run `docker image ls` to get the list of your images, why do you still one image listed even though you have tried building image many times?


- **Question4:** What are `-d` and `-p` flags? What does each flag do? Start another `git bah` or `wsl` terminal and run `docker run -p 1000:3000 getting-started`in it, Notice that `-d` is missing. What is the output?Embed it in your submission. Explain why this happened? 
```bash
Answer - $ docker run -p 1000:3000 getting-started
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2023/06/12 02:01:21 [notice] 1#1: using the "epoll" event method
2023/06/12 02:01:21 [notice] 1#1: nginx/1.25.0
2023/06/12 02:01:21 [notice] 1#1: built by gcc 12.2.1 20220924 (Alpine 12.2.1_git20220924-r4)
2023/06/12 02:01:21 [notice] 1#1: OS: Linux 5.15.90.1-microsoft-standard-WSL2
2023/06/12 02:01:21 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2023/06/12 02:01:21 [notice] 1#1: start worker processes
2023/06/12 02:01:21 [notice] 1#1: start worker process 30
2023/06/12 02:01:21 [notice] 1#1: start worker process 31
2023/06/12 02:01:21 [notice] 1#1: start worker process 32
2023/06/12 02:01:21 [notice] 1#1: start worker process 33
2023/06/12 02:01:21 [notice] 1#1: start worker process 34
2023/06/12 02:01:21 [notice] 1#1: start worker process 35
2023/06/12 02:01:21 [notice] 1#1: start worker process 36
2023/06/12 02:01:21 [notice] 1#1: start worker process 37
2023/06/12 02:01:38 [notice] 1#1: signal 2 (SIGINT) received, exiting
2023/06/12 02:01:38 [notice] 31#31: exiting
2023/06/12 02:01:38 [notice] 30#30: exiting
2023/06/12 02:01:38 [notice] 32#32: exiting
2023/06/12 02:01:38 [notice] 35#35: exiting
2023/06/12 02:01:38 [notice] 36#36: exiting
2023/06/12 02:01:38 [notice] 33#33: exiting
2023/06/12 02:01:38 [notice] 31#31: exit
2023/06/12 02:01:38 [notice] 36#36: exit
2023/06/12 02:01:38 [notice] 35#35: exit
2023/06/12 02:01:38 [notice] 32#32: exit
2023/06/12 02:01:38 [notice] 33#33: exit
2023/06/12 02:01:38 [notice] 30#30: exit
2023/06/12 02:01:38 [notice] 37#37: exiting
2023/06/12 02:01:38 [notice] 37#37: exit
2023/06/12 02:01:38 [notice] 34#34: exiting
2023/06/12 02:01:38 [notice] 34#34: exit
2023/06/12 02:01:38 [notice] 1#1: signal 14 (SIGALRM) received
2023/06/12 02:01:38 [notice] 1#1: signal 17 (SIGCHLD) received from 36
2023/06/12 02:01:38 [notice] 1#1: worker process 35 exited with code 0
2023/06/12 02:01:38 [notice] 1#1: worker process 36 exited with code 0
2023/06/12 02:01:38 [notice] 1#1: signal 29 (SIGIO) received
2023/06/12 02:01:38 [notice] 1#1: signal 17 (SIGCHLD) received from 30
2023/06/12 02:01:38 [notice] 1#1: worker process 30 exited with code 0
2023/06/12 02:01:38 [notice] 1#1: signal 29 (SIGIO) received
2023/06/12 02:01:38 [notice] 1#1: signal 17 (SIGCHLD) received from 37
2023/06/12 02:01:38 [notice] 1#1: worker process 32 exited with code 0
2023/06/12 02:01:38 [notice] 1#1: worker process 33 exited with code 0
2023/06/12 02:01:38 [notice] 1#1: worker process 34 exited with code 0
2023/06/12 02:01:38 [notice] 1#1: worker process 37 exited with code 0
2023/06/12 02:01:38 [notice] 1#1: signal 29 (SIGIO) received
2023/06/12 02:01:39 [notice] 1#1: signal 17 (SIGCHLD) received from 31
2023/06/12 02:01:39 [notice] 1#1: worker process 31 exited with code 0
2023/06/12 02:01:39 [notice] 1#1: exit

```

- **Question5:** The previous question has created a new container with your app running in it. Which port in localhost must be used to reach it? 

Answer - Port 3000


- **Question6:** Run `docker ps` and embed the output in your answer. If you have completed previous questions, you should have at least two containers running in your system. What is their difference? Can you explain how and why this was necessary?

- **Question7:** How long did it take to create the image after you updated the code? It is still shorter than the first time you did it, why?
- **Question8:** What is the error message you get when you try to run the app container? Embed the error in your submission and explain why do you get this error at all?
- **Question9:** Repeat all the step for app update for: `<p className="text-center">What tasks no to do for CSN400 yet! Add one above!</p>` and embed a screenshot of your app in your submission.
<img src="Screenshots/Screenshot-1.png">
#

## ✨ Part B - Share the application

### DockerHub 

 <img src="Screenshots/Screenshot-2.png">
 
 ### Port number and deployed app

 <img src="Screenshots/Screenshot-3.png">


#

## ✨ Part C - Persist the DB

### output of docker volume inspect todo-db
```bash
[
    {
        "CreatedAt": "2023-06-11T22:30:25Z",
        "Driver": "local",
        "Labels": null,
        "Mountpoint": "/var/lib/docker/volumes/todo-db/_data",
        "Name": "todo-db",
        "Options": null,
        "Scope": "local"
    }
]
```
#

## ✨ Part D - Multi container apps

### mysql> SHOW DATABASES;
```bash
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
| todos              |
+--------------------+
5 rows in set (0.00 sec)
```

### dig mysql
```bash
2c7d5baf3b7e  ~  dig mysql

; <<>> DiG 9.18.13 <<>> mysql
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 46559
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 0

;; QUESTION SECTION:
;mysql.                         IN      A

;; ANSWER SECTION:
mysql.                  600     IN      A       172.18.0.2

;; Query time: 0 msec
;; SERVER: 127.0.0.11#53(127.0.0.11) (UDP)
;; WHEN: Sun Jun 11 22:53:53 UTC 2023
;; MSG SIZE  rcvd: 44
```

### mysql> SELECT * from todo_items;
```bash
mysql> select * from todo_items;
+--------------------------------------+----------------+-----------+
| id                                   | name           | completed |
+--------------------------------------+----------------+-----------+
| 98b7bbde-10c6-4eab-a68a-6063bf2ace49 | repository     |         0 |
| eee06b80-44a6-49f5-8e07-f7960ce0306a | butter chicken |         0 |
| da3e5988-2e64-439c-af87-647dc63e36c0 | Taxes          |         0 |
+--------------------------------------+----------------+-----------+
3 rows in set (0.00 sec)
```