# IAM :-
IAM infrastructure includes the following elements:-
   Principal   
   Request 
   Authentication 
   Authorization 
   Action
   Resources

When users, groups & roles are created they are available all over the world.
New users have no permissions when first created

IAM user Arn: arn:aws:iam::accountid without hyphen:user/bob
AWS console signin link:- https://myawsaccountid.signin.aws.amazon.com/console/

Principal:- defines who is going to access aws resources
## Principal can be:- 
    -Root user
    -IAM user 
    -Roles/Temporary security tokens

## There are three ways that IAM authenticates a principal
   -username/password
   -IAM user
   -Accesskey/ Session Token

## When a principal sends a request via console, cli, sdks or apis include following:-
   -Actions that the principal wants to perform
   -Resources upon which the actions are performed
   -principal information including the environment from which the request was made

IAM can be accessed using:- console, cli, sdk , api
Power users are those who have the full access to aws services except IAM users, groups, roles, billing


## Two types of policies:-
  -Identity Based Policies (based on user, role, federated user, application.)
     1)Managed Policy
           A)AWS managed policy:- standalone policies managed by aws.
           B)Customer managed policy:- standalone policies managed by customers.
     2)Inline policies :- An inline policy is a policy that's embedded in a principal entity (a user, group, or role)—that is, the policy is an inherent part of the principal entity. You can create a policy and embed it in a principal entity, either when you create the principal entity or later.
  -Resource based policies (these policies are attached to resources like s3 bucket)

## Identity based policies has following elements:-
   -Effect
   -Service
   -Resource
   -Action
   -Condition

1 explicit deny will override all explicit allow in the policy 
1 explicit allow will override all implicit deny in the policy


## Cross account access can be done in two ways:-
    -Assuming Roles
    -Resource based policy

Cross account access with a resource based policy has an advantage over a role , with a resource that is accessed through a resource based policy , the user still works in the trusted account and does not  have to give up his or her user permissions in place of the role permissions.



## STS has multiple apis to request session token (temporary security credentials)
   -AssumeRole
     Who can call:- IAM user or user with existing temporary security credentials
   -AssumeRolewithSAML
      Who can call:- caller must pass a SAML authentication response that indicates authentication from a known identity provider
   -AssumeRolewithWebIdentities
      Who can call:-Any user , caller must pass a web identity token that indicates authentication form a known identity provider.
   -GetSessionToken 
      Who can call:-IAM user or AWS account root user
   -GetFederationToken
      Who can call:- IAM users or aws account root user


## There are two ways to assume a role
   - Interactively in the IAM console
   - Programmatically with the AWS CLI 

IAM role delegation :- To delegate permission to access a resource you create an IAM role that has two policies attached
   - permission policy where action & resources the role can assumed are defined.
   - trust policy specifies which trusted accounts are allowed to grant its user permissions to assume the role.
   
## Activity:
1. cross account access using roles & resource based policy.
2. Login to aws management console using login with amazon, google, Facebook , (with/without)cognito    i.e. oidc compliant.
3. Access any aws service from webpage, or  mobile app using login with amazon, google, Facebook , (with/without)cognito  i.e. oidc compliant.
4. Try with saml above 2.
