<a id="top"></a>
<div align="center">

# 🦈 Project 03 — Index
### Wireshark Packet Capture Case Studies
**Project 03 of 4 — Tier-2 Support Portfolio**

![Wireshark](https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white)
![Windows](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![DNS](https://img.shields.io/badge/DNS-2EA043?style=for-the-badge)
![TCP](https://img.shields.io/badge/TCP-4A3FA6?style=for-the-badge)
![ARP](https://img.shields.io/badge/ARP-C6501F?style=for-the-badge)
![Cost](https://img.shields.io/badge/Cost-Free-2EA043?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)

**Quick guide to every step and screenshot in this project.**

### [📖 Open the full README](README.md)

</div>

---

<div align="center">

| 🧩 Cases | 🖼️ Screenshots | 🎯 Filters Used | 📦 Packets Captured |
|:---:|:---:|:---:|:---:|
| **3** | **26** | **6** | **860,523** |

</div>

<p align="center">🧩 <b>Lab:</b> Windows PC on Wi-Fi ➜ Wireshark 4.6.8 · home router as gateway <code>192.168.100.1</code></p>

---

## 📑 Step Index

All 16 steps of the project, with the screenshot that shows each one.

| # | Step | Module | Result | Evidence |
|:---:|---|:---:|---|:---:|
| 1 | Select the Wi-Fi interface | 🔵 Setup | Wi-Fi chosen on the Wireshark start screen | [Exhibit 1](#ex1) |
| 2 | Start a live capture | 🔵 Setup | Capture running with no filter | [Exhibit 2](#ex2) |
| 3 | Record the local network details (`ipconfig`) | 🔵 Setup | IPv4 `192.168.100.38`, gateway `192.168.100.1` | [Exhibit 3](#ex3) |
| 4 | Trigger the failing lookup (`nslookup`) | 🟢 Case 1 | "Non-existent domain" from `192.0.2.1` | [Exhibit 4](#ex4) |
| 5 | Look at all DNS traffic (`dns`) | 🟢 Case 1 | Queries go to both `192.0.2.1` and `192.0.2.2` | [Exhibit 5](#ex5) |
| 6 | Isolate the failing query | 🟢 Case 1 | 4 queries and 4 "No such name" replies | [Exhibit 6](#ex6) |
| 7 | Read the NXDOMAIN response | 🟢 Case 1 | Flags `0x8183`, reply code 3 | [Exhibit 7](#ex7) |
| 8 | Reset the capture | 🟠 Case 2 | Capture restarted so Case 1 packets don't mix in | Exhibits [9](#ex9), [10](#ex10) |
| 9 | Generate slow-link traffic | 🟠 Case 2 | 1 GB download at about 130 KB/s | 📝 Notes only ([Exhibit 15](#ex15)) |
| 10 | Filter for retransmissions | 🟠 Case 2 | `[TCP Fast Retransmission]` rows on one stream | [Exhibit 11](#ex11) |
| 11 | Open one retransmitted packet | 🟠 Case 2 | Frame 470777: 1412-byte segment, stream 180 | [Exhibit 12](#ex12) |
| 12 | Confirm the retransmitted data field | 🟠 Case 2 | `Retransmitted TCP segment data (1412 bytes)` | Exhibits [13](#ex13), [14](#ex14) |
| 13 | Re-apply the same static IP | 🟣 Case 3 | `192.168.100.38` set by hand | [Exhibit 16](#ex16) |
| 14 | Filter for ARP activity | 🟣 Case 3 | 3 ARP Probes, then 1 Announcement | [Exhibit 17](#ex17) |
| 15 | Check for a second MAC answering | 🟣 Case 3 | 14 replies, all from one MAC | [Exhibit 18](#ex18) |
| 16 | Cross-check with the ARP table (`arp -a`) | 🟣 Case 3 | Only the gateway is a dynamic entry | [Exhibit 19](#ex19) |

---

## 🔵 Setup — Capture Environment

Exhibits 1 to 3. Click a screenshot to open it full size.

<table>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex1"></a>
<a href="screenshots/ss-01-wireshark-interface-select.PNG"><img src="screenshots/ss-01-wireshark-interface-select.PNG" width="380" alt="Exhibit 1"></a>
<br><b>Exhibit 1 — Wi-Fi interface selected</b>
<br><sub>Wireshark 4.6.8 start screen with <code>Wi-Fi</code> highlighted</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex2"></a>
<a href="screenshots/ss-02-capture-start.PNG"><img src="screenshots/ss-02-capture-start.PNG" width="380" alt="Exhibit 2"></a>
<br><b>Exhibit 2 — Live capture running</b>
<br><sub>Wi-Fi, no display filter, TCP, QUIC and UDP traffic</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex3"></a>
<a href="screenshots/ss-03-network-info.PNG"><img src="screenshots/ss-03-network-info.PNG" width="380" alt="Exhibit 3"></a>
<br><b>Exhibit 3 — <code>ipconfig</code> output</b>
<br><sub>IPv4 <code>192.168.100.38</code>, mask <code>255.255.255.0</code>, gateway <code>192.168.100.1</code></sub>
</td>
<td></td>
</tr>
</table>

---

## 🟢 Case 1 — DNS Query Failure

Exhibits 4 to 8.

<table>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex4"></a>
<a href="screenshots/ss-04-nxdomain-terminal-output.PNG"><img src="screenshots/ss-04-nxdomain-terminal-output.PNG" width="380" alt="Exhibit 4"></a>
<br><b>Exhibit 4 — <code>nslookup</code> result</b>
<br><sub>"Non-existent domain" from server <code>192.0.2.1</code></sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex5"></a>
<a href="screenshots/s-05-dns-filter-applied.PNG"><img src="screenshots/s-05-dns-filter-applied.PNG" width="380" alt="Exhibit 5"></a>
<br><b>Exhibit 5 — <code>dns</code> filter</b>
<br><sub>Queries to both DNS servers, <code>192.0.2.1</code> and <code>192.0.2.2</code></sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex6"></a>
<a href="screenshots/ss-06-dns-query-packet-detail.PNG"><img src="screenshots/ss-06-dns-query-packet-detail.PNG" width="380" alt="Exhibit 6"></a>
<br><b>Exhibit 6 — Failing query isolated</b>
<br><sub>8 packets: four queries (A, AAAA, A, AAAA) and four "No such name" replies</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex7"></a>
<a href="screenshots/ss-07-dns-nxdomain-response-detail.PNG"><img src="screenshots/ss-07-dns-nxdomain-response-detail.PNG" width="380" alt="Exhibit 7"></a>
<br><b>Exhibit 7 — NXDOMAIN response</b>
<br><sub>Frame 2059, flags <code>0x8183</code>, SOA for <code>com</code> from <code>a.gtld-servers.net</code></sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex8"></a>
<a href="screenshots/ss-08-case1-annotated-analysis.PNG"><img src="screenshots/ss-08-case1-annotated-analysis.PNG" width="380" alt="Exhibit 8"></a>
<br><b>Exhibit 8 — Case 1 analysis notes</b>
<br><sub>My notes in Hinglish. The README has an English version</sub>
</td>
<td></td>
</tr>
</table>

---

## 🟠 Case 2 — TCP Retransmission

Exhibits 9 to 15.

<table>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex9"></a>
<a href="screenshots/ss-09-capture-restart-dialog.PNG"><img src="screenshots/ss-09-capture-restart-dialog.PNG" width="380" alt="Exhibit 9"></a>
<br><b>Exhibit 9 — Restart dialog</b>
<br><sub>"Unsaved packets" prompt, Case 1 DNS packets still on screen</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex10"></a>
<a href="screenshots/ss-10-capture-restarted-fresh.PNG"><img src="screenshots/ss-10-capture-restarted-fresh.PNG" width="380" alt="Exhibit 10"></a>
<br><b>Exhibit 10 — Restarted capture</b>
<br><sub>Empty list because the Case 1 filter is still applied</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex11"></a>
<a href="screenshots/ss-11-tcp-retransmission-filter.PNG"><img src="screenshots/ss-11-tcp-retransmission-filter.PNG" width="380" alt="Exhibit 11"></a>
<br><b>Exhibit 11 — Retransmission filter</b>
<br><sub><code>[TCP Fast Retransmission]</code> rows from <code>141.95.207.211:443</code>, all <code>Len=1412</code></sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex12"></a>
<a href="screenshots/ss-12-retransmitted-packet-detail.PNG"><img src="screenshots/ss-12-retransmitted-packet-detail.PNG" width="380" alt="Exhibit 12"></a>
<br><b>Exhibit 12 — Retransmitted packet</b>
<br><sub>Frame 470777, stream index 180, segment length 1412</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex13"></a>
<a href="screenshots/ss-12a-retransmitted-packet-detai.PNG"><img src="screenshots/ss-12a-retransmitted-packet-detai.PNG" width="380" alt="Exhibit 13"></a>
<br><b>Exhibit 13 — Retransmitted segment data</b>
<br><sub><code>Retransmitted TCP segment data (1412 bytes)</code> with the payload highlighted</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex14"></a>
<a href="screenshots/ss-12b-retransmitted-packet-detail-seqack.PNG"><img src="screenshots/ss-12b-retransmitted-packet-detail-seqack.PNG" width="380" alt="Exhibit 14"></a>
<br><b>Exhibit 14 — SEQ/ACK analysis</b>
<br><sub>Window 501 (calculated 64128), server contiguous streams 7</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex15"></a>
<a href="screenshots/ss-13-case2-annotated-analysis.PNG"><img src="screenshots/ss-13-case2-annotated-analysis.PNG" width="380" alt="Exhibit 15"></a>
<br><b>Exhibit 15 — Case 2 analysis notes</b>
<br><sub>My notes in Hinglish. The only source for the download speed</sub>
</td>
<td></td>
</tr>
</table>

---

## 🟣 Case 3 — ARP Conflict Detection

Exhibits 16 to 20.

<table>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex16"></a>
<a href="screenshots/ss-17-ip-settings-manual.PNG"><img src="screenshots/ss-17-ip-settings-manual.PNG" width="380" alt="Exhibit 16"></a>
<br><b>Exhibit 16 — Manual IPv4 settings</b>
<br><sub><code>192.168.100.38</code>, DNS <code>192.0.2.1</code> and <code>192.0.2.2</code></sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex17"></a>
<a href="screenshots/ss-14-arp-conflict-probe-announcement.PNG"><img src="screenshots/ss-14-arp-conflict-probe-announcement.PNG" width="380" alt="Exhibit 17"></a>
<br><b>Exhibit 17 — ARP probes and announcement</b>
<br><sub>Three probes, then one <code>ARP Announcement for 192.168.100.38</code></sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex18"></a>
<a href="screenshots/ss-15-arp-conflict-check.PNG"><img src="screenshots/ss-15-arp-conflict-check.PNG" width="380" alt="Exhibit 18"></a>
<br><b>Exhibit 18 — ARP reply check</b>
<br><sub>14 replies, all from <code>00:24:d7:28:69:f8</code></sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex19"></a>
<a href="screenshots/ss-18-arp-table-crosscheck.PNG"><img src="screenshots/ss-18-arp-table-crosscheck.PNG" width="380" alt="Exhibit 19"></a>
<br><b>Exhibit 19 — <code>arp -a</code> table</b>
<br><sub>One dynamic entry: the gateway at <code>04-8c-16-67-f4-9a</code></sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex20"></a>
<a href="screenshots/ss-16-case3-annotated-analysis.PNG"><img src="screenshots/ss-16-case3-annotated-analysis.PNG" width="380" alt="Exhibit 20"></a>
<br><b>Exhibit 20 — Case 3 analysis notes</b>
<br><sub>My notes in Hinglish. The README has an English version</sub>
</td>
<td></td>
</tr>
</table>

---

## 📈 Capture-Wide Analysis & Saved Capture

Exhibits 21 to 26. The ⚠️ items were captured while Wireshark was still loading, so they are an overview only.

<table>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex21"></a>
<a href="screenshots/ss-19-protocol-hierarchy.PNG"><img src="screenshots/ss-19-protocol-hierarchy.PNG" width="380" alt="Exhibit 21"></a>
<br><b>Exhibit 21 — Protocol Hierarchy</b>
<br><sub>860,523 frames, about 728 MB. TCP is 87.2% of packets</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex22"></a>
<a href="screenshots/ss-20-conversations-tcp.PNG"><img src="screenshots/ss-20-conversations-tcp.PNG" width="380" alt="Exhibit 22"></a>
<br><b>Exhibit 22 — Conversations ⚠️</b>
<br><sub>752 TCP and 1,557 UDP conversations. Window still says "Loading"</sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex23"></a>
<a href="screenshots/ss-21-io-graph.PNG"><img src="screenshots/ss-21-io-graph.PNG" width="380" alt="Exhibit 23"></a>
<br><b>Exhibit 23 — I/O Graph ⚠️</b>
<br><sub>"All Packets" and "TCP Errors" (<code>tcp.analysis.flags</code>), one spike</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex24"></a>
<a href="screenshots/ss-22-save-pcap-dialog.PNG"><img src="screenshots/ss-22-save-pcap-dialog.PNG" width="380" alt="Exhibit 24"></a>
<br><b>Exhibit 24 — Save dialog</b>
<br><sub>An earlier full-capture file is listed. New name: <code>sample-capture</code></sub>
</td>
</tr>
<tr>
<td align="center" valign="top" width="50%">
<a id="ex25"></a>
<a href="screenshots/ss-23-pcap-files-folder.PNG"><img src="screenshots/ss-23-pcap-files-folder.PNG" width="380" alt="Exhibit 25"></a>
<br><b>Exhibit 25 — Documents folder</b>
<br><sub><code>sample-capture</code>, modified 9/15/2026 5:43 PM</sub>
</td>
<td align="center" valign="top" width="50%">
<a id="ex26"></a>
<a href="screenshots/ss-24-project-summary-doc.PNG"><img src="screenshots/ss-24-project-summary-doc.PNG" width="380" alt="Exhibit 26"></a>
<br><b>Exhibit 26 — Project summary notes</b>
<br><sub>My notes in Hinglish. Tools used: Wireshark, Command Prompt, adapter settings</sub>
</td>
</tr>
</table>

---

## 🎯 Verification Checklist

| Check | Method | Layer | Status |
|:---:|---|---|:---:|
| DNS failure proven | `dns` filters, reply code 3 in the flags | DNS | ✅ Confirmed |
| TCP retransmissions flagged | `tcp.analysis.retransmission` | TCP | ✅ Confirmed |
| ARP probe and announcement seen | `arp` filter, `arp -a` cross-check | ARP | ✅ Confirmed |
| Download speed and "hundreds" of packets | My notes only | TCP | 📝 Notes only |
| Where the packet loss happened | Not shown by a client-side capture | TCP | ⚠️ Inferred |
| Conversations and I/O Graph | Statistics windows | Overview | ⚠️ Captured while loading |
| A real IP conflict | Needs a second device | ARP | ❌ Not reproduced |

> [!NOTE]
> Case 3 shows Windows' duplicate-address check (ARP Probe and Announcement), not a real conflict, because only one device was used. Every result above links to a screenshot, and items with no screenshot are marked.

---

<div align="center">

[⬆️ Back to top](#top) &nbsp;·&nbsp; [📖 Full README](README.md)

🦈 **[Wireshark](https://www.wireshark.org)** · 🪟 **[Windows](https://www.microsoft.com/windows)** · 📚 **[RFC 5227 — IPv4 Address Conflict Detection](https://datatracker.ietf.org/doc/html/rfc5227)** · 🧭 **[Troubleshooting Pipeline](README.md#troubleshooting-pipeline)**

</div>
