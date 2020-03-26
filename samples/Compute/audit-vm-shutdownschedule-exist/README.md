# Audit if VM has a schedule for automatic shutdown

This policy audits if a shedule for automatic shutdown exists.

## Try on Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-policy%2Fmaster%2Fsamples%2FCompute%2Faudit-vm-shutdownschedule-exist%2Fazurepolicy.json)

## Try with PowerShell

````powershell
$definition = New-AzPolicyDefinition -Name "audit-vm-shutdownschedule-exist" -DisplayName "Audit if VM has a schedule for automatic shutdown" -description "This policy audits if a shedule for automatic shutdown exists." -Policy 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/Compute/audit-vm-shutdownschedule-exist/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/Compute/audit-vm-shutdownschedule-exist/azurepolicy.parameters.json' -Mode All
$definition
$assignment = New-AzPolicyAssignment -Name <assignmentname> -Scope <scope>  -publisher <Extension Publisher> -type <Extension Type> -PolicyDefinition $definition
$assignment
````

## Try with CLI

````cli

az policy definition create --name 'audit-vm-shutdownschedule-exist' --display-name 'Audit if VM has a schedule for automatic shutdown' --description 'This policy audits if a shedule for automatic shutdown exists.' --rules 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/Compute/audit-vm-shutdownschedule-exist/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/Compute/audit-vm-shutdownschedule-exist/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "audit-vm-shutdownschedule-exist"

````
