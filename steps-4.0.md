Steps to prepare OGM disk image for what C&G will call OS v4.0

Start with OS v3.2, http://thepeacetreaty.org/organellem/images/

Then...

# update Organelle OS
    
    cd 
    sudo fw_dir/scripts/remount-rw.sh 
    sudo timedatectl set-time "2020-01-08 16:33"
    cd Organelle_OS/
    git pull
    make clean
    sudo make organelle_m_deploy
    
# install software

    sudo apt-get update
    sudo apt-get install luarocks
    sudo apt-get install csound
    sudo apt-get install supercollider
    
nodejs

    curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
    sudo apt-get install -y nodejs
    
# config

fix circle icon not showing up in Pd (tcl/tk doesn't like the adwaita circle icon for some reason, so just rename it to force fallback)

    sudo mv /usr/share/icons/Adwaita/cursors/circle /usr/share/icons/Adwaita/cursors/circleORIG

fix sort order.  enable en_US.UTF8 in /etc/locale.gen, then 

    sudo locale-gen

# update patches
        
    cd /sdcard/
    rm -fr Patches/
    git clone https://github.com/critterandguitari/Organelle_Patches.git
    mv Organelle_Patches/ Patches/
    rm -fr Patches/.git
    rm -fr Patches/.gitignore 
    rm -fr Patches/README.md 
   
# release
         
check for default ap.txt and wifi.txt

check Patches folder looks good

clean up /sdcard

remove .viminfo

remove git config

clear command history:

    cat /dev/null > ~/.bash_history && history -c && exit

run fsck
reboot and test
    
    
