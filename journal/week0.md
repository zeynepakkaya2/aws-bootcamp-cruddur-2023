# Week 0 — Billing and Architecture

I created a GitPod account and I created a workspace for this repository.

I created an AWS account.

---

## Installing AWS CLI

I installed AWS CLI.

[Install AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

I installed it on GitPod environment so I used instructions for Linux x86.

`curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"`

`unzip awscliv2.zip`

`sudo ./aws/install`

![AWS CLI](https://github.com/zeynepakkaya2/aws-bootcamp-cruddur-2023/blob/main/journal/assets/aws-cli.png)

I updated `.gitpod.yml`:

```
tasks:
  - name: aws-cli
    env:
      AWS_CLI_AUTO_PROMPT: on-partial
    init: |
      cd /workspace
      curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
      unzip awscliv2.zip
      sudo ./aws/install
      cd $THEIA_WORKSPACE_ROOT
```

---

## Billing Alarm

---

## Budget

I created a budget with (Example Tag Budget):

```
aws budgets create-budget \
    --account-id 633454501883 \
    --budget file://aws/json/budget.json \
    --notifications-with-subscribers file://aws/json/notifications-with-subscribers.json
```

![My AWS budgets](https://github.com/zeynepakkaya2/aws-bootcamp-cruddur-2023/blob/main/journal/assets/budget.png)
