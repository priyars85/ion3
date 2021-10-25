{
  "source": [
    {
      "amazon-ebs": [
        {
          "pr-ion-image": [
            {
              "ami_name": "ion-ami",
              "instance_type": "t2.micro",
              "region": "us-east-2",
              "source_ami": "ami-00399ec92321828f5",
              "ssh_username: "ubuntu"
            }
          ]
        }
      ]
    }
  ],
  "build": [
    {
      "name": "ion-packer-build",
      "provisioner": [
        {
          "shell": [
            {
              "inline": [
                "sleep 30",
                "sudo apt-get update",
                "sudo apt-get upgrade -y",
                "sudo apt-get install libtomcat9-java -y",
                "sudo apt-get update -y",
                "sudo apt-get install tomcat9-admin tomcat9-common -y",
                "sudo apt-get install tomcat9 -y",
                "cd /var/lib/tomcat9/webapps/",
                "sudo wget https://app-ion-dev-bucket-us-east-2.s3.us-east-2.amazonaws.com/ion.war",
                "sudo systemctl start tomcat9"
              ]
            }
          ]
        }
      ],
      "sources": [
        "source.amazon-ebs.pr-ion-image"
      ]
    }
  ]
}
