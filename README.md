
######      Sheet structure and Organization of the sheet          ############





//NIA AND AMARI


📌 Instructions for the Sheet Organization Team

📍 Overview

The Sheet Organization Team is responsible for structuring Google Sheets to ensure seamless integration between JotForm data intake and mentor input, while maintaining clarity for future automation. The goal is to keep things visually organized, prevent errors, and set up a clean foundation for scripting later.

📌 Key Responsibilities

1️⃣ Volunteer Data Sheet (JotForm Integration)
	•	📄 Sheet Name: "Volunteers_Main" (Main Sheet where JotForm submissions land)
	•	This will act as the primary intake sheet, receiving raw submissions from JotForm.
	•	JotForm Team & Sheet Team should collaborate to make sure:
	•	All required form fields translate directly into column headers.
	•	Column names match exactly to avoid issues when retrieving data via Apps Script.
	•	The format remains consistent across all entries.

✅ Suggested Columns for “Volunteers_Main” Sheet:

Submission ID	First Name	Last Name	Email	Phone	Role	Blackout Week	Notes
(Auto-Gen)	John	Doe	john@email.com	(123) 456-7890	Camera	03-10-2025	Loves photography

🔹 Flair Tip: Add a header row with color formatting for easy visibility.
🔹 Automation Readiness: Leave the first row intact for Apps Script referencing.

2️⃣ Mentor Data Sheet (Manual Input by Director)
	•	📄 Sheet Name: "Mentors_Main"
	•	Unlike the volunteer sheet, mentors will not fill this out themselves—instead, the Director will manage this manually to maintain consistency and avoid clutter.

✅ Suggested Columns for “Mentors_Main” Sheet:

Mentor Name	Email	Phone	Role	Blackout Dates	Notes
Jane Smith	mentor@email.com	(987) 654-3210	Audio	03-10-2025	Prefers morning sessions

🔹 Flair Tip: Use a separate color theme from "Volunteers_Main" to distinguish mentor entries.
🔹 Automation Readiness: Keep column headers structured the same way as Volunteers, making it easy to match fields later.

3️⃣ Structuring Sheets for Future Automation

Once the main sheets ("Volunteers_Main" and "Mentors_Main") are ready, Apps Script will handle extracting & organizing the data dynamically.
	•	A secondary set of sheets will be created via script, where each volunteer entry gets expanded into role-specific sheets.
	•	Example:
	•	"Camera Team" Sheet: Automatically populated from "Volunteers_Main" whenever a new Camera volunteer is added.
	•	"Audio Team" Sheet: Same process for Audio volunteers.

🛠 The Sheet Team’s Main Task Now:
✅ Ensure "Volunteers_Main" is ready to directly receive JotForm data.
✅ Ensure "Mentors_Main" is structured for easy manual input.
✅ Keep formatting clean & easy to read for automation compatibility.

📌 Action Items for Sheet Team
	•	Set up "Volunteers_Main" to match the JotForm structure.
	•	Set up "Mentors_Main" for Director-only input.
	•	Add minor formatting to improve visibility.
	•	Test by entering sample data to see how it looks before automation begins.

Once the sheets are ready, we’ll move forward with Apps Script development to automate role-based sheet extraction & scheduling! 🚀







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

###INSTRUCTIONS FOR SCRIPTING###

📌 Core Scripts You Will Need in Apps Script
1️⃣ Volunteer-to-Mentor Matching Script (Main Script)
🔹 Purpose:

Matches Volunteers (from Volunteers_Main) with Mentors (from Mentors_Main) based on Role.
Ensures mentors are not scheduled during their blackout dates.
Generates a final training schedule, categorized into separate role-based sheets within a new Google Sheet.
Runs automatically every Monday at 8 AM for the upcoming training sessions.
Sends email notifications with the training details.
🔹 Trigger Type:
✅ Time-based trigger (Runs every Monday morning).

🔹 Expected Output:
📁 Final Google Sheet ("Volunteer-Mentor Schedule")
📄 "Camera Team" | "Audio Team" | "CG Team" | "Lights Team"

2️⃣ Volunteer Profile Generation Script
🔹 Purpose:

Every time a new volunteer signs up, this script creates an individual sheet within the Volunteers file.
Stores detailed information about the volunteer (e.g., Name, Contact, Role, Availability, Notes).
Allows for manual mentor assignments later (if needed).
🔹 Trigger Type:
✅ On Form Submit Trigger (Runs when a new entry is added to "Volunteers_Main").
✅ On Edit Trigger (Runs if data changes).

🔹 Expected Output:
📁 Inside the "Volunteers" Google Sheet
📄 Main Sheet (Volunteers_Main) stays intact.
📄 Individual profile sheets for each volunteer ("John_Doe_Profile", "Jane_Smith_Profile").

3️⃣ Mentor Availability Update Script
🔹 Purpose:

Allows mentors to update their blackout dates using a JotForm submission.
Updates only the "Blackout Dates" column in "Mentors_Main", instead of creating new entries.
🔹 Trigger Type:
✅ On Form Submit Trigger (Runs when a mentor submits an availability update via JotForm).

🔹 Expected Output:

📄 Mentors_Main stays up-to-date with blackout dates.
Ensures no duplicate mentor entries while allowing updates.
📌 Optional Enhancements (Future Considerations)
4️⃣ Email Notification Script
💡 This can be built into the Main Matching Script or handled separately.
🔹 Sends weekly emails on Monday morning to volunteers and mentors.
🔹 Includes training dates, assigned mentors, and location details.

🔹 Trigger Type:
✅ Time-based trigger (Monday 8 AM, after schedule is created).


