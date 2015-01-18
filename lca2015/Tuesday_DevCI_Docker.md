Sven "Docker" Dowideit

prior assumed knowledge - hard learning curve

hobby images - debian 85MB, no editor

command line: `-it` interative terminal, `--rm` remove after (?), `-v` bind mount local dir

local docker flavour x will not be pure kernal (local linking), but close enough for user space

replace hobby image with dockerfile to install required from GH - works every time (pending upstream bugs)

(sample apache code creates 1.4GB image)

box vs container installations

slim container (expanded on in another talk by same)
 - build from source image, extract /usr/lib files -> 1.4GB down to ~300MB

Dockerfiles, terrible cheats

bandwith saving caching techniques

fig - multi container setup via yaml

company behind fig bought by docker

java in a container -> x windows

boot2docker - 24MB distro

rocket - improving services in container

apt-get docker, fig 

s/fig/compose rename coming (since incorporation)

vagrant has docker feature replacement
