# FreeIPA IAM Lab Setu - Phase 2

In this phase, I extended my FreeIPA lab by creating an Ubuntu Virtual Machine, adding it to the FreeIPA domain, and applying access controls.

### 1. Created Ubuntu VM
- Setup an Ubuntu VM in my environment to simulate a client machine

## 2. Added Ubuntu VM to the FreeIPA Domain
- Installed the FreeIPA client on ubuntu
- Successfully joined the VM to the FreeIPA domain using the command

'Sudo ipa-client-install --mkhomedir --hostname=ubuntu-vm.mdp.local --domain=mdp.local --server=ipa.mdp.local'

## 3. Verified iit worked by logging in with domain user credentials

 - id christian.it

 ## 4. Restricted access with HBAC
 - Implemented rule where only IT and Dev group can login to the VM 

 
