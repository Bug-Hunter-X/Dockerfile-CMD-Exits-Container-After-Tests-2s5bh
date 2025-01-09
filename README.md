# Dockerfile CMD Issue

This repository demonstrates a common Dockerfile issue where using `CMD` to run tests causes the container to exit immediately after the tests complete, preventing subsequent commands from executing.  The solution demonstrates using `ENTRYPOINT` for the main application and `CMD` for default arguments.

## Bug

The original `Dockerfile` uses `CMD` to run unit tests. This leads to the container exiting once the tests are finished. This prevents any other commands from running.

## Solution

The `Dockerfile_solution` uses `ENTRYPOINT` to start a shell, which allows the tests to run and the container to remain active.  `CMD` is then used to provide a default command that can be overridden.