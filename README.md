# EDR

### Open Source cross platform AV: ClamAV - supported by Cisco
https://www.clamav.net/

### Open Source malware and antivirus protection - immunet 
https://www.immunet.com/index supported by Cisco - cloud based

### Comparison of AV softwares in the market
https://en.wikipedia.org/wiki/Comparison_of_antivirus_software

### Cisco AMP (Advanced Malware Protection) for endpoints

### Clam AV on Linux
sudo apt update
sudo apt-get install clamav clamav-daemon -y
sudo apt-get install clamtk # install a GUI
sudo systemctl stop clamav-freshclam
sudo freshclam #update clam
sudo wget https://database.clamav.net/daily.cvd # get daily datatabase udpate
sudo cp daily.cvd /var/lib/clamav/
sudo systemctl start clamav-freshclam
systemctl start clamav-freshclam # if deamon not started automatically


## Test commnads
sudo clamscan --infected --detect-pua=yes --recursive /var/www/html/

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
wget -P ~/ http://www.eicar.org/download/eicar.com
mv eicar.com ~/

sudo clamscan --infected --remove --recursive ~/


## More resource - create a cron job for running virus scanning automatically
https://www.techrepublic.com/article/how-to-install-and-use-clamav-on-ubuntu-server-20-04/



  .
