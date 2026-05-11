# azure-entra-id-rbac
Hands-on lab: Configuring Microsoft Entra ID users, RBAC role assignments and access control in Azure. Includes real-world Authorization Failed error demonstration using Reader vs Contributor roles.

# Azure Entra ID & RBAC Lab

## Objective
Configure Microsoft Entra ID users and Role-Based Access Control (RBAC) 
role assignments in Azure and verify access permissions hands-on.

## Environment
- Microsoft Azure Free Account
- Microsoft Entra ID Free Tier
- Azure Portal
- Resource Group: rsg1

## Tasks Completed
- [x] Created test user (user1) in Microsoft Entra ID
- [x] Created Resource Group (rsg1)
- [x] Assigned Reader role to user1 at Subscription scope
- [x] Logged in as user1 in incognito browser to verify access
- [x] Verified user1 can view resources but cannot create or delete
- [x] Confirmed AuthorizationFailed error when user1 attempted to create a VM in rsg1
- [x] Tested password reset from admin account

## Screenshots

### 1. Created User in Entra ID

### 2. Assigned Reader Role via Access Control (IAM) - Resource Group: rsg1
### 3. User1 Subscription View (Read Only)
![Created User]
<img width="952" height="473" alt="image" src="https://github.com/user-attachments/assets/2d9e5699-5622-456a-ac09-f6fbd7de9753" />
### 4. AuthorizationFailed Error - VM Creation Blocked in rsg1
![Authorization Failed](screenshots)
<img width="808" height="380" alt="image" src="https://github.com/user-attachments/assets/7843d1ff-5728-4792-a177-c3d69280845d" />
### 5. Password Reset from Admin Account
<img width="953" height="502" alt="Screenshot 2026-05-11 111035" src="https://github.com/user-attachments/assets/a45e01eb-0685-4e6a-845f-c6281778718d" />


## Key Concepts Learned

### Authentication vs Authorization
- **Authentication** - Verifying who you are (handled by Microsoft Entra ID)
- **Authorization** - Controlling what you can do (handled by Azure RBAC)
- These are two separate steps - a user can be authenticated but still 
  unauthorized to perform certain actions

### RBAC Roles
| Role | View Resources | Create Resources | Delete Resources | Assign Roles |
|------|---------------|-----------------|-----------------|--------------|
| Reader | Yes | No | No | No |
| Contributor | Yes | Yes | Yes | No |
| Owner | Yes | Yes | Yes | Yes |

### RBAC Scope Levels
- Management Group
- Subscription (assigned Reader role at this level in this lab)
- Resource Group (rsg1)
- Resource

## Important Notes
- RBAC changes can take up to 5-10 minutes to propagate
- Always test access by logging in as the user in a separate incognito browser
- Deleting a user in Entra ID does not automatically remove their role assignments
- Users created in Entra ID have no access by default - roles must be explicitly assigned
- Deleting a Resource Group (rsg1) removes all resources inside it in one click

## References
- [Microsoft Entra ID Documentation](https://learn.microsoft.com/en-us/entra/identity/)
- [Azure RBAC Documentation](https://learn.microsoft.com/en-us/azure/role-based-access-control/)
- [AZ-104 Study Guide](https://learn.microsoft.com/en-us/certifications/exams/az-104)
