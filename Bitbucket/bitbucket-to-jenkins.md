# Bitbucket to Jenkins Webhook Integration (Full Guide)

This file provides detailed instructions for configuring Bitbucket to trigger Jenkins builds via webhook integration.

---

## 1. Create App Password in Bitbucket

- Go to:
Bitbucket → Personal Settings → App Passwords → Create App Password
- Grant the following permissions:
- ✅ Repository: Read
- ✅ Webhooks: Read and Write
- Save the generated password securely.

---

## 2. Get Bitbucket Username

- Go to:
Bitbucket → Account Settings → Username
- This will be used in Jenkins credentials.

---

## 3. Add Credentials in Jenkins

1. Navigate to:
Jenkins → Manage Jenkins → Credentials → System → Global Credentials
2. Add a new credential:
- Kind: `Username with password`
- Username: Bitbucket username
- Password: App password
- (Optional) ID: `bitbucket-cred`

---

## 4. Install Bitbucket Plugin in Jenkins

- Go to `Manage Jenkins → Manage Plugins`
- Install plugin: **Bitbucket Plugin**
- Restart Jenkins if needed

---

## 5. Configure Jenkins Job

- Open a Jenkins job
- Go to **Configure**
- Under **Build Triggers**, enable:
- ✅ "Build when a change is pushed to Bitbucket"
- Save the configuration

---

## 6. Create Webhook in Bitbucket

- Go to:
Repositories → Repository Settings → Webhooks → Add Webhook
- Fill in:
- **Title:** Jenkins Trigger
- **URL:** `http://<jenkins-server>:8080/bitbucket-hook/`
- **Triggers:** Keep default or select "Push"

---

## ✅ Done!

Pushing to the configured Bitbucket repo will now trigger a Jenkins build automatically.
