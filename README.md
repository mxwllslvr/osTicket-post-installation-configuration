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

<table>
  <tr>
    <td>
      <img width="1000" alt="Admin Panel View" src="https://github.com/user-attachments/assets/6eb7584e-d271-4898-bc03-b7f9ca96ae4b"/>
    </td>
    <td>
      <img width="1000" alt="Agent Panel View" src="https://github.com/user-attachments/assets/fd5c7c79-6fb8-4e88-a9b9-2e85f71ebf61"/>
    </td>
  </tr>
</table>

**Panel Navigation**

Within the Staff Control Panel, you'll work with two distinct interfaces:

- **Admin Panel**: Backend configuration interface for system administrators to manage settings, users, and system parameters
- **Agent Panel**: Operational interface for help desk agents to process and resolve tickets

**Panel Switching**: Toggle between panels using the panel name indicator in the top-right corner of the interface. This guide will frequently require switching between both panels.

### Section 2: Role Configuration

<table>
  <tr>
    <td>
      <img width="996" alt="Role Creation" src="https://github.com/user-attachments/assets/df8905b9-0e3d-430e-8885-08588f3e6030"/>
    </td>
    <td>
      <img width="1000" alt="Role Setup" src="https://github.com/user-attachments/assets/a8b2e1e6-bb7d-44f9-8d95-03e1a2c11848"/>
    </td>
  </tr>
</table>

Roles define permission levels and access rights within osTicket. Let's create a comprehensive administrative role:

**Creating the Supreme Admin Role**
1. Navigate to **Admin Panel** (verify "Agent Panel" displays in top-right)
2. Access **Agents → Roles → + Add New Role**
3. Set **Role Name**: "Supreme Admin"
4. Click the **Permissions** tab to configure access rights

<table>
  <tr>
    <td>
      <img width="1000" alt="Ticket Permissions" src="https://github.com/user-attachments/assets/a1965a84-0e17-4795-8cea-d20e615f2e57"/>
    </td>
    <td>
      <img width="1000" alt="Task Permissions" src="https://github.com/user-attachments/assets/f08a9c02-64fb-43d7-9d4f-b31b96b8e978"/>
    </td>
  </tr>
</table>

**Permission Configuration**
- **Tickets Section**: Enable all permission checkboxes, then proceed to **Tasks**
- **Tasks Section**: Enable all permission checkboxes, then proceed to **Knowledgebase**

<table>
  <tr>
    <td>
      <img width="1000" alt="Knowledge Permissions" src="https://github.com/user-attachments/assets/9572c073-cd09-4830-bf9e-8a625174c555"/>
    </td>
    <td>
      <img width="1000" alt="Role Confirmation" src="https://github.com/user-attachments/assets/309c26d3-2617-4c07-b935-52435e386fa3"/>
    </td>
  </tr>
</table>

- **Knowledgebase Section**: Enable the available permission checkbox
- Click **Add Role** to finalize creation

**Result**: The Supreme Admin role is now available for assignment, providing comprehensive system access for demonstration purposes.

### Section 3: Department Setup

<table>
  <tr>
    <td>
      <img width="1000" alt="Department Creation" src="https://github.com/user-attachments/assets/fc13e32e-8127-4037-813c-bee039b3c6c8"/>
    </td>
    <td>
      <img width="1000" alt="Department Configuration" src="https://github.com/user-attachments/assets/c811a5ca-7646-49ee-bfb1-5be7f2ca4c69"/>
    </td>
  </tr>
</table>

Departments organize agents and tickets based on functional areas or expertise domains.

**Creating the SysAdmins Department**
1. In **Admin Panel**, navigate to **Agents → Departments → + Add New Department**
2. **Settings Configuration**:
   - **Parent**: Maintain "Top-Level Department" selection
   - **Department Name**: "SysAdmins"
3. **Note**: The Access tab configuration will be completed after agent creation
4. Scroll down and click **Create Dept**

<p>
<img width="950" alt="Department Success" src="https://github.com/user-attachments/assets/0d4b64e2-148d-4889-9711-d1cb122557f7"/>
</p>

**Confirmation**: The SysAdmins Department has been successfully established and is ready for agent assignment.


### Section 4: Team Management

<table>
  <tr>
    <td>
      <img width="1000" alt="Team Creation" src="https://github.com/user-attachments/assets/27583949-d847-477c-a6c8-af30529204bb"/>
    </td>
    <td>
      <img width="1000" alt="Team Setup" src="https://github.com/user-attachments/assets/0962e05e-297f-4f90-a6a8-6b10711565b1"/>
    </td>
  </tr>
</table>

Teams enable cross-departmental collaboration for specialized support areas.

**Creating the Online Banking Team**
1. From **Admin Panel**, access **Agents → Teams → + Add New Team**
2. **Team Name**: "Online Banking"
3. **Member Assignment**: Defer until agent creation is complete
4. Click **Create Team**

<p>
<img width="750" alt="Registration Settings" src="https://github.com/user-attachments/assets/c5f92127-fa03-4f0f-a353-75419901fb3d"/>
</p>

