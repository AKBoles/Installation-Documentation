Install Matlab onto BareMetal Instance on Chameleon Cloud
=========================================================

1. Download the installer that you with to use
    
      For Linux R2016a, file is: matlab_R2016a_glnxa64.zip
      
      Link: http://www.mathworks.com/downloads/web_downloads/download_release?release=R2016b

2.	Unzip this file using the command: `unzip matlab_R2016a_glnxa64.zip`
      
      If unzip is not installed, please use this command: `sudo apt-get install unzip`

3. Make sure that Java is installed. If not, please install it. For instructions, see: https://github.com/AKBoles/Installation-Documentation/blob/master/Various%20Ubuntu%20Installation

4. At this time, navigate to the location where you unzipped the matlab folder. All that is needed is to type the command: `sudo ./install`. This will start the matlab installation process and will walk the user though the necessary process of installing matlab onto the server.
