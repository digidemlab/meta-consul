# Credentialing on AWS

* Create your IAM user;  
* Sign in with the password;  
* Download the credentials keys under the **Security Credentials** tab, and create an **Access Key**;  
* When prompted, download the `CSV` file with the keys;  
* Create a folder called **consul-deploy** in your local computer;  
* `cd` into a `consul-deploy` folder and create a file `consulvars.tfvars`;  
* `consulvars.tfvars` file will hold the credentials and variables to the deploy;  
* The content of `consulvars.tfvars` file must be:  

```
consul_aws_access_key = "XXXXXXXXXXXXXXXXXXXXXXXX"
consul_aws_secret_key = "XXXXXXXXXXXXXXXXXXXXXXXXX"
consul_deploy_region = "eu-central-1"
```

* Replace the `XXXX` to your following access and secrets keys download in the previous `CSV` file;  
* In your browser go to [terraform.io/downloads.html](terraform.io/downloads.html);  
* Download the version for your Operational System;  
* Unzip the archive;   
* Install Terraform according the OS directions;  

> **Terraform** is a software we would use to build the cloud context for the deploy  

* In the browser, go to [github.com/digidemlab](https://github.com/digidemlab/) and clone 3 repositories in your folder "consul-deploy" in your computer:
    * [terraform-consul](https://github.com/digidemlab/terraform-consul)
    * [meta-consul](https://github.com/digidemlab/meta-consul)
    * [server-builds-consul](https://github.com/digidemlab/server-builds-consul)
 * After the clone, `cd` into `terraform-consul/aws_small`
 * Then run this cmd:

``` bash
$ terraform apply --var-file=../../consulfar.tfvars
```
You will see the basic network being created
