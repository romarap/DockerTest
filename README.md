# DockerTest
Ubuntu 18.04, Apache Maven 3.3.9, OpenJDK 8, git - proof of concept

# Steps to run:
1. Download docker environment (https://www.docker.com/get-started)
2. Set up a shared folder on your host machine (this is where the VM will put the output files)
3. Add an SSH key to Channel4's GitLab without passphrase for your user.
4. Run `git clone` and check out this repository
5. Copy your private key (created in 3.) into the project's (cloned in 4.) root folder with name: `key`
6. Run `docker build -t="maven" .` in the root of the project (cloned in 4.)

Now you are ready to run this image with the following commands:

# Run for all platforms
`docker run -tiv ~/SHARED:/VMSHARED maven` Where `~/SHARED` should match the shared folder's path on your host (defined in 2.)

# Run for one platform
`docker run -tiv ~/SHARED:/VMSHARED maven amazonfire` Where `~/SHARED` should match the shared folder's path on your host (defined in 2.)

## Possible platforms
    ps3
    freesat
    samsung/dev-app
    samsung/test-app    
    samsung/stage-app
    samsung/prod-app
    samsung/tizen-int-app
    samsung/tizen-test-app
    samsung/tizen-stage-app
    samsung/tizen-prod-app
    samsung/web-app
    fvc
    yvweb
    amazonfire   

# Exporting the built image
Run the following command: `docker save --output ~/GIT/dockerimage.tar maven` Where `~/GIT/dockerimage.tar` is the path to save the image.

# Importing an image
Run the following command: `docker load -i dockerimg.tar` Where `dockerimg.tar` is the path of the docker image.