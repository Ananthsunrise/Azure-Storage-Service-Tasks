# Azure-Storage-Service-Tasks

Without storage account you cant able to access azure storege services. 
Max capacity of storage account 500tb
storage account also used for cost optimization
Types of storages: 1.container 2.file share 3.table 4.queue 5.managed disks

Task 1 :**create storage account**
Go to azure portal->search storage accounts->click create->give storage account name(must br unique and small)->select region->select performance as standard or premium->select redundancy(LRS,GRS,ZRS,GZRS)->select access tier(hot or cold)->select network access(public or private)->select howmany days retainn deleted files->click review and create.

Task 2:**create container or blob in storage account**
Go to azure portal->search storage accounts->select 1 storage account->click containers under data storage->click create->now you can upload files inside it.

Note: you can access container files over the webbrowser by copy and paste the url

Task 3 : **restore storage account**
Go to azure portal->search storage accounts->click restore->select subscription->it will show what are the storage accounts you have previously->select the storage account you want and restore it.

Task 4: **Details you need to provide about storage account to client**
you can provide storage account name,connection string,sas token deatils to client.

Go to azure portal->search storage accounts->click 1 storage account->click access keys under security+monitoring->here you can find connection string details
Go to azure portal->search storage accounts->click 1 storage account->click shared access signature under security+monitoring->here you can generate sas token

Note: connection string for permananent access , sas token for temperory access

Task 5 :**create file share in azure storage account** 
Go to azure portal->search storage accounts->click 1 storage account->click create file share->give name of file share,select access tie(hot or cold) ->you can also enable backup of fileshare using RSV->click review and crate

Task 6 : **extend capacity of azure file share from 5tb to 100tb**
bydefault fileshare have max capacity 5tb. You can extend this capacity

Go to azure portal->search storage accounts->click 1 storage account->select 1 fileshare->click edit quota->in this you can extend size upto 100tb->you can upload files by clicking upload option 

Task 7 : **Mount azure file share in virtual machines**
Go to azure portal->search storage accounts->click 1 storage account->select 1 fileshare->click connect->select windows or linux->select drive letter->select storage account key->click show script->copy the script->login virtual machine and open powershell->here you can paste and enter
Now file share is mount on vm

Task 8 : **Enable all network access for accessing storage account**
Go to azure portal->search storage accounts->click 1 storage account->select networking under security+monitoring->slect enable from all networks.

To check this,
Go to azure portal->search storage accounts->click 1 storage account->go to azure file share->click connect ->copy the script->login any virtual machine and open powershell->paster and enter->now file share is mounted inside that virtual machine. similarly, In any virtual machine file share can be mount because of enable from all networks.

Task 9: **Enable slected network access for accessing storage account**
Go to azure portal->search storage accounts->click 1 storage account->select networking under security+monitoring->slect enable from selected networks and ip addresses->select 1 vnet and save.

To check this,
Go to azure portal->search storage accounts->click 1 storage account->go to azure file share->click connect ->copy the script->login  virtual machine which is under above selected vnet and open powershell->paster and enter->now file share is mounted inside that virtual machine. except the particular vnet, there is no virtual machine can acess storage account.

Task 10 : **Disable public access and allow private access for accessing storage account**

Go to azure portal->search storage accounts->click 1 storage account->select networking under security+monitoring->slect disabled.

To get private endpoint access,
Go to azure portal->search storage accounts->click 1 storage account->select networking under security+monitoring->select private endpoint connections->click create private endpoint->give name->select target sub resource(container or file)->select vnet,subnet->select ip as satatic->configure dns->click review and create.

To check this,
Go to azure portal->search storage accounts->click 1 storage account->go to azure file share->click connect ->copy the script->login  virtual machine which is under above selected vnet and open powershell->paster and enter->now file share is mounted inside that virtual machine. except the particular vnet, there is no virtual machine can acess storage account.

Task 11 : **Azure virtual machine backup**
Azure RSV is a store which stores azure vm's backup,database backups,file storage account backups,etc,..you can create rsv policy to maintain backup how long, how many days,..
You can achieve virtual machine backup in 3 ways 1.while creating a virtual machine 2.after creating a virtual machine, you can go backup options in virtual machine and then proceed. 3.you can create RSV and inside RSV you can add virtual machine

go to azure portal->search virtual machines->click 1 virtual machine->go to backup under backup+dissaster recovery->create new RSV->select policy type as enhanced or standard->give policy details(when backup will start,end, instance restore days)->click create backup

Task 12 : **Restore virtual machine from backup**
3 catagories in this 1.restore existing virtual machine from backup 2.create new virtual machine from backup 3.restore only disk from backup, not virtual machine

Go to azure backup center->click backup instances under manage->clcick restore->select the backup which you want to restore->select restore point->In resore configuration you can select  you wantnew virtual machine or disk or existing virtual machine->give name of virtual machine,subscription,resource group,vnet,subnet->clicck start.




