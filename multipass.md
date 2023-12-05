# Build a local Kubernetes Cluster with Multipass
[Multipass](https://multipass.run/) is a CLI tool, build by Canonical, in order to generate cloud-systel Ubuntu VMs on a Linux, MacOS or Windows machine. Depending on the size of the underlying infrastructure you can quickly build out a local mini-cloud. This is a great way to practice development with Kubernetes ecosystem on a budget. Other options include [AWS](https://portal.aws.amazon.com/billing/signup?refid=em_127222&redirect_url=https%3A%2F%2Faws.amazon.com%2Fregistration-confirmation#/start/email), [Azure](https://azure.microsoft.com/en-us/free/search/?ef_id=_k_CjwKCAiAjrarBhAWEiwA2qWdCPW1oFMX8yFDQGIUHnvArjt4XP_giNV0HIFIYAl0nSDK6Da6FIPcoxoC2V0QAvD_BwE_k_&OCID=AIDcmmfq865whp_SEM__k_CjwKCAiAjrarBhAWEiwA2qWdCPW1oFMX8yFDQGIUHnvArjt4XP_giNV0HIFIYAl0nSDK6Da6FIPcoxoC2V0QAvD_BwE_k_&gad_source=1&gclid=CjwKCAiAjrarBhAWEiwA2qWdCPW1oFMX8yFDQGIUHnvArjt4XP_giNV0HIFIYAl0nSDK6Da6FIPcoxoC2V0QAvD_BwE), [GCP](https://cloud.google.com/free?utm_source=google&utm_medium=cpc&utm_campaign=na-US-all-en-dr-bkws-all-all-trial-e-dr-1605212&utm_content=text-ad-none-any-DEV_c-CRE_665665924741-ADGP_Hybrid+%7C+BKWS+-+MIX+%7C+Txt_Google+Cloud+Free-KWID_43700077224933019-kwd-886545049102&utm_term=KW_gcp%20free%20account-ST_gcp+free+account&gad_source=1&gclid=CjwKCAiAjrarBhAWEiwA2qWdCD_OFhSy3ihdoKlgLzwWUXV81n_kRJJIXCae-v1ivhf_G92dckjlpxoCAIMQAvD_BwE&gclsrc=aw.ds), [IBM Cloud](https://cloud.ibm.com/registration) and a host of other platforms that you might otherwise have to pay for. My motto is do what is best for your learning experience!

## Multipass Installation
In my current setup, I am using MacOS on a M2 device. So understand that there may arise an instance where certain configurations or changes need to be made regarding your own setup. Follow the installation process for your workstation OS:

### MACOS 
The steps for MacOS were are listed under the assumption that you have [Brew installed](https://brew.sh/). If you do not, you can see what this package manager is about and download it to simplify your life. Thank me later! If you would rather use the install manager, then you can visit [this page](https://multipass.run/docs/installing-on-macos) for more guidance.

1. brew install --cask multipass

## MicroK8s Installation
For this scenario we are going to utilize MicroK8s for the Kubernetes installation. You can also use K3s or toy around with the lastest upstream Kubernetes release. For resource consumption purposes coupled with wanting something that maintains similar functionality to upstream Kubernetes releases, Microk8s was the best option.

1. `brew install ubuntu/microk8s/microk8s`
    <!--- Install Microk8s on your local workstation or operating system --->
2. `microk8s install`
3. `microk8s status`
    <!--- You will see a list of addons available to enable on your cluster --->
4. `microk8s enable <addon>`
    <!--- Run this command for each addon you would like to enable in your cluster. In this scenario we are enabling the DNS, Istio service, Kube Dashboard, and a private registry. --->
5. `microk8s disable <addon>`
    <!--- This command can be used in order to disable a service that you have enabled. --->

### Windows OS
For Windows operating systems, you can view the following [document](https://microk8s.io/docs/install-windows) for installation. 

### Ubuntu Linux
For Ubuntu operating systems, you can use the following [document](https://microk8s.io/docs/getting-started) for installation. 

## Creating Your Multi-Node Cluster

## For Additional Help