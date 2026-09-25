# 🧩 Puzzle Competition — GitHub + Firebase

A complete React/Vite puzzle competition starter with **six working games**, student registration, score storage, and a live leaderboard.

## Six games
1. Word Guess — 5-letter Wordle-style game
2. Number Puzzle — 10 questions
3. Logic Puzzle — 10 reasoning questions
4. Connections — four groups of four
5. Puzzle Solver — 10 riddles/puzzles
6. Speed Challenge — 10 rapid questions

## Run locally
```bash
npm install
cp .env.example .env
npm run dev
```
Without Firebase variables, the app automatically runs in **demo mode** using browser storage so you can test every game.

## Firebase setup
1. Create a Firebase project.
2. Enable Firestore.
3. Enable Authentication (Email/Password) for organizers.
4. Create a web app and copy its config into `.env`.
5. Replace `CHANGE_ME_ADMIN_EMAIL` in `firestore.rules` with the organizer email.
6. Publish rules.

> For a high-stakes event, move answer validation to trusted server-side code/Cloud Functions. The included frontend is a functional competition scaffold, not a substitute for a security audit.

## GitHub
```bash
git init
git add .
git commit -m "Build live puzzle competition"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
git push -u origin main
```

## Firebase Hosting
```bash
npm install -g firebase-tools
firebase login
firebase init hosting
npm run build
firebase deploy
```

When Firebase Hosting asks for the public directory, use `dist`; configure it as a single-page app.

## Registration flow
Students enter name + roll number. Registrations are stored in Firestore when Firebase is configured and are visible to the organizer dashboard. Roll numbers are checked for duplicates.

## Live leaderboard
With Firebase configured, Firestore `onSnapshot()` listens for score changes. The public leaderboard updates without a refresh.

## Important before the live event
- Replace the sample questions with your real questions.
- Configure the organizer email and Firebase rules.
- Test duplicate registration and simultaneous users.
- Add trusted backend validation for any competition where cheating resistance matters.
- Remove demo/test data before opening registration.