**User Registration Configuration**
To streamline ticket creation for end users:
1. Navigate to **Admin Panel → Settings → Users**
2. Under **Authentication Settings**, uncheck **"Require registration and login to create tickets"**
3. Click **Save Changes**

This setting allows anonymous ticket submission, improving accessibility for end users.



### Section 5: Agent and User Administration

<table>
  <tr>
    <td>
      <img width="1000" alt="Agent Creation" src="https://github.com/user-attachments/assets/06d0c399-a9fc-46da-8915-75f2c41a06c4"/>
    </td>
    <td>
      <img width="1000" alt="Agent Details" src="https://github.com/user-attachments/assets/5dce60a7-b2fc-4d88-8775-48b98666cf6f"/>
    </td>
  </tr>
</table>

**Creating Agent: Jane Doe**
1. In **Admin Panel**, navigate to **Agents → Agents → + Add New Agent**
2. **Account Information**:
   - **Full Name**: Jane Doe
   - **Email**: jane.doe@helpdesk.com (demonstration email)
   - **Username**: jane_doe
3. Click **Set Password**

<p>
<img width="750" alt="Password Configuration" src="https://github.com/user-attachments/assets/3b2e7fea-5741-4422-9643-5e7e3de070e0"/>
</p>

**Password Setup Process**
1. Uncheck **"Send the agent a password reset email"**
2. Set password: "Password1"
3. Uncheck **"Require password change at next login"**
4. Click **Update**

<table>
  <tr>
    <td>
      <img width="1000" alt="Jane Access Settings" src="https://github.com/user-attachments/assets/b6633d6b-a9e6-47a1-86e1-cfca4039d2e4"/>
    </td>
    <td>
      <img width="1000" alt="Jane Team Assignment" src="https://github.com/user-attachments/assets/1fe1b914-dfcc-4d60-a19e-bd18b256c4e7"/>
    </td>
  </tr>
</table>

**Access and Team Assignment**
- **Access → Primary Department**: SysAdmins
- **Role/Permissions**: Supreme Admin
- **Teams**: Online Banking
- Click **Create**

<table>
  <tr>
    <td>
      <img width="1000" alt="John Creation" src="https://github.com/user-attachments/assets/804c5041-1792-4e1d-b7b0-5fc0eee254fe"/>
    </td>
    <td>
      <img width="1000" alt="John Details" src="https://github.com/user-attachments/assets/812bdb1b-2181-473e-b3cc-1ab8cf8d2a6d"/>
    </td>
  </tr>
</table>

**Creating Agent: John Doe**
1. Click **+ Add New Agent**
2. **Account Information**:
   - **Full Name**: John Doe
   - **Email**: john.doe@helpdesk.com
   - **Username**: john_doe
3. Apply the same password configuration process as with Jane

<table>
  <tr>
    <td>
      <img width="1000" alt="John Access Settings" src="https://github.com/user-attachments/assets/4a6164f2-9c06-4a10-bb1f-e4eed2c5b5c3"/>
    </td>
    <td>
      <img width="1000" alt="John Final Setup" src="https://github.com/user-attachments/assets/2a3ff3f5-ada6-4e58-8f82-d897d865fb9c"/>
    </td>
  </tr>
</table>

**John's Access Configuration**
- **Access → Primary Department**: Support
- **Role/Permissions**: Expanded Access
- Click **Create**

**Note**: Expanded Access provides sufficient permissions for ticket handling while maintaining appropriate restrictions.

<table>
  <tr>
    <td>
      <img width="1000" alt="User Creation" src="https://github.com/user-attachments/assets/5697db2d-6cc5-4401-a209-e9a334981215"/>
    </td>
    <td>
      <img width="1000" alt="User Setup" src="https://github.com/user-attachments/assets/5d6d66ac-814b-40fb-97ca-90522c755ab8"/>
    </td>
  </tr>
</table>

**Creating End User: Karen**
1. Switch to **Agent Panel** (click "Admin Panel" in top-right)
2. Navigate to **Users → + Add User**
3. **User Information**:
   - **Email**: karen@lonpacific.com
   - **Full Name**: Karen
4. Click **Add User**

<p>
<img width="750" alt="User Confirmation" src="https://github.com/user-attachments/assets/11678d78-05de-4dab-8ca4-c4d4b01466f8"/>
</p>

Karen is now registered as an end user and can submit tickets through the support portal.

### Section 6: Service Level Agreement Configuration

<p>
<img width="750" alt="SLA Overview" src="https://github.com/user-attachments/assets/8e58d223-6c8c-4d15-b701-e46897bb6fd6"/>
</p>

Service Level Agreements establish response and resolution timeframes for different ticket priorities.

**Accessing SLA Configuration**
- Switch to **Admin Panel**
- Navigate to **Manage → SLA → + Add New SLA Plan**

<p>
<img width="750" alt="Sev-A Configuration" src="https://github.com/user-attachments/assets/8a46f7b9-9598-4943-9174-00234b34b119"/>
</p>

**Critical Priority SLA (Sev-A)**
- **Name**: Sev-A
- **Grace Period**: 1 hour
- **Schedule**: 24/7
- Click **Add Plan**

