# FlutterFlow
🧩 Step-by-Step Signup Setup in FlutterFlow (with Supabase)
1️⃣ Enable Authentication in Supabase
Go to Supabase:

Click on your project → Go to Authentication → Providers

Enable Email → Save

2️⃣ Connect Supabase to FlutterFlow
In FlutterFlow:

Go to Settings > Authentication

Select Supabase

Enter:

Supabase URL

Anon Key

[Get both from Supabase → Project Settings → API]

✅ Test Connection → Should say “Connected”



==============================================================================================================================================================================================================
 Step-by-Step — Signup Button in FlutterFlow (New UI)
1️⃣ Prepare the Input Fields
Email Field

Select the email TextField.

In the Properties panel → set:

Label: Email

Hint Text: Enter your email

Keyboard Type: Email

Field Name: emailField (important — this makes it selectable in actions)

Password Field

Select the password TextField.

Properties:

Label: Password

Hint Text: Enter your password

Obscure Text ✅

Field Name: passwordField

Confirm Password Field (optional, just for UI check)

Field Name: confirmPasswordField

2️⃣ Add the First Action — Supabase Create Account
Select your Signup button.

Go to Actions tab → click + Add Action.

Choose:

Supabase → Create Account

Fill Required Fields:

Email Field → select emailField

Password Field → select passwordField

Turn OFF “Navigate after signup” (we will add navigation manually later).

If you skip either Email Field or Password Field, FlutterFlow shows “Action configuration not defined” — so make sure these are linked.

3️⃣ Add the Second Action — Supabase Insert Row
Still in the Actions panel, click + Add Action again.

Choose:

Supabase → Insert Row

Table: select your table (e.g., profiles or students).

Map only the needed columns:

email → from emailField

name → from a name TextField if you have one.

Do NOT map id — Supabase fills it automatically from auth.uid().

4️⃣ Add Navigation
Add another action:

Navigation → Navigate to Page

Select your home/dashboard page.

5️⃣ Run & Test
Preview the app.

Enter email & password, click Signup.

Check:

Supabase → Authentication → Users (new user should appear).

Supabase → Table Editor → profiles
