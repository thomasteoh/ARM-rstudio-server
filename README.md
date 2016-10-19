# ARM-rstudio-server
Build script for rstudio-server on an ARM-based Android system.

![RStudio on Android](https://github.com/thomasteoh/thomasteoh.github.io/raw/master/public/images/2016-10-20-rstudio-android.png)

This is built on the excellent scripts of [dashaub/ARM-RStudio](https://github.com/dashaub/ARM-RStudio) and [jrowen/ARM-rstudio-server](https://github.com/jrowen/ARM-rstudio-server).

## Build
This script has been used to successfully build RStudio Server on a Motorola Moto X (2013) (ARMv7) running Debian 8.6 (jessie) via a chroot environment created by [Linux Deploy](https://github.com/meefik/linuxdeploy). A fully installed chroot instance of a Linux installation should be installed on your device (requires root). The command below can be used to build the server

```
sudo ./build_rstudio.sh
```

The build may take several hours to complete. It is recommended to keep the screen on or to use performance settings on the Android system while compiling, as well as to use a `screen` or `tmux` instance in case the connection is lost. Additionally, at least 3Gb of space should be made available within the container. 

The `VERS` variable in the script can be updated to build different versions of the server.  The latest version number and be found on the rstudio server [download page](https://www.rstudio.com/products/rstudio/download-server/), and note that this will likely differ from the latest desktop version.

## Launching RStudio Server
After the server has been built and installed, the easiest way to start the server is using the command below

```
sudo rstudio-server start
```

Finally, from a web browser on your device, navigate to `localhost:8787` and log in using your user credentials. Alternatively, access your RStudio server through the device's network address at port 8787.

## Contributions
Please don't hesitate to file an issue if you run into problems, and pull requests are welcome.
