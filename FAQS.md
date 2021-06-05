Availability
Scalability
Maintenance
## CloudFormation
  -gives devs and businesses easy way to create collection of related AWS and 3rd party resources and provisision and mange them in orderly/predictable fashion
  -can deploy and update compute, db, and othe rresources
  -allows resource lifecycels to be managed repeateably, predictable adn safely
  -allows for auto rollbacks, auto state management
  -managaement of resources across accounts and regions
  -Elastic Beanstalk uses CloudFromation to create adn maintain resources
  -uses json or yaml templates 
  -templates provide declarative code that described instend state of all resources needed to deploy 
  -Elements of templates
    1.  Optional list of template para (input values supplied at stack creation time)
    2.  Optional list of output values (i.e. complete URL to a web app)
    3.  Optional list of data tables used to look up static config values (i.e. AMI name)
    4.  List of resources and their config values
    5.  Template file format version controle
  - by default when a resource in stack is not created successfully, the "automatic rollback on error" feature is enabled
        * directs CloudFormation to only create or update all resources in your stack if all individual ops succeed.  If not, CF revers stack to last knownn stable config
  - supports creating VPCs, subnets, gateways, rout tables, and network ACLs as well as creating resources like elastic IPs, EC2 ISNTANCES, EC2 security groups, auto scaling groups, elastic load balancers, RDS db isntances adn RDS security groups in a VPC
  - AWS CloudFormation Registry is a managed service that lets you register, use and discover AWS and third-party resource types
  - Third-party resource types must be registered before they can be used to provision resources with AWS CloudFormation templates
  - no additional charge to use CF w/ resource providers in the AWS::*, Alex::*, or Custom::* namespaces
    ** pay for AWS resources like EC2, Elastic Load Balancing, etc)
    


Serverless
## IAM
  - used to control individual and groupe access
  - IAM groups
      ** collection of IAM users
      ** can add or remove users from a gorup
      ** user can belong to multiple groups
      ** groups cannot belong to othe rgroups
      ** groups can be granted permission using access control policies
      ** groups do not have security credentials and cannot access web services directly.; exist only to make easier to manage user permissions
STS
Identify Federation
DyanmoDB
SNS
SQS
AWS Step Functions
API Gateway
CloudFront
ElastiCache
Migrating
Refacotring
CloudTrail
X-Ray

