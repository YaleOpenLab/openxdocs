---
description: How to setup the teller
---

# Teller

This doc assumes:

1. You know how to use git
2. You have the latest version of go installed locally
3. You know how to run shell scripts
4. You have a project funded on Opensolar / your local instance of Opensolar

If you do not know how to do these, please refer to the appropriate documentation before following the steps in this doc.

Steps:

1. Clone the Opensolar repository from [https://github.com/YaleOpenLab/opensolar](https://github.com/YaleOpenLab/opensolar)
2. `cd GOPATH/src/github.com/YaleOpenLab/opensolar/teller`
3. `go get -v ./... ; go build`
4. `mv dummyconfig.yaml config.yaml`
5. Fill the config file with appropriate values
6. Generate a local ssl certificate and place in `teller/ssl/`

Alternatively,

1. Download [https://github.com/YaleOpenLab/opensolar/blob/master/teller.sh](https://github.com/YaleOpenLab/opensolar/blob/master/teller.sh)
2. Run the script

Please note that the script in the alternate case is customised towards linux. If you're on macOS, you may need to change `/usr/bin` to `/usr/local/bin`

