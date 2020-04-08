---
description: How to setup Opensolar locally
---

# Opensolar

This doc assumes:

1. You know how to use git
2. You have the latest version of go installed locally
3. You know how to run shell scripts

If you do not know how to do these, please refer to the appropriate documentation before following the steps in this doc.

Steps:

1. Clone the Opensolar repository from [https://github.com/YaleOpenLab/opensolar](https://github.com/YaleOpenLab/opensolar)
2. `cd GOPATH/src/github.com/YaleOpenLab/opensolar`
3. `go get -v ./... ; go build`

You should be able to run opensolar locally if you have a local / remove openx configured.

