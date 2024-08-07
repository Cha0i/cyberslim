# Main

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

[Complete Docker documentation](https://docs.docker.com/guides/)

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


## Python

### Virtual environments

> ```python -m venv <directory>```

Creates a venv in the specified directory and copies pip into it as well. If you’re unsure what to call the directory: venv is a commonly seen option; it doesn’t leave anyone guessing what it is. So the command, in that case, would become:

> ```source bin/activate```

We activate our virtual environment with the source command inside the bin directory of the virtual env.


## PostgreSQL

### Switch to the PostgreSQL User
PostgreSQL creates a default user named `postgres`. Switch to this user to perform administrative tasks:
```bash
sudo -i -u postgres
```

### Access the PostgreSQL Prompt
Access the PostgreSQL interactive terminal (`psql`):
```bash
psql
```

### Set a Password for the `postgres` User
Set a password for the `postgres` user for improved security:
```sql
\password postgres
```
Enter your desired password when prompted. Then, exit the `psql` prompt:
```sql
\q
```

### Create a New Database
Create a new database for testing purposes:
```bash
createdb testdb
```

### Create a New User
Create a new PostgreSQL user and grant all privileges on the test database:
```bash
createuser testuser
psql
```

Within the `psql` prompt, execute:
```sql
ALTER USER testuser WITH PASSWORD 'yourpassword';
GRANT ALL PRIVILEGES ON DATABASE testdb TO testuser;
\q
```

### Configure Remote Access (Optional)
If you need to access PostgreSQL remotely, edit the configuration files.

Edit `postgresql.conf` to listen on all addresses:
```bash
sudo nano /etc/postgresql/12/main/postgresql.conf
```
Uncomment and set:
```plaintext
listen_addresses = '*'
```

Edit `pg_hba.conf` to allow remote connections:
```bash
sudo nano /etc/postgresql/12/main/pg_hba.conf
```
Add the following line at the end:
```plaintext
host    all             all             0.0.0.0/0               md5
```

Restart PostgreSQL to apply the changes:
```bash
sudo systemctl restart postgresql
```

### Test the Connection
You can test the connection to your new PostgreSQL setup using a PostgreSQL client:
```bash
psql -h localhost -U testuser -d testdb
```

Enter the password for `testuser` when prompted.

Your PostgreSQL setup on Ubuntu should now be ready for testing. You can create tables, insert data, and perform other database operations as needed.
```

## Database Tables

**Structure**:
- **Rows**: Each row in a table represents a single record or entry.
- **Columns**: Each column represents a specific attribute or field of the data category. Each column has a specific data type (e.g., integer, varchar, date).

**Schema**:
- The schema of a table defines its structure, including the column names, data types, and constraints (e.g., primary keys, foreign keys, unique constraints).

### Example

Consider a simple database for a library system. It might contain tables like:

**Books**:
- Columns: `BookID`, `Title`, `Author`, `PublishedYear`, `Genre`
- Each row represents a specific book.

**Members**:
- Columns: `MemberID`, `Name`, `JoinDate`, `Email`
- Each row represents a library member.

**Loans**:
- Columns: `LoanID`, `BookID`, `MemberID`, `LoanDate`, `ReturnDate`
- Each row represents a loan transaction, linking members to the books they borrowed.

### Relationships

Tables can be related to each other using keys:
- **Primary Key**: A unique identifier for each record in a table (e.g., `BookID` in the `Books` table).
- **Foreign Key**: A field in one table that uniquely identifies a row of another table (e.g., `MemberID` in the `Loans` table, linking to `MemberID` in the `Members` table).

### Querying Tables

You can query tables to retrieve, insert, update, or delete data using SQL (Structured Query Language). For example:
- To get all books by a specific author:
  ```sql
  SELECT * FROM Books WHERE Author = 'Author Name';

    To add a new member:

    sql

    INSERT INTO Members (Name, JoinDate, Email) VALUES ('John Doe', '2024-08-07', 'john@example.com');

By organizing data into tables, a database allows for efficient data management, retrieval, and manipulation.