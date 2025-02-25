#######   JOTFORM        ####


//Kelsey AND CHRIS

📌 Volunteer Sign-Up Form Requirements (GitHub Instructions for Team)

📍 Overview

The following requirements outline the fields and structure for the Volunteer Sign-Up Form. This form will collect essential details from volunteers and ensure they are categorized correctly for scheduling and matching with mentors.

📌 Volunteer Sign-Up Form Fields & Requirements

1️⃣ Personal Information (Required Fields)
	•	First Name (Required)
	•	Last Name (Required)
	•	*Contact Information (Choose One Required Option)
	•	Email (Preferred Required Field)
	•	Phone Number (Required only if Email is not provided)
	•	If JotForm does not support “either-or” validation, make Email Required instead.

2️⃣ Desired Role (Required)
	•	Volunteers must select one Desired Role from the following options:
	•	📷 Camera
	•	🔊 Audio
	•	🖥 CG (Computer Graphics)
	•	❓ “I Forgot” (Placeholder until final role is confirmed)

3️⃣ Blackout Week (Required)
	•	Field Type: Dropdown or Date Picker
	•	Purpose: Volunteers will select one week they will be unavailable.
	•	Options:
	•	If using Dropdown, predefine week-long ranges.
	•	If using Date Picker, allow selection of any 7-day range.

4️⃣ Notes / Fun Fact (Optional)
	•	Field Type: Text Input
	•	Purpose: Volunteers may provide:
	•	A fun fact about themselves.
	•	How they heard about The Community Church.
	•	Requirement: This field is optional.

📌 Next Steps for Implementation
	1.	Create the JotForm using the above field structure.
	2.	Ensure “Email” is required or, if possible, allow “Phone OR Email”.
	3.	Set up a dropdown or date picker for “Blackout Week”.
	4.	Make “Desired Role” a required multiple-choice selection.
	5.	Make “Notes / Fun Fact” an optional text input field.

🚀 Action Items for Team
	•	Create JotForm with the specified fields.
	•	Confirm Email/Phone requirement handling.
	•	Ensure Blackout Week selection is structured correctly.
	•	Review form before integrating it into the scheduling system.

Once completed, we will proceed with integrating the form data into Google Sheets & the scheduling automation system. Let me know if any adjustments are needed! 🚀





######      Sheet structure and Organization of the sheet          ############





//NIA AND AMARI










####       TRAINING          #####

//MUSTAFA AND KELSEY

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
