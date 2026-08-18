# Day 95: Create Security Group Using Terraform

**subject**

***

The Nautilus DevOps team is strategizing the migration of a portion of their infrastructure to the AWS cloud. Recognizing the scale of this undertaking, they have opted to approach the migration in incremental steps rather than as a single massive transition. To achieve this, they have segmented large tasks into smaller, more manageable units. This granular approach enables the team to execute the migration in gradual phases, ensuring smoother implementation and minimizing disruption to ongoing operations. By breaking down the migration into smaller tasks, the Nautilus DevOps team can systematically progress through each stage, allowing for better control, risk mitigation, and optimization of resources throughout the migration process.

Use**Terraform**to create a security group under the default VPC with the following requirements:

1\) The name of the security group must be`nautilus-sg`.

2\) The description must be`Security group for Nautilus App Servers`.

3\) Add an**inbound rule**of type`HTTP`, with a port range of`80`, and source CIDR range`0.0.0.0/0`.

4\) Add another**inbound rule**of type`SSH`, with a port range of`22`, and source CIDR range`0.0.0.0/0`.

Ensure that the security group is created in the**us-east-1**region using Terraform. The Terraform working directory is`/home/bob/terraform`. Create the`main.tf`file (do not create a different`.tf`file) to accomplish this task.

`Note:`Right-click under the`EXPLORER`section in`VS Code`and select`Open in Integrated Terminal`to launch the terminal.

***

https://registry.terraform.io/providers/-/aws/6.8.0/docs/resources/security\_group

https://blog.stephane-robert.info/docs/infra-as-code/provisionnement/terraform/aws/sg-subnet-instance/

https://medium.com/@18bhavyasharma/creating-security-groups-with-terraform-a-beginners-guide-8561da3ec777

https://dev.to/omkara18/-in-depth-guide-to-aws-security-groups-with-terraform-ingress-egress-ports-and-protocols-21mk

* Check the current work

![](assets/LBV94HvQHDpnaot0uZ6a43eNzkpaS6L1DW-qEqeqQII=.png)

* Create the security group

using inline rules

![](assets/68wfsakI6rfXTE7oAIIiL444K_GtyyKGE_a-q0DShRc=.png)

using standalone rules

* Run and check

![](assets/ILfAQzTUvFWKKW6B39kGFW3tR03LNRNhaYSeJlIzVSg=.png)

![](assets/1QrYozbxovg4tCuUbPZOREaAUSCG3-x_0Jl2ldrdfCM=.png)
