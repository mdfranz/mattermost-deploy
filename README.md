
# Starting points

- [Elastic Beanstalk "Docker" Source](https://raw.githubusercontent.com/mattermost/mattermost-docker/master/contrib/aws/Dockerrun.aws.json)
- [Local Machine Docker Setup](https://docs.mattermost.com/install/docker-local-machine.html)
- [Production Dockerfile](https://github.com/mattermost/mattermost-docker)
- [Mattermost Docker Hub](https://hub.docker.com/u/mattermost)

# The MVP
- Terraform deployment
- SSL Termination on ALB with ACM 
- WAF to block all non-US traffic
- Cheapest RDS instance available (db.t3.micro)
- Database Passwords stored securely
- Use S3 for data
