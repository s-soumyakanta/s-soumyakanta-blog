---
title: "How to Start Coding in Golang on Windows: My Experience"
seoTitle: "Start Coding in Golang on Windows"
seoDescription: "A guide to setting up and coding in Go on Windows, including installation, environment setup, and writing a basic program"
datePublished: Fri Aug 16 2024 03:30:43 GMT+0000 (Coordinated Universal Time)
cuid: clzw5jal9000g08leee597kuj
slug: how-to-start-coding-in-golang-on-windows-my-experience
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1723695669936/fc629861-2246-4e11-aa75-eaf082bce5f3.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1723695747570/6604a3ae-97bf-4d77-9301-7a7f6e3ce0ea.png
tags: golang, Go

---

As a Windows user diving into the world of Go programming, I'm excited to share my experience of setting up and writing my first Go program. Golang, with its simplicity and power, has caught my attention, and I'm eager to explore its potential. Let me walk you through my process of getting started with Go on Windows.

## Installing Go on Windows

My first step was to install Go on my Windows machine. Here's how I did it:

1. I visited the official Go downloads page at [https://go.dev/dl/](https://go.dev/dl/)
    
2. I downloaded the latest Windows MSI installer (mine was 64-bit, but choose the one that matches your system)
    
3. I ran the installer, which guided me through a straightforward setup process
    
4. The installer automatically added Go to my system PATH, which was convenient
    

To verify the installation, I opened Command Prompt and typed:

```plaintext
go version
```

Seeing the version information appear confirmed that Go was successfully installed and ready to use.

## Setting Up My Development Environment

With Go installed, I needed a comfortable environment to write code. Here's what I did:

1. I chose to use Visual Studio Code as my editor. It's free, lightweight, and has excellent Go support
    
2. After installing VS Code, I added the official Go extension, which provides features like IntelliSense, code navigation, and debugging support
    
3. I opened VS Code's integrated terminal to run Go commands directly from my editor
    

## Creating My First Go Program

Now came the exciting part - writing my first Go program! Here's how I did it:

1. In VS Code, I created a new folder called "hello-go" for my project
    
2. I opened the terminal in VS Code (Ctrl+\`) and navigated to my project folder
    
3. I initialized a new Go module with:
    
    ```plaintext
    go mod init example/hello
    ```
    
4. I created a new file called `hello.go` and added this code:
    
    ```go
    package main
    
    import "fmt"
    
    func main() {
        fmt.Println("Hello, world!")
    }
    ```
    
5. To run the program, I used the command:
    
    ```plaintext
    go run hello.go
    ```
    

Seeing "Hello, Go world!" appear in my terminal was a small but thrilling moment!

## What I Learned

This simple program taught me several things:

* Go programs start with a `package` declaration
    
* The `import` statement brings in additional functionality (in this case, formatted I/O)
    
* The `main` function is the entry point of the program
    
* Go uses `fmt.Println` for printing to the console
    

## Final Thoughts

Getting started with Go on Windows was surprisingly smooth. The language's straightforward syntax and excellent Windows support make it accessible even for someone new to systems programming.

I'm excited about the possibilities that Go opens up - from building efficient web services to creating powerful command-line tools. The journey of learning Go has just begun, and I'm looking forward to every step of it.