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
### Fork the `greedlove/screenshots_diff_report` repo
(skip this step if you've already forked it)

In order to submit a change, you'll need your own copy of the `screenshots_diff_report` repo. Make sure you're signed in to your github account and then:
* Go to the [screenshots diff_report repo](https://github.com/greedlove/screenshots_diff_report)
* Click the green **"Code"** button.
* Click "Fork" at the top right.

<img width="600" alt="Screenshot 2568-09-24 at 10 07 28" src="https://github.com/user-attachments/assets/43b89269-87e7-4292-873f-0b05c454f298" /><br/>

Leave all the defaults as they are and proceed with creating the fork.

---
### Upload your changes to your fork
Your browser url should now be: github.com/<your_username>/screenshots_diff_report

Click into the `l10n/<language_code>/LC_MESSAGES` folder.

`<language_code>` will be "th" for Thai.

You should see a messages.po file. In the upper right click "Add file" and choose "Upload files":

<img width="1430" alt="Screenshot 2568-09-24 at 10 13 45" src="https://github.com/user-attachments/assets/a6c9357b-b392-4a84-83d7-e67af925639b" /><br/>

Verify that the following screen is listing the correct directory (you should be within the LC_MESSAGES folder for your language!):

<img width="800" alt="Screenshot 2568-09-24 at 10 19 16" src="https://github.com/user-attachments/assets/f9aa5871-e2ea-41fb-a1bf-4bb8ad68b576" />

* Click to upload your `messages.po` file.
* Select "Create a new branch for this commit and start a pull request."
* Name your new branch with the language code and date: e.g. `es_2025-09-24`
* Click "Propose changes".

On the following screen we will finalize your Pull Request (PR):

<img width="800" alt="Screenshot 2568-09-24 at 10 25 51" src="https://github.com/user-attachments/assets/6f286c16-0e05-4dff-9fa7-e418dd6c5443" /><br />

* Click on "compare across forks". That will alter the "base repository" droplist options.
* Select "greedlove/screenshots_diff_report" as the "base repository".
  * Its "main" branch should already automatically be selected.
* Add a title that includes the language code and (optional) additional context/info.
* Scroll down and review the diff at the bottom.
  * If you spot any translations issues, you can only fix them back in Transifex. After any issues are fixed, you'll have to download the `messages.po` file and repeat this process.
* Click "Create pull request" when you're ready.

---
### Review new/updated screenshots
Once it is created, you'll see the results of our automated checks:

<img width="1317" alt="Screenshot 2568-09-24 at 10 30 30" src="https://github.com/user-attachments/assets/8c43a1d1-0db5-46c5-8f0d-cde9f08a746e" /><br />

Once those checks are complete, you'll see the results displayed below the PR.

✅ If everything goes well, all checks will pass and show up in green, which means the PR is ready for downloading screenshots.

❌ If something goes wrong, one or more checks will fail and show up in red. In that case, we’ll need to review the errors, fix the issues, and push an update before the PR can proceed.

<img width="1256" alt="Screenshot 2568-09-24 at 10 40 45" src="https://github.com/user-attachments/assets/470f695f-7183-44c9-9fca-67be76d6d46a" /><br />

Click into "All checks have passed" to reveal the "CI / test (pull_request)" line. Click on that to view the details.

<img width="821" alt="Screenshot 2568-09-24 at 10 43 07" src="https://github.com/user-attachments/assets/df0eeea0-01d3-4cfc-a62e-66fc6b459c3b" /><br />

Click "Summary" and scroll down to the "Artifacts" section:

<img width="1044" alt="Screenshot 2568-09-24 at 10 43 37" src="https://github.com/user-attachments/assets/96fd3506-6776-4db5-8242-ce54fd85953f" /><br />

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

### Submitting revised translations to your repo

If a screenshot does reveal a problematic translation, make your translation edits in Transifex, then repeat the process of downloading the translation file.

Follow the same steps from "Upload your changes to your repo" above to navigate to the proper folder and then "Upload files". Once again, select your `messages.po` file.

This will be treated as an additional commit on top of the one you did earlier. Once the updated file is committed, your repo will automatically include the latest changes.

At this point the automated system will re-run itself and generate a new Screenshot Diff Report for you to download and review.

Repeat this process as many times as necessary until you're satisified with all screens in the Screenshot Diff Report.

---

### How to View Your PR and Check the Automated Results

Once you’ve created a Pull Request (PR), you can view it by going to the "Pull Requests" tab at the top of the repository.<br />
Go to the [screenshots diff_report repo](https://github.com/greedlove/screenshots_diff_report)

<img width="1432" alt="Screenshot 2568-09-24 at 10 49 14" src="https://github.com/user-attachments/assets/9cd2de6a-e57e-4034-9c45-93e0fa1eafc1" /><br />

When you open your PR, you’ll see a section showing the results of our automated checks — these might include things like build status, tests, screenshot generation, etc.

✅ If all checks pass, they’ll appear in green, and your PR is good to go.

❌ If any check fails, it will appear in red, and you can click into it to see what went wrong and how to fix it.

<img width="1315" alt="Screenshot 2568-09-24 at 10 50 15" src="https://github.com/user-attachments/assets/4ba36a8b-9793-4806-bec9-21c3fd280ccf" /><br />
