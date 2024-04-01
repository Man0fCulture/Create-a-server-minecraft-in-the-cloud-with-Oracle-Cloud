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

Java https://docs.oracle.com/en/java/

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

### Three: Generate an SSH key

It's the most important thing keep it and don't lost it you will need it if you want to enter your VM anytime!

## Step: 2 Connect to the VM

The VM is about to run it's state is normally PROVISIONING you just need to wait untill it switch to RUNNING

Now you will copy the Public IP Address to connect to your newly acquired VM and use the SSH protocol https://linuxcommand.org/lc3_man_pages/ssh1.html

`ssh opc@"The ip of your VM" -i (the Key of your VM)`

You will install the update of your image

`sudo yum update`

And now leave it alone

## Step: 3 Send a file to your VM

You will download the Minecraft server.jar 

Now you will use the SCP protocol to send to your VM the server.jar

`scp -i (the Key of your VM) (the file you want to send) opc@"The ip of your VM":"the directory you want the copy to be send"`

Example:
![image](https://github.com/Man0fCulture/Create-a-server-minecraft-in-the-cloud-with-Oracle-Cloud/assets/114578137/6b930645-dfd6-4b2a-abf9-f04884600383)

## Step: 4 Install the dependency

Now you will install java the lastest version with yum

Now you will start the server

`java -Xmx6G -Xms6G -jar server.jar nogui`

Oh no! It didn"t work!

Don't worry it's normal now you will have a eula.txt file 

Edit it with nano to change the "eula=false" to "eula=true"

To save exit, type CTRL + C, 'Y' to accept changes, and then ENTER.

### Optional: change the properties of your server

You can edit the server.properties

Change the description of the server, the max-player connected at the same time etc...

## Step: 5 Open the server Firewall

Now we will need to open the subnet so your friends can join you in your server

In your VCN we will add 2 new Ingress Rules one TCP and one UDP each with a "Source CIDR" of 0.0.0.0/0 and a destination port of 25565 so it will be connected with any port!

Now you will open the ports of the vm in the VM use these 2 commands to open it:

`sudo firewall-cmd --permanent --zone=public --add-port=25565/tcp`

`sudo firewall-cmd --permanent --zone=public --add-port=25565/udp`

and now we reload the firewall

`sudo firewall-cmd --reload`

## Step: 6 Starting the Server

Now run the Server

`java -Xmx6G -Xms6G -jar server.jar nogui`

You can allocate any ram you want i put 6 just for the example!

## Step: Bonus Let the server run all the time with Tmux

Now that your server is up, as you know if you quit your vm the server will shut down the second you quit it and so to avoid that we will use Tmux a terminal multiplexer.

So first of all install Tmux

`yum install tmux`

And now we will create a sesion

I will let you read the documentation here if you have any question come ask to one of us!

## Step: Bonus Install Mods in your server

Now you have your server who run all the time try to install mods in it!


