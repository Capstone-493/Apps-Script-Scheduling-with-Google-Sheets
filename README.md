
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
