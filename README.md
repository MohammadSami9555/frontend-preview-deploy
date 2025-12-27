# 🚀 Preview Deployments for Frontend Pull Requests (GitHub Actions + Vercel)

This project implements **automatic preview deployments** for every Pull Request.  
Whenever a developer opens a PR, this system:

- builds the frontend automatically
- deploys it to Vercel
- generates a **unique live preview link**
- comments that link inside the PR

So reviewers can **see the actual running app before merging** ✔️


---

## 🧠 What are Preview Deployments?

Preview deployments allow you to:

✔️ test features before merging  
✔️ share live link with teammates  
✔️ visually verify UI changes  
✔️ catch bugs early  

Example:

main branch → production website
PR #5 → https://pr-5-preview.vercel.app

PR #9 → https://pr-9-preview.vercel.app



Each PR gets its **own live URL**.

---

## 🛠️ Tech Used

- React (frontend)
- GitHub Actions (CI/CD automation)
- Vercel (hosting + deployments)

---

## ✅ Prerequisites

Before setup, you must have:

- GitHub account
- Vercel account
- React project pushed to GitHub

---

## 🚀 Step 1 — Create React App (if not already)

```bash
npx create-react-app frontend-preview
cd frontend-preview


🌍 Step 2 — Push project to GitHub


git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin <repo-link>
git push -u origin main



⚡ Step 3 — Connect GitHub repo to Vercel

1️⃣ Login to Vercel
2️⃣ Add New Project
3️⃣ Select GitHub repo
4️⃣ Click Deploy

Production URL will be created ✔️


🔐 Step 4 — Create Vercel Token

Go to:

Vercel → Settings → Tokens


Create token → copy it → do not share


🆔 Step 5 — Get ORG ID & Project ID

Go to:

Vercel → Project → Settings


Copy:

Organization ID

Project ID


🔑 Step 6 — Add GitHub Secrets

GitHub Repo → Settings → Secrets → Actions → New repository secret

Add:

| Secret Name         | Value           |
| ------------------- | --------------- |
| `VERCEL_TOKEN`      | Vercel token    |
| `VERCEL_ORG_ID`     | Organization ID |
| `VERCEL_PROJECT_ID` | Project ID      |



🤖 Step 7 — Create GitHub Actions Workflow

Create file:

.github/workflows/preview.yml


🧪 Step 8 — How to test preview deployment

1️⃣ Create new branch

git checkout -b test-preview

2️⃣ Make any change in UI
3️⃣ Commit & push

git add .
git commit -m "test preview"
git push origin test-preview


4️⃣ Create Pull Request

✔️ GitHub Actions will run
✔️ Vercel will deploy
✔️ PR gets live link 🎉

🎉 Result

Every PR automatically gets:

build

live deployed preview

PR comment with link

No manual deployment required 🚀

💡 Why this is useful?

easier code reviews

faster team collaboration

avoids breaking production

works for any frontend framework