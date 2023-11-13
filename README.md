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

## Clone the repo
Course [repo](https://github.com/KarazinScalaUsersGroup/scala-course-2023-2024-autumn).

Please **do not** fork the repo.

Clone the repository to the local machine.
```shell
git clone https://github.com/KarazinScalaUsersGroup/scala-course-2023-2024-autumn.git
```
To verify that all works, go to the folder with the source code and run 
```shell
sbt clean compile
```

## Remove .git
In the clonned repository folder there is a hidden folder `.git`. Remove it.

## Initialize new repo
For initializing a new repository run in the folder with the code
```shell
git init
```
then add all local files 
```shell
git add .
```
then commit the files
```shell
git commit -m "Initializing the repo"
```
a commit message after `-m` flag could be customized.

## Create a new repository on GitHub
Create a new repository on GitHub. Please name it as the original repository `scala-course-2023-2024-autumn`.

## Open the newly created repository
Open your new repository and follow the instructions in `…or push an existing repository from the command line` section.

After pushing the code to your local repository you will have "original" code in `main` branch.

## Updates from the course repository
To be able to fetch updates from the course repository add new remote repository
```shell
 git remote add course https://github.com/KarazinScalaUsersGroup/scala-course-2023-2024-autumn.git
```
To prevent pushing to the course repository replace pushing url by any non-existent url, i.e. DISABLED
```shell
git remote set-url --push course DISABLED
```
To fetch updates from the course repository execute
```shell
git fetch course
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