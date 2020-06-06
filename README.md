# motioneye-k8s
Run [motioneye](https://github.com/ccrisan/motioneye) within kubernetes

This repo contains a couple kubernetes yaml files to stand up a
[motioneye](https://github.com/ccrisan/motioneye) server.

Configuring [motion](https://motion-project.github.io/motion_config.html) is
more of an art than science.  This repo contains my "current" config for a few
different inexpensive PoE security cameras, but I'm sure it's not perfect.

Assumptions:
* This config has 4 cameras.  If you have more/less, you'll need to modify various parts
* I use an NAS appliance to store the recorded video clips to make it easier to do downstream processing with [dhiltgen/video](https://github.com/dhiltgen/video)
* All my cameras use a common user/password - if you have different ones on each camera the secret stitching logic in these yaml's wont work


If you want to leverage this in your own environment, the steps I recommend:

* First get `vlc` to stream properly from your camera via rtsp (google search for your camera brand/model to try to figure out the magic url, since no camera vendor seems to document this clearly)
* Modify the yaml files in this tree to match the number of cameras you have
* Tweak the settings (as needed) until you're able to see captured clips and are happy with the results
