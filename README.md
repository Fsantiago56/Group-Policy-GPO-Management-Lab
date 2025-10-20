# 🧱 1️⃣ Group Policy (GPO) Management Lab

## 🎯 Goal
Learn how organizations enforce system rules, security configurations, and user restrictions through Group Policy Objects (GPOs) in Active Directory.

---

## 🧩 Objectives

You’ll create and apply GPOs to:

- 🔒 Enforce password complexity

- 🚫 Disable USB storage

- 🖼️ Set department-specific wallpapers (IT / HR / Sales)

- 🧑‍💻 Apply GPOs to Organizational Units (OUs) created in your previous AD lab

- 🔁 Use gpupdate /force and gpresult /r on the client to verify policy enforcement

---

## 🖥️ Environments Used
- Host OS: Windows 11

- Server VM: Windows Server 2022 (Domain Controller: DC01.company.local)

- Client VM: Windows 10 / 11 (Domain-joined: Client01)

- Virtualization: VirtualBox

---  

## 🧠 Skills Gained

- Policy creation and enforcement

- System security configuration

- Troubleshooting GPO application failures

- Understanding inheritance and OU targeting

---

## 🛠️ Lab Walkthrough

### 🔹Step 1 – Open Group Policy Management

1. Log into DC01 as a Domain Admin.

2. Open Server Manager → Tools → Group Policy Management.

3. Expand your domain company.local.

  <details><summary>Click to view Steps Results✅</summary>
 <p align="center">  Group Policy Management Console open with your domain expanded.<p>
<p align="center"><img src="https://i.imgur.com/oW34dlF_d.png?maxwidth=520&shape=thumb&fidelity=high" height="60%" width="60%" alt="SSH Setup"/><p>
  <p>
 </details>
 
---

### 🔹Step 2 – Create a Password Complexity GPO

1. Right-click your domain → Create a GPO in this domain, and Link it here...

2. Name it: ``` Enforce Password Policy.```

3. Edit the GPO → Navigate to:
```
Computer Configuration → Policies → Windows Settings → Security Settings → Account Policies → Password Policy
```

4. Enable:

- Minimum password length: 8
- Password must meet complexity requirements: Enabled
- Maximum password age: 60 days
  

<details>
  <summary>Click to view Steps Results✅</summary>

  <p align="center"><strong>Password Policy settings</strong></p>

  <p align="center">
    <img src="https://i.imgur.com/VQK9zWg.png" height="60%" width="60%" alt="Password Policy Screenshot"/>
  </p>

</details>

 
---

### 🔹Step 3 – Disable USB Storage

 1. Create a new GPO named Disable USB Storage.

2. Edit → ``` Computer Configuration → Policies → Administrative Templates → System → Removable Storage Access```

3. Set All Removable Storage classes: Deny all access → Enabled.

4. Repeat these steps under "User Configuration" also in the Group Policy Editor.

<details>
  <summary>Click to view Steps Results✅</summary>

  <p align="center"><strong>USB access policy screen.</strong></p>

  <p align="center">
    <img src="https://i.imgur.com/k2kPkgv.png" height="60%" width="60%" alt="Password Policy Screenshot"/>
  </p>

</details>

---

### 🔹Step 4 – Department Wallpapers

1. For each OU (IT, HR, Sales), create a separate GPO (e.g., IT Wallpaper, HR Wallpaper, Sales Wallpaper).

2. Edit each → ``` User Configuration → Policies → Administrative Templates → Desktop → Desktop → Desktop Wallpaper```
Enable Desktop Wallpaper.

4. Point to unique wallpaper paths (ex: \\DC01\shared\wallpapers\it.jpg).

  <details>
  <summary>Click to view Steps Results✅</summary>

  <p align="center"><strong>HR Department wallpaper Settings.</strong></p>

  <p align="center">
    <img src="https://i.imgur.com/w6Dr1ae.png" height="60%" width="60%" alt="Password Policy Screenshot"/>
  </p>

  <p align="center"><strong>IT Department wallpaper Settings.</strong></p>

  <p align="center">
    <img src="https://i.imgur.com/Zyub5M3.png" height="60%" width="60%" alt="Password Policy Screenshot"/>
  </p>
    <p align="center"><strong>Sales Department wallpaper Settings.</strong></p>

  <p align="center">
    <img src="https://i.imgur.com/Pwdu3Jz.png" height="60%" width="60%" alt="Password Policy Screenshot"/>
  </p>
</details>

---

### 🔹Step 5 – Apply & Test

On Client01 (domain-joined):

```bash
gpupdate /force
gpresult /r
```

✅ Confirm:
- Password policy applied
- USB access blocked
- Correct wallpaper per OU

<details>
<summary>Click to view Steps Results✅</summary>

  <p align="center"><strong>USB access policy screen.</strong></p>

  <p align="center">
    <img src="https://i.imgur.com/k2kPkgv.png" height="60%" width="60%" alt="Password Policy Screenshot"/>
  </p>
