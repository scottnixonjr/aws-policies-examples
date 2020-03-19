
## Policy Types

The following policy types, listed in order of frequency, are available for use in AWS. For more details, see the sections below for each policy type.

 - Identity-based policies – Attach managed and inline policies to IAM identities (users, groups to which users belong, or roles). Identity-based policies grant permissions to an identity.

 - Resource-based policies – Attach inline policies to resources. The most common examples of resource-based policies are Amazon S3 bucket policies and IAM role trust policies. Resource-based policies grant permissions to a principal entity that is specified in the policy. Principals can be in the same account as the resource or in other accounts.

 - Permissions boundaries – Use a managed policy as the permissions boundary for an IAM entity (user or role). That policy defines the maximum permissions that the identity-based policies can grant to an entity, but does not grant permissions. Permissions boundaries do not define the maximum permissions that a resource-based policy can grant to an entity.

 - Organizations SCPs – Use an AWS Organizations service control policy (SCP) to define the maximum permissions for account members of an organization or organizational unit (OU). SCPs limit permissions that identity-based policies or resource-based policies grant to entities (users or roles) within the account, but do not grant permissions.

 - Access control lists (ACLs) – Use ACLs to control which principals in other accounts can access the resource to which the ACL is attached. ACLs are similar to resource-based policies, although they are the only policy type that does not use the JSON policy document structure. ACLs are cross-account permissions policies that grant permissions to the specified principal entity. ACLs cannot grant permissions to entities within the same account.

 - Session policies – Pass advanced session policies when you use the AWS CLI or AWS API to assume a role or a federated user. Session policies limit the permissions that the role or user's identity-based policies grant to the session. Session policies limit permissions for a created session, but do not grant permissions. For more information, see Session Policies.


### Principal Examples

Everyone (anonymous users)
`"Principal": "AWS": "*.*"`

Specific Account or Accounts
`"Principal": {"AWS": "arn:aws:iam::123456789012:root"}`
`"Principal": {"AWS": "123456789012"}`

Individual IAM user
`"Principal": {"AWS": "arn:aws:iam::123456789012:user/scott.nixon"}`

Federated user (using web identity federation)
`"Principal": {"Federated": "accounts.google.com"}`

Specific Role
`"Principal": {"AWS": "arn:aws:iam::123456789012:role/myservicerole"}`

Specific Service
`"Principal": {"Service": "ec2.amazonaws.com"}`

### Actions

- Action

Wildcards (* or ?) in the action name.
`"Action": "iam:*AccessKey*"`

- NotAction - everything but what's on this list.


### Conditions

ResourceTag allows you to Tag on an existing instance.
RequestTag means you are requesting to create a new tag.
