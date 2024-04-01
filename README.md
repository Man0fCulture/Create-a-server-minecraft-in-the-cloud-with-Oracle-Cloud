# Create-a-server-minecraft-in-the-cloud-with-Oracle-Cloud
Workshop organized by Suleman MAQSOOD, John DE-KETTELBUTTER and Loic RAVALISON  for Epitech Students (April 2024)

Suleman MAQSOOD https://github.com/Man0fCulture

John DE-KETTELBUTTER https://github.com/JDK-Tek

Loic RAVALISON https://github.com/loicrava

## What we will use during this Workshop

Public Cloud : Oracle Cloud https://www.oracle.com/fr/cloud/definition-cloud-public/

### Minecraft server.jar

https://www.minecraft.net/en-us/download/server

### To connect to the VM

The SSH protocol https://www.ssh.com/academy/ssh/protocol

The SCP protocol https://www.ionos.com/digitalguide/server/know-how/scp-secure-copy/

### In the VM

JDK Package https://docs.oracle.com/en/java/

#### For the BONUS:

Tmux https://github.com/tmux/tmux/wiki

## Step: 0 Create an account

https://www.oracle.com/fr/cloud/free/

You will need to enter your credit card but don't worry, you will never pay anything if you only use the always free option.

## Step: 1 Create an Instance

### One: Init the VM

The first thing that you’ll need to do to get your Minecraft server up and running is to create a VM instance ("Virtual Machine" 🗿) select the "Create a VM instance".

In the ‘Image and shape’ section change the shape of your VM and then select ‘Ampere’ (ARM) under ’Shape series’. Choose the ‘VM.Standard.A1.Flex’ shape and choose the amount of CPU and RAM that you want to allocate to this server. 

For your “always free” ARM servers, you get up to 4 OCPU and 24 GB of RAM to allocate. This means that you can turn up one virtual machine with 4 OCPU and 24GB of RAM, or any combination up to the limit.

**For this Workshop i recommand at least 2 OCPU and 6GB of RAM**, which should be plenty of resources for a reliable server that can host 20+ players at a time! (I use everything for my server🗿)

### Two: Create a new VCN ("Virtual Cloud Network" 🗿) 

Edit the "Primary VNIC information" Section.

I will let you choose what to do for this sub step.

### Two: Generate an SSH key

It's the most important thing keep it and don't lost it you will need it if you want to enter your VM anytime!

## Step: 2 Connect to the VM

The VM is about to run it's state is normally PROVISIONING you just need to wait untill it switch to RUNNING

Now you will copy the Public IP Address to connect to your newly acquired VM and use the SSH protocol https://linuxcommand.org/lc3_man_pages/ssh1.html

`ssh opc@"The ip of your VM" -i (the Key of your VM)`

## Step: 3 Send a file to your VM

You will download the Minecraft server.jar 

Now you will use the SCP protocol to send to your VM the server.jar

`scp -i (the Key of your VM) (the file you want to send) opc@"The ip of your VM":"the directory you want the copy to be send"`

Example:
![image](https://github.com/Man0fCulture/Create-a-server-minecraft-in-the-cloud-with-Oracle-Cloud/assets/114578137/6b930645-dfd6-4b2a-abf9-f04884600383)



