## Forest Buddy FTP

#### Prerequisites

A computer with adequate space for your application.

## FTP Server

We used [Filezilla Server](https://filezilla-project.org/download.php?type=server) to set up our FTP server so our Cameras can store their video.


### 1. Install Filezilla

FileZilla should automatically open your ports for sending and reciving information. If not you may have to do this manually.

### 2. Create a user

When logged onto FileZilla Server, go onto Server -> Configure... then select user. Once in user, select Add, and insert the name of the user. This is the username your clients will use to log onto your server.

### 3. Set up your Virtual and Local path

You're going to need to set up a Virtual Path, and a Native(local) path. The easiest course of action is to just set up a root path (ie. /) on your Virtual side, and then add the necessary directories. Afterwards, select where you want all the information to be stored within the server. Ensure you write out the entire path (ie C:\User\Your_User\Desktop\FTP_server).

**DISCLAIMER-** anyone who logs onto this user will be able to read and write in all the branch directories, this could be a security hazard.

### 4. Set up a password

It is strongly recomended to add a password to the user. Remember, if left with no password, anyone in your network who see's this open port, can log into it, and inject malware within your computer, and it may be worse if you have port fowarded beforehand.

### 5. Look over your user settings

Lastly, ensure the user is enabled, that whoever logs in is able to read + write (or just write), and has a password. Aside from that you should have a working FTP Server. It is recomended that you test it by logging into your user from a external computer (ie your smartphone, laptop, etc.) and see if youre able to read and write and retrieve information.

### Recomendation

It is recomended that your server has a set IP address so your devices can always find it within the network.


## Set up FTP on WyzeCam v2 

With the [Dafang hack](https://github.com/EliasKotlyar/Xiaomi-Dafang-Hacks) you [installed](https://github.com/ereedsanchez/Forest-Buddy-Server/blob/main/Camera_WyzeCamv2_Install.md) on the Wyzecamv2 camera, you can send your pictures and video through FTP. To configure this it is recomended to do it through the SD card, although it can be done through SSH too.

### 1. Navigate into motion.conf

When you connect your SD card to your computer, you want to navigate and open:
```
(your letter drive):/config/motion.conf
```

### 2. Edit the snapshot & FTP snapshot settings

If you want photo to be active scroll down to **# Snapshot** and set **save_snapshot=** to true
Then scroll down to **# Configure FTP snapshots and videos** and set **ftp_snapshot=** to true

If you want video to be active scroll down to **$ Videos** and set **save_video=** to false
Then scroll down to **# Configure FTP snapshot and videos** and set **ftp_video=** to true

### 3. Set your FTP login settings

On **ftp_host=** put in your servers ip address
Then on **ftp_port=** put in the port you have open (typically it is port 21)
Afterwards put your username on **ftp_user=**
Finally, set your password on  **ftp_password=**

it should look something like this:
```
# Configure FTP snapshots and videos
ftp_snapshot=true
ftp_video=false
ftp_host="192.168.10.100"
ftp_port=21
ftp_username="user1"
ftp_password="********"
```

### 4. Set up your directories

On **ftp_stills_dir=** and **ftp_videos_dir=** you want to put the virtual directory you assigned. 

As an example, on my Filezila Server for the Virtual path I created 
```
/
```
with the local path being
```
C:/user/my-user/desktop/ftp/user1
```
Within the folder user1 there are 2 folders, **motion** and **stills**. so on **ftp_stills_dir=** and **ftp_video_dir=** I put
```
ftp_stills_dir="/stills"
ftp_videos_dir="/motion"
```

### Conclusion

In conclusion, your motion.conf should look something like this starting at **# Snapshots**
```
# Snapshots
save_snapshot=true
save_snapshot_dir=/system/sdcard/DCIM/Motion/Stills
max_snapshot_days=5

# Videos
save_video=false
save_video_dir=/system/sdcard/DCIM/Motion/Videos
max_video_days=10

# Configure FTP snapshots and videos
ftp_snapshot=true
ftp_video=false
ftp_host="192.168.10.100"
ftp_port=21
ftp_username="user1"
ftp_password="********"
ftp_stills_dir="/stills"
ftp_videos_dir="/motion"
```

On mine I turned off videos as an example of how it will look. Ensure those are the settings you want, and try not to forget any quotes.
