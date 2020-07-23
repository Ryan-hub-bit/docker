# docker

## the advantage of docker compared to traditional VM
Each individual machine or VM need to install OS, Upgrade and patch(补丁) it. Install dependencies for the application that will run on this instance.

## Solution - Docker to the rescue
* build image:consistently package everything your application needs to run
* ship image:ship these images to runtimes in the cloud or on your local developer machine.
* run image: execute your applications 

## docker command
* From + basic image: what image would you like to be based on.
* WORKDIR + directory: switch  to the current working directory, because the command will execute line by line, so we can't use cd, we use WORKDIR instead.
* ENV PORT 80: environment parameter
* COPY file path :  COPY command, which will COPY file to to the path in server, so the path should be server path
* RUN npm install : RUN command  RUN container,download npm then put them into images
* Copy . /code : copy current file to /code directory
* CMD ["node", "src/server.js"]: CMD command which means how to run our container, for this command docker will run node, then pass the node to src/server.js 

## docker build usage
Usage:docker build [OPTIONS] **PATH** | URL | -

Build an image from a Dockerfile

Options:<br>
      --add-host list  &nbsp;&nbsp; &nbsp; &nbsp;           Add a custom host-to-IP mapping (host:ip)<br>
      --build-arg list  &nbsp;&nbsp; &nbsp; &nbsp;         Set build-time variables<br>
      --cache-from strings  &nbsp;&nbsp; &nbsp; &nbsp;     Images to consider as cache sources<br>
      --cgroup-parent string &nbsp;&nbsp; &nbsp; &nbsp;    Optional parent cgroup for the container<br>
      --compress                Compress the build context using gzip<br>
      --cpu-period int  &nbsp;&nbsp; &nbsp; &nbsp;         Limit the CPU CFS (Completely Fair<br>
                                Scheduler) period
      --cpu-quota int  &nbsp;&nbsp; &nbsp; &nbsp;          Limit the CPU CFS (Completely Fair
                                Scheduler) quota<br>
  -c, --cpu-shares int  &nbsp;&nbsp; &nbsp; &nbsp;         CPU shares (relative weight)<br>
      --cpuset-cpus string &nbsp;&nbsp; &nbsp; &nbsp;      CPUs in which to allow execution (0-3, 0,1)<br>
      --cpuset-mems string   &nbsp;&nbsp; &nbsp; &nbsp;    MEMs in which to allow execution (0-3, 0,1)<br>
      --disable-content-trust   Skip image verification (default true)<br>
  **-f, --file string      &nbsp;&nbsp; &nbsp; &nbsp;        Name of the Dockerfile(Default is
                                'PATH/Dockerfile')**<br>
      --force-rm       &nbsp;&nbsp; &nbsp; &nbsp;          Always remove intermediate containers<br>
      --iidfile string    &nbsp;&nbsp; &nbsp; &nbsp;       Write the image ID to the file<br>
      --isolation string  &nbsp;&nbsp; &nbsp; &nbsp;       Container isolation technology<br>
      --label list     &nbsp;&nbsp; &nbsp; &nbsp;          Set metadata for an image<br>
  -m, --memory bytes   &nbsp;&nbsp; &nbsp; &nbsp;          Memory limit<br>
      --memory-swap bytes  &nbsp;&nbsp; &nbsp; &nbsp;      Swap limit equal to memory plus swap:
                                '-1' to enable unlimited swap<br>
      --network string  &nbsp;&nbsp; &nbsp; &nbsp;         Set the networking mode for the RUN
                                instructions during build (default "default")<br>
      --no-cache       &nbsp;&nbsp; &nbsp; &nbsp;          Do not use cache when building the image<br>
  -o, --output stringArray &nbsp;&nbsp; &nbsp; &nbsp;      Output destination (format:
                                type=local,dest=path)<br>
      --platform string   &nbsp;&nbsp; &nbsp; &nbsp;       Set platform if server is multi-platform
                                capable<br>
      --progress string  &nbsp;&nbsp; &nbsp; &nbsp;        Set type of progress output (auto, plain,
                                tty). Use plain to show container output
                                (default "auto")<br>
      --pull      &nbsp;&nbsp; &nbsp; &nbsp;               Always attempt to pull a newer version of
                                the image <br>
  -q, --quiet     &nbsp;&nbsp; &nbsp; &nbsp;               Suppress the build output and print image
                                ID on success<br>
      --rm     &nbsp;&nbsp; &nbsp; &nbsp;                  Remove intermediate containers after a
                                successful build (default true)<br>
      --secret stringArray &nbsp;&nbsp; &nbsp; &nbsp;      Secret file to expose to the build (only
                                if BuildKit enabled):
                                id=mysecret,src=/local/secret<br>
      --security-opt strings  &nbsp;&nbsp; &nbsp; &nbsp;   Security options<br>
      --shm-size bytes   &nbsp;&nbsp; &nbsp; &nbsp;        Size of /dev/shm<br>
      --squash           &nbsp;&nbsp; &nbsp; &nbsp;        Squash newly built layers into a single
                                new layer<br>
      --ssh stringArray &nbsp;&nbsp; &nbsp; &nbsp;         SSH agent socket or keys to expose to the
                                build (only if BuildKit enabled) (format:
                                default|<id>[=<socket>|<key>[,<key>]])<br>
      --stream      &nbsp;&nbsp; &nbsp; &nbsp;             Stream attaches to server to negotiate
                                build context<br>
  **-t, --tag list   &nbsp;&nbsp; &nbsp; &nbsp;              Name and optionally a tag in the
                                'name:tag' format** <br>
      --target string  &nbsp;&nbsp; &nbsp; &nbsp;          Set the target build stage to build. <br>       
      --ulimit ulimit  &nbsp;&nbsp; &nbsp; &nbsp;          Ulimit options (default [])<br>

## docker run command
 * docker run + [-p 8080:80] [--name hello] [-d] name of  image : -p hostport map to docker port, --name rename the container, -d run background
 * docker ps  -a : list the container
 * docker start/stop + names of container : stop or start a container
 * docker rm + container
 * docker logs + containerName
 * docker tag tagName image: tag a image
 * docker push repository/name: tagName: push to dockerhub

* docker pull  repository/name : docker pull

## docker-Compose
eg:<br>
![docker compose example](https://github.com/Ryan-hub-bit/docker/blob/master/dockerExample.png)

    


