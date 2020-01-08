Steps to prepare OGM disk image for what C&G will call OS v4.0

Start with OS v3.2, http://thepeacetreaty.org/organellem/images/

Then...

# update Organelle OS
    cd 
    sudo fw_dir/scripts/remount-rw.sh 
    sudo timedatectl set-time "2020-01-08 16:33"
    cd Organelle_OS/
    git pull
    sudo make organelle_m_deploy
    
# other software

    sudo apt-get update
    sudo apt-get install luarocks
    sudo apt-get install csound
    sudo apt-get install supercollider
    
