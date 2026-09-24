<a id="top"></a>
<div align="center">

# 🎫 Project 01 — Index
### Real Ticketing System Deployment
**Project 01 of 4 — Tier-2 Support Portfolio**

![Azure](https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu_24.04-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![Apache](https://img.shields.io/badge/Apache-D22128?style=for-the-badge&logo=apache&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)
![osTicket](https://img.shields.io/badge/osTicket_v1.18.1-F4740E?style=for-the-badge)
![Cost](https://img.shields.io/badge/Cost-Azure_Student_Credit-2EA043?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)

**Quick guide to every step and screenshot in this project.**

### [📖 Open the full README](README.md)

</div>

---

<div align="center">

| 🧩 Modules | 🖼️ Screenshots | 🎫 Tickets Created | ✅ Tickets Closed |
|:---:|:---:|:---:|:---:|
| **4** | **33** | **5** | **4** |

</div>

<p align="center">🧩 <b>Lab:</b> Azure VM (Ubuntu 24.04 · Apache · MySQL · PHP) ➜ osTicket v1.18.1 · customer portal <code>/open.php</code> and staff panel <code>/scp</code></p>

---

## 📑 Step Index

All 16 steps and 5 ticket simulations of the project, with the screenshots that show each one.

| # | Step | Module | Result | Evidence |
|:---:|---|:---:|---|:---:|
| 1 | Provision the Azure VM | 🔵 Module 1 | `osticket-vm` running, Ubuntu 24.04, India South Central | [Exhibit 1](#ex1) |
| 2 | Open ports 22 and 80 in the NSG | 🔵 Module 1 | SSH and HTTP allowed | 📝 No screenshot |
| 3 | Install the LAMP stack | 🔵 Module 1 | Apache, MySQL and PHP installed over SSH | [Exhibit 2](#ex2) |
| 4 | Confirm Apache is running | 🔵 Module 1 | `active (running)` since 21:20:44 UTC | [Exhibit 3](#ex3) |
| 5 | Create the MySQL database | 🔵 Module 1 | Database and user created, all `Query OK` | [Exhibit 4](#ex4) |
| 6 | Download and unzip osTicket | 🟢 Module 2 | v1.18.1 zip saved (51,759,267 bytes) and extracted | Exhibits [5](#ex5), [6](#ex6) |
| 7 | Copy files into the web root, prepare the config | 🟢 Module 2 | Works on the VM, fails in the local Windows prompt | Exhibits [7](#ex7), [8](#ex8) |
| 8 | Open the installer, check prerequisites | 🟢 Module 2 | PHP 8.3.6 and MySQLi pass, optional Intl extension missing | [Exhibit 9](#ex9) |
| 9 | Fill in the install form | 🟢 Module 2 | Helpdesk, admin account and database details entered | Exhibits [10](#ex10), [11](#ex11) |
| 10 | Installation complete | 🟢 Module 2 | "Congratulations!" page, `chmod 0644` step listed | [Exhibit 12](#ex12) |
| 11 | Log in to the staff panel | 🟢 Module 2 | First login, system ticket `#331925` | Exhibits [13](#ex13), [14](#ex14) |
| 12 | Create the Priority SLA plan | 🟣 Module 3 | 4-hour grace period | [Exhibit 15](#ex15) |
| 13 | Create the Standard SLA plan | 🟣 Module 3 | 24-hour grace period | [Exhibit 16](#ex16) |
| 14 | Check the SLA list | 🟣 Module 3 | 3 plans: Default 18 h, Standard 24 h, Priority 4 h | Exhibits [17](#ex17), [18](#ex18) |
| 15 | Add three custom departments | 🟣 Module 3 | IT, Network and Email/ VPN added, 6 departments total | Exhibits [19](#ex19), [20](#ex20) |
| 16 | Review the help topics | 🟣 Module 3 | 4 topics set department and priority | [Exhibit 21](#ex21) |
| 17 | Ticket 1 — WiFi not connecting | 🟠 Module 4 | `#693589` High, closed in 13 min 29 s | Exhibits [22](#ex22), [23](#ex23) |
| 18 | Ticket 2 — Email not receiving | 🟠 Module 4 | `#196889` High, closed in 14 min 52 s | Exhibits [24](#ex24), [25](#ex25) |
| 19 | Ticket 3 — VPN connection failing | 🟠 Module 4 | `#505400` Normal, Maintenance, closed in 14 min 43 s | Exhibits [26](#ex26), [27](#ex27) |
| 20 | Ticket 4 — Forgot password | 🟠 Module 4 | `#894015` Normal, replied to but still open | Exhibits [28](#ex28), [29](#ex29) |
| 21 | Ticket 5 — Printer not working | 🟠 Module 4 | `#738368` High, closed in 9 min 0 s | Exhibits [30](#ex30), [31](#ex31) |
| 22 | Review the open and closed queues | 🟠 Module 4 | 4 closed, 1 open | Exhibits [32](#ex32), [33](#ex33) |

---

## 🔵 Module 1 — Azure VM & LAMP Stack

Exhibits 1 to 4. Click a screenshot to open it full size.

<table>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex1"></a>
<a href="Screenshots/01-azure-vm-overview.PNG"><img src="Screenshots/01-azure-vm-overview.PNG" width="380" alt="Exhibit 1"></a>
<br><b>Exhibit 1 — Azure VM overview</b>
<br><sub><code>osticket-vm</code> running: Ubuntu 24.04, Standard B4as v2, India South Central</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex2"></a>
<a href="Screenshots/02-lamp-stack-install.PNG"><img src="Screenshots/02-lamp-stack-install.PNG" width="380" alt="Exhibit 2"></a>
<br><b>Exhibit 2 — LAMP install</b>
<br><sub><code>apt install</code> for Apache, MySQL and PHP, run over SSH</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex3"></a>
<a href="Screenshots/03-apache-status.PNG"><img src="Screenshots/03-apache-status.PNG" width="380" alt="Exhibit 3"></a>
<br><b>Exhibit 3 — Apache running</b>
<br><sub><code>active (running)</code>. The lines above show an early config copy that failed</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex4"></a>
<a href="Screenshots/04-mysql-database-setup.PNG"><img src="Screenshots/04-mysql-database-setup.PNG" width="380" alt="Exhibit 4"></a>
<br><b>Exhibit 4 — MySQL setup</b>
<br><sub>MySQL 8.0.46: database, user, grant and flush all <code>Query OK</code></sub>
</td>
</tr>
</table>

---

## 🟢 Module 2 — osTicket Installation

Exhibits 5 to 14.

<table>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex5"></a>
<a href="Screenshots/05-osticket-download-unzip.PNG"><img src="Screenshots/05-osticket-download-unzip.PNG" width="380" alt="Exhibit 5"></a>
<br><b>Exhibit 5 — Download and <code>unzip</code> install</b>
<br><sub><code>osTicket-v1.18.1.zip</code> saved at 21:22:46 UTC</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex6"></a>
<a href="Screenshots/05-osticket-unzip.PNG"><img src="Screenshots/05-osticket-unzip.PNG" width="380" alt="Exhibit 6"></a>
<br><b>Exhibit 6 — Second download and unzip</b>
<br><sub><code>.zip.1</code> saved (same size), archive extracted into <code>osticket</code></sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex7"></a>
<a href="Screenshots/07-ssh-cmd-error.PNG"><img src="Screenshots/07-ssh-cmd-error.PNG" width="380" alt="Exhibit 7"></a>
<br><b>Exhibit 7 — Wrong machine</b>
<br><sub><code>'ls'</code> and <code>'sudo'</code> not recognized in the local Windows prompt</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex8"></a>
<a href="Screenshots/06-osticket-files-copied.PNG"><img src="Screenshots/06-osticket-files-copied.PNG" width="380" alt="Exhibit 8"></a>
<br><b>Exhibit 8 — Files copied on the VM</b>
<br><sub>Web root filled, <code>ost-config.php</code> created from the sample</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex9"></a>
<a href="Screenshots/08-installer-prerequisites.PNG"><img src="Screenshots/08-installer-prerequisites.PNG" width="380" alt="Exhibit 9"></a>
<br><b>Exhibit 9 — Installer prerequisites</b>
<br><sub>PHP 8.3.6 ✅, MySQLi ✅. Only the optional Intl extension shows ❌</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex10"></a>
<a href="Screenshots/09-installer-form-blank.PNG"><img src="Screenshots/09-installer-form-blank.PNG" width="380" alt="Exhibit 10"></a>
<br><b>Exhibit 10 — Blank installer form</b>
<br><sub>Helpdesk URL <code>http://172.198.77.154/</code>, table prefix <code>ost_</code></sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex11"></a>
<a href="Screenshots/10-installer-form-filled.PNG"><img src="Screenshots/10-installer-form-filled.PNG" width="380" alt="Exhibit 11"></a>
<br><b>Exhibit 11 — Filled installer form</b>
<br><sub>Helpdesk name, admin account and database <code>osticket</code> on <code>localhost</code></sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex12"></a>
<a href="Screenshots/11-installation-complete.PNG"><img src="Screenshots/11-installation-complete.PNG" width="380" alt="Exhibit 12"></a>
<br><b>Exhibit 12 — Installation complete</b>
<br><sub>"Congratulations!" and the <code>chmod 0644</code> instruction</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex13"></a>
<a href="Screenshots/13-scp-login.PNG"><img src="Screenshots/13-scp-login.PNG" width="380" alt="Exhibit 13"></a>
<br><b>Exhibit 13 — Staff panel login</b>
<br><sub>"Authentication Required" at <code>/scp</code></sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex14"></a>
<a href="Screenshots/12-agent-first-login.PNG"><img src="Screenshots/12-agent-first-login.PNG" width="380" alt="Exhibit 14"></a>
<br><b>Exhibit 14 — First login</b>
<br><sub>Only the system ticket <code>#331925</code> "osTicket Installed!"</sub>
</td>
</tr>
</table>

---

## 🟣 Module 3 — Helpdesk Configuration

Exhibits 15 to 21.

<table>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex15"></a>
<a href="Screenshots/15-sla-priority-add.PNG"><img src="Screenshots/15-sla-priority-add.PNG" width="380" alt="Exhibit 15"></a>
<br><b>Exhibit 15 — Priority SLA</b>
<br><sub>Active, grace period 4 hours, schedule "System Default"</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex16"></a>
<a href="Screenshots/14-sla-standard-add.PNG"><img src="Screenshots/14-sla-standard-add.PNG" width="380" alt="Exhibit 16"></a>
<br><b>Exhibit 16 — Standard SLA</b>
<br><sub>Active, grace period 24 hours, schedule "System Default"</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex17"></a>
<a href="Screenshots/16-sla-final-list.PNG"><img src="Screenshots/16-sla-final-list.PNG" width="380" alt="Exhibit 17"></a>
<br><b>Exhibit 17 — SLA list</b>
<br><sub>3 plans. The "delete the setup directory" warning is still visible</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex18"></a>
<a href="Screenshots/16b-sla-final-list-alt.PNG"><img src="Screenshots/16b-sla-final-list-alt.PNG" width="380" alt="Exhibit 18"></a>
<br><b>Exhibit 18 — SLA list, later screenshot</b>
<br><sub>Same 3 plans, no warning banner</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex19"></a>
<a href="Screenshots/17-departments-before.PNG"><img src="Screenshots/17-departments-before.PNG" width="380" alt="Exhibit 19"></a>
<br><b>Exhibit 19 — Departments before</b>
<br><sub>Maintenance, Sales and Support (default), all from the install</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex20"></a>
<a href="Screenshots/18-departments-final.PNG"><img src="Screenshots/18-departments-final.PNG" width="380" alt="Exhibit 20"></a>
<br><b>Exhibit 20 — Departments after</b>
<br><sub><code>Email/ VPN</code>, <code>IT</code> and <code>Network</code> added</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex21"></a>
<a href="Screenshots/19-help-topics.PNG"><img src="Screenshots/19-help-topics.PNG" width="380" alt="Exhibit 21"></a>
<br><b>Exhibit 21 — Help topics</b>
<br><sub>4 topics set the department and priority of a new ticket</sub>
</td>
<td></td>
</tr>
</table>

---

## 🟠 Module 4 — Ticket Simulations

Exhibits 22 to 33. Each row is one ticket: the customer form on the left, the agent reply on the right.

<table>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex22"></a>
<a href="Screenshots/20-ticket1-wifi.PNG"><img src="Screenshots/20-ticket1-wifi.PNG" width="380" alt="Exhibit 22"></a>
<br><b>Exhibit 22 — WiFi ticket, form</b>
<br><sub>Ali Raza, "Report a Problem / Access Issue"</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex23"></a>
<a href="Screenshots/26-wifi-reply.PNG"><img src="Screenshots/26-wifi-reply.PNG" width="380" alt="Exhibit 23"></a>
<br><b>Exhibit 23 — WiFi ticket, reply</b>
<br><sub><code>#693589</code> closed ✅ after 13 min 29 s</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex24"></a>
<a href="Screenshots/21-ticket2-email.PNG"><img src="Screenshots/21-ticket2-email.PNG" width="380" alt="Exhibit 24"></a>
<br><b>Exhibit 24 — Email ticket, form</b>
<br><sub>Sara Khan, "Report a Problem / Access Issue"</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex25"></a>
<a href="Screenshots/28-email-resolve.PNG"><img src="Screenshots/28-email-resolve.PNG" width="380" alt="Exhibit 25"></a>
<br><b>Exhibit 25 — Email ticket, reply</b>
<br><sub><code>#196889</code> closed ✅ after 14 min 52 s</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex26"></a>
<a href="Screenshots/22-ticket3-vpn.PNG"><img src="Screenshots/22-ticket3-vpn.PNG" width="380" alt="Exhibit 26"></a>
<br><b>Exhibit 26 — VPN ticket, form</b>
<br><sub>Hamza Tariq, "Report a Problem"</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex27"></a>
<a href="Screenshots/29-vpn-resolve.PNG"><img src="Screenshots/29-vpn-resolve.PNG" width="380" alt="Exhibit 27"></a>
<br><b>Exhibit 27 — VPN ticket, reply</b>
<br><sub><code>#505400</code> Maintenance, closed ✅ after 14 min 43 s</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex28"></a>
<a href="Screenshots/23-ticket4-password.PNG"><img src="Screenshots/23-ticket4-password.PNG" width="380" alt="Exhibit 28"></a>
<br><b>Exhibit 28 — Password ticket, form</b>
<br><sub>Ayesha Malik, "General Inquiry"</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex29"></a>
<a href="Screenshots/30-password-resolve.PNG"><img src="Screenshots/30-password-resolve.PNG" width="380" alt="Exhibit 29"></a>
<br><b>Exhibit 29 — Password ticket, reply</b>
<br><sub><code>#894015</code> still 🟠 Open, never closed</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex30"></a>
<a href="Screenshots/24-ticket5-printer.PNG"><img src="Screenshots/24-ticket5-printer.PNG" width="380" alt="Exhibit 30"></a>
<br><b>Exhibit 30 — Printer ticket, form</b>
<br><sub>Bilal Ahmed, "Report a Problem / Access Issue"</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex31"></a>
<a href="Screenshots/27-printer-resolve.PNG"><img src="Screenshots/27-printer-resolve.PNG" width="380" alt="Exhibit 31"></a>
<br><b>Exhibit 31 — Printer ticket, reply</b>
<br><sub><code>#738368</code> closed ✅ after 9 min 0 s</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex32"></a>
<a href="Screenshots/25-all-open-tickets.PNG"><img src="Screenshots/25-all-open-tickets.PNG" width="380" alt="Exhibit 32"></a>
<br><b>Exhibit 32 — Open queue</b>
<br><sub>All five tickets plus the system ticket: "Showing 1 - 6 of about 6"</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex33"></a>
<a href="Screenshots/31-closed-tickets.PNG"><img src="Screenshots/31-closed-tickets.PNG" width="380" alt="Exhibit 33"></a>
<br><b>Exhibit 33 — Closed list</b>
<br><sub>4 tickets closed. <code>#894015</code> is not in it</sub>
</td>
</tr>
</table>

### 🎫 Tickets at a Glance

| Ticket | Customer | Priority | Department | Status | Time to Close |
|---|---|:---:|:---:|:---:|:---:|
| #693589 WiFi not connecting | Ali Raza | 🔴 High | not shown | ✅ Closed | 13 min 29 s |
| #196889 Email not receiving | Sara Khan | 🔴 High | Support | ✅ Closed | 14 min 52 s |
| #505400 VPN connection failing | Hamza Tariq | 🟡 Normal | Maintenance | ✅ Closed | 14 min 43 s |
| #894015 Forgot password | Ayesha Malik | 🟡 Normal | Support | 🟠 Open | — |
| #738368 Printer not working | Bilal Ahmed | 🔴 High | Support | ✅ Closed | 9 min 0 s |

---

## 🎯 Verification Checklist

| Check | Method | Layer | Status |
|:---:|---|---|:---:|
| Web stack running | `systemctl status apache2`, MySQL `Query OK` | Server | ✅ Confirmed |
| osTicket installed | "Congratulations!" page, staff panel login | Application | ✅ Confirmed |
| SLA plans created | Staff panel SLA list | Configuration | ✅ Confirmed |
| SLA plans applied to tickets | Ticket pages show Default SLA | Configuration | ⚠️ Not applied |
| Custom departments used | Help topics still route to Support and Maintenance | Configuration | ⚠️ Created, not routed to |
| Tickets closed | Closed list | Workflow | ✅ 4 of 5 |
| Customer confirmed the fixes | No customer replies in any ticket | Workflow | ❌ Not covered |
| Email delivery through the helpdesk | No screenshot shows mail sent or received | Mail | ❌ Not tested |
| NSG rules and the `chmod 0644` step | Described in the README | Server | 📝 Notes only |

> [!NOTE]
> This is a simulation: the customer and the agent are both me, so "closed" means I closed the ticket. Times in the ticket sections are agent-panel time, 5 hours ahead of the UTC times Azure shows.

---

<div align="center">

[⬆️ Back to top](#top) &nbsp;·&nbsp; [📖 Full README](README.md)

🎫 **[osTicket](https://osticket.com)** · ☁️ **[Microsoft Azure](https://azure.microsoft.com)** · 🐧 **[Ubuntu](https://ubuntu.com)** · 🧭 **[Ticket Lifecycle](README.md#ticket-lifecycle)**

</div>
