# Review SeedSigner translation changes

Create an account on github.com if you haven't already.

---
### Finish translation changes, download .po file
* Update and review translations in Transifex.
* Navigate to this screen in Transifex and click "Download for use":

<p align="center">
  <img width="500" height="811" alt="397990936-0a332a7e-2f75-4a44-a3bf-4c8126139588" src="https://github.com/user-attachments/assets/e49cbbe8-acbf-43e8-b4cc-afe5d1f79e66" />
</p>

* IMPORTANT: Rename the downloaded file to: `messages.po`

---
### Clone the `greedlove/seedsigner-translations` repo

In order to submit a change, you'll need your own copy of the `seedsigner-translations` repo. Make sure you're signed in to your github account and then:
* Go to the [translations repo](https://github.com/greedlove/seedsigner-translations)
* Click the green **"Code"** button.
* Under **"Clone"**, make sure you're using the **HTTPS** tab (or SSH if you've set it up).
* Copy the URL shown (e.g., `https://github.com/greedlove/seedsigner-translations.git`)

<img width="600" alt="Screenshot 2568-09-23 at 21 02 52" src="https://github.com/user-attachments/assets/1bbc51b5-6ea4-40ec-956b-8621388b77fd" /><br/>

Open Your Terminal or Command Prompt : use your terminal (on macOS/Linux) or Command Prompt (on Windows) and then:

 - Navigate to the Directory Where You Want the Project
```bash
cd path/to/your/folder
```

 - Clone the Repository : Paste the URL you copied after the `git clone` command:
```shell
git clone https://github.com/greedlove/seedsigner-translations.git
```

- Enter the Project Directory : After cloning, go into the project folder:
```bash
cd seedsigner-translations
```

---
### Push an Existing Repository to a New GitHub Repository (Step-by-Step)

After cloning or working on a local Git repository, you may want to push it to a **new GitHub repository**. Here’s how to do it:

#### **Step 1: Create a New Repository on GitHub**

1. Go to [https://github.com](https://github.com)
2. In the top-right corner, click the **"+" icon** > **"New repository"**
3. Set the repository name, e.g., `screenshots_diff_report`
4. **Do NOT initialize with a README**, `.gitignore`, or license if you're pushing an existing local repository
5. Click **"Create repository"**

Your new repository URL will look something like:
- HTTPS: `https://github.com/your-username/screenshots_diff_report.git`
- SSH: `git@github.com:your-username/screenshots_diff_report.git`

#### **Step 2: Push an Existing Repository from the Command Line**

If you already have a local Git repository that you want to push to this new GitHub repository, follow these steps in your terminal:

```bash
# Set the remote URL to your new GitHub repository
git remote set-url origin git@github.com:your-username/screenshots_diff_report.git

# Rename the current branch to 'main' (optional but recommended)
git branch -M main

# Push the code to GitHub and set the upstream
git push -u origin main
```

Replace `your-username` with your actual GitHub username.
#### Done!
Now your local repository is connected to the GitHub remote, and the code is uploaded to the new GitHub repository.

---
### Upload your changes to your fork
Your browser url should now be: github.com/<your_username>/screenshots_diff_report

Click into the `l10n/<language_code>/LC_MESSAGES` folder.

`<language_code>` will be "th" for Thai, "pt_BR" for Brazilian Portuguese, etc.

You should see a messages.po file. In the upper right click "Add file" and choose "Upload files":

<img width="600" alt="402710396-807a1b2d-8df8-4a3e-b671-49c72a903ede" src="https://github.com/user-attachments/assets/ca2f57e3-3361-4ea1-9632-7af7559e87fe" /><br/>

Verify that the following screen is listing the correct directory (you should be within the LC_MESSAGES folder for your language!):

<img width="800" alt="Screenshot 2568-09-23 at 21 31 44" src="https://github.com/user-attachments/assets/699923d8-5369-4ba0-abb8-ab008ddf90d0" />

* Click to upload your `messages.po` file.
* Select "Commit directly to the main branch"
* Click "Commit changes".

---
### Review new/updated screenshots
Once it is created, you'll see the results of our automated checks:

<img width="612" alt="439648126-1970d974-4241-4155-923f-ff637cc5f84f" src="https://github.com/user-attachments/assets/356cedbe-aaa1-4ee5-8517-5b2f476c92fc" />

Click into "All checks have passed" to reveal the "CI / test (pull_request)" line. Click on that to view the details.

<img width="853" alt="439648979-c87861ea-5f82-4439-adc7-9900c3943a9c" src="https://github.com/user-attachments/assets/bf186057-30c5-46dc-931f-1809e34417ac" />

Click "Summary" and scroll down to the "Artifacts" section:

<img width="1025" alt="439649382-3bcb1b0e-dd7e-4944-a728-af8cacc91d6f" src="https://github.com/user-attachments/assets/45640725-b729-4c6e-9500-3ca7d93e0650" />

Click the download arrow to download a zip file of the results.

Inside you'll see:

<img width="180" alt="439649821-918d0590-e87e-4fce-a62c-cd62cf6ce034" src="https://github.com/user-attachments/assets/11db5b15-2a47-42ad-ae88-13424858d51b" />

Double click on the "index.html". This will open the "Screenshots Diff Report" in your browser. It will show a before/after of all screens that have been changed. It will also display new screens that were added and display any that were removed (adding or removing screens would only result from core codebase changes OR if you're adding a brand new language for the first time).

It is up to you to review this diff report and visually inspect the impact your translation have had on the listed screens.

We expect that many translations will need adjusting. The point of the Screenshot Diff Report is so that you can quickly identify problem translations and immediately return to Transifex to revise them.

---

### Which text can run offscreen and which cannot?

#### Okay to run long:
* Titles
* Buttons

<img width="240" height="240" alt="ToolsDiceEntropyMnemonicLengthView" src="https://github.com/user-attachments/assets/5d31edba-d3ce-4dcd-a236-0b3c82c45270" /><br />

In this screenshot both the title and the active button will scroll the text back and forth into view. Better to avoid if possible, but totally acceptable if either require scrolling.

#### NOT okay to run long:
* Warning screen subheads
* Any other body content

<img width="240" height="240" alt="SeedTranscribeSeedQRWarningView" src="https://github.com/user-attachments/assets/dc30ec2c-4ac1-4be1-a4c4-30c67ed911c4" /><br/>

Notice that the red subheader text does not fit. These subheads do NOT currently autoscroll.


<img width="240" height="240" alt="SeedExportXpubWarningView" src="https://github.com/user-attachments/assets/01ad298b-0724-4295-ac40-0a924055f31a" /><br/>


Any text that runs too long vertically and ends up offscreen or obscured by another screen element would need to be rewritten to be shorter.

---
