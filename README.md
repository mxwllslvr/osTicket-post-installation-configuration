<div align="center">

<img src="https://github.com/AnderMendoza/AnderMendoza/raw/main/assets/line-neon.gif" width="100%">
<br/><br/>

![Github Banner - osTicket Prerequisites and Installation](https://github.com/user-attachments/assets/6d1da7f1-0e10-4c99-baef-9855c11e4dc4)

<img src="https://github.com/AnderMendoza/AnderMendoza/raw/main/assets/line-neon.gif" width="100%">

</div>

# osTicket: Post-Installation Configuration Guide

This comprehensive guide covers the essential post-installation configuration steps for osTicket, the open-source help desk ticketing system, to prepare it for production use.

## Prerequisites

- [osTicket Installation and Prerequisites](https://github.com/mxwllslvr/osTicket-prerequisites-and-installation)

## Technologies and Environments

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection (mstsc)
- Internet Information Services (IIS)
- osTicket Help Desk System

## Operating Systems

- Windows 11 Home (24H2)
- Windows 10 (22H2)

## Configuration Objectives

This guide is organized into seven key sections:

- **Section 1**: [Understanding URLs and Panel Navigation (Admin vs Agent Panel)](https://docs.osticket.com/en/latest/Admin%20Panel.html)
- **Section 2**: [Role Configuration](https://docs.osticket.com/en/latest/Admin/Agents/Roles.html)
- **Section 3**: [Department Setup](https://docs.osticket.com/en/latest/Admin/Agents/Departments.html)
- **Section 4**: [Team Management](https://docs.osticket.com/en/latest/Admin/Agents/Teams.html)
- **Section 5**: [Agent and User Administration](https://docs.osticket.com/en/latest/Admin/Agents/Agents.html)
- **Section 6**: [Service Level Agreement Configuration](https://docs.osticket.com/en/latest/Admin/Manage/SLA%20Plans.html)
- **Section 7**: [Help Topic Creation](https://docs.osticket.com/en/latest/Admin/Manage/Help%20Topic.html)

---

## Configuration Steps

### Section 1: Understanding URLs and Panel Navigation
![osTicket Post-Installation Configuration Guide 1]()
![osTicket Post-Installation Configuration Guide 2]()

<table>
  <tr>
    <td>
      <img width="1000" alt="Admin Panel" src="https://github.com/user-attachments/assets/b252fd8b-8ae6-4a0b-94a2-5d0a1a8c0ffe"/>
    </td>
    <td>
      <img width="1000" alt="User Portal" src="https://github.com/user-attachments/assets/9c7229fb-fc2e-4561-aec6-e1bc71d08700"/>
    </td>
  </tr>
</table>

osTicket operates through two primary access points that serve different user types:

**Staff Control Panel (Admin/Agent Access)**
- URL: `http://localhost/osTicket/scp`
- Purpose: Administrative interface for system administrators and help desk agents
- **Bookmark Recommendation**: Save as "osTicket Agent Portal" in your VM browser

**End User Support Center**
- URL: `http://localhost/osTicket`
- Purpose: Customer-facing portal for ticket submission and status tracking
- **Bookmark Recommendation**: Save as "osTicket Support Center Portal" in your VM browser
