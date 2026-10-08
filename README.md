# Unknown Coaching Centre: Fee & Student Management

One service = website + API + real-time. Deploy steps:

1. MongoDB Atlas: create free cluster, a database user, Network Access "Allow from anywhere", copy the connection string (replace <password>).
2. Gmail (unknowncoachingcentre@gmail.com): turn on 2-Step Verification, create an App password (16 letters).
3. Upload this folder to a GitHub repository.
4. Render.com > New > Blueprint > pick the repo. Fill in: MONGODB_URI, SEED_ADMIN_PASSWORD (your admin password, 8+ chars), GMAIL_APP_PASSWORD.
5. Wait for the build. Open the Render link. Sign in with admin@unknowncoachingcentre.com and your password. The admin account is created automatically on first start.
6. Open the link in Android Chrome > menu > Install app.

Using it: Students > Add student (parent mobile is the login ID; a one-time password is shown). Fees > "Create this month's fees" once every month, then record payments. Notifications > send to a mobile number.

Local development: backend/.env (copy .env.example), `cd backend && npm install && npm run dev`; in another terminal `cd frontend && npm install && npm run dev`. Try without a backend: set VITE_DEMO=true in frontend/.env.
Optional demo data: `cd backend && npm run seed -- --demo` (delete these demo students before real use).

Not included: Firebase push when the app is fully closed (live in-app notifications and Gmail updates work).
