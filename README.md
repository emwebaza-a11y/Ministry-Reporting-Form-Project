# Ministry-Reporting-Form-Project
Potential new reporting Form website code storage.

Plans:
1
Settle open requirements
Group the 28 stories into four chunks: accounts, the submission form, quarters and carry-over, and admin reporting.
2
Design the data model
Sketch your tables on paper first. A likely shape: profiles (first/last name, admin flag), submissions (user, quarter), organizations (name, location, relationship level, new-to-YFC flag, contact name and title), ministry events (type, linked organization), and comments. Deciding how organizations persist across quarters is the most important design choice in the project.
3
Create the Supabase project and login
Make a Supabase project, turn on email and password sign-in, and set up the profiles table so each new account stores a first and last name. Add a way to mark certain accounts as admins. This covers stories #10, #11, and #15.
4
Build the tables and access rules
Create the tables from your design, then write Row Level Security rules: users can see and edit only their own data, admins can see everything. Test these early with two dummy accounts, because the security story (#16) is easiest to get right at the start and hard to retrofit.
5
Build the site skeleton and hosting
Choose how to build the front end. Plain HTML and JavaScript is simplest for a small project, and a framework like React is an option if you want more structure. Connect it to Supabase with their JavaScript library, add sign-up and login pages, and deploy to a free host like Netlify, Vercel, or Cloudflare Pages so you have a live link from the start.
6
Build the user submission form
Add the form: quarter selection, adding as many organizations as needed, relationship level choices, contact and title, event logging with the fixed event types, and the comments box. Then add the carry-over logic so starting a new quarter copies the right data and clears the rest. This covers most of stories #2-4, #7, #14, #19-25, and #28.
7
Build the admin side
Create admin-only pages: submission lists with submitter names, counts by relationship level and event type, the new-organization view, the one-click quarterly report with spreadsheet (CSV) export, and the email notification on submission. This covers #8, #9, #12, #13, #17, #18, #29-31, and is where Supabase's SQL queries pay off.
8
Test with real users and refine
Have a few of the actual non-technical users try the site with no instructions, and note where they get stuck. Fix confusing wording, then re-check the access rules and test the quarter rollover with realistic data before launch.
