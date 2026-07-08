# How to setup this repository in aws from starting?
1. download aws cli and install that aws cli
- check it install successfully or not
- type in cmd: aws --version
2. setup IAM user in AWS give addministrator permission and create access Key
3. configure User in CLI
  - open cmd type: aws configure
  - fill all details
  ```
AWS Access Key ID [None]:
AWS Secret Access Key [None]:
Default region name [None]: ap-south-1
Default output format [None]: json
  ```
- check it configure correct or not?
- type in cmd: aws sts get-caller-identity
output: 
 ```
  {
  "UserId": "...",
  "Account": "446483464882",
  "Arn": "arn:aws:iam::446483464882:user/you-username"
  }
```

4. for deploy this repo in aws need some tools and command:
```
npm install
cdk bootstrap
npm run build
cdk deploy
```

