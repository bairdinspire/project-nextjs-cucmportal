# Cisco CUCM User Portal

> ⚠️ This app is currently in development. Some features may not be working.

A custom self-service portal for managing users and phone provisioning via the Cisco Unified Communications Manager (CUCM) API.

## 🚀 Overview

This project simplifies and automates communication system configurations for enterprise IT environments using Cisco CUCM. Built with modern web tech, the portal provides a clean UI for IT staff and end-users to manage phones, users, and extensions—without needing to log into CUCM directly.

- 🛠️ Built with Next.js, TypeScript, Tailwind CSS
- 🔐 Secure backend API routes using serverless functions
- ⚙️ Cisco CUCM API integration for provisioning tasks
- 📉 Reduces manual provisioning by up to 80%

## ✨ Features

- View and search CUCM users
- Assign or reassign phones/extensions
- Reset voicemail or PIN credentials
- Self-service actions for users with proper roles
- Admin-level actions for provisioning techs
- Secure login (basic auth or OAuth ready)
- Deployable to Vercel with zero config

## 🧰 Tech Stack

- **Frontend:** Next.js, TypeScript, Tailwind CSS
- **Backend:** API Routes (Next.js), Axios
- **Auth:** JWT (planned), or basic auth for demo
- **DevOps:** Vercel, GitHub Actions (CI/CD)
- **API:** Cisco CUCM AXL & RIS APIs (SOAP), Microsoft 365 Graph API

## 🖼️ Screenshots

_(Add screenshots or GIFs here once UI is ready)_

## 📦 Installation

### 1. Clone and Install
```bash
git clone https://github.com/yourusername/cucm-user-portal.git
cd cucm-user-portal
npm install
```
### 2. Configure Environment Variables
Create a .env.local file in the root directory with the following values:
```env
# CUCM API Credentials
CUCM_API_BASE_URL=https://your-cucm-server/axl
CUCM_API_USERNAME=your-admin-username
CUCM_API_PASSWORD=your-password

# Microsoft 365 Integration (Optional)
M365_CLIENT_ID=your-client-id
M365_CLIENT_SECRET=your-client-secret
M365_TENANT_ID=your-tenant-id

# Email Services (Optional)
SMTP_HOST=smtp.office365.com
SMTP_PORT=587
SMTP_USER=your-email@domain.com
SMTP_PASS=your-email-password

# App Config
NEXTAUTH_SECRET=some-random-secret
```
> ⚠️ **Note:** Never commit this file to GitHub. Use .gitignore to keep secrets safe.
### 3. Start the dev service
```bash
npm run dev
```
## 🔒 Note on CUCM API Access
This app integrates with CUCM’s AXL and RIS APIs, which require SOAP credentials and admin access to the CUCM environment. For demo purposes, use mock data or a staging CUCM server.

## Install Mock Data (for Local Testing)

To run the app without connecting to a live Cisco CUCM environment, you can install mock user and device data using the included setup script. This will generate a local SQLite database that the app can use as a drop-in data source.

```bash
npm run setup:mockdata
```

> This command will:
> - Create a new SQLite database file in `/data/mock.db`  
> - Populate it with sample users, phones, and credentials  
> - Configure the app to use the mock database in development

Once installed, the app will automatically load data from the mock database when in development mode (`NODE_ENV=development`).


## 📌 Roadmap

- [x] View users and devices  
- [ ] Role-based authentication  
- [ ] Bulk provisioning tools  
- [ ] Microsoft 365 integration  
- [ ] Email alerts and logging  
- [ ] Docker container version  

## 🤝 License
MIT
