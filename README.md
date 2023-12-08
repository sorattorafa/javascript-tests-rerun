# Projects rerun

Steps:

    1 - Make a repository fork;
    2 - Clone on projects dir

## Clone Repository on Projects dir

```bash
cd projects/
git clone repo
```
## 1 Nachos-ui


```bash 

cd projects/nachos-ui

asdf install

./shaker-js/shaker/shaker.py jest "projects/nachos-ui" -tc "yarn test" -o "projects/nachos-ui/output" -sr 1 -nsr 1
```

## React

```bash 

cd projects/react

asdf install

./shaker-js/shaker/shaker.py jest "projects/react" -tc "yarn test" -o "projects/react/output" -sr 1 -nsr 1000
```


# Projects rerun into GitHubCI


- Create the file `.github/workflows/shaker.yml` into project dir
- Add content:

```yml
name: Flaky Shaker # This is a basic workflow to help you get started with Actions 

# Controls when the action will run. 
on:
  # Triggers the workflow on push or pull request events but only for the main branch
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
# This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
      - uses: actions/checkout@v3
      - name: Jest tests
        uses: sorattorafa/shaker-js@main
        with:
          tool: jest
          tests_command: yarn test:source
          runs: 1
          output_folder: freeCodeCamp/output
```
