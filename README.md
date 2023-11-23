# Setup asdf



* Install curl and git

    ```bash
    sudo apt install curl git
    ```

* Clone asdf

    ```bash
    git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.10.2
    ```

* Add into `.bashrc`

    ```bash
    . $HOME/.asdf/asdf.sh
    . $HOME/.asdf/completions/asdf.bash
    ```

* Install node plugin on asdf

    ```bash
        asdf plugin add nodejs https://github.com/asdf-vm/asdf-nodejs.git
        asdf install nodejs 20.9.0 # change version here
    ```

* List plugins added
    ```bash
        asdf plugin list
    ```

* List Nodejs Last Versions
    ```bash
    asdf nodejs update-nodebuild

    asdf nodejs resolve lts --latest-installed
    ```

* References:
    - [Install asdf](https://fumachi.mat.br/2022/10/05/ubuntu-22-04-lts-asdf-python/)
    - [Install nodejs plugin](https://blog.logrocket.com/manage-node-js-versions-using-asdf/)


# Projects rerun

## 1 Nachos-ui


```bash 

cd projects/nachos-ui

asdf install

./shaker-js/shaker/shaker.py jest "projects/nachos-ui" -tc "yarn test" -o "logs/nachos-ui/output"
```
