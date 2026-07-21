# Individual Learning Phase: First Steps with Azure CLI

## Your Goal

You will set up the Azure CLI, sign in to Azure, and independently perform typical administrative tasks. In doing so, you will create and manage resources using the Azure CLI, verify results directly in Azure, and compare selected commands with PowerShell.

## What you need

- Azure access with an active subscription
- A computer with internet access
- A terminal:
  - Windows Terminal, PowerShell, or Command Prompt
  - alternatively, Azure Cloud Shell
- A text editor for notes
- Optional: Access to the Azure portal to verify results

## Schedule

- 15 minutes: Task 1
- 15 minutes: Task 2
- 25 minutes: Task 3
- 25 minutes: Task 4
- 20 minutes: Task 5
- 10 minutes: Cleanup, Review, Reflection
- 10 minutes: Reserve or Extension tasks

## Basic Tasks

### Task 1:

Make Azure CLI ready for use **Goal:** You ensure that you can use the Azure CLI and that your working environment is correctly prepared.

**Instructions:** Check if the Azure CLI is available on your system. If it is not yet installed, install it or switch to Azure Cloud Shell. Then open a terminal and check the installed version. Briefly document the environment you are working in and the version of the Azure CLI you are using.

**Expected Result / Target State:** You can execute `az` in the terminal, display the version information, and clearly name your chosen working environment.

### Task 2:

Login and Basic Configuration **Goal:** You sign in to Azure and set up the appropriate subscription for your subsequent work.

**Instructions:** Sign in using the Azure CLI. Then list the available subscriptions and specifically select the subscription you want to work with. After that, check which default values are currently active. Also research how to set default values such as location or resource group in the Azure CLI, and set at least one meaningful default value. Note the most important commands used.

**Expected Result / Target State:** You are successfully signed in, working in the correct subscription, and have set or consciously checked at least one default value for your CLI session.

### Task 3:

Create and Manage a Resource Group **Goal:** You perform your first simple administrative tasks with the Azure CLI.

**Instructions:** Create a new resource group in a region of your choice. Use a unique name. Then list all resource groups and specifically filter or search for your newly created resource group. Add tags like `Project`, `Environment`, and `Owner` or update them. Then check the details of your resource group with an appropriate display command.

**Expected Result / Target State:** A new resource group exists in your subscription, is discoverable via CLI, and contains traceable metadata through tags.

### Task 4:

Deploy an Azure Service via CLI **Goal:** You use the Azure CLI for the deployment and verification of a selected Azure service.

**Instructions:** Create a Storage Account in your resource group with a globally unique name. Choose a meaningful SKU and ensure that the name meets Azure requirements. After creation, check the properties of the Storage Account. Then list the Storage Accounts in your resource group. Additionally, determine which endpoints or security-relevant settings can be displayed for your Storage Account.

**Expected Result / Target State:** A functional Storage Account is present in your resource group, which you can list and display in detail via CLI.

### Task 5:

Practically Compare Azure CLI and PowerShell **Goal:** You identify differences in syntax, operation, and application areas based on your own work steps.

**Instructions:** Select three tasks from your previous steps, for example:

- List resource groups
- Display a resource group
- Create or display a Storage Account

For each of these tasks, find the corresponding PowerShell command from the Az module and compare it with your used Azure CLI command. Briefly compare:

- Command structure
- Parameter logic
- Readability
- Typical use case

Create a small table with three rows for this purpose.

**Expected Result / Target State:** You have compared an Azure CLI command and a suitable PowerShell command for three specific administrative tasks and briefly documented the practical differences.

## Extension Tasks

### Extension Task 1: Query and Format Resources Specifically

**Goal:** You work more efficiently with output formats and filtering options of the Azure CLI.

**Instructions:** Output your resource groups or storage accounts in at least two different output formats, for example, as a table and as JSON. Then filter the output so that only specific information remains visible, such as name, region, and tags. Document which format is most useful for you for which purpose.

**Expected Result / Target State:** You can format Azure CLI outputs legibly and reduce them to relevant information.

### Extension Task 2: Another Simple Administrative Task with an Azure Service

**Goal:** You transfer your approach to another Azure service.

**Instructions:** Choose an additional simple service or a simple configuration change in your resource group, for example:

- Change tags of a resource
- Create a second resource
- Update properties of a resource
- Query available regions or resource types

Completely perform the task using Azure CLI and then check the result.

**Expected Result / Target State:** You have successfully implemented at least one additional administrative task with the Azure CLI and checked the result.

### Extension Task 3: Clean Up and Avoid Costs

**Goal:** You complete your work cleanly and avoid unnecessary ongoing costs.

**Instructions:** Check which resources you have created. Then either specifically delete individual resources or the entire resource group. Afterwards, verify whether the deletion has been successfully started or completed. Note which deletion strategy you have chosen and why.

**Expected Result / Target State:** Your test resources have been removed, or the deletion process has been correctly initiated and verifiably documented.

## Important Notes

- Use unique resource names, especially for Storage Accounts.
- Work preferably in your own test resource group.
- Pay attention to the selected subscription before creating resources.
- Check region and naming conventions before starting a creation command.
- Document used commands and error messages in bullet points.
- Delete no longer needed resources at the end, if you have permissions to do so.
- If a command fails, first check syntax, permissions, names, region, and active subscription.

## Reflection Questions

- Which steps in installation, login, or configuration worked smoothly for you?
- Which command required the most research for you?
- Based on your comparison, what are the biggest practical differences between Azure CLI and PowerShell?
- For which types of tasks would you prefer to use Azure CLI in the future?
- How confident do you feel now managing simple Azure resources via the command line?
- Which two commands would you particularly like to remember for daily work?
