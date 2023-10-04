---
sidebar_position: 10
---

# AWS

- **Create IAM users and groups** - **[Link](https://docs.aws.amazon.com/cli/latest/userguide/cli-services-iam-new-user-group.html)**.

## Create user group, put policy to group, create users, attach users to group, create login profile for users and generate csv files with credentials

1) Create file:
```json title=read-access-policy.json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "CommandLineInterface",
            "Effect": "Allow",
            "Action": [
                "iam:Get*",
                "iam:List*",
                "iam:Generate*"
            ],
            "Resource": "*"
        }
    ]
}
```
2) Create file:
```bash title=task1.sh
account_alias=myaccountalias
read_access_policy_name=TutorsPolicyOnlyReadAccess
group_name=TUTORS
user_names=("user1" "user2" "user3" "user4")
log_file=task1.txt
log_folder=logs
log_full_path=./$log_folder/$log_file

mkdir -p $log_folder

echo "Start the awesome hi-eddy's script!" > $log_full_path

echo "Folder $log_folder was created!" >> $log_full_path

aws iam create-group --group-name $group_name >> $log_full_path 2>&1
aws iam put-group-policy --group-name $group_name --policy-document file://read-access-policy.json --policy-name $read_access_policy_name >> $log_full_path 2>&1

csvFileName="users-console-credentials.csv"
echo "User name,Password,Console sign-in URL" > $csvFileName

for name in ${user_names[@]}
do
    aws iam create-user --user-name $name >> $log_full_path 2>&1
    aws iam add-user-to-group --user-name $name --group-name $group_name >> $log_full_path 2>&1
    password=(`(gpg --gen-random --armor 1 8)`)
    aws iam create-login-profile --user-name $name --password $password --password-reset-required >> $log_full_path 2>&1

    echo "$name,$password,https://$account_alias.signin.aws.amazon.com/console" >> $csvFileName
done
```
3) Set variables in **task1.sh**. 
Variables you should set:
* account_alias
* group_name
* user_names

4) Run script:
```bash
sh task1.sh
```