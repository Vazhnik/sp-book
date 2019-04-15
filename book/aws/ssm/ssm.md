# SSM - Systems Manager


## Enable EC2 Reporting
[Link](https://aws.amazon.com/ru/blogs/mt/reporting-and-remediating-ec2-instances-that-aws-systems-manager-doesnt-list-as-managed-instances/)

For an EC2 instance to be considered a managed instance in AWS Systems Manager, it must:

- Be running a supported operating system
- Be in an AWS Region that supports AWS Systems Manager
- Have an IAM instance profile with permission to perform AWS Systems Manager actions on your instance
- Have the AWS Systems Manager Agent installed and the service running
- Be able to reach the Systems Manager endpoints with internet access or VPC endpoints

## Document
Документ - некоторый набор функциональности закатанный в Document.
Можно создавать свои документы.
Документы могут предоставлять разнообразную функциональность:
Документ можнт собирать информацию о EC2, запускать на ней скрипт много всего разного.

## Association
Ассоциация - кроновская запускалка документа.
Может раскатывать по таргетам:
 - ec2 (Global)
 - по тегам
 - конкретные Instance id

Note: Ассоциация Software Gathering уровня Global может быть только одна

Note: <br>
Ассоциация не будет запущена для EC2, если такая версия уже была удачно установлена ранее на эту ec2. (оверрайда нету)

## Run command
Одноразовый запускатор документа


# На UI для юзера есть удобный абстракции
## Distributor
Если собрать свой пакет, то его можно запустить с помощью Association или Run command

## Inventory
Набор информации собранный с помощью документа SoftwareGathering
