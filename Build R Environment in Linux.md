# Clean your sources.list

I always find the sources list in Ubuntu is messy. If you want to clean this file, you can use following steps
```
locate sources.list #find where is the file, it should be the first one
cd /etc/apt/sources.list
cat sources.list # see what is inside the list, I always get duplicate and error message from some mirrors
# so I just want to clean it before run any 'apt-get' commands
mv sources.list sources.list.bak # make a copy of this file to avoid mistakes
```

Next step, open the application center or just press `super` then search `software & update`
tick all option under `UBUNTUN Software' tag. For other tag, you don't necessarily need to tick any option.

Now, you should get a new sources.list without duplicates.
```
cat sources.list # check your new sources.list
```

# Install the latest R base
You can browser R website to search for information of R. [R website](https://cloud.r-project.org/)
If you feel lost after you click `Download R for Linux`, don't worry. Try to find `README` file under the directory named
after your operation system.
[install manual](https://cloud.r-project.org/)
You should see something likes this:
```
To obtain the latest R 3.6 packages, add an entry like
    deb https://cloud.r-project.org/bin/linux/ubuntu disco-cran35/
    or
    deb https://cloud.r-project.org/bin/linux/ubuntu cosmic-cran35/
    or
    deb https://cloud.r-project.org/bin/linux/ubuntu bionic-cran35/  
    or
    deb https://cloud.r-project.org/bin/linux/ubuntu xenial-cran35/
    or
    deb https://cloud.r-project.org/bin/linux/ubuntu trusty-cran35/
```
Remeber to use the current version. For my Linux, the version is disco.
Now what you need is to add this sentence into sources.list
```
sudo vim sources.list # if you don't have vim installed, you can use `less` or `nano` instead, 
# or you can use `sudo apt-get install vim`
# you can add that line into sources.list
# you need the use 'sudo' to get root authority to overwrite this file
```
or 
```
sudo echo 'deb https://cloud.r-project.org/bin/linux/ubuntu disco-cran35/' >> sources.list
```

# install r-base and r-base-dev
Unless you have special reason, you should always install r-base rather than r-base-core.
```
sudo apt-get update # update the search path before installing
sudo apt-get remove r-base # you may want to remove previous installed r-base before install the new one
sudo apt-get install r-base # use 'apt-get' instead of 'apt' for more robust installation
sudo apt-get install r-base-dev # also remember to install the latest r-base-dev otherwise you may encounter
# problems when install packages.
```

# install rstudio
```
sudo apt-get remove rstudio # you can remove the previous installed Rstudio
```
You can download deb package from Rstudio official website.
