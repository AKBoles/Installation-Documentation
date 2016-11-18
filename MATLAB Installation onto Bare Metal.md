Install Matlab onto BareMetal Instance on Chameleon Cloud:
==========================================================


1.	Download the installer that you with to use. 

    a.	Must be appropriate for your machine (Windows, Mac, Linux)

    b.	For Linux R2016a, file is: matlab_R2016a_glnxa64.zip

    c.	Link: http://www.mathworks.com/downloads/web_downloads/download_release?release=R2016b

2.	Unzip this file using the command: “unzip matlab_R2016a_glnxa64.zip”

    a.	If unzip is not installed, please use this command: “sudo apt-get install unzip”

3.	Once this is done, make sure that Java is installed on the machine. Follow these steps:

    ~~~
    $ sudo add-apt-repository ppa:webupd8team/java    
    $ sudo apt-get update
    $ sudo apt-get install oracle-java8-installer
    $ sudo apt-get install oracle-java8-set-default
    $ sudo apt-get install default-jre
    ~~~

At this time, navigate to the location where you unzipped the matlab folder. All that is needed is to type the command: `sudo ./install`. This will start the matlab installation process and will walk the user though the necessary process of installing matlab onto the server.
