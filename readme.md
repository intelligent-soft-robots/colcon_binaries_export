
# What it is

colcon_binaries_export is a convenient tool for exporting the content of a colcon workspace to an installable binary tar ball.

# Installation

```bash
git clone https://github.com/intelligent-soft-robots/colcon_binaries_export.git
cd colcon_binaries_export
sudo ./install
```

# Usage

The instructions below assume ```$Workspace``` is  the root folder of a colcon workspace.

## Colcon build

First, compile the workspace with the ```merge-install``` argument:

```bash
cd $Workspace
colcon build --merge-install
```

If you previously compiled the workspace without the ```merge-install``` argument, you may need to delete the folders ```install``` and ```build``` first.

## Set extra content folder

Create a folder with the extra files to be included in the tar file ('extra' meaning: not already in the install folder). Typically, such file would be executable installing the dependencies required to use the binaries or libraries of your workspace.

The instruction belows assume ```$Extra``` is the root folder of the extra files folder

## Create the tar file

```bash
cd $Workspace
# replace my_project by any project name of your choice
colcon_tar $Extra my_project
```

## Deploy the tar file

On the target machine, if ```my_project_ubuntu20.04_py3.8.10_binaries.tar.gz``` is the created tar file:

```
mkdir /tmp/my_project
cd /tmp/project
cp /path/to/my_project_ubuntu20.04_py3.8.10_binaries.tar.gz .
tar -zxvf ./my_project_ubuntu20.04_py3.8.10_binaries.tar.gz
./configure
sudo make install
ldconfig
```
