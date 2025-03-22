# 🖥️ Ansible Playbook: Deploy Windows Domain Infrastructure on VMware

This playbook automates the provisioning of a **Windows Domain Controller** and a **member server** in a **VMware vSphere** environment using Ansible. It sets up a brand new **Active Directory forest**, joins a second Windows server to the domain, and fully automates networking, guest customization, and reboots.

---

## 🚀 What This Playbook Does

1. **Clones a Domain Controller (DC)** from a Windows template
2. Customizes the VM with static IP, DNS, local admin password, etc.
3. Runs a script to enable **WinRM** for Ansible
4. **Promotes the DC** to a new forest using `win_domain`
5. **Clones a second VM**, configured as a member server
6. Waits for WinRM to be available on the second VM
7. **Joins the second VM to the new domain**
8. **Reboots** the member server to finalize the domain join
