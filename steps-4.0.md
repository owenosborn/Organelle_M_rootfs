Steps to prepare OGM disk image for what C&G will call OS v4.0

Start with OS v3.2, http://thepeacetreaty.org/organellem/images/

Then...

# Update Organelle OS
    cd 
    sudo fw_dir/scripts/remount-rw.sh 
    sudo timedatectl set-time "2020-01-08 16:33"
    cd Organelle_OS/
    git pull
    sudo make organelle_m_deploy
    
# Install Software

    sudo apt-get update
    sudo apt-get install luarocks
    sudo apt-get install csound
    sudo apt-get install supercollider
    
# Config

fix circle icon not showing up in Pd (tcl/tk doesn't like the adwaita circle icon for some reason, so just rename it to force fallback)

    sudo mv /usr/share/icons/Adwaita/cursors/circle /usr/share/icons/Adwaita/cursors/circleORIG
