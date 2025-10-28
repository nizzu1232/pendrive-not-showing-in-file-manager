# pendrive-not-showing-in-file-manager
# if the pendrive is showing in others device and not showing in file manager then go to disk management
# check your pendirve is showing and right click on pendrive 
# if it says Unallocated right click on unallocated area then choose "new simple volume"
next ->next->Assign a drive letter->Formate as NTFS or exFAT->Finish. now the pendrive will show in file manager

# if it has a partition but no drive letter then
 right click that partition -> change drive letter and paths.click add then choose a letter then click ok. now check the file manager 

# if change drive and paths after right click on the partition under the disk in disk management then the corrupted or not it not mounted properly.
# To solve problem 
open terminal(Admin)

#type the command

diskpart
list disk
select <your pendrive name showed in the disk management>
list volume

# if the volumn matches to your pendrive volume then type 

select volume x <-(replace x with your pendrive volume)
assign letter=f <-(replace f to you wanted to give the letter to pendrive)
exit
# if the volume is not listed in the list volume then your pendrive is currently has no valid partition or corrupted partition table. type the command

select disk 1(your pendrive name)
clean 
create partition primary
format fs=exfat quick
assign letter=F(letter that you
 wnated to give)
exit 
