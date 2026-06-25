# aufgabe 3

## Azure Policy – Scenario Table

| **Policy** | **What it controls** | **Available Effects** | **Real-world scenarios** | **Practical example** |
|------------|----------------------|------------------------|---------------------------|------------------------|
| [Allowed locations](ca://s?q=Explain_Allowed_Locations_Policy) | Restricts which Azure regions resources can be deployed to | Audit / Deny / Disabled | - Enforcing data residency (e.g., GDPR)  
- Preventing accidental deployments in wrong regions  
- Cost control (some regions are more expensive)  
- Standardizing deployments across teams | If only *West Europe* is allowed, creating a VM in *East US* will be denied |
| [Require a tag on resources](ca://s?q=Explain_Require_Tag_On_Resources) | Ensures all resources include a specific tag | Deny | - Cost management and chargeback  
- Identifying resource owners  
- Enforcing organizational governance  
- Keeping the environment clean and traceable | If the required tag is *Environment*, creating a Storage Account without this tag will be denied |




Compliance Analysis – Allowed Locations Policy
Policy name: Allowed locations

Scope: Azure for Students / rg-policy-lab-sama

Compliance state: Not started

Reason: No resources exist inside the scope yet, so Azure has not evaluated compliance.

Behavior observed: When attempting to create a VM in an unauthorized region (Korea Central), the deployment failed during validation due to policy enforcement.

Conclusion: Although compliance shows “Not started,” the policy is functioning correctly because it successfully denied the creation of a resource in a disallowed region.
