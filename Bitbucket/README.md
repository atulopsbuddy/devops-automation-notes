# Bitbucket Webhook Integration with Jenkins

This repository documents the setup process for integrating Bitbucket with Jenkins to trigger builds automatically using webhooks.

## 🔧 Steps Overview

1. **Create App Password in Bitbucket**
   - Go to **Bitbucket → Personal Settings → App Passwords**
   - Create a password with `Repository Read` and `Webhooks Read and Write` permissions.
   - Copy and save it securely.

2. **Get Bitbucket Username**
   - Go to **Bitbucket → Account Settings → Username**
   - Use this username (not email) in Jenkins credentials.

3. **Configure Jenkins Credentials**
   - Navigate to `Jenkins → Manage Jenkins → Credentials → Global Credentials`
   - Add a **Username with password** using the Bitbucket username and app password.

4. **Install Bitbucket Plugin in Jenkins**
   - Go to `Manage Plugins`
   - Install: **Bitbucket Plugin**
   - Restart Jenkins if required.

5. **Configure Webhook in Bitbucket**
   - Go to **Repository → Settings → Webhooks → Add webhook**
     - **Title:** Jenkins Trigger
     - **URL:** `http://<jenkins-server>/bitbucket-hook/`
   - Save the webhook.

6. **Enable Trigger in Jenkins Job**
   - In your job’s configuration:
     - Enable ✅ "Build when a change is pushed to Bitbucket"
   - Save the job.

---

📄 See [bitbucket-to-jenkins.md](bitbucket-to-jenkins.md) for full setup instructions.
