# EDR

### Open Source cross platform AV: ClamAV - supported by Cisco
https://www.clamav.net/

### Open Source malware and antivirus protection - immunet 
https://www.immunet.com/index supported by Cisco - cloud based

### Comparison of AV softwares in the market
https://en.wikipedia.org/wiki/Comparison_of_antivirus_software

### Cisco AMP (Advanced Malware Protection) for endpoints

### Clam AV on Linux
1. sudo apt update
2. sudo apt-get install clamav clamav-daemon -y
3. sudo apt-get install clamtk # install a GUI
4. sudo systemctl stop clamav-freshclam
5. sudo freshclam #update clam
6. sudo systemctl start clamav-freshclam # if deamon not started automatically

##  manual database update steps:
-- sudo wget https://database.clamav.net/daily.cvd # get daily datatabase udpate
-- sudo cp daily.cvd /var/lib/clamav/

## Test commnads
sudo clamscan --infected --detect-pua=yes --recursive /home/XXX-USER/Downloads/

#Full Scan
sudo clamscan \
  --suppress-ok-results \
  --recursive \
  --remove \
  --log=/var/log/clamav-scan.log \
  --cross-fs=no \
  /


# Local Recursive Scan
clamscan \
  --suppress-ok-results \
  --recursive \
  
  
## test using a sample malware file (**https://www.eicar.org/?page_id=3950**)
1. wget -P ~/ http://www.eicar.org/download/eicar.com
2. mv eicar.com ~/
3. sudo clamscan --infected --remove --recursive ~/


## More resource - create a cron job for running virus scanning automatically
https://www.techrepublic.com/article/how-to-install-and-use-clamav-on-ubuntu-server-20-04/



  .
