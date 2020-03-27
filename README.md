Sample configuration

Table of Contents
- Contexts
- Permissions

# Contexts
## Create a context as a non-admin user of your organization
https://circleci.com/gh/organizations/ORGNAME/settings#contexts > `Create Context`
Name: test > `create`
Error: Something unexpected happened
https://circleci.com/docs/2.0/contexts/#creating-and-using-a-context
`Note: Any organization member can create a context only organization administrators can restrict it with a security group.`
angelisacci was able to create the context `test`, when viewing the org users page (https://circleci.com/gh/organizations/ORGNAME/settings#users), only angelisacci is listed

### Troubleshooting
1. have angelisamaria follow project on Circle (https://circleci.com/gh/ORGNAME/REPONAME) > `Follow Project` and am still unable to create a context as a non-admin
2.  changing angelisamaria's role to owner (https://github.com/orgs/ORGNAME/people) and still unable to create a context
3. log out and log back in, still does not work, able to click into context and view (need to try using one). Upon clicking `+ Add Environment Variable`, the same error `Something unexpected happened.` appears
Viewing the network tab, I see the POST request to GraphQL:
```
locations: [{line: 2, column: 3}]
message: "Internal error occurred."
path: ["createContext"]
0: "createContext"
```
```
Request URL: https://circleci.com/graphql-unstable
Request Method: POST
Status Code: 200 OK
```

4. visiting (https://circleci.com/gh/ORGNAME/REPONAME/edit#env-vars) as angelisamaria to add env. var to a specific project, click `Add Variable` and creating `TEST` works. Need to determine if the env var can be read when using in a config.
5. Downloading firefox and attemping to create a context that way annnndddd it worked.. tried replicating this again and it did not work. 
6. Also changing permissions for the team from `read` to `write` also worked

# Permissions
- Inviting a user to the team via GitHub will be mirrored in CircleCI
- Users can see other team members (https://circleci.com/team/gh/ORGNAME) and the # projects followed
- While part of the org, users can view their usage (https://circleci.com/gh/organizations/ORGNAME/settings#usage)
- A user's permissions for a specific repo within the org https://github.com/orgs/ORGNAME/people/USERNAME/repositories/ORGNAME/REPONAME 
- Shows the "orgs" a user has permissions to, including their user account https://circleci.com/account/plans


---
Other things to test & evaluate:
- Using PRs
- GH Statuses
- CircleCI Checks
- Admin/non-admin permissions
- Context groups
(perhaps having the table of contents reflect various branches)
