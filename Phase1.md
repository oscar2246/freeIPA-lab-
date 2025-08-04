

# FreeIPA IAM Lab Setup -Phase 1

This project simulates an enterprise grade Identity and Access Management environment using FreeIPA on a virtualized lab environment using Proxmox.
I have implemented 

- Centralized user and group management
- Access control with HBAC (Host-Based Access Control)
- Secure password policies
- Realistic department-based organization

Created FreeIPA groups to simulate orginzation departments


ipa group-add dev --desc="Developers"
ipa group-add hr --desc="Human Resources"
ipa group-add finance --desc="Finance Department"
ipa group-add it --desc="IT Administrators"

Created and and assigned realistic users to groups

ipa user-add john.hr --first=John --last=HR --password
ipa user-add bob.finance --first=Bob --last=Finance --password
ipa user-add christian.it --first=Christian --last=IT --password

ipa group-add-member hr --users=john.hr
ipa group-add-member finance --users=bob.finance
ipa group-add-member it --users=christian.it

Password policy 

ipa pwpolicy-mod --minlife=1 --maxlife=90 --history=5 --minclasses=3 --minlength=12

HBAC Rule: Group based SSH access control

Created an HBAC (Host Based Access Control) rule to restrict which rgoups can SSH into a specific group of servers

ipa hbacrule-add dev-login-rule --desc="Dev and IT login to dev servers"
ipa hbacrule-add-user dev-login-rule --groups=dev
ipa hbacrule-add-user dev-login-rule --groups=it



