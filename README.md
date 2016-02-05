This is a docker image that was made for UIUC's [CS421](https://courses.engr.illinois.edu/cs421/) course on Programming Languages.

Essentially, I got tired of dealing with `cabal` shenanigans mucking up my system's Haskell setup.

## Requirements

You need some familiarity with [docker](http://docker.com). If you don't know what that is, [this](http://blog.scottlowe.org/2014/03/11/a-quick-introduction-to-docker/) is a nice intro.

On OS X and Windows you'll want to install the [Docker Toolbox](https://www.docker.com/products/docker-toolbox), which will install the `docker` cli, `docker-machine` to manage virtual machines, and `virtualbox` to run those VMs. 

On a Linux distro like Arch Linux, you'll first need to follow your distro's instructions on installing `docker`.

## Usage

For CS421, you are given access to a GitLab repo that contains all your CS421 programming homework.

Assuming you've cloned that repo locally at `~/src/cs421-assignments`, you'll want to `cd` into that directory:

```
cd ~/src/cs421-assignments
```

Then run the following to invoke `ghci`:

```
docker run -v $(pwd):/src/cs421 --rm -it cdrnyx/uiuc-cs421-docker-haskell
```

`-v` maps a path on the host machine to `/src/cs421` which lives inside the container.

`--rm` is a flag to tell docker to destroy the container when exiting.

`-it` invokes an interactive tty.

