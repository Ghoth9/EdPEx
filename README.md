# 🎓 EdPEx Category 7 Quality Assurance & KPI Tracking System (PWA)
> **An enterprise-grade Progressive Web Application (PWA) engineered for the Faculty of Education, Chandrakasem Rajabhat University, streamlining 5-year strategic performance tracking, bi-directional Google Sheets cloud synchronization, and automated quality assurance reporting across 95 KPIs.**

[![React](https://img.shields.io/badge/React-18.x-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/TailwindCSS-3.x-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Vite](https://img.shields.io/badge/Vite-5.x-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![PWA](https://img.shields.io/badge/PWA-Installable-5A0FC8?style=for-the-badge&logo=pwa&logoColor=white)](https://web.dev/progressive-web-apps/)
[![Google Apps Script](https://img.shields.io/badge/Google%20Apps%20Script-Auto--Sync-4285F4?style=for-the-badge&logo=google-sheets&logoColor=white)](https://developers.google.com/apps-script)
[![Vercel](https://img.shields.io/badge/Deployment-Vercel%20Production-black?style=for-the-badge&logo=vercel&logoColor=white)](https://edpex-pwa-dashboard.vercel.app)

---

## 📌 Project Overview & Context

**EdPEx (Education Criteria for Performance Excellence) Category 7** measures organizational operational outcomes and overall educational performance. Educational institutions traditionally manage this through disconnected spreadsheets, resulting in data desynchronization, delayed report collection from responsible staff, and cumbersome preparation for executive board audits.

This project delivers a **centralized, cloud-synchronized performance tracking hub** that bridges academic administration with modern web technology, empowering university executives, responsible staff, and QA administrators.

<img width="1919" height="870" alt="image" src="https://github.com/user-attachments/assets/2844d49b-4448-4f53-bc4b-bc1413c69b6a" />


---

## ✨ Core Feature Highlights

### 1. 👑 Executive Strategic Dashboard (High-Level Overview)
- **5-Year Strategic Roadmap (2567 - 2571):** Trend charts comparing actual performance against the university strategic target (85%).
- **Unified Donut Chart:** Categorization into 4 key statuses: `Met Target`, `Monitor (80-99%)`, `OFI - Opportunity for Improvement (<80%)`, and `Pending`.
- **5 Category Drilldown Cards:** Instant filtering across Category 7.1 (Learners), 7.2 (Customers), 7.3 (Workforce), 7.4 (Leadership/Governance), and 7.5 (Finance/Strategy).
- **Official A4 Report & Excel Exporter:** Generate board-ready summary documents with official university letterheads and signature blocks.

<img width="1919" height="870" alt="image" src="https://github.com/user-attachments/assets/ce4f615d-7a54-4853-ab19-ba49533f07aa" />



---

### 2. 👨‍💼 Staff Portal & Evidence Cloud Uploader
- **Personalized KPI Workspace:** Filtered views displaying only KPIs assigned to the logged-in staff member with real-time completion progress (0% - 100%).
- **Dual-Mode Evidence Attachment:**
  - Direct Google Drive folder/file URL embedding.
  - Direct file drag-and-drop uploading to the Faculty Google Drive folder with automatic Sheets URL linking.
- **Deadline Countdown Alerts:** Visual countdown clocks for the 6-month and 12-month reporting milestones.

<img width="1919" height="870" alt="image" src="https://github.com/user-attachments/assets/5379e99f-58e7-4284-961d-96da7e3ccd26" />
<img width="1919" height="870" alt="image" src="https://github.com/user-attachments/assets/581bbb33-adbc-4cd1-a8a0-a1ceb0edf35e" />
<img width="1919" height="870" alt="image" src="https://github.com/user-attachments/assets/78965a13-3eda-4d54-84f8-8acbdb5a3380" />



---

### 3. 🛡️ Admin Command Center & Automation Suite
- **1-Click Google Sheets Access:** Instant navigation button to the central database spreadsheet.
- **5-Year KPI Target Manager:** Configure yearly targets (2567-2571), Thai KPI titles, units of measure, external benchmarks, and staff assignments with *Auto-DropUp* UI protection.
- **12 Staff Matrix Directory:** Personnel workload distribution cards with click-to-view KPI tags and 1-click cloud synchronization.
- **Automated Email Dispatcher:** One-click automated HTML email dispatch via Google Apps Script directly into staff `@chandra.ac.th` inboxes for pending items.
- **View-As Simulator:** Super Admin view emulator enabling instant role simulation without credential requests.

<img width="1919" height="870" alt="image" src="https://github.com/user-attachments/assets/c7aa96e9-788e-4645-b668-86f5d9382f89" />
<img width="1919" height="870" alt="image" src="https://github.com/user-attachments/assets/86e2291b-0dfa-46f4-9275-532856700965" />
<img width="1919" height="870" alt="image" src="https://github.com/user-attachments/assets/5fb128cb-5cf5-453a-b680-5b89a8d8132f" />
<img width="1919" height="870" alt="image" src="https://github.com/user-attachments/assets/8aaf4274-2866-4789-863b-d0336875d191" />


---

## 🏗️ Technical Architecture & Data Flow

```mermaid
graph TD
    subgraph Client ["Frontend Client (React 18 + PWA)"]
        UI["Tailwind CSS + Lucide Icons"]
        State["Dynamic KPI State & Year Filter"]
        Worker["Service Worker & Offline Cache"]
    end

    subgraph Roles ["Role-Based Portals"]
        Exec["Executive Dashboard (Roadmap / A4 Print)"]
        Staff["Staff Portal (Input & Drive Upload)"]
        Admin["Admin Center (Matrix / Target / Email)"]
    end

    subgraph Integration ["Cloud Integration & Automation Layer"]
        GAS["Google Apps Script (GAS) Webhook API"]
        GSheets[("Central Google Sheets Database")]
        GDrive["Faculty Evidence Storage (Google Drive)"]
        Gmail["Automated Gmail Notification Engine"]
    end

    UI --> State
    State --> Worker
    State --> Exec
    State --> Staff
    State --> Admin

    Staff --> GAS
    Admin --> GAS
    GAS <--> GSheets
    GAS --> GDrive
    GAS --> Gmail
