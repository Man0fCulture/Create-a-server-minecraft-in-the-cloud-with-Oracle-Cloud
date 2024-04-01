# Create-a-server-minecraft-in-the-cloud-with-Oracle-Cloud
Workshop organized by Suleman MAQSOOD, John DE-KETTELBUTTER and Loic RAVALISON  for Epitech Students (April 2024)

Suleman MAQSOOD https://github.com/Man0fCulture

John DE-KETTELBUTTER https://github.com/JDK-Tek

Loic RAVALISON https://github.com/loicrava

## What we will use during this Workshop

Public Cloud : Oracle Cloud https://www.oracle.com/fr/cloud/definition-cloud-public/

### To connect to the VM

The SSH protocol https://www.ssh.com/academy/ssh/protocol

### In the VM

JDK Package https://docs.oracle.com/en/java/

Tmux https://github.com/tmux/tmux/wiki

## Step: 1 Create an Instance

The first thing that you’ll need to do to get your Minecraft server up and running is to create a VM instance ("Virtual Machine" 🗿).

In the ‘Image and shape’ section change the shape of your VM and then select ‘Ampere’ (ARM) under ’Shape series’. Choose the ‘VM.Standard.A1.Flex’ shape and choose the amount of CPU and RAM that you want to allocate to this server. 

For your “always free” ARM servers, you get up to 4 OCPU and 24 GB of RAM to allocate. This means that you can turn up one virtual machine with 4 OCPU and 24GB of RAM, or any combination up to the limit.

For this Workshop i recommand at least 2 OCPU and 6GB of RAM, which should be plenty of resources for a reliable server that can host 20+ players at a time! (I use everything for my server🗿)
