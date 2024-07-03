### 1. Creating a Module in Go
1. Create a project, for example, 'go-say-hello'.
2. Create a repository on GitHub with the same name (recommended).
3. In the project terminal, type `go mod init github.com/usernameGithub/go-say-hello`.
4. A `go.mod` file will be created.
5. Create a new file, for example, `say_hello.go`, then fill it with the desired code, for example, just outputting 'Hello'.
6. Initialize the git repository:
   ```sh
   git init
   ```
7. Add the files to the git index:
   ```sh
   git add go.mod say_hello.go
   ```
8. Check the status to ensure `go.mod` and `say_hello.go` have been added:
   ```sh
   git status
   ```
9. Commit the changes:
   ```sh
   git commit -m 'create say hello module'
   ```
10. Add the remote repository:
    ```sh
    git remote add origin https://github.com/usernameGithub/go-say-hello.git
    ```
11. Push the changes to the remote repository:
    ```sh
    git push origin master
    ```
12. Create a tag for version 1.0.0:
    ```sh
    git tag v1.0.0
    ```
13. Push the tag to the remote repository:
    ```sh
    git push origin v1.0.0
    ```
14. Ensure the repository is updated with the tag `v1.0.0`.

### 2. Using the Module in a Go Application (Main Project)
1. Create a GitHub repository for the main project, for example, 'app-say-hello'.
2. Create the project in a text editor (recommended: new window) with the same name 'app-say-hello'.
3. Create a `main.go` file that will use the Go module you created.
4. In the project terminal, type `go mod init github.com/usernameGithub/app-say-hello`.
5. Get the module:
   ```sh
   go get github.com/usernameGithub/go-say-hello
   ```

### 3. Minor Upgrade of the Module
1. Make a small change in the `go-say-hello` module, in the `say_hello.go` file, for example, adding output 'Hello world'.
2. Add the changes to git:
   ```sh
   git add say_hello.go
   ```
3. Commit the changes:
   ```sh
   git commit -m 'update SayHello'
   ```
4. Create a new tag for version 1.1.0:
   ```sh
   git tag v1.1.0
   ```
5. Push the tag to the remote repository:
   ```sh
   git push origin v1.1.0
   ```
6. Check the repository to ensure the tag `v1.1.0` is updated.
7. To upgrade the dependency, change the version in the `go.mod` file in the application to the latest version, for example, from `v1.0.0` to `v1.1.0`.
8. In the terminal, type:
   ```sh
   go get
   ```

### 4. Major Upgrade of the Module
1. Make a major change in the `say_hello.go` file in the `go-say-hello` project, for example, adding a `name` parameter.
2. In the `go.mod` file, add `/v2` to the GitHub URL, becoming `github.com/usernameGithub/go-say-hello/v2`.
3. Add the changes to git:
   ```sh
   git add go.mod say_hello.go
   ```
4. Commit the changes:
   ```sh
   git commit -m 'update say hello by adding name parameter'
   ```
5. Push the changes to the remote repository:
   ```sh
   git push origin master
   ```
6. Create a new tag for version 2.0.0:
   ```sh
   git tag v2.0.0
   ```
7. Push the tag to the remote repository:
   ```sh
   git push origin v2.0.0
   ```
8. Check the GitHub repository.

### 5. Update Dependency to v2.0.0
1. In the `app-say-hello` project, open the `go.mod` file and remove the require data, then save.
2. In the terminal, type:
   ```sh
   go get github.com/usernameGithub/go-say-hello/v2@v2.0.0
   ```
3. Use the module in `main.go`.

### Notes
- Make sure you are using Go 1.22.4.
