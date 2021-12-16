# Github Workflows

This repository contains multiple basic Workflows that we use in our projects

Here you can find the following workflows:

- **Basic CI workflow:** A basic workflow that runs tests and builds the project: `mobile/flutter-mobile-ci.yml` 
    and `web/flutter-web-ci.yml`.
- **CI workflow with submodules:** Some of our projects uses an API project located in another repository.
    For that, we need an special workflow that clones that submodule: `mobile/flutter-mobile-ci-with-submodules.yml`.
- **CI workflow with lint and coverage checks:** If you need to run lint and test coverage: `web/flutter-web-ci-with-coverage.yml`.
- **CD for web:** Workflow to build and deploy the page in an unique url per PRs: `web/flutter-web-cd.yml`.

### Use

To use a worflow, just place it in the `.github/workflows` folder of your repository.

You can change the branches where it will be executed in this part of the code: 

```
on:
  pull_request:
    branches: [ main, dev ]
```

Some workflows needs some secret vars to be setted. You can do this on `Settings > Secrets` on you repository.
This is some of the secret vars used:

- `TELEGRAM_TOKEN`: The token of the Telegram bot. Ask the backend team lead for this token.
- `CHAT_ID`: The id of the chat that the Telegram bot sends the alerts. Ask the backend team lead for this id.
- `ACCESS_TOKEN`: This is a GitHub access token to clone private repos. Ask the backend team lead for this token.
- `CODECOV_TOKEN`: The token used to upload the coverage report to codecov. Ask the backend team lead for this token.
- `GITHUB_TOKEN`: You don't need to set this, GitHub set this automatically.
- `FIREBASE_SERVICE_ACCOUNT`: This is a special token used to deploy a web page into firebase. Ask for backend team lead for this token.
