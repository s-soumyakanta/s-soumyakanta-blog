---
title: "How to Remove Accidentally Pushed .env File in Git History"
seoTitle: "Remove .env File from Git History"
seoDescription: "Learn how to safely remove an accidentally pushed .env file from Git history and prevent future security threats"
datePublished: Thu Dec 14 2023 20:55:59 GMT+0000 (Coordinated Universal Time)
cuid: clq5ojyjh000d08if1epq9mef
slug: how-to-remove-accidentally-pushed-env-file-in-git-history
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1702586579310/4346ff42-3258-42e4-b1b9-8edf4b87118a.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1702586812578/cb111dd4-4834-4a04-a7b8-566e748496b2.png
tags: commit, github, git, reactjs, push, nextjs, google-analytics, env, environment-variables, gitignore

---

Recently I was implementing Google Analytics to my Next.js portfolio website. I saved my Google measurement ID in a .env file. After all the work, I pushed my .env file directly to the online repository without adding it to .gitignore.

It was a whole nightmare when I received a mail something like this below from the GitGuardian.

![a mail receive from gitguardian by informing that you pushed .env file.](https://cdn.hashnode.com/res/hashnode/image/upload/v1702581401179/95d8e9f8-41ed-4ee2-9921-8b62d76a9667.png align="center")

> *However, it's not necessary to hide the Google Analytics ID because anyone can see it by inspecting the webpage.*

I felt so frustrated when I accidentally pushed .env to Github.

But don't worry in this article I've shared a great git feature that will help us to remove specific files from the commit history.

Environment variables play a crucial role in any software application. The .env files are designed to store environmental variables in key-value pairs that hold various sensitive configuration settings for an application.

Accidentally pushing a .env file can lead to a serious security threat to our application. It can lead to unauthorized API uses, access to databases, and more. So it's very necessary to keep the .env file confidential.

## **Solution**

I'm assuming that you have already pushed the .env file to the remote repository without saving it to the .gitignore file.

### Save The .env File To .gitignore File First

`.env`

### To Remove .env File From Git History Run This Command

`git filter-branch --index-filter "git rm -rf --cached --ignore-unmatch .env" HEAD`

### Push The Filtered Changes

`git push --force`

## **Conclusion**

In this way, you can completely remove the .env file from the git history. Although It's removed I will highly recommend you to check .gitignore even before making any **git commit** to ensure that the .env file is added to it. Thanks for reading this article till the end. Subscribe to my newsletter & Let's Connect!