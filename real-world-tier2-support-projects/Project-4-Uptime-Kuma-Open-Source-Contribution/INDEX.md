<a id="top"></a>
<div align="center">

# 🔧 Project 04 — Index
### Open-Source Contribution — Uptime Kuma
**Project 04 of 4 — Tier-2 Support Portfolio**

![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![Vue.js](https://img.shields.io/badge/Vue.js-4FC08D?style=for-the-badge&logo=vue.js&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)
![Windows](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![Cost](https://img.shields.io/badge/Cost-Free-2EA043?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-PR_Open-yellow?style=for-the-badge)

**Quick guide to every step and screenshot in this project.**

### [📖 Open the full README](README.md) &nbsp;·&nbsp; [🔗 View PR #7882](https://github.com/louislam/uptime-kuma/pull/7882)

</div>

---

<div align="center">

| 🐛 Issue | 🖼️ Screenshots | 📄 Files Changed | ➕/➖ Lines | 🔀 PR Status |
|:---:|:---:|:---:|:---:|:---:|
| **#7062** | **20** | **1** | **+14 / −7** | **Open, checks passed** |

</div>

<p align="center">🧩 <b>Lab:</b> Windows PC, Git Bash ➜ forked repo run locally with Vite + Node ➜ fix submitted as a pull request</p>

---

## 📑 Step Index

All 16 working steps of the project, with the screenshot that shows each one.

| # | Step | Module | Result | Evidence |
|:---:|---|:---:|---|:---:|
| 1 | Open the issue | 🔵 Setup | Issue #7062 read and understood | [Exhibit 1](#ex1) |
| 2 | Ask to be assigned | 🔵 Setup | Comment posted on the issue | [Exhibit 2](#ex2) |
| 3 | Fork the repository | 🔵 Setup | Forked to `malaika-azhar/uptime-kuma` | [Exhibit 3](#ex3) |
| 4 | Clone locally | 🔵 Setup | `git clone` completed in Git Bash | [Exhibit 4](#ex4) |
| 5 | Read the contribution guide | 🔵 Setup | `CONTRIBUTING.md` reviewed | [Exhibit 5](#ex5) |
| 6 | First setup attempt | 🟢 Local Run | `npm run setup` failed; Node version checked | [Exhibit 6](#ex6) |
| 7 | Install without dev deps | 🟢 Local Run | `npm ci --omit dev`, 597 packages | [Exhibit 7](#ex7) |
| 8 | Dev server first attempt | 🟢 Local Run | Failed — `concurrently` missing | [Exhibit 8](#ex8) |
| 9 | Full reinstall | 🟢 Local Run | `npm install`, 633 packages | [Exhibit 9](#ex9) |
| 10 | Dev server succeeds | 🟢 Local Run | Vite on `:3000`, backend on `:3001` | [Exhibit 10](#ex10) |
| 11 | First-time setup done | 🟢 Local Run | Live dashboard reached | [Exhibit 11](#ex11) |
| 12 | Build test data | 🟠 Reproduce | 3 test monitors created | [Exhibit 12](#ex12) |
| 13 | Build a test group | 🟠 Reproduce | "Test Group" monitor created | [Exhibit 13](#ex13) |
| 14 | Confirm nesting | 🟠 Reproduce | Monitors nested inside the group | [Exhibit 14](#ex14) |
| 15 | Read `MonitorList.vue` | 🟣 Investigate | Top-level list rendering, no drag logic here | [Exhibit 16](#ex16) |
| 16 | Diff the fix | 🔴 Fix & Submit | `onDrop` change: 14 added, 7 removed | [Exhibit 17](#ex17) |

---

## 🔵 Setup — Issue, Fork, Clone

Exhibits 1 to 5.

<table>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex1"></a>
<a href="Screenshots/01_issue_page_opened.PNG"><img src="Screenshots/01_issue_page_opened.PNG" width="380" alt="Exhibit 1"></a>
<br><b>Exhibit 1 — Issue #7062 opened</b>
<br><sub>"Allow a monitor to be dragged on top of the hierarchy," labeled <code>help wanted</code></sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex2"></a>
<a href="Screenshots/02_comment_posted.PNG"><img src="Screenshots/02_comment_posted.PNG" width="380" alt="Exhibit 2"></a>
<br><b>Exhibit 2 — Assignment requested</b>
<br><sub>"I'd like to work on this, can I be assigned?"</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex3"></a>
<a href="Screenshots/03_forked_repo.PNG"><img src="Screenshots/03_forked_repo.PNG" width="380" alt="Exhibit 3"></a>
<br><b>Exhibit 3 — Repository forked</b>
<br><sub><code>malaika-azhar/uptime-kuma</code>, up to date with upstream</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex4"></a>
<a href="Screenshots/04_git_clone_terminal.PNG"><img src="Screenshots/04_git_clone_terminal.PNG" width="380" alt="Exhibit 4"></a>
<br><b>Exhibit 4 — <code>git clone</code></b>
<br><sub>Cloned locally in Git Bash, 43,739 objects received</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex5"></a>
<a href="Screenshots/05_contributing_md_read.PNG"><img src="Screenshots/05_contributing_md_read.PNG" width="380" alt="Exhibit 5"></a>
<br><b>Exhibit 5 — <code>CONTRIBUTING.md</code> read</b>
<br><sub>Project info and directory structure reviewed first</sub>
</td>
<td></td>
</tr>
</table>

---

## 🟢 Local Run — Getting the App Working

Exhibits 6 to 11.

<table>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex6"></a>
<a href="Screenshots/06_node_version_and_setup.PNG"><img src="Screenshots/06_node_version_and_setup.PNG" width="380" alt="Exhibit 6"></a>
<br><b>Exhibit 6 — Setup attempt fails</b>
<br><sub><code>npm run setup</code> hit a bad version pathspec; Node confirmed as <code>v24.14.1</code></sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex7"></a>
<a href="Screenshots/07_npm_setup_complete.PNG"><img src="Screenshots/07_npm_setup_complete.PNG" width="380" alt="Exhibit 7"></a>
<br><b>Exhibit 7 — <code>npm ci --omit dev</code></b>
<br><sub>597 packages added, EBADENGINE warnings noted</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex8"></a>
<a href="Screenshots/08_dev_server_running.PNG"><img src="Screenshots/08_dev_server_running.PNG" width="380" alt="Exhibit 8"></a>
<br><b>Exhibit 8 — Dev server fails</b>
<br><sub><code>'concurrently' is not recognized</code> — dev deps were skipped</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex9"></a>
<a href="Screenshots/09_npm_install_and_dev_server.PNG"><img src="Screenshots/09_npm_install_and_dev_server.PNG" width="380" alt="Exhibit 9"></a>
<br><b>Exhibit 9 — Full reinstall</b>
<br><sub><code>npm install</code> without <code>--omit dev</code>, 633 packages</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex10"></a>
<a href="Screenshots/10_npm_install_output.PNG"><img src="Screenshots/10_npm_install_output.PNG" width="380" alt="Exhibit 10"></a>
<br><b>Exhibit 10 — Dev server succeeds</b>
<br><sub>Vite on <code>localhost:3000</code>, backend listening on <code>:3001</code></sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex11"></a>
<a href="Screenshots/11_local_run_success.PNG"><img src="Screenshots/11_local_run_success.PNG" width="380" alt="Exhibit 11"></a>
<br><b>Exhibit 11 — Dashboard live</b>
<br><sub>First-time setup finished, empty dashboard reached</sub>
</td>
</tr>
</table>

---

## 🟠 Reproduce — Building the Bug Scenario

Exhibits 12 to 15.

<table>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex12"></a>
<a href="Screenshots/12_three_monitors_created.PNG"><img src="Screenshots/12_three_monitors_created.PNG" width="380" alt="Exhibit 12"></a>
<br><b>Exhibit 12 — Test monitors created</b>
<br><sub>Cloudflare, GitHub, and Google test monitors, all Up</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex13"></a>
<a href="Screenshots/13_group_monitor_created.PNG"><img src="Screenshots/13_group_monitor_created.PNG" width="380" alt="Exhibit 13"></a>
<br><b>Exhibit 13 — Group monitor created</b>
<br><sub>"Test Group" added as a Group-type monitor</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex14"></a>
<a href="Screenshots/14_monitors_auto_nested_in_group.PNG"><img src="Screenshots/14_monitors_auto_nested_in_group.PNG" width="380" alt="Exhibit 14"></a>
<br><b>Exhibit 14 — Monitors nested</b>
<br><sub>Confirmed via the "Monitor Group" field on the edit page</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex15"></a>
<a href="Screenshots/15_dashboard_overview_events.PNG"><img src="Screenshots/15_dashboard_overview_events.PNG" width="380" alt="Exhibit 15"></a>
<br><b>Exhibit 15 — Event history</b>
<br><sub>Live dashboard events while the group was being tested</sub>
</td>
</tr>
</table>

---

## 🟣 Investigate & 🔴 Fix — Code, Diff, Submission

Exhibits 16 to 20.

<table>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex16"></a>
<a href="Screenshots/16_monitorlist_vue_source_code.PNG"><img src="Screenshots/16_monitorlist_vue_source_code.PNG" width="380" alt="Exhibit 16"></a>
<br><b>Exhibit 16 — <code>MonitorList.vue</code> read</b>
<br><sub>Renders the top-level list; the drag handler lives elsewhere</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex17"></a>
<a href="Screenshots/17_git_diff_pr_comparison.PNG"><img src="Screenshots/17_git_diff_pr_comparison.PNG" width="380" alt="Exhibit 17"></a>
<br><b>Exhibit 17 — The fix, as a diff</b>
<br><sub>14 lines added, 7 removed, confined to <code>onDrop</code></sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex18"></a>
<a href="Screenshots/18_pr_opened_successfully.PNG"><img src="Screenshots/18_pr_opened_successfully.PNG" width="380" alt="Exhibit 18"></a>
<br><b>Exhibit 18 — PR #7882 opened</b>
<br><sub>Correct template followed; status Open</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex19"></a>
<a href="Screenshots/19_checks_passed_maintainer_interaction.PNG"><img src="Screenshots/19_checks_passed_maintainer_interaction.PNG" width="380" alt="Exhibit 19"></a>
<br><b>Exhibit 19 — Checks passed</b>
<br><sub>18 successful checks; maintainer edited the PR title</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex20"></a>
<a href="Screenshots/20_final_status_awaiting_review.PNG"><img src="Screenshots/20_final_status_awaiting_review.PNG" width="380" alt="Exhibit 20"></a>
<br><b>Exhibit 20 — Current status</b>
<br><sub>Open, mergeable, no conflicts, awaiting formal review</sub>
</td>
<td></td>
</tr>
</table>

---

## 🎯 Verification Checklist

| Check | Method | Status |
|:---:|---|:---:|
| Bug understood from the issue report | Read issue #7062 directly | ✅ Confirmed |
| Local environment fully working | `npm install` + `npm run dev`, dashboard reached | ✅ Confirmed |
| Faulty code located | Read `MonitorListItem.vue`, found `onDrop` | ✅ Confirmed |
| Fix scoped to one method, one file | Diff shows +14/−7 in a single file | ✅ Confirmed |
| Fix explainable line by line | Documented in README's "The Fix, Plainly" | ✅ Confirmed |
| PR follows repository's own template | Rewritten after two auto-closes, now matches | ✅ Confirmed |
| AI assistance disclosed | Explicit "AI Disclosure" section in the PR | ✅ Confirmed |
| Automated checks pass | 18 successful, 1 neutral, 0 failed | ✅ Confirmed |
| No merge conflicts | GitHub reports "can be cleanly merged" | ✅ Confirmed |
| Maintainer review / merge | Not yet completed | ⏳ Pending |

> [!NOTE]
> This project tracks a real, currently open pull request. Everything through submission and CI checks is complete and verified. The final outcome — review comments, requested changes, or merge — was still pending at the time this project was documented.

---

<div align="center">

[⬆️ Back to top](#top) &nbsp;·&nbsp; [📖 Full README](README.md) &nbsp;·&nbsp; [🔗 View PR #7882](https://github.com/louislam/uptime-kuma/pull/7882)

🔧 **[Uptime Kuma](https://github.com/louislam/uptime-kuma)** · 🐛 **[Issue #7062](https://github.com/louislam/uptime-kuma/issues/7062)** · 🧭 **[Contribution Pipeline](README.md#contribution-pipeline)**

</div>
