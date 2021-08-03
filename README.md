###     README:
###     This is a playbook to deploy Raspbian or Ubuntu on Raspberry Pi's for various uses
###     I want to run headless, via ssh and avoid repeating tasks.
###     This is a playbook that grew over time, so some style might be inconsistent.
###     A lot was learned between starting this and the current state.
###
###     I restricted myself to use no community plugins in this file and have all information in a single yaml-file.
###     This is a starting point for my roles. 
###     Everything beyond that should have a sane directory structure.
###     
###     Some assumptions are to be respected.
###     - We run this file from some machine that has ansible(current tested version 4.10) installed.
###     - Runs with a user that has sudo rights.
###     - The machine that runs this file has some kind of sdcard slot available.
###   
###     Most of the time, I run this from another Raspi, that I just use to do ansible stuff.
###     
###     !!! This will destroy data that is reachable under "/dev/{{ carddev }}". 
###         The raspi config that I use lists the usb-cardreader under /dev/sdb.
###
###     Yes, stuff gets destroyed. We will write to /dev/ and there is no check for sane inputs.
###     I already destroyed data involuntarly in the process. So please be careful. No Backups, no mercy.
###
###     Another thing would be physical disc space. 
###     We need some at {{ tmppath }} to hold the distro images.
###     This playbook has variables to download images from the interwebs and writes it to the sdcard.
