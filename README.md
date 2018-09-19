# ansible-copy-ami
Provides ansible and python code which can easily copy an ami to an appropriate region and encrypt it.

To copy a marketplace image, you'll use

ansible-playbook copy_marketplace_image.yml -e "ami=`<marketplace ami to copy>` sourceRegion=`<source Region>` destRegion=`<Destination Region>` keypair_name=`<keypair name you want, irrelevant but no spaces>`, kms_arn=`<kms key arn that you wish to encrypt the target ami with>`"

Produces an ami with the name "properly-encrypted-copy-<ami>" which is a copy of that marketplace ami encrypted with the key of your choosing in the destination region you wish.

if you just want to copy an ami to another region, you can use

ansible-playbook copy_ami_to_region.yml -e "ami=`<source ami>` sourceRegion=`<source Region>` destRegion=`<Destination Region>`, kms_arn=`<kms key arn that you wish to encrypt the target ami with>`"
