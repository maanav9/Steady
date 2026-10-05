STEADY: putting it on her iPhone home screen

Her details are inside index.html only in encrypted form. They can't be read without the four-word
setup code, which is NOT in these files. Keep the code private and give it to her separately.

1. PUBLISH (about 10 minutes, easiest on a laptop)
   a. Sign in at github.com and create a new repository, e.g. "steady".
      A free account publishes Pages from a public repository. The files contain nothing personal in
      readable form, and everything she records stays encrypted on her phone, never in the repository.
   b. Choose "uploading an existing file", drag in every file from this folder, then Commit changes.
   c. Settings > Pages: "Deploy from a branch", branch "main", folder "/ (root)", Save.
   d. A minute or two later it's live at https://YOUR-USERNAME.github.io/steady/

2. ON HER IPHONE
   Open that link in Safari, tap Share > Add to Home Screen, then open Steady from the Home Screen.
   She enters the four-word setup code once, checks her details, and chooses a passcode.
   Use the home-screen icon from then on: Safari tabs and the home-screen app keep separate storage.

3. FITBIT (optional, about 15 minutes, once)
   Google is closing the old Fitbit Web API on 30 October 2026, so Steady connects through its
   replacement, the Google Health API. Sign-in happens on Google's own page; Steady never sees a
   password, and it only asks for read-only access to activity, sleep and health measurements.
   a. console.cloud.google.com: create a project, then enable the "Google Health API".
   b. Google Auth Platform > Branding/Audience: user type External, publishing status Testing.
      Add her Google account (the one her Fitbit uses) under Test users.
   c. Data access: add these three read-only scopes
        https://www.googleapis.com/auth/googlehealth.activity_and_fitness.readonly
        https://www.googleapis.com/auth/googlehealth.health_metrics_and_measurements.readonly
        https://www.googleapis.com/auth/googlehealth.sleep.readonly
   d. Clients > Create client > Web application.
        Authorised JavaScript origin:  https://YOUR-USERNAME.github.io
        Authorised redirect URI:       https://YOUR-USERNAME.github.io/steady/
   e. Copy the client ID into config.js (googleClientId: '...'), upload config.js again, or paste it
      in Steady under Profile > Fitbit > Setting it up.
   f. In Steady: Profile > Fitbit > Connect Fitbit.
   Google gives browser-only apps access for about an hour per sign-in, so when it has lapsed Steady
   shows "Sign in and sync": one tap, and Google usually skips the password the second time.
   While the project is in Testing, Google may ask her to re-approve access every 7 days.

4. PHOTO ESTIMATES (optional)
   Profile > Photo estimates: paste an Anthropic API key from console.anthropic.com. It is stored on
   her phone only, encrypted with her passcode. Without a key, photos still attach to meals.

Updates: upload the new files over the old ones. Her data stays on her phone and isn't affected.
Backups: Profile > Backup and restore saves an encrypted file she can keep in iCloud Drive.
