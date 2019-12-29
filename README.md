
# The Exercise
I've been looking for usable application to build my ECS Fargate knowledge and I noticed that [Mattermost](https://docs.mattermost.com/guides/administrator.html#installing-mattermost) has Kubernetes and Elastic Beanstalk but no version for ECS. I was able to install the [Ubuntu 18.04 Version](https://docs.mattermost.com/install/install-ubuntu-1804.html) and get it working on a LXD container in less than 30 minutes. Onwards and upwards to something more complex.

# Starting points
- [Elastic Beanstalk "Docker" Source](https://raw.githubusercontent.com/mattermost/mattermost-docker/master/contrib/aws/Dockerrun.aws.json)
- [Local Machine Docker Setup](https://docs.mattermost.com/install/docker-local-machine.html)
- [Production Dockerfile](https://github.com/mattermost/mattermost-docker)
- [Mattermost Docker Hub](https://hub.docker.com/u/mattermost)
- [Terraform for Load Test Cluster](https://github.com/mattermost/mattermost-load-test/blob/master/terraform/cluster.tf)
- [Manual Load Testing](https://github.com/mattermost/mattermost-load-test/blob/master/docs/manual.md)
- [Packer & CodeBuild](https://aws.amazon.com/blogs/devops/how-to-create-an-ami-builder-with-aws-codebuild-and-hashicorp-packer/)

# The MVP
- Packer builds in AWS Code Build
- Terraform deployment (new VPC in arbitrary region)
- SSL Termination on ALB with ACM with existing domain managed by Route53
- WAF Rules to block all non-US traffic
- Cheapest RDS instance available (db.t3.micro)
- Database Passwords stored securely with SSM
- Use S3 for data
- Single Instance with separate data partition with EBS snapshots enabled 
