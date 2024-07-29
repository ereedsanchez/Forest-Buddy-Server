## Forest Buddy FTP

#### Prerequisites

A computer with adequate space for your application.

## FTP Server

We used [Filezilla Server](https://filezilla-project.org/download.php?type=server) to set up our FTP server so our Cameras can store their video.

FileZilla should automatically open your ports for sending and reciving information. If not you may have to do this manually.
When logged onto FileZilla Server, go onto Server -> Configure... then select user. Once in user, select Add, and insert the name of the user. This is the username your clients will use to log onto your server. You're going to need to set up a Virtual Path, and a Native(local) path. The easiest course of action is to just set up a root path (ie. /) on your Virtual side, and then add the necessary directories. Just remember, anyone who logs onto this user will be able to read and write in all the branch directories. Afterwards, select where you want all the information to be stored within the server. Ensure you write out the entire path (ie C:\User\Your_User\Desktop\FTP_server).
### 1. Install Filezilla

FileZilla should automatically open your ports for sending and reciving information. If not you may have to do this manually.

### 2. Create a user

When logged onto FileZilla Server, go onto Server -> Configure... then select user. Once in user, select Add, and insert the name of the user. This is the username your clients will use to log onto your server.

![Model](https://github.com/ereedsanchez/Forest-Buddy-Server/blob/main/media/pics/Screenshot%202024-07-29%20132634.png?raw=true)

### 3. Set up your Virtual and Local path

You're going to need to set up a Virtual Path, and a Native(local) path. The easiest course of action is to just set up a root path (ie. /) on your Virtual side, and then add the necessary directories. Afterwards, select where you want all the information to be stored within the server. Ensure you write out the entire path (ie C:\User\Your_User\Desktop\FTP_server).

**DISCLAIMER-** anyone who logs onto this user will be able to read and write in all the branch directories, this could be a security hazard.

### 4. Set up a password

It is strongly recomended to add a password to the user. Remember, if left with no password, anyone in your network who see's this open port, can log into it, and inject malware within your computer, and it may be worse if you have port fowarded beforehand.

### 5. Look over your user settings

Lastly, ensure the user is enabled, that whoever logs in is able to read + write (or just write), and has a password. Aside from that you should have a working FTP Server. It is recomended that you test it by logging into your user from a external computer (ie your smartphone, laptop, etc.) and see if youre able to read and write and retrieve information.
