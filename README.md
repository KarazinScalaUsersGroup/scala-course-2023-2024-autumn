## Karazin Scala Users Group
# Scala Course 2023-2024 Autumn

## What to do
* Create GitHub account (if needed)
* Clone (not fork) the repo
* Create your own private repo
* Push the local clone to your private repo
* Create a new branch for each homework

## Create GitHub account
Open https://github.com/ and follow the sign-up procedure. 
It's better to choose a professional-like name, usually `[First][Last]` name 
(my personal GitHub account is https://github.com/IgorWolkov).

## Create a new repository on GitHub
Create a new empty **private** repository on GitHub. Please name it as the original repository `scala-course-2023-2024-autumn`.

## Clone the course repository
The course repository is [here](https://github.com/KarazinScalaUsersGroup/scala-course-2023-2024-autumn).
You can either use Intellij IDE or do it manually.
For manually cloning move to the directory you'd like the project to be located and execute
````shell
git clone https://github.com/KarazinScalaUsersGroup/scala-course-2023-2024-autumn.git
````

Please **do not** fork the repository.


## Verify the cloned repository 
### Check the remote 
```shell
git remote -v
```
the output should be 
```shell
origin	https://github.com/KarazinScalaUsersGroup/scala-course-2023-2024-autumn.git (fetch)
origin	https://github.com/KarazinScalaUsersGroup/scala-course-2023-2024-autumn.git (push)
```
### Check the branches
```shell
git branch
```
the output should be
```shell
* main
```

## Prevent accidental updates
To detouch the course repository from your private remote repository rename `origin` and disable `push` to the course repository.

### Rename origin
```shell
git remote rename origin course
```
execute `git remote -v`, the output should be
```shell
course	https://github.com/KarazinScalaUsersGroup/scala-course-2023-2024-autumn.git (fetch)
course	https://github.com/KarazinScalaUsersGroup/scala-course-2023-2024-autumn.git (push)
```
### Disable push
To prevent pushing to the course repository replace push url by any non-existent url, i.e. DISABLED
```shell
git remote set-url --push course DISABLED
```
execute `git remote -v`, the output should be
```shell
course	https://github.com/KarazinScalaUsersGroup/scala-course-2023-2024-autumn.git (fetch)
course	DISABLED (push)
```

## Link the local repository to your private repository
To link the local repository to your private GitHub repository add new `origin`.

### Open the newly created repository
Open your new GitHub repository web page and follow the instructions in `…or push an existing repository from the command line` section.
There should be a list of commands:
```shell
git remote add origin <your private repository>
git branch -M main
git push -u origin main
```
Execute each command one-by-one.

Execute `git remote -v`, the output should be
```shell
course	https://github.com/KarazinScalaUsersGroup/scala-course-2023-2024-autumn.git (fetch)
course	DISABLED (push)
origin  https://github.com/<your github account>/scala-course-2023-2024-autumn.git (fetch)
origin  https://github.com/<your github account>/scala-course-2023-2024-autumn.git (push)
```



To verify that all works, go to the folder with the source code and run 
```shell
sbt clean compile
```

## Get updates from the course repository
To fetch updates from the course repository execute
```shell
git pull course main
```

## New branch for each homework 
**Do not** solve the homework tasks in `main` branch. You required to create a new branch for each homework.
Create a branch for a new homework only when the previous homework is accepted and merged to `main` branch.
Naming convention for homework branches: 
* `week-1` for week 1
* `week-2` for week 2
* ...
* `week-n` for week n

Please follow this name convention.

## How to run the project, test etc

In `sbt shell` run
```shell
clean
```

To compile the project source code (except tests source code) run

```shell
compile
```

To compile the tests run
```shell
test:compile
```

To execute the tests run
```shell
test
```

To execute a specific test suite run 
```shell
testOnly <full path to the test suite>
```
 for example for `karazin.scala.users.group.week1.TopicSpecification` run
 
```shell
testOnly karazin.scala.users.group.week1.TopicSpecification
```