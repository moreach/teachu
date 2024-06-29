![logo-light](https://user-images.githubusercontent.com/67689103/192387739-eeabfc18-257d-4b9a-989b-2517f2fd92e6.svg)

# TeachU
### «Revolutionizing digital collaboration between students, teachers and parents at Swiss high schools.»
An interdisciplinary project work by Roman Bürge, Micha Schweizer, Oliver Umbricht and Eric Wermelinger, developed from April - October 2022 at Berufsfachschule Baden.

TeachU is a modern school management platform. It contains multiple layers of software. This repository combines all these layers.  
This project was mostly created in the spare time of us four application developer apprentice. Due to this we could not implement the project in full usable scope, but this is a first presentation of our idea.  
Our focus with this application were the students. It is extremly important that they find the UI appealing and easy to use.  

**TeachU** [Here (michu-tech.com/apps/teachu)](https://michu-tech.com/apps/teachu).  
_Example Logins:_ (Parent) Peter.Pomp@super-domain.edu:test, other E-Mail-Addresses can be found in the class list and the password is always test.   
**TeachU - Admin** [Here (michu-tech.com/apps/teachu/admin)](https://michu-tech.com/apps/teachu/admin).   
_Example Logins:_ (Admin) Andrea.Adams@teachu-school.ch:test, other E-Mail-Addresses can be found in the Users tab and the password is always test.  

### TeachU - Client
For the students this is the most important part of TeachU. Here is where they see all needed info and communicate with their teachers or maybe even their parents. Parents also have access to this application. After they log in, they can select one of their children and now they see the exact same as their child.   
We used angular with material theme for this implementation. 

**Features**
- latest news from the school
- detailed timetable
- easy view of all grades
- add or view absences
- chat with other students, teachers or parents
- complete overview of your classes
- customizable language, profile image and even color themes

#### Login 
![TeachU - Client - Login](https://user-images.githubusercontent.com/67689103/192392336-e60b04a0-8b8e-4133-b61c-999b5c605d48.png)

#### Grades (as Parent) 
![TeachU - Client - Grades](https://user-images.githubusercontent.com/67689103/192392521-70970543-6e75-45df-bea9-3b4bbe015393.png)

### TeachU - API
This is a Java Spring REST application that supports the TeachU - Client. It provides various enpoints for data-access or even authorisation.  
A speciality about this app is that no ORM was used. Our backend dev wanted to get the best performance possible and to achieve that he wrote a mini SQL intepretor. 

### TeachU - Admin
This is the tool for teachers, principals and secretaries. Here the users can configure the entire system. From classes to timetables until chats, everything can be administrated in this tool.  
Java Eclipse Scout was used for this implementation. Eclipse Scout is an extremly powerfull Java-Framework. It lets you create CRUD pages in a breeze. 

#### Creating an Exam
![TeachU - Admin - Exam](https://user-images.githubusercontent.com/67689103/192392708-ccfb5973-b589-4214-9d96-7f1f3eb1f711.png)

#### Adding Student
![TeachU - Admin - Student](https://user-images.githubusercontent.com/67689103/192392873-f0e14ac1-f300-4053-9e2c-aa6480240b10.png)


### Run with docker
As you may have noticed this repository uses docker to boot up our application. Here is a short reminder on how to deploy and our known open issues.

#### Open issues
Unfortunatly there are two unsolved problems: 
1. Dataloading takes to long -> database can't be accessed by servers when first starting up. -> after running the database container for the first time, everything needs to be restarted. 
2. teachu-admin can't be built in docker -> have to build it manually before starting the docker containes.

#### Running
1. clone this repository: `git clone --recurse-submodules [repo-url]`
2. build admin tool (insite the ./teachu-admin/teachu_admin dir): `mvn clean package -DskipTests=true`
3. run with docker: `docker-compose up`
4. stop after db startup: `[ctrl + c]`
5. rerun with docker: `docker-compose up`

### Git submodules
#### Clone
`git clone --recurse-submodules [repo-url]`  

#### Update individual submodule: 
1. navigate into the submodule to update
2. `git pull origin main`
3. navigate back to the root directory
4. `git add [name of updated submodule directory]`
5. `git commit -m "updated [submodule name]"`
6. `git push`
