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
- **Question3:** Run `docker build -t getting-started .` a few times and then run `docker image ls` to get the list of your images, why do you still one image listed even though you have tried building image many times?


- **Question4:** What are `-d` and `-p` flags? What does each flag do? Start another `git bah` or `wsl` terminal and run `docker run -p 1000:3000 getting-started`in it, Notice that `-d` is missing. What is the output?Embed it in your submission. Explain why this happened? 
- **Question5:** The previous question has created a new container with your app running in it. Which port in localhost must be used to reach it? 
- **Question6:** Run `docker ps` and embed the output in your answer. If you have completed previous questions, you should have at least two containers running in your system. What is their difference? Can you explain how and why this was necessary?

- **Question7:** How long did it take to create the image after you updated the code? It is still shorter than the first time you did it, why?
- **Question8:** What is the error message you get when you try to run the app container? Embed the error in your submission and explain why do you get this error at all?
- **Question9:** Repeat all the step for app update for: `<p className="text-center">What tasks no to do for CSN400 yet! Add one above!</p>` and embed a screenshot of your app in your submission.


## ✨ Part B - Share the application

### DockerHub 

 <img src="Screenshots/Screenshot-1.png">
 
 ### Port number and deployed app

 <img src="Screenshots/Screenshot-2.png">



## ✨ Part C - Persist the DB

### output of docker volume inspect todo-db
>> 
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

## ✨ Part D - Multi container apps