<p>
<img width="750" alt="Sev-B Configuration" src="https://github.com/user-attachments/assets/c8e1583e-d974-4411-9fe6-5ab960941759"/>
</p>

**High Priority SLA (Sev-B)**
- **Name**: Sev-B
- **Grace Period**: 4 hours
- **Schedule**: 24/7
- Click **Add Plan**

<p>
<img width="750" alt="Sev-C Configuration" src="https://github.com/user-attachments/assets/a60a7a72-b34f-4d1c-a265-57be2d2342f5"/>
</p>

**Normal Priority SLA (Sev-C)**
- **Name**: Sev-C
- **Grace Period**: 8 hours
- **Schedule**: Monday - Friday, 8am - 5pm with Holidays
- Click **Add Plan**

<p>
<img width="975" alt="SLA Confirmation" src="https://github.com/user-attachments/assets/cf93acda-9e8b-446c-bcfe-ae4bac75c61d"/>
</p>

**Result**: Three-tier SLA structure established, providing appropriate response expectations for varying ticket severities.

### Section 7: Help Topic Creation

<p>
<img width="750" alt="Help Topics Overview" src="https://github.com/user-attachments/assets/2295446d-68e8-41f6-aa7c-cbbb1f2f0c1a"/>
</p>

Help Topics categorize incoming tickets and can trigger automatic routing and priority assignments.

**Accessing Help Topic Configuration**
- Remain in **Admin Panel**
- Navigate to **Manage → Help Topics → + Add New Help Topic**

<table>
  <tr>
    <td>
      <img width="1000" alt="Business Critical Topic" src="https://github.com/user-attachments/assets/57a0c188-9688-47e5-8043-f6adb030b20b" />
    </td>
    <td>
      <img width="1000" alt="PC Issues Topic" src="https://github.com/user-attachments/assets/e17ba0ed-dc31-4012-8d19-71097cc923f3" />
    </td>
  </tr>
</table>

**Creating Business Critical Outage Topic**
- **Topic**: Business Critical Outage
- **Parent Topic**: Report a Problem
- Click **Add Topic**

**Creating Personal Computer Issues Topic**
- **Topic**: Personal Computer Issues
- **Parent Topic**: Report a Problem
- Click **Add Topic**

<table>
  <tr>
    <td>
      <img width="1000" alt="Equipment Request Topic" src="https://github.com/user-attachments/assets/ff0e79ac-72af-4843-b6c9-6b2217231aea" />
    </td>
    <td>
      <img width="1000" alt="Password Reset Topic" src="https://github.com/user-attachments/assets/896e8e56-21b2-49f0-90f1-76d82e009dea" />
    </td>
  </tr>
</table>

**Creating Equipment Request Topic**
- **Topic**: Equipment Request
- **Parent Topic**: General Inquiry
- Click **Add Topic**

**Creating Password Reset Topic**
- **Topic**: Password Reset
- **Parent Topic**: Report a Problem
- Click **Add Topic**

<table>
  <tr>
    <td>
      <img width="1000" alt="Other Topic" src="https://github.com/user-attachments/assets/982a99ad-addc-41a0-90dc-d6412a80a4ec" />
    </td>
    <td>
      <img width="1000" alt="Topics Overview" src="https://github.com/user-attachments/assets/115c6b7f-b5a7-4cef-bb84-44b7286827e1" />
    </td>
  </tr>
</table>

**Creating General Other Topic**
- **Topic**: Other
- **Parent Topic**: General Inquiry
- Click **Add Topic**

**Final Result**: A comprehensive help topic structure that supplements osTicket's default categories, providing users with clear categorization options for various support requests.

<img src="https://github.com/AnderMendoza/AnderMendoza/raw/main/assets/line-neon.gif" width="100%">

<div align="center"> <img src="https://github.com/user-attachments/assets/2eebaf6f-f0f7-4521-9ef0-1bc83ac1ccfe" width="75%"> </div>

<img src="https://github.com/AnderMendoza/AnderMendoza/raw/main/assets/line-neon.gif" width="100%">

## Conclusion

This post-installation configuration has successfully established:

✅ **Administrative Infrastructure**
- Supreme Admin role with comprehensive permissions
- SysAdmins department for specialized system support
- Online Banking team for cross-functional collaboration

✅ **User Management**
- Two operational agents (Jane and John) with appropriate access levels
- End user (Karen) ready for ticket submission
- Streamlined registration settings for improved accessibility

✅ **Service Standards**
- Three-tier SLA framework (Sev-A: 1hr, Sev-B: 4hr, Sev-C: 8hr)
- Appropriate scheduling for business operations

✅ **Ticket Classification**
- Comprehensive help topic structure for effective ticket routing
- Categories covering critical outages, routine requests, and general inquiries

**Next Steps**: The system is now ready for operational ticket management. The next phase will involve practical ticket lifecycle management, demonstrating the creation, assignment, and resolution of support requests using the configured infrastructure.

Remember to stop your Azure virtual machines when not in use to optimize costs.

---

<div align="center">

<a href="https://www.github.com/mxwllslvr">- BACK TO MAIN PAGE -</a>

</div>


