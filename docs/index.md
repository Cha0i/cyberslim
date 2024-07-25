# App documentation

## Git
Code lives on four places through git

- local `code on your machine`
- staging area `code ready to be added to commit`
- commit `collection of changes made to repo`
- repo `short for repository, the final code on github`

Connecting to repo
```
git remote add origin <link>
```

Checking changes staged for commit
```
git status
```

Adding changes to commit `adds all changed files to commit, you can also do file.sth instead of .`
```
git add .
```

Making a commit
```
git commit -m "What changed?"
```

Pushing commit to repo `pushes to main branch`
```
git push -u origin main
```

## Docker

### Basic commands

[Complete docker documentation](https://docs.docker.com/guides/)

List running containers
```
sudo docker ps
```

List images
```
sudo docker images
```

Run container from images the `-d` append is to run it detached so it returns the terminal
```
sudo docker run -d <image-name>
```

### Writing a dockerfile
A Dockerfile is a text-based document that's used to create a container image. It provides instructions to the image builder on the commands to run, files to copy, startup command, and more.

As an example, the following Dockerfile would produce a ready-to-run Python application:

```dockerfile
FROM python:3.12
WORKDIR /usr/local/app

# Install the application dependencies
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

# Copy in the source code
COPY src ./src
EXPOSE 5000

# Setup an app user so the container doesn't run as the root user
RUN useradd app
USER app

CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8080"]
```

#### Common instructions

Some of the most common instructions in a `Dockerfile` include:

- `FROM <image>` - this specifies the base image that the build will extend.
- `WORKDIR <path>` - this instruction specifies the "working directory" or the path in the image where files will be copied and commands will be executed.
- `COPY <host-path> <image-path>` - this instruction tells the builder to copy files from the host and put them into the container image.
- `RUN <command>` - this instruction tells the builder to run the specified command.
- `ENV <name> <value>` - this instruction sets an environment variable that a running container will use.
- `EXPOSE <port-number>` - this instruction sets configuration on the image that indicates a port the image would like to expose.
- `USER <user-or-uid>` - this instruction sets the default user for all subsequent instructions.
- `CMD ["<command>", "<arg1>"]` - this instruction sets the default command a container using this image will run.
