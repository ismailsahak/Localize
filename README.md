# Kaodim iOS Translation Repository Setup
​
### 1. Get access to AWS repository from a backend engineer.
* Ask for access for iOS translation repo on AWS. Make sure you get a UNIQUE ID which looks something like `APKAXBA63XDWMV3ZDCDC`. Keep this ID for later use.
* Sign-in URL: https://kaodim.signin.aws.amazon.com/console 
* Bookmark this URL: https://ap-southeast-1.console.aws.amazon.com/codesuite/codecommit/repositories/kaodim-ios-translation/browse?region=ap-southeast-1 (this will be the repo's URL)
​
### 2. Add config to SSH file
​
Add the following config to your ~/.ssh/config file. _(E.g. Users/ismail/.ssh/config)_
```java
Host awscodecommit
  Hostname git-codecommit.ap-southeast-1.amazonaws.com
  User {YOUR UNIQUE ID}
```
​
### 3. Clone repository
​
Enter the following in Terminal.
```java
git clone awscodecommit:/v1/repos/kaodim-ios-translation
```
After this process. You're done with setting up the repository. You may view the repository on your Git client.
​
***
​
## Updating/Adding Translations
​
1. In the repository, create a feature branch from Main/Master.
2. Go to the 'Locale' folder.
3. There are two folders named 'User' and 'Pro' which contain translations for the respective projects.
4. Edit the JSON translation files accordingly and commit.
5. There are **3 main branches** in this repo with deployment workflows; `master`, `omega`, and `staging`.
6. As an example, if you'd like to apply the translations from your branch to staging environment, merge the staging branch:
    ```java
    git merge origin/staging
    ```
7. _Step 6_ applies for Omega branch too.
8. You can refer to `engn_builds` channel on Slack to monitor the deployment.
​
***
​
## Deploying Translations to Production
​
1. From the AWS repo console, create a PR from your feature branch to `master`.
2. Get another engineer to review the changes first before merging.
3. Once merged, the deployment to production will start automatically.
​
***
​
#### Repo link: https://ap-southeast-1.console.aws.amazon.com/codesuite/codecommit/repositories/kaodim-ios-translation/browse?region=ap-southeast-1
