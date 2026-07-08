Note: in this repository, cdk bootstrap is old version install new version and do your work.
```
npm install --save-dev aws-cdk@latest
```
- After deploy also configure CORS for uploading file.
```
[
    {
        "AllowedHeaders": [
            "*"
        ],
        "AllowedMethods": [
            "GET",
            "PUT",
            "HEAD"
        ],
        "AllowedOrigins": [
            "http://localhost:3000"
        ],
        "ExposeHeaders": [
            "ETag"
        ],
        "MaxAgeSeconds": 3000
    }
]
```


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
# for changing Bucket name or cloudFormatio
- In this File change bucket name -----> lib/image-optimization-stack.ts
-search: new s3.Bucket(

- example: 
<img width="825" height="580" alt="image" src="https://github.com/user-attachments/assets/a0a88e1a-8af2-42d2-9415-28a1fb1ee97b" />
<img width="815" height="662" alt="image" src="https://github.com/user-attachments/assets/3ce14eed-d683-4614-a77c-ffaecc811871" />

<img width="842" height="442" alt="image" src="https://github.com/user-attachments/assets/5e48c9fd-4a2d-4ef6-8c14-1676cc2c437a" />

4. for deploy this repo in aws need some tools and command:
```
npm install
cdk bootstrap
npm run build
cdk deploy
```
5. just hit all command and you project deploy in aws.

- to see changes in aws use cloudformation
- cloud watch <-- here in log we see all error log
