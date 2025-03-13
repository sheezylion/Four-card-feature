
# Continuous Integration with GitHub Actions: A Beginner-Friendly Guide
### Introduction
Continuous integration also short form for CI is a software development lifecycle where code changes are automatically tested and validated before merging into the main branch. This helps catch errors early, maintain code quality, and streamline development.

In this project, we'll use GitHub Actions as our CI tool to check for syntax errors in an HTML/CSS form page whenever changes are pushed to the repository.

### What You'll Learn

- Basics of CI and why it's important.

- How to set up GitHub Actions in a project.

- How to create a simple HTML/CSS form page.

- How to configure a GitHub Actions workflow to run a syntax check.

## Project Overview

We'll create a basic HTML and CSS card feature and use a GitHub Actions workflow to check for syntax errors whenever we push changes. The workflow will be defined in a .yml file inside the .github/workflows/ directory.

### Steps:

### 1. Create the index.html File

Inside the repository, create an index.html file and add the following:

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles.css" />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Poppins:wght@200;400;600&display=swap"
      rel="stylesheet"
    />
    <link rel="icon" type="image/x-icon" href="images/favicon-32x32.png" />
    <title>Four card feature session project</title>
  </head>
  <body>
    <div class="main-container">
      <div class="card-container">
        <div class="header-container">
          <h1>
            <span>Reliable, efficient delivery</span> <br />
            Powered by technology
          </h1>
          <p>
            Our artificial intelligence powered tools use millions of projects
            data points to ensure that your project is successful
          </p>
        </div>
        <div class="card-info">
          <div class="first-card">
            <h3>Supervisor</h3>
            <p>Monitors activity to identify project roadblocks</p>
            <img src="images/icon-supervisor.svg" alt="Supervisor" />
          </div>
          <div class="second-card">
            <h3>Team builder</h3>
            <p>
              Scans our talent network to create the optimal team for your
              project
            </p>
            <img src="images/icon-team-builder.svg" alt="team-builder" />
          </div>
          <div class="third-card">
            <h3>Karma</h3>
            <p>Regularly evaluates our talent to ensure quality</p>
            <img src="images/icon-karma.svg" alt="karma" />
          </div>
          <div class="forth-card">
            <h3>Calculator</h3>
            <p>
              Uses data from past projects to provide better delivery estimates
            </p>
            <img src="images/icon-calculator.svg" alt="Calculator" />
          </div>
        </div>
      </div>
    </div>
  </body>
</html>

```

Inside the repository, create an styles.css file and add the following:

```
/* font-family: 'Poppins', sans-serif; */

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: "Poppins", sans-serif;
}

body {
  background-color: rgb(250, 250, 250);
}
.card-container {
  margin: 4rem 2rem 4rem 2rem;
}

.header-container h1 span {
  font-weight: 200;
  font-size: 25px;
  color: hsl(0, 2%, 66%);
}

.header-container h1 {
  font-weight: 600;
  font-size: 26px;
  color: hsl(240, 1%, 18%);
  margin-bottom: 15px;
}

.header-container p {
  font-weight: 400;
  font-size: 15px;
  color: hsl(0, 2%, 66%);
  margin-bottom: 40px;
  text-align: start;
}

.first-card {
  background-color: rgb(255, 255, 255);
  height: 300px;
  border-top: 5px solid hsl(180, 62%, 55%);
  border-radius: 10px;
  box-shadow: 10px 10px 10px rgb(231, 236, 242);
  margin-bottom: 40px;
  position: relative;
}

.second-card {
  background-color: rgb(255, 255, 255);
  height: 300px;
  border-top: 5px solid hsl(0, 78%, 62%);
  border-radius: 10px;
  box-shadow: 10px 10px 10px rgb(231, 236, 242);
  margin-bottom: 40px;
  position: relative;
}

.third-card {
  background-color: rgb(255, 255, 255);
  height: 300px;
  border-top: 5px solid hsl(34, 97%, 64%);
  border-radius: 10px;
  box-shadow: 10px 10px 10px rgb(231, 236, 242);
  margin-bottom: 40px;
  position: relative;
}

.forth-card {
  background-color: rgb(255, 255, 255);
  height: 300px;
  border-top: 5px solid hsl(212, 86%, 64%);
  border-radius: 10px;
  box-shadow: 10px 10px 10px rgb(231, 236, 242);
  margin-bottom: 40px;
  position: relative;
}

.first-card h3,
.second-card h3,
.third-card h3,
.forth-card h3 {
  font-weight: 600;
  font-size: 26px;
  padding: 30px 30px 20px 30px;
}

.first-card p,
.second-card p,
.third-card p,
.forth-card p {
  font-weight: 200;
  font-size: 15px;
  color: hsl(0, 2%, 66%);
  padding: 0 30px 0 30px;
  line-height: 25px;
}

.first-card img,
.second-card img,
.third-card img,
.forth-card img {
  position: absolute;
  right: 40px;
  bottom: 40px;
}

