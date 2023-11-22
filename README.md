Cloud Native Week 2023 Winter!
Test.

# Orca Security - Shift Left Security quick demo guide
Secure by design & default is a mandatory concept for every software development orginization!  The tutorial here is a quick demo guide that shows you how you can demo Orca Security Shift Left Security.
<br>
<br>


## Prerequisites
- Orca Security free trial license - visit [Orca Security](https://orca.security/lp/cloud-security-risk-assessment/) if you don't have a free trial license.
- GitHub account.
- MacBook with GitHub CLI.
<br>
<br>


## Set-up
Fork [the repo](https://github.com/hisashiyamaguchi/shift-left-secret).
<br>
<br>

Go Orca UI, and hit "Settings" -> "Users & Permissions" -> "API".  Hit "+Add API Token" on the top right, and put a name of the API Token and hit "Add" - grab your API Token.
<br>
<div align="center">
<img src="./images/API Token.png" width=50%>
</div>
<br>

Go your forked repo, hit "Settings" on the top right, and hit "Secrets and valuables" -> "Actions" on the left pane. Hit "New repository secret", and put the API Key you just created and hit "Add secret".
<br>
<div align="center">
<img src="./images/GHA Env Valuable.png" width=50%>
</div>
<br>

Go back to Orca UI, and hit "Shift Left" -> "Management" on the left pane, and hit "Projects" -> "Default" - grab the project key.
<br>
<div align="center">
<img src="./images/SLS Project Key.png" width=50%>
</div>
<br>

Go [GitHub Actions workflow yml](https://github.com/hisashiyamaguchi/shift-left-secret/blob/main/.github/workflows/sample.yaml), and put your project key.
```yml
project_key:
"default"
```
<br>

Hit "Policy Management", and check "Orca Built-in - Source Code Secret Detection Policy" on.
<br>
<div align="center">
<img src="./images/SLS Policies.png" width=50%>
</div>
<br>
<br>


## Demo!
1. Say the concept of DevSecOps to your audiences with short words, and expain the demo platform and technical prerequisites.
2. Show [sample.yaml](https://github.com/hisashiyamaguchi/shift-left-secret/blob/main/.github/workflows/sample.yaml), and explain that the integration has been completed with just 2 lines!
3. Show [secret.tf](https://github.com/hisashiyamaguchi/shift-left-secret/blob/main/samples/secret.tf) - it has an AWS Key. Say that Orca is going to scan and identify the AWS Key, and stop the pipeline.
4. Clone the repo to your local laptop. Go the repo directory and chagen any codes - README.md is the easiest.
5. Commit the change locally and push the commit to remote repo - GitHub Actions workflow will be triggered, and start buiding and scanning terraform definition.
5. Orca Security is going to detect the source code secret policy violation, and the delivery pipeline will be red.
6. Visit Orca dashboard and show scanning logs - you can show red flag error logs.
<br>
<div align="center">
<img src="./images/Scan Log Sample.png" width=50%>
</div>
<br>
<br>


## Issue Reporting
If you have found a bug or if you have updates request, please report them at this repository issues section.
