Sample configuration

Things to test & evaluate:
- Using PRs
- GH Statuses
- CircleCI Checks
- Admin/non-admin permissions
- Context groups

Invited angelisamaria (non-admin) to the team and this was reflected in CircleCI
angelisamaria can see other team members (https://circleci.com/team/gh/angcci) and the # projects followed
While logged in as angelisamaria, plan usage (https://circleci.com/gh/organizations/angcci/settings#usage) can be viewed

Attempting to create a context as angelisamaria
https://circleci.com/gh/organizations/angcci/settings#contexts > `Create Context`
Name: test > `create`
Error: Something unexpected happened
https://circleci.com/docs/2.0/contexts/#creating-and-using-a-context
`Note: Any organization member can create a context only organization administrators can restrict it with a security group.`
angelisacci was able to create the context `test`, when viewing the org users page (https://circleci.com/gh/organizations/angcci/settings#users), only angelisacci is listed
Next step: have angelisamaria follow project on Circle (https://circleci.com/gh/angcci/cci-sandbox-angcci-org) > `Follow Project` and am still unable to create a context as a non-admin
Next step: changing angelisamaria's role to owner (https://github.com/orgs/angcci/people) and still unable to create a context
Next step: log out and log back in, still does not work, able to click into context and view (need to try using one). Upon clicking `+ Add Environment Variable`, the same error `Something unexpected happened.` appears
Next step: visiting (https://circleci.com/gh/angcci/cci-sandbox-angcci-org/edit#env-vars) as angelisamaria to add env. var to a specific project, click `Add Variable` and creating `TEST` works. Need to determine if the env var can be read when using in a config.


https://circleci.com/account/plans
Tells me the "orgs" I have permissions to, even though only one is an actual GitHub org and the other is just a user account
