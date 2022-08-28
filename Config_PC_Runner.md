# Requirements

## Gitlab CI Installation

### get gitlab runner from scoop

Command:

``` sh
scoop install gitlab-runner.exe
```

### Install gitlab runner

Command: 

``` sh
gitlab-runner.exe install
```

### Register a runner in GitLab

Command:

```sh
gitlab-runner.exe register
```

## git configuration

Configure longpaths variable on git configuration

```sh
git config --system core.longpaths true
```

## windows configuration

Configure longpath variable on windows using the following tutorial:

[How to Make Windows 10 Accept File Paths Over 260 Characters](https://www.howtogeek.com/266621/how-to-make-windows-10-accept-file-paths-over-260-characters/)

### System variables

Add engine paths to :

- pwsh
- git 
- python
- msbuild
- go 

