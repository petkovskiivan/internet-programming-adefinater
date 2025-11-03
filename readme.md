# How to do an exam for the Internet Programming course

## 0. Prerequisites

1. In order to do the exam for the Internet Programming course, you need to have a GitHub account. If you don't have one, go to [GitHub](https://github.com/) and create one. You can use your university email address, or any other email address you have access to.
2. You need to have Git installed on your computer. If you don't have it, go to [Git](https://git-scm.com/) and install it. You can use the default settings for the installation.
3. You need to have a code editor installed on your computer. You can use any code editor you like, but I recommend [Visual Studio Code](https://code.visualstudio.com/). You can use the default settings for the installation.
4. You need to have Node.js installed on your computer. If you don't have it, go to [Node.js](https://nodejs.org/en/) and install it. You can use the default settings for the installation.
5. You need to have a browser installed on your computer. You can use any browser you like, but I recommend [Google Chrome](https://www.google.com/chrome/). You can use the default settings for the installation.
6. You need to be familiar with the basics of Git and GitHub. If you are not, go to [Git Handbook](https://guides.github.com/introduction/git-handbook/) and read the first two chapters: "Getting Started" and "Git Basics". You can skip the "Git Branching" chapter for now.
7. You need to have TypeScript installed globally on your computer. If you don't have it, open a terminal and run the following command: `npm install -g typescript`. You can verify that it is installed by running the following command: `tsc --version`. It should print the version of TypeScript installed on your computer. If you get an error mentioning an execution policy, run the following command: `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser` and try again.



## 1. Fork the repository

1. Go to the exam repository page: [https://github.com/sweko/internet-programming-adefinater/](https://github.com/sweko/internet-programming-adefinater/)
2. Click on the "Fork" button in the top right corner of the page. This will create a copy of the repository in your GitHub account.
3. Go to your GitHub account and open the forked repository. The URL should be something like `https://github.com/<your-user-name-here>/internet-programming-adefinater`


### 1.1 Sync your fork with the original repository

If you already forked the repository 

1. Go to your forked repository page
2. Click on the "Sync fork" button in the top right corner of the page. This will sync your fork with the original repository. More details are available [here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork)

## 2. Clone the repository

1. Go to your forked repository page
2. Click on the "Code" button in the top right corner of the page
3. Copy the URL of the repository
4. Open a terminal and run the following command: `git clone <url-of-the-repository>`. This will create a local copy of the repository on your computer. The URL should be something like `https://github.com/<your-user-name-here>/internet-programming-adefinater.git` *Make sure not to clone the original repository, but your forked repository - the string `sweko` should not be in your url*

## 3. Make sure that you have the correct folder structure

1. Locate the folder for the correct exam. For groups 1 and 2, the folder name is `alternative-one`. For group 3, the folder name is `alternative-two`.

2. Inside that folder will be a folder called `docs`  and a folder called `code`. The `docs` folder contains the instructions for the exam.

3. The `code` folder should contain folders with student ids. Locate the folder with your student id and open it. It should contain the starter code. This is where you will write your code for the exam.


## 4. Do the exam

1. Open the markdown files in the `docs` folder in your browser. There are two files called `exam-specification.md` and `student-instructions.md`.

2. **Carefully read the instructions for the exam**. If you have any questions, ask the instructor.

3. Execute the instructions for the exam. Note that the instructions may require you to do some research on your own, and that you may need to use the internet to find the information you need. You are allowed and expected to use online resources such as documentation, Stack Overflow, and AI assistants like ChatGPT to help you complete the exam.  
However, you are not allowed to ask for help from anyone else.

## 5. Commit and push your changes

1. Open a terminal and navigate to the folder for the exam. The folder should be something like `<repository-folder>/<alternative>/code/<your-student-id>`

2. Run the following command: `git add .`. This will add all the files in the folder to the staging area.

3. Run the following command: `git commit -m "<your-commit-message-here>"`. This will commit your changes to the local repository. Make sure that your commit message is descriptive enough to understand what you did.

4. Run the following command: `git push`. This will push your changes to your remote repository. Note, if the push fails, refer to the [FAQ](https://github.com/sweko/uacs-internet-programming-exams/blob/main/faq.md).

## 5a. Commit and push your changes (alternative)

1. Use the Visual Studio Code interface to commit and push your changes. More details are available [here](https://code.visualstudio.com/docs/sourcecontrol/intro-to-git)

## 6. Create a pull request

1. Go to your forked repository page

2. Click on the "Pull requests" tab

3. Click on the "New pull request" button

4. Click on the "Compare across forks" link

5. In the "base repository" dropdown, select the original repository, i.e. `sweko/internet-programming-adefinater`

6. In the "head repository" dropdown, select your forked repository, i.e. `<your-user-name-here>/internet-programming-adefinater`

7. Click on the "Create pull request" button

8. Add a descriptive title for your pull request

9. Add a descriptive description for your pull request (including your name and student id)

Note that you can continue to push changes to your forked repository, and the pull request will automatically update with the new changes. However, you should not push any changes after the deadline for the exam has passed.

## 7. Wait for the results

The instructor will review your pull request and provide feedback on your work.