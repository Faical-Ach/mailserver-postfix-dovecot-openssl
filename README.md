## 📧 Mail Server: Postfix + Dovecot + OpenSSL + Samba AD-DC
Secure mail server configuration on Ubuntu, integrating:

• Postfix for sending mail (SMTP)

• Dovecot for receiving mail (IMAP/POP3)

• Samba AD-DC for centralized user authentication

• TLS encryption with OpenSSL for secure communication

• DHCP server for dynamic IP management

## 🧪 Lab Topology
![Lab Setup](images/pic_srvmail.png)

## 🛠 Step 1: Lab Environment Setup
🖥️ Virtual Machines
Use any virtualization platform you prefer: VirtualBox, VMware, KVM, etc.

Set up the following VMs:

| VM Name      | Operating System | Role                                           | IP Address   | Notes                                                                   |
| ------------ | ---------------- | ---------------------------------------------- | ------------ | ----------------------------------------------------------------------- |
| `Srvmail`    | Ubuntu (GUI)     | Mail Server, Samba AD-DC, OpenSSL, DHCP Server | 192.168.1.10 | Hosts Postfix, Dovecot, Samba AD-DC, OpenSSL (TLS), and DHCP Server |
| `computer_1` | Windows 10       | Client Machine                                 | 192.168.1.11 | Mail user client                                                        |
| `computer_2` | Windows 10       | Client Machine                                 | 192.168.1.12 | Mail user client                                                        |

## 🛠 Step 2 : Install and config SAMBA-AD-DC

You Should be root :

### active root :
```bash
passwd root
```
Insert Your Password.

### install samba-ad-dc :
```bash
apt update

apt install -y samba winbind krb5-config smbclient dnsutils net-tools
```
Insert <--> Your Domain exemple : CMC.MA
![Step](images/step1.png)

Insert <--> hostname.domain exemple : srv-mail.ofppt.ma
![Step](images/step2.png)

Insert <--> hostname.domain exemple : srv-mail.ofppt.ma
![Step](images/step3.png)

