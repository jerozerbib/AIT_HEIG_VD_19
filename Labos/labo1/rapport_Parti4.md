We are going to start by creating a directory and into it two files : `file1` and `file2`. The directory is in `/tmp`

![](/home/jeremy/Images/2019-10-07-220637_335x121_scrot.png)

Then we are creating some links with the commands : 

```bash
ln -s file1 SL #Symbolic link
ln file2 HL #Hard Link
```

![](/home/jeremy/Images/2019-10-07-220925_533x302_scrot.png)

Then we archive the folder in the `backup1`, then create a `restore` folder and *unarchive* the archive into it. Then we check the links.

```bash
sudo tar -czf /mnt/backup1/testLinks.tar.gz test/
sudo ls -al /mnt/backup1/testLinks.tar.gz 
mkdir restore
cd restore/
tar -xf /mnt/backup1/testLinks.tar.gz 
ls
cd test
ls -al
```



![](/home/jeremy/Images/2019-10-07-221350_738x315_scrot.png)

We can then conclude that the links are saved via the `tar` command.

### Using `zip`

We used the folder used prior to this to zip and unzip. The commands are as follows : 

```bash
zip -r /mnt/backup1/testLinks.zip test/
cd restore/
unzip /mnt/backup1/testLinks.zip -d .
cd test/
ls
ls -la
```

![](/home/jeremy/Images/2019-10-07-223638_581x523_scrot.png)

We can see that the links are not kept with `zip`.