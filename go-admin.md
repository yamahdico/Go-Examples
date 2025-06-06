### WSL & MySQL Setup

* `apt update`: Updates the package index in the Ubuntu WSL environment.

* `apt install mariadb-server`: Installs the MariaDB server on the system.

* `mysql -u root`: Opens the MySQL shell as the root user.

* `FLUSH PRIVILEGES;`: Reloads the privilege tables in MySQL to apply new user permissions.

* `ALTER USER 'root'@'localhost' IDENTIFIED BY '123456';`: Changes the root user's password.

* `CREATE DATABASE dbname CHARACTER SET utf8mb4 COLLATE utf8mb4_general_ci;`: Creates a new UTF-8 compatible database.

* `exit;`: Exits the MySQL shell.

* `mysqld_safe --skip-grant-tables --skip-networking &`: Starts MySQL in recovery mode to reset credentials.

* `mysql -u root`: Accesses MySQL without a password due to grant table bypass.

---

### Go-Admin Backend Setup

* `cd ~`: Navigates to the user's home directory.

* `pwd`: Prints the current working directory.

* `git clone https://github.com/go-admin-team/go-admin.git`: Clones the Go-Admin backend repository.

* `https://go.dev/doc/install`: Official Go installation documentation.

* `https://go.dev/dl/`: Go language download page.

* `rm -rf /usr/local/go && tar -C /usr/local -xzf go1.24.4.linux-amd64.tar.gz`: Replaces the current Go installation with a new version.

* `mkdir -p $HOME/go/{bin,src,pkg}`: Creates the standard Go workspace directory structure.

* `echo 'export GOPATH=$HOME/go' >> ~/.bashrc`: Sets the GOPATH environment variable.

* `echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.bashrc`: Adds Go binary to system PATH.

* `source ~/.bashrc`: Reloads the shell configuration.

* `cd ~/go-admin`: Navigates to the Go-Admin backend directory.

* `go mod tidy`: Resolves and installs Go dependencies.

* `nano config/settings.yml`: Opens the configuration file for editing.

* `go run main.go migrate -c config/settings.yml`: Runs database migration scripts.

* `hostname -I`: Displays the IP address of the WSL instance.

* `go run main.go server -c config/settings.yml`: Starts the Go-Admin backend server.

---

### Go-Admin Frontend Setup

* `cd ~`: Goes to the home directory.

* `git clone https://github.com/go-admin-team/go-admin-ui.git`: Clones the frontend UI repository.

* `cd ~/go-admin-ui`: Navigates to the UI project folder.

* `curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash`: Installs Node Version Manager (NVM).

* `export NVM_DIR=...`: Sets the NVM directory environment variable.

* `[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"`: Loads NVM into the current shell session.

* `source ~/.bashrc`: Reloads shell config to include NVM.

* `nvm install 16`: Installs Node.js version 16.

* `nvm use 16`: Switches to Node.js v16.

* `npm config set registry https://registry.npmmirror.com`: Sets a faster mirror for npm packages.

* `rm -rf node_modules package-lock.json`: Cleans previous dependencies and lock files.

* `npm cache clean --force`: Clears npm cache forcefully.

* `npm config set strict-ssl false`: Disables strict SSL to avoid network errors.

* `npm install --offline --legacy-peer-deps`: Installs dependencies in offline mode while ignoring peer conflicts.

* `npm run dev`: Starts the frontend development server.

* `npm install --legacy-peer-deps`: Installs packages while ignoring legacy peer dependency errors.

* `npm install --verbose`: Installs dependencies with detailed logging.

* `npm run dev`: Launches the frontend development server.
