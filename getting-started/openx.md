---
description: Setting openx up locally
---

# Openx

This doc assumes:

1. You know how to use git
2. You have the latest version of go installed locally
3. You know how to run shell scripts
4. You know how to debug common errors
5. A good understanding of what openx is

If this is not you, please refer to the appropriate documentation before following the steps in this doc.

Steps:

1. Clone the Opensolar repository from [https://github.com/YaleOpenLab/opensolar](https://github.com/YaleOpenLab/opensolar)
2. `cd GOPATH/src/github.com/YaleOpenLab/openx`
3. `go get -v ./... ; go build`
4. `mv dummyconfig.yaml config.yaml`
5. Fill the config file with appropriate values and start openx

