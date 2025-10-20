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
 <p align="center"> 1️⃣ Group Policy Management Console open with your domain expanded.<p>
<p align="center"><img src="https://i.imgur.com/oW34dlF_d.png?maxwidth=520&shape=thumb&fidelity=high" height="60%" width="60%" alt="SSH Setup"/><p>
  <p>
 </details>
 
