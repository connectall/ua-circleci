# connectall-circleci-adapter
Circle CI Adapter for ConnectALL


ConnectALL Circle CI adapter is built on top of Universal adapter configuration. 

## Usecase
Trigger a pipeline when an action is done in the source system. 

## Examples
* Deploy to staging, on review complete
* Deploy to production, on regression complete and an approval

## Define application links
* Create an application link in ConnectALL between CircleCI and a destination application of your choice
* Use Circle CI Token in username and leave password empty when creating a new connection to CircleCI
* Navigate to `Configuration -> Connections` screen and create a new connection to Trello using `https:/circleci.com` as the endpoint
* In the Entity mapping tab under Advanced Properties choose "Sync Type" as POLL
* In the WebHook Grid use the templates below for each operation

> As of now only Get Record, Create Record API's are implemented for triggering the pipelines in CircleCI

|Operation|API Method|Template|
|--- | --- | ---|
|QUERY MODIFIED RECORDS|GET|/api/v2/project/${VCS}/${Organization}/${Repository}/pipeline|
|READ RECORD BY ID|GET|/api/v2/project/${VCS}/${Organization}/${Repository}/pipeline/${recordId}|
|CREATE RECORD|POST|/api/v2/project/${VCS}/${Organization}/${Repository}/pipeline|
|UPDATE RECORD|PUT|/api/v2/project/${VCS}/${Organization}/${Repository}/pipeline|


> In order to use the circleci adapter you will need to get the license from ConnectALL sales team. Please reach out to sales@connectall.com for licenses and quotes.
