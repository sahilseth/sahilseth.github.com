# Installing R on a server

This guide talks about installing R on unix like systems. If R available from package managers like 
`apt-get` on ubuntu and `yum` on centos/redhat is not the most current.  
This guide is helpful for installing , where you may not have `sudo` (admin) privileges and 
need to get around without installing dependencies.


```
## make a dir to install
sudo mkdir -m 775 /apps
chown sahilseth /apps

## download to a tmp space
install_dir=/rsrch2/iacs/apps/R/3.2/
cd /tmp
wget http://cran.r-project.org/src/base/R-3/R-3.2.2.tar.gz

## open up the archive
tar -zxvf R-3.2.2.tar.gz

## cd into the new folder and configure
cd R-3.2.2
./configure --prefix $install_dir --enable-R-shlib --enable-R-profiling \
  --enable-memory-profiling --enable-R-static-lib --enable-BLAS-shlib \
  --enable-long-double --with-cairo --with-libpng --with-jpeglib --with-x \
  --with-tcltk
```

One may see errors relating to some of the unavailable libraries. For example if R 
is looking for a `readline` package from linux, it might throw a error like:

```
R -with-readline=yes (default) and headers/libs are not available
```

I was having troubles with both X11 and readline libraries, so had to turn both of them off; by adding these to the configure command.

```
 --with-x=no --with-readline=no
 ```

Mostly, after the install is configured, rest is a smooth sail.


**install**

When configure passes without errors, its time to install R.


```
make
make pdf
make info
make install
```

**Change the group**

In case you would would like 

```
chgrp admin -R /apps/
```

**Let R studio know of the new installation**

For this we would edit `/etc/rstudio/rserver.conf` and add this line:

```
rsession-which-r=/apps/R/3.2/bin/R
```

**restart rstudio**

```
sudo /usr/lib/rstudio-server/bin/rstudio-server restart
```


**pkg upgrade**
If there was a major upgrade from the previous version of R you were using, 
one may need to upgrade all the packages.

```
upgrade(packageStatus())
source("http://bioconductor.org/biocLite.R")
biocLite()
```