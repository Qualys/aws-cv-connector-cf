# aws-cv-connector-cf
THIS SCRIPT IS PROVIDED TO YOU "AS IS."  TO THE EXTENT PERMITTED BY LAW, QUALYS HEREBY DISCLAIMS ALL WARRANTIES AND LIABILITY FOR THE PROVISION OR USE OF THIS SCRIPT.  IN NO EVENT SHALL THESE SCRIPTS BE DEEMED TO BE CLOUD SERVICES AS PROVIDED BY QUALYS

CloudFormation Template to create a Qualys AWS Connector and associated cross-account trust role using the Security Audit managed policy.
To run the script you will need to supply credentials for the
Qualys user name, password, and Qualys API endpoint URL for API access to Qualys Cloud View.
This CloudFormation Template is intended to be run in your AWS existing AWS accounts or as part of your AWS Account provisioning process to create an associated Qualys Cloud View Connector. An example of storing the Qualys API user name and password in AWS Secrets Manager is available in the branch for https://github.com/snicholson-qualys/aws-cv-connector-cf/tree/aws_secrets_mgr

Parameters:

  UserName:

    Default: {supply_Qualys_user_name}
...

  Password:

    Default: {supply_Qualys_user_password}

  BaseUrl:

    Default: Qualys API URL for Cloud View API endpoint. See https://www.qualys.com/docs/qualys-cloud-view-user-guide.pdf page 27

# External ID
You can specify a unique External ID consisting of 9-90 numeric characters in place of Empty on line 23 or if one is not supplied, the Lambda function will generate one and use that for the unique External ID.

Parameters:

...

  ExternalId:

    Default: Empty

    Description: Specify a unique number from 9-90 digits, or one will be generated for you

    Type: String

# Role Name
If you want to change the Role name you can edit these settings in line number 27

Parameters:

...

  RoleName:

    Default: CF-QualysAWSConnectorRole
