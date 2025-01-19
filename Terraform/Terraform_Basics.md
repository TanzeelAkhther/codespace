**Providers**
Three tiers of Providers:
1. **Official Provider** - Owned and maintained by HashiCorp and includes major cloud providers such as AWS, Azure and GCP.
2. **Partner Provider** - owned and maintained by a third-party tech company that has gone through a partner provider process with HashiCorp and includes BIG-IP Provider from F5 networks, heroku, Digital Ocean,etc.
3. **Community Provider** - Published and maintained by individual contributors of the HashiCorp Community. Ex: Activedirectory, ucloud and netapp-gcp
---------------------------------------------------------------

**terraform init** command shows the version of the plugin that has been installed.

**Plugins**
Plugins are downloaded in a hidden dir called .terraform/plugins in the working dir containing the  config files.
Plugin name that we see, hashicorp/local is also known as source address.
This is an identified that is used by terraform to locate and download the plugin from the registry.
```
registry.terraform.io/hashicorp/local: version = "~> 2.0.0"
#registry.terraform.io -hostname is the name of the registry where the plugin is located.It is optional.It is default registry
#hashicorp - organizational namespace
#local- Type
```
**random provider** - allows us to create random resources such as random ID or random interger or random paswd etc.

**Multiple Providers**
```
resource "local_file" "pet"{
  filename = "/root/pets.txt"
  content = "We love pets!"
}
resource "random_pet" "my-pet"{
  prefix = "Mrs"
  seperator = "."
  length = "1"
}
```

**Note: we have to initialize the directory by running terraform init command because whenever we add a resource for a provider that has not been used so far in the configuration directory, it will require us to initialize once again to install the required providers.**







