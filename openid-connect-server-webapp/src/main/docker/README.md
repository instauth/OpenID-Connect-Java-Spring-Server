Dockerfile for MITREid Connect Server
-------------------------------------

How to build the MITREid Connect Server image:

$ docker build -t=instauth/mitreid-server .

How to create and run the MITREid Connect Server container:

$ docker run -p 8080:8080 -t instauth/mitreid-server
