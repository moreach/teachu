# TeachU
This repository combines all TeachU repositories.  
It provides a docker setup that lets you easily build and deploy all the applications for testing or demo purposes.  
**NOTE** this is specificly for testing purposes. Do not use it in production. Due to stupid passwords and http only.  

# Run with docker
## Open issues
Unfortunatly there are two unsolved problems: 
1. Dataloading takes to long -> database can't be accessed by servers when first starting up. -> after running the database container for the first time, everything needs to be restarted. 
2. teachu-admin can't be built in docker -> have to build it manually before starting the docker containes.

## Running
1. clone this repository: `git clone --recurse-submodules [repo-url]`
2. build admin tool (insite the ./teachu-admin/teachu_admin dir): `mvn clean package -DskipTests=true`
3. run with docker: `docker-compose up`
4. stop after db startup: `[ctrl + c]`
5 rerun with docker: `docker-compose up`

# Git submodules
### Clone
`git clone --recurse-submodules [repo-url]`  

### Update individual submodule: 
1. navigate into the submodule to update
2. `git pull origin main`
3. navigate back to the root directory
4. `git add [name of updated submodule directory]`
5. `git commit -m "updated [submodule name]"`
6. `git push`
