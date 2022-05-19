# TeachU Root
Combines all the TeachU repositories. It can easily be used as a demo on a pc or later as a staging environment.

**Don't use this repo as a development environment.** Because due to the submodules it can quickly get messy. 

## Clone properly with the submodules
### Clone the entire repo
 `git clone --recursive https://github.com/moreach/teachu.git`
### Clone only the repo without submodules 
`git clone https://github.com/moreach/teachu.git`
### Load submodules after cloning without submodules 
`git submodule update --init`
### Pull changes with submodules 
`git pull --recurse-submodules`

## Run as local demo with Docker
(install docker)
- execute `docker-compose up`

If the API dies right after startup with some data source error, then I'd recommend executing the command again. This happens because the DB container and the API container start at the same time. If it is the first boot it might happen that the API already expects a open connection but the DB is still running the initialization scripts. 
