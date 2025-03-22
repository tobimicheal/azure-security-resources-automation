# Azure Security Resources Automation with ARM & Bicep

This project automates the deployment of core security infrastructure on Microsoft Azure using **Infrastructure as Code (IaC)** principles and **Azure DevOps Pipelines**. It includes two key resources:

- 🔐 **Azure Key Vault** deployed via ARM template
- 🛡️ **Network Security Group (NSG)** deployed via Bicep

All deployments are triggered through a CI/CD pipeline defined in `azure-pipelines.yml`.

---

### 📁 What's Inside

```bash
AzureSecurityAutomation/
├── templates/
│   ├── keyvault-arm-template.json     # ARM template to deploy Azure Key Vault
│   └── nsg-bicep-template.bicep       # Bicep template to deploy Network Security Group (NSG)
├── azure-pipelines.yml                # Azure DevOps pipeline for automated deployments
├── README.md                          # Project documentation
```
---

## 🧠 Key Features

- ✅ **Key Vault** deployed with custom name, tenant ID, and SKU
- ✅ **NSG** includes an inbound SSH rule (port 22) for controlled remote access
- ✅ **CI/CD Pipeline** using Azure CLI with managed identity login
- ✅ **Hybrid IaC** using both ARM (for Key Vault) and Bicep (for NSG)..

---

## 🛠️ Technologies Used

- [Azure Resource Manager (ARM) Templates](https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/overview)
- [Bicep](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/overview)
- [Azure DevOps Pipelines](https://learn.microsoft.com/en-us/azure/devops/pipelines/?view=azure-devops)
- [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)

---

## 🚀 How to Use

> **Note**: You'll need an Azure DevOps project connected to your Azure subscription using a service connection (Managed Identity recommended).

✅ How to Use
1. Clone the repository
git clone https://github.com/your-username/azure-security-resources-automation.git
2. Push to Azure Repos or GitHub-Azure DevOps integration
3. Edit the pipeline if needed
   Resource group name: ade-sandbox-rg
   Vault name: You can modify this inside keyvault-arm-template.json (make sure it's globally unique!)
4. Run the pipeline
   It will trigger automatically on changes to the main branch
   Or you can trigger it manually from Azure DevOps


### 📦 Deployment Output

Once the pipeline completes successfully, you’ll see:

- ✅ A **Key Vault** resource in the specified resource group
- ✅ A **Network Security Group (NSG)** with an SSH rule visible under **“Inbound security rules”**

