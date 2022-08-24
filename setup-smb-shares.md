### SETUP SMB SHARES in TRUENAS 13
ASSUMPTIONS
This tutorial assumes a user and group already exist.
The steps are outlined below:
- create a new dataset
- create and set new ACL permissions
- create an SMB share
- test to confirm the share is accessible in a windows client
- (optional) create additional users and assign groups for shares
- (optional) check the ACL from the command line
- (optional) configure some advanced ACL items


### CREATE THE NEW DATASET
- go to storage >> pools >> click three dots on the right side of the pool you want to work with >>
- then in the popup menu click `add dataset` >> on the next page provide a name >> add a comment (optional) >> 
- then near the bottom of the page change to share type to `SMB` >> leave all other settings alone for now >> press submit 

### CREATE AND SET NEW ACL PERMISSIONS
- now you will be back on the pool page >> click on the three dots on the right side of the new dataset you just created >> 
- in the popup menu click `edit permissions` >> then on the next page click on `use ACL manager` >> In the ACL manager popup window select `use a preset ACL` >>
- in the `select a preset ACL` window click the little downward arrow on the right and select `RESTRICTED` >> click `continue` >>
- then on the preconfigured ACL page, on the left side change the `User` from root to the user account you want to grant access to this share >>
- then also on the left side of the page change the `Group` from wheel to the group that the user account you want to share with is a part of >>
- then under the `User` section click `Apply User` and under the `Group` section click `Apply Group` >> scroll down and check the box next to `Apply Recusively` >>
- there will be a warning popup about recursively applying the permissions to the share but just ignore this and click `continue` to make the box go away >>
- then click `save`

### CREATE AN SMB SHARE
- in the menu on the left side of the main TrueNAS home screen click on `SHARING` >> then click on `Windows Shares (SMB)` >> then click on `ADD` >>
- in the popup window there will be a folder with a little arrow next to it with the source pool name listed, click the arrow which will show the next directory level down, keep clicking the little down arrows until the share that you want to make available is displayed >>
- there should be a little blue `ACL` icon next to the share that you just created >> make sure to click on the name of the share. This is important and easy to forget >>
- below the share is a section for name, provide a name >> add a description (optional) >> in the `Purpose` section leave it set to `Default sharea parameters` >>
- at the bottom of the page click `SUBMIT`

### TEST TO CONFIRM THE SHARE IS ACCESSIBLE
- 

 