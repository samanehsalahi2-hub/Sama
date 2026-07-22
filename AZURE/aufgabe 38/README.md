# Individual Learning Phase: PowerShell Scripting Fundamentals in Azure

## Your Goal

You will step-by-step create a small PowerShell automation package for Azure. At the end, you will have a runnable script that uses variables, arrays, hashtables, conditions, and loops to prepare, create, evaluate, and optionally clean up multiple Azure resource groups.

## What you need

- Azure access with permissions to create and delete resource groups
- Azure Cloud Shell **or** PowerShell 7 with the **Az** module installed
- An editor for scripts, for example Visual Studio Code
- A unique name prefix, for example your initials and the current date
- A local working folder or a Cloud Shell folder for your scripts

## Schedule

- **10 Minutes:** Check environment and create working folder
- **20 Minutes:** Task 1
- **20 Minutes:** Task 2
- **25 Minutes:** Task 3
- **25 Minutes:** Task 4
- **15 Minutes:** Task 5
- **5 Minutes:** Reflection
- **Optional remaining time:** Extension tasks

## Basic Tasks

### Task 1:

Prepare script environment **Goal:** You set up your working environment and execute your first PowerShell script in an Azure context.

**Task Description:**
Create a working folder for this Learning Phase. Inside it, create a script named `01-setup.ps1`. The script should:

- output the current PowerShell version
- output your current date and time
- display your Azure context, at least with account name, tenant, and subscription
- output a short status message indicating that your environment is ready for use

If you are working locally, first connect to Azure. If you are working in Cloud Shell, check the already active context. Execute the script and note down the name of the active subscription.

**Expected Outcome / Desired State:**
You have a functioning working folder, an executable first script, and a visible Azure context without error messages.

### Task 2:

Create variables and data structures for your Azure script **Goal:** You plan your automation with variables, an array, and a hashtable.

**Task Description:**
Create a script named `02-planung.ps1`. Store the following information in variables and simple data structures within it:

- a unique prefix for your resources
- an Azure region
- an environment designation like `dev`
- an array with at least three workload names, for example `app`, `data`, `monitor`
- a hashtable with tags, for example for `Owner`, `Environment`, `Training`

Automatically construct the names for at least three resource groups from these values. Output the planned names and tags neatly formatted in the console.

**Expected Outcome / Desired State:**
You have a script that works with variables, an array, and a hashtable, and from it, generates several resource group names in a comprehensible way.

### Task 3:

Incorporate conditions for safe creation **Goal:** You control your script with a simple condition and avoid duplicate creation.

**Task Description:**
Create a script named `03-rg-check.ps1` or extend your existing script. For each planned resource group, the script should check:

- if the resource group already exists
- if it needs to be created
- what status message is output for it

Use an `if`-/`else` logic for this. If a resource group does not yet exist, the script should create it in the specified region with your defined tags. If it already exists, the script should skip it and clearly report this.

**Expected Outcome / Desired State:**
Your script detects existing resource groups, creates missing groups, and outputs an understandable message for each case.

### Task 4:

Automate multiple resource groups with a loop **Goal:** You automate recurring tasks with a loop.

**Task Description:**
Extend your script so that it processes not just a single resource group, but all names from your array one after another. Use a loop for this. Add the following to the script:

- a count of how many resource groups were newly created
- a count of how many resource groups already existed
- a concluding output with a short summary

Make sure to structure your script clearly, for example with clearly named variables, meaningful output messages, and comment blocks.

**Expected Outcome / Desired State:**
A single script automatically processes multiple resource groups and provides a traceable summary at the end.

### Task 5:

Prepare inventory and optional cleanup **Goal:** You create a simple Azure report and add controllable cleanup logic.

**Task Description:**
Create a script named `04-report-cleanup.ps1`. The script should read all resource groups with your prefix or your Training tag and create a small report from them. Include at least the following information in the report:

- Name
- Region
- Provisioning State
- Tags

Save the report as a file in your working folder. Additionally, add a variable like `$Cleanup` that you use to control whether the found resource groups should only be listed or also deleted. Initially, set this variable to a safe default value.

**Expected Outcome / Desired State:**
You have a reporting script that documents your created resource groups and contains a clearly identifiable, controllable cleanup option.

## Extension Tasks

### Extension Task 1: Parameterize your main script

**Goal:** You make your script more flexible and reusable.

**Task Description:**
Add a `param` block to your main script. Pass at least the following values as parameters:

- Prefix
- Region
- Environment
- Number or list of workloads

Afterward, start your script at least twice with different parameters, without changing the script code itself.

**Expected Outcome / Desired State:**
Your script can be executed with different inputs and remains organized and reusable.

### Extension Task 2: Build simple validations

**Goal:** You increase the reliability of your script.

**Task Description:**
Extend your script with at least two checks, for example:

- The prefix must not be empty.
- The region must be available in Azure.
- The workload array must contain at least one entry.

If a check fails, the script should abort with a clear error message or output a meaningful alternative.

**Expected Outcome / Desired State:**
Your script reacts controllably to faulty inputs and provides understandable feedback.

### Extension Task 3: Create a small inventory for Azure resource groups

**Goal:** You apply your scripting fundamentals to a typical management task in Azure.

**Task Description:**
Create an additional script named `05-inventar.ps1`. Read all resource groups in your subscription and determine:

- how many resource groups are present in total
- in which regions they are located
- which resource groups do not have an `Owner` tag

Output the results in a structured way and additionally save a file with your inventory.

**Expected Outcome / Desired State:**
You have a practical analysis script that automatically collects and visualizes Azure inventory data.

## Important Notes

- Work as much as possible in a test or sandbox environment.
- Use a unique prefix so that you can uniquely identify your resource groups.
- Only create resources that you understand and can clean up properly afterward.
- Before each deletion action, carefully check that only your own test resource groups are affected.
- Keep your scripts readable, for example, with meaningful variable names and clear outputs.
- Save each script version so that you can revert to a working state in case of errors.

## Reflection Questions

- Where did you effectively use variables, arrays, and hashtables in your script?
- At which point did an `if`-/`else` condition help you avoid errors or duplicate actions?
- Which recurring Azure task could you simplify with a loop?
- How would you extend your script to make it usable in another subscription or project?
- Which output messages in your script help you most in understanding the flow?
