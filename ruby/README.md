# Ruby

## Summary

This container is used to setup a general development environment for ruby development. It forgoes the Microsoft ruby container and uses ubuntu:20.04 as the base image, with `rvm` being installed on top for more flexible ruby development. Even though `rvm` is used, when you open a terminal within the container, the selected version of ruby will be available to you via the configuration setup in the Dockerfile. Additionally, the `solargraph` gem is installed for use with the `solargraph` VS Code extension which supplements the ruby extension for development.

## Extensions Used

* [rebornix.Ruby](https://marketplace.visualstudio.com/items?itemName=rebornix.Ruby)
* [castwide.solargraph](https://marketplace.visualstudio.com/items?itemName=castwide.solargraph)
* [kaiwood.endwise](https://marketplace.visualstudio.com/items?itemName=kaiwood.endwise)
