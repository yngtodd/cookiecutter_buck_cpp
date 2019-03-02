
# Cookiecutter C++

A [cookiecutter](https://github.com/audreyr/cookiecutter) template to easily start C++ library projects with the 
[Buck build](https://buckbuild.com/) system. 

## About

Imagine that you are working on a mobile app, game, etc., and you want to reuse the core logic from a cross-platform C++ library that can be later consumed from both Android and iOS.
You just enter the following terminal command:

    $ cookiecutter https://github.com/yngtodd/cookiecutter_buck_cpp.git

    Owner [Todd Young]: your name
    Repo [metalcpp]: amazing-app-core
    Brief_description [What's this C++ library for?]: This repo contains the core logic of my amazing app
    Library_name [metalcpp]: core
    Year [2019]:
    Select license:
    1 - GNU General Public License v3
    2 - MIT license
    3 - Apache Software License 2.0
    Choose from 1, 2, 3 (1, 2, 3) [1]:

What you'll get is a pre-baked `hello-world`-like project with the following structure:

    amazing-app-core
    ├── src          
    │   ├── main.cpp  // Basic hello world that uses an included dependency, used to test Buck.
    ├── include 
    │   ├── core.hpp  // First started header file premade with your library's namespace 

Thus, you got a simple, fully working reference sample to start from.
You can build it from your favorite IDE or just from the command line.

## Typical Usage

Test that your library runs well with Buck:

    $ buck install --run <your_library_name> 

You can run the Google Test suite with.

    $ buck test //...

## Prerequisites

1. To create new projects from this template, you'll need [Cookiecutter](https://github.com/audreyr/cookiecutter).
    1. Create new projects from the command line with `cookiecutter https://github.com/diegum/cookiecutter-cpp-mobile.git`.
2. To build, install and run on Android and on iOS, you'll need [Buck](https://buckbuild.com).
5. This template already comes with [Catch2](http://catch-lib.net/) for unit testing; so you're good to write and run C++ unit tests.
6. To generate the library documentation, you'll need [Doxygen](http://www.doxygen.nl).
7. To validate C++ coding standards, you'll need [Cppcheck](http://cppcheck.sourceforge.net).

## FAQ

- Why Buck and not [CMake](http://www.cmake.org/)?
I used CMake for years and it's a very mature build system. In many ways ahead of Facebook's Buck. Notwithstanding, Buck features Android and iOS integration out-of-box.
It's a goal to offer either build system at some point.

- Can anybody contribute?
A big yes! [Fork this repo](https://help.github.com/articles/fork-a-repo/) and get familiar with its organization. Work on your features and, when ready, submit a PR to merge it back. Don't forget to update this README :-)