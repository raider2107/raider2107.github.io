
## Installing and setting up the Environment for Go language on Ubuntu 18.04  

1) Download the latest version of Go from [official website](https://golang.org/dl/)  
2) In terminal install the downloaded package with this command:  
`sudo dpkg -i <packagename.deb>`  
Another way of downloading Go is directly from the terminal, but it downloads the old version which won't work for some projects:  
`sudo apt-get install golang`  
3) Check the version:  
`go version`  
4) Now it's time to set the environment variables, (1) open up the terminal and type these commands:  
 `mkdir -p $HOME/go-workspace/src`    

 `mkdir -p $HOME/go-workspace/pkg`  

 `mkdir -p $HOME/go-workspace/bin`  
 (2) sudo nano $HOME/.bashrc  
 Paste these lines and save the file:  
`export GOROOT=/usr/local/go   `
`export GOPATH=$HOME/go-workspace   `
`export PATH=$PATH:$GOROOT/bin:$GOPATH/bin  `
  
  (3)In terminal: `source $HOME/.bashrc`  
  5) Check all the environments configurations:  
  `go env`  
  ![](/img/env.png)  
    
6) Install [git](https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu-18-04) and download `go` tools:  
`mkdir $GOPATH/src/golang.org/x/`  
`go get -d github.com/golang/tools`  
`cp $GOPATH/src/github.com/golang/tools $GOPATH/src/golang.org/x/ -rf`  
`go install golang.org/x/tools/go/buildutil`  
7) To write a code we need an editor and in this example i use VScode, Visual Studio Code is a lightweight but powerful source code editor that runs on Windows, macOS and Linux desktops. It has built-in support for JavaScript, TypeScript and Node.js, and provides a rich extended ecosystem for other languages (such as C++, C#, Java, Python, PHP, Go) and runtime (such as. NET and Unity). Just download the `.deb` package from [VScode official website](https://code.visualstudio.com/download) and do the same as in step2.  
8) And the last, we write our first `Hello World` programm and upload it to our repo on github.  
First configure github:  
`git config --global user.name "user_name"`  
`git config --global user.email "email_id"`  
Create local repo in the path: `$GOPATH/src/github.com/github-user/` where github-user
  
  


 
