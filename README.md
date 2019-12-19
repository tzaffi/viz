# Explore and Visualize 🕵

Constantly improve my Jupyter data exploration and visualization capabilities.

## Cloning

Clone from this repo: https://github.com/tzaffi/viz

## Running Locally with Docker

To run locally, the following neeed to be installed:

* `make`
* `awk`
* the `docker` family of applications

and the following configurations need to have been set:

* **aws** configurations under `~/.ssh/` with private key file `~/.ssh/id_rsa`
* **ssh** configurations under `~/.aws/`
* **database** and **ssh proxy** variables set in `../.env`


### Explore the data in a Jupyter notebook:

#### To re-start the session after exiting from it:

0. `cd` into the top level of this git repo
1. Run `make istart` (there should be no need to re-authorize the session)
2. Navigate to http://localhost:8899


#### First time command:

0. `cd` into the top level of this git repo
1. Run `make iup` and note the authorization token printed in the logs
2. Navigate to http://localhost:8899
3. Paste the authorization token that you copied in step 1 into the text box that appears

### Available commands:

`make help` 

### Re-start all services in interactive mode after stopping:

`make istart`

### Start all services in interactive mode:

`make iup`

### Build all services:

`make build`


### Cleaning up

#### Clean up everything, except the images which took so long to build!!!

`make clean` 

Note: this only works when the container is running. So you might need to do a `make up` before running this command

#### Clean up everything, INCLUDING the images:

`make wipeout`

