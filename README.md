# Apps-Script-Scheduling-with-Google-Sheets#

## 📌 Overview
The **Volunteer Training Scheduling System** is an automated solution for **matching volunteers with mentors** for scheduled training sessions. This system dynamically schedules participants based on **roles and availability**, ensuring an organized and structured training workflow.

## 📅 How It Works
1. **Volunteer Sign-Up (Google Form & Sheet)**
   - Volunteers sign up for **one of four roles**:
     - 📷 **Camera**
     - 💡 **Lights**
     - 🖥️ **CG (Computer Graphics)**
     - 🔊 **Audio**
   - They specify their **availability start date**.
   - Optional: Volunteers may provide **blackout dates** (to be integrated later).

2. **Mentor Availability (Google Sheet)**
   - Mentors are **assigned to one of the four roles**.
   - They are **always available** for training unless a **blockout date** is specified.

3. **Automated Weekly Scheduling**
   - **First training session:** **Thursday**.
   - **Second training session:** **Sunday**.
   - The system schedules **each volunteer** for these sessions starting from their **availability date**.

4. **Dynamic Matching System**
   - Volunteers are matched **only with mentors in their specified role**.
   - If multiple mentors exist, the first available one is assigned.
   - If no mentor is found, the volunteer is listed as **unassigned**.

5. **Finalized Weekly Schedule**
   - A new **Google Sheets file** is created **each week**.
   - **Each role gets its own sheet** inside the file (e.g., "Camera Team", "Audio Team").
   - The sheets include:
     - Volunteer Name, Phone, Email
     - Matched Mentor Name, Phone, Email
     - Training Dates (Thursday & Sunday)

6. **Automated Email Notifications**
   - Every **Monday morning**, an email is sent to all participants.
   - The email contains:
     - Their training schedule for the week.
     - The name & contact of their assigned mentor.
     - Additional details for the session.

## 📌 Features (Current & Future)
- ✅ **Role-based matching** for volunteers and mentors.
- ✅ **Automated weekly scheduling**.
- ✅ **New sheets for each role** inside the final schedule file.
- ✅ **Automated Google Sheet creation**.
- 🛠 **Blackout date filtering** (Planned).
- 🛠 **Custom mentor-priority ranking** (Planned).
- 🛠 **Advanced email customization** (Planned).

## 📌 Technology Stack
- **Google Sheets** (Data Storage)
- **Google Apps Script** (Automation)
- **Gmail API** (Email Notifications) *(Future)*

## 📌 Setup & Integration
1. **Clone this repository**
   ```sh
   git clone https://github.com/YOUR-USERNAME/volunteer-scheduling.git