@media screen and (min-width: 768px) {
  .header-container {
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-content: center;
    align-items: center;
    text-align: center;
  }

  .header-container p {
    text-align: center;
    margin-left: 100px;
    margin-right: 100px;
  }
  .card-info {
    position: relative;
    display: grid;
    margin: 1.5rem;
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: 20px;
  }

  .first-card h3,
  .second-card h3,
  .third-card h3,
  .forth-card h3 {
    padding: 20px 30px 0px 30px;
  }

  .first-card {
    position: absolute;
    grid-column-start: 1;
    grid-column-end: 2;
    top: 200px;
    height: 350px;
  }

  .second-card {
    grid-column-start: 2;
    grid-column-end: 3;
    height: 350px;
  }

  .third-card {
    grid-column-start: 2;
    grid-column-end: 3;
    height: 350px;
  }

  .forth-card {
    grid-column-start: 3;
    position: absolute;
    top: 200px;
    height: 350px;
  }
}

@media screen and (min-width: 1024px) {
  .header-container p {
    text-align: center;
    margin-left: 230px;
    margin-right: 230px;
  }

  .first-card,
  .second-card,
  .third-card,
  .forth-card {
    height: 250px;
  }
}

@media screen and (min-width: 1440px) {
  .header-container p {
    text-align: center;
    margin-left: 410px;
    margin-right: 410px;
  }

  .card-info {
    position: relative;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: 20px;
  }

  .first-card {
    position: absolute;
    grid-column-start: 1;
    grid-column-end: 2;
    top: 200px;
    padding: 40px;
    height: 250px;
    left: 30px;
  }

  .second-card {
    grid-column-start: 2;
    grid-column-end: 3;
    padding: 40px;
    height: 250px;
  }

  .third-card {
    grid-column-start: 2;
    grid-column-end: 3;
    padding: 40px;
    height: 250px;
  }

  .forth-card {
    grid-column-start: 3;
    position: absolute;
    top: 200px;
    padding: 40px;
    height: 250px;
  }
}

```

## How GitHub Actions Work 
Before setting up our GitHub Action, let's first understand how it works. GitHub Actions help us automate tasks like running tests, checking for syntax errors, and deploying our projects. The structure of GitHub Actions is built around three key concepts:

### Events (Triggers)
Events are what kickstart a workflow. Think of them as the triggers that tell GitHub, "Hey, it's time to run this process!"
Some common events include:
- push → Runs the workflow when new code is pushed to the repository.
- pull_request → Runs when someone creates a pull request.
- workflow_dispatch → A manual trigger (you run it yourself).
We define these events in our workflow file using on:

### Workflows
A workflow is a process that runs automatically when an event occurs. Each workflow lives inside a .github/workflows/ directory in the repo and is written in a .yml file.
A workflow consists of jobs that run a series of steps to achieve a goal.

### Jobs & Actions
A job is a group of steps that runs on a runner (a virtual machine like Ubuntu). Each job consists of steps, which are instructions for what needs to be done.

Steps can include:
- Checking out the code (using actions from the GitHub marketplace)
- Installing dependencies
- Running tests
- Deploying the application

Jobs can run independently or depend on each other.

## Understanding a Basic GitHub Actions File
Let’s break down a simple GitHub Actions .yml file.

```
name: Basic Syntax Check  

on: push  # This runs when code is pushed  

jobs:  
  lint-check:  
    runs-on: ubuntu-latest  # The OS the job runs on  

    steps:  
      - name: Checkout Repository  
        uses: actions/checkout@v3  # Pulls the latest code  

      - name: Run Linter  
        run: npx htmlhint "**/*.html"  # Checks for syntax errors in HTML

      - name: Run CSS Linter  
        run: |  
          npm install -g stylelint stylelint-config-standard  
          stylelint "**/*.css"  # Checks for CSS syntax errors  
```

### Breaking it Down:
1️ name: - The name of our workflow.
2️ on: - Specifies the event that triggers the workflow (push).
3️ jobs: - Defines the tasks our workflow will perform.
4️ runs-on: - Specifies the OS (Ubuntu) where the job will run.
5️ steps: - The individual tasks within the job. Each step is executed in order.
6️ uses: - Calls a prebuilt action from the GitHub Marketplace.
7️ run: - Runs a shell command (in this case, a linter to check HTML and CSS syntax).

Now that we understand how GitHub Actions work, let's move forward and create our workflow!

### 2. Create the GitHub Actions Workflow

Now, let's create the directory where our workflow file will live.

```
mkdir -p .github/workflows
```

Inside this directory, create a file named basic-github-action.yml and add the following content:

```
name: Linter CI

on:  
  push:  
    branches:  
      - main  

jobs:  
  lint-check:  
    runs-on: ubuntu-latest  

    steps:  
      - name: Checkout repository  
        uses: actions/checkout@v3  

      - name: Install Dependencies  
        run: |  
          npm install -g htmlhint  
          npm install -g stylelint stylelint-config-standard  

      - name: Run HTML Linter  
        run: htmlhint "**/*.html"  

      - name: Run CSS Linter  
        run: stylelint "**/*.css"  

```

### 3. Commit and Push Changes

Now that we have everything set up, commit and push your changes to trigger the GitHub Action.

```
git add .
git commit -m "Added HTML, CSS and GitHub Actions workflow"
git push origin main
```

### 4. Check GitHub Actions

Head over to your GitHub repository > Actions Tab to see the workflow in action. If there are syntax errors in the index.html file, the workflow will catch them.


#### Conclusion

You've just set up a basic CI pipeline using GitHub Actions! Now, every time you push changes, your code is automatically checked for syntax errors. This workflow is a stepping stone towards automated testing and deployment in real-world projects. Note: You can extend this by adding CSS linters to check for css syntax error or integrating automated tests under jobs.
