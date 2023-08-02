terrraform init -backend-config=../../backend.hcl


env( passing value to terraform via enviromenta variable)

export TF_VAR_username=root
export TF_VAR_password=devops2010


terrraform plan
terrraform apply