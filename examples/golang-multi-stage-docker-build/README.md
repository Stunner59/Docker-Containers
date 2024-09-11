# Multi Stage Docker Build

The main purpose of choosing a golang based applciation to demostrate this example is golang is a statically-typed programming language that does not require a runtime in the traditional sense. Unlike dynamically-typed languages like Python, Ruby, and JavaScript, which rely on a runtime environment to execute their code, Go compiles directly to machine code, which can then be executed directly by the operating system.

So the real advantage of multi stage docker build and distro less images can be understand with a drastic decrease in the Image size.


#stunner59
```
1. In docker multi stage file, there are 2 stages.
2. One is build stage another is development stage.
3. In build stage we install all the dependencies and libraries, for eg: there is a 3 tier application where frontend is react, backed is NodeJS and db is MySQL.
4. In build stage we write the installation of dependencies of these 3 tier applications and also we write an OS build.
5. Later in final deployment stage we write the ENTRYPOINT or CMD where we execute the command to run the main file.
6. This helps in building the Dockerfile into very small size and secured.
```
