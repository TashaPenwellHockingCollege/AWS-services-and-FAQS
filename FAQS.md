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
## DyanmoDB
  - nonrelational db service for any scale
  - manages db SW and provisioning of HW
  - auto scales throughput capacity to meet workload demands adn partitions and repartitions data as your size grows
  - replicates across 3 facilities in an AWS Regions to provide high availability and high durability
  - Can specify whether want the read to be eventually consistent or strongly consistent
      ** EVENTUAL CONSISTIST READS
          - default
          - maximzes read throughput
          - may not reflects results of recently completed write
          - all copies of data usually reach consistency w/in a second
      ** STRONGLY CONSISTENT READS
          - returns result that reflects all writes that received a successful response before the read
      ** ACID TRANSACTIONS
          - provide deveopers atomicty, consistency, isolation and durability (ACID) across one more tables w/in single AWS account and region
          - can use transactions when building apps that require coordinated inserts, deletes or updates to multiple items as part of a single business ops
  - supports GET/PUT ops by useing a user-defined PK
  - PK is specified when create a table
  - PK can be either a single-attribute partition key or a composite partition-sort key
      ** Single Attribute Partition Key
      ** Compositie Partition-Sort Key
            - maintains hierarchy between the first and second element values
            - i.e. combo of UserID (partition) and Timestamp (sort)
            - holding the partitional key element constant, can search across the sort key element to retrieve items (ie.. by using Query API)
  - can be created using the console or CreateTable API
  - use PutItem or BatchWriteItem APIs to insert items
  -  use GetItem BatchGetItem or Query API (for compositie) to retrieve items from table
  -  each table has provisioned read-throughput and write-throughput associated w/ it and are billed by the hour for throughput beyond free tier whether using sending requests to table or not
      ** can change provisioned throughput capaicty in console, the UpdateTable API or PutScalingPolicy API for auto scaling
  - also charges for data storage an standard internet data transfer fees
## SNS
  -web service that makes it easy to set up, operate and send notifications from the cloud
  - highly scalable, flexibile and cost efective capability to publish message and deliver to subscribers or other apps
  - Benefits
    ** instantaneous, push-based deliverying (no polling)
    ** simple APIs adn easy integration w/ other apps
    ** Flexible message delivery over multiple tranport protocols
    ** inexpensive, pay as your go, no up-front costs
    ** simple interface

## SQS
  - cost is calculated per requrest plus data transfer charges transferred out of SQS 
    ** exception on charges for data transferred out is if transferred to EC2 isntances or to Lambda functions w/in the same region)
  - free tier allows 1 million requests but data transfer charged can still appy
  - only the AWS account owner (or user that owner delegrate rights to) can perform operations on SQS meassage queue
  - SQS Long polling is a way to retrieve messages from SQS queue.
  - Short polling returns immediately even if empty but Long Polling does not return a response until a message arrives in message queue or long poll times out
  - Long Polling make it inexpensive to retrieve messages from SQS queue
  - Most cases prefer long polling

## AWS Step Functions
  -fully managed service 
  -provides easy to coordiante components of distributed applications and microservices using visual workflows
  -reliable way to coordinate components and step through the functions of your app
  -provide a GUI console to arrange and visualize components of app as a series of steps
  -makes it simple to build and run multi-step apps
  -auto triggers and tracks each step and retries when there are errors so your app executes in order as expected
  - logs the state of each step, so when things do go wrong, can diagnose and debug problems quickly
  - can change and add steps w/o writing code
  - helps w/ computational problem or business process that can be subdivided into a series of steps
  - useful for creating end-to-end workflows to manage jobs w/ interdpendeinces
  - Use cases 
      ** Data Processing
      ** DevOps and IT automation
      ** Ecommerce
      ** Web applications
  - How does it work
      1.  define state machine that describes workflow as a series of steps, their relationships and their inputs and outputs
      2.  State machines contain a number of states, each represents an individual step in a workflow diagram
      3.  States can perform work, make choices, pass parameters, initial parrallel execution, manage timeouts or termining workflow w/ success or failure
  - How to connect to resources
      1.  congigure state machines to perform work by usign activity tasks and service tasks
      2.  Activity Tasks lets you assign a specific step in your workflow to code running somehwhere else (aka activity worker)
            ** Activity Workers can be any app that can make an HTTP connection, hosted anywhere
      3.  Service tasks let you connect a step in your workflow to a supported AWS service
      4.  Step functions pushes request  to other services so they can perform actions for your workflow, waits for service taks to complete and continues to next step
  - 
API Gateway
CloudFront
ElastiCache
Migrating
Refacotring
CloudTrail
X-Ray

