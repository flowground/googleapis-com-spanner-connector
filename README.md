# ![LOGO](logo.png) Cloud Spanner **flow**ground Connector

## Description

A generated **flow**ground connector for the Cloud Spanner API (version v1).

Generated from: https://api.apis.guru/v2/specs/googleapis.com/spanner/v1/swagger.json<br/>
Generated at: 2019-05-07T17:42:00+03:00

## API Description

Cloud Spanner is a managed, mission-critical, globally consistent and scalable relational database service.

## Authorization

Supported authorization schemes:
- OAuth2

For OAuth 2.0 you need to specify OAuth Client credentials as environment variables in the connector repository:
* `OAUTH_CLIENT_ID` - your OAuth client id
* `OAUTH_CLIENT_SECRET` - your OAuth client secret

## Actions

### Drops (aka deletes) a Cloud Spanner database.

*Tags:* `projects`

#### Input Parameters
* `database` - _required_ - Required. The database to be dropped.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Returns the schema of a Cloud Spanner database as a list of formatted<br/>
> DDL statements. This method does not show pending schema updates, those may<br/>
> be queried using the Operations API.

*Tags:* `projects`

#### Input Parameters
* `database` - _required_ - Required. The database whose schema we wish to get.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Updates the schema of a Cloud Spanner database by<br/>
> creating/altering/dropping tables, columns, indexes, etc. The returned<br/>
> long-running operation will have a name of<br/>
> the format `<database_name>/operations/<operation_id>` and can be used to<br/>
> track execution of the schema change(s). The<br/>
> metadata field type is<br/>
> UpdateDatabaseDdlMetadata.  The operation has no response.

*Tags:* `projects`

#### Input Parameters
* `database` - _required_ - Required. The database to update.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Lists all sessions in a given database.

*Tags:* `projects`

#### Input Parameters
* `database` - _required_ - Required. The database in which to list sessions.
* `filter` - _optional_ - An expression for filtering the results of the request. Filter rules are
case insensitive. The fields eligible for filtering are:

  * `labels.key` where key is the name of a label

Some examples of using filters are:

  * `labels.env:*` --> The session has the label "env".
  * `labels.env:dev` --> The session has the label "env" and the value of
                       the label contains the string "dev".
* `pageSize` - _optional_ - Number of sessions to be returned in the response. If 0 or less, defaults
to the server's maximum allowed page size.
* `pageToken` - _optional_ - If non-empty, `page_token` should contain a
next_page_token from a previous
ListSessionsResponse.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Creates a new session. A session can be used to perform<br/>
> transactions that read and/or modify data in a Cloud Spanner database.<br/>
> Sessions are meant to be reused for many consecutive<br/>
> transactions.<br/>
> <br/>
> Sessions can only execute one transaction at a time. To execute<br/>
> multiple concurrent read-write/write-only transactions, create<br/>
> multiple sessions. Note that standalone reads and queries use a<br/>
> transaction internally, and count toward the one transaction<br/>
> limit.<br/>
> <br/>
> Cloud Spanner limits the number of sessions that can exist at any given<br/>
> time; thus, it is a good idea to delete idle and/or unneeded sessions.<br/>
> Aside from explicit deletes, Cloud Spanner can delete sessions for which no<br/>
> operations are sent for more than an hour. If a session is deleted,<br/>
> requests to it return `NOT_FOUND`.<br/>
> <br/>
> Idle sessions can be kept alive by sending a trivial SQL query<br/>
> periodically, e.g., `"SELECT 1"`.

*Tags:* `projects`

#### Input Parameters
* `database` - _required_ - Required. The database in which the new session is created.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Deletes a long-running operation. This method indicates that the client is<br/>
> no longer interested in the operation result. It does not cancel the<br/>
> operation. If the server doesn't support this method, it returns<br/>
> `google.rpc.Code.UNIMPLEMENTED`.

*Tags:* `projects`

#### Input Parameters
* `name` - _required_ - The name of the operation resource to be deleted.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Gets the latest state of a long-running operation.  Clients can use this<br/>
> method to poll the operation result at intervals as recommended by the API<br/>
> service.

*Tags:* `projects`

#### Input Parameters
* `name` - _required_ - The name of the operation resource.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Updates an instance, and begins allocating or releasing resources<br/>
> as requested. The returned long-running<br/>
> operation can be used to track the<br/>
> progress of updating the instance. If the named instance does not<br/>
> exist, returns `NOT_FOUND`.<br/>
> <br/>
> Immediately upon completion of this request:<br/>
> <br/>
>   * For resource types for which a decrease in the instance's allocation<br/>
>     has been requested, billing is based on the newly-requested level.<br/>
> <br/>
> Until completion of the returned operation:<br/>
> <br/>
>   * Cancelling the operation sets its metadata's<br/>
>     cancel_time, and begins<br/>
>     restoring resources to their pre-request values. The operation<br/>
>     is guaranteed to succeed at undoing all resource changes,<br/>
>     after which point it terminates with a `CANCELLED` status.<br/>
>   * All other attempts to modify the instance are rejected.<br/>
>   * Reading the instance via the API continues to give the pre-request<br/>
>     resource levels.<br/>
> <br/>
> Upon completion of the returned operation:<br/>
> <br/>
>   * Billing begins for all successfully-allocated resources (some types<br/>
>     may have lower than the requested levels).<br/>
>   * All newly-reserved resources are available for serving the instance's<br/>
>     tables.<br/>
>   * The instance's new resource levels are readable via the API.<br/>
> <br/>
> The returned long-running operation will<br/>
> have a name of the format `<instance_name>/operations/<operation_id>` and<br/>
> can be used to track the instance modification.  The<br/>
> metadata field type is<br/>
> UpdateInstanceMetadata.<br/>
> The response field type is<br/>
> Instance, if successful.<br/>
> <br/>
> Authorization requires `spanner.instances.update` permission on<br/>
> resource name.

*Tags:* `projects`

#### Input Parameters
* `name` - _required_ - Required. A unique identifier for the instance, which cannot be changed
after the instance is created. Values are of the form
`projects/<project>/instances/a-z*[a-z0-9]`. The final
segment of the name must be between 6 and 30 characters in length.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Starts asynchronous cancellation on a long-running operation.  The server<br/>
> makes a best effort to cancel the operation, but success is not<br/>
> guaranteed.  If the server doesn't support this method, it returns<br/>
> `google.rpc.Code.UNIMPLEMENTED`.  Clients can use<br/>
> Operations.GetOperation or<br/>
> other methods to check whether the cancellation succeeded or whether the<br/>
> operation completed despite cancellation. On successful cancellation,<br/>
> the operation is not deleted; instead, it becomes an operation with<br/>
> an Operation.error value with a google.rpc.Status.code of 1,<br/>
> corresponding to `Code.CANCELLED`.

*Tags:* `projects`

#### Input Parameters
* `name` - _required_ - The name of the operation resource to be cancelled.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Lists Cloud Spanner databases.

*Tags:* `projects`

#### Input Parameters
* `pageSize` - _optional_ - Number of databases to be returned in the response. If 0 or less,
defaults to the server's maximum allowed page size.
* `pageToken` - _optional_ - If non-empty, `page_token` should contain a
next_page_token from a
previous ListDatabasesResponse.
* `parent` - _required_ - Required. The instance whose databases should be listed.
Values are of the form `projects/<project>/instances/<instance>`.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Creates a new Cloud Spanner database and starts to prepare it for serving.<br/>
> The returned long-running operation will<br/>
> have a name of the format `<database_name>/operations/<operation_id>` and<br/>
> can be used to track preparation of the database. The<br/>
> metadata field type is<br/>
> CreateDatabaseMetadata. The<br/>
> response field type is<br/>
> Database, if successful.

*Tags:* `projects`

#### Input Parameters
* `parent` - _required_ - Required. The name of the instance that will serve the new database.
Values are of the form `projects/<project>/instances/<instance>`.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Lists the supported instance configurations for a given project.

*Tags:* `projects`

#### Input Parameters
* `pageSize` - _optional_ - Number of instance configurations to be returned in the response. If 0 or
less, defaults to the server's maximum allowed page size.
* `pageToken` - _optional_ - If non-empty, `page_token` should contain a
next_page_token
from a previous ListInstanceConfigsResponse.
* `parent` - _required_ - Required. The name of the project for which a list of supported instance
configurations is requested. Values are of the form
`projects/<project>`.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Lists all instances in the given project.

*Tags:* `projects`

#### Input Parameters
* `filter` - _optional_ - An expression for filtering the results of the request. Filter rules are
case insensitive. The fields eligible for filtering are:

  * `name`
  * `display_name`
  * `labels.key` where key is the name of a label

Some examples of using filters are:

  * `name:*` --> The instance has a name.
  * `name:Howl` --> The instance's name contains the string "howl".
  * `name:HOWL` --> Equivalent to above.
  * `NAME:howl` --> Equivalent to above.
  * `labels.env:*` --> The instance has the label "env".
  * `labels.env:dev` --> The instance has the label "env" and the value of
                       the label contains the string "dev".
  * `name:howl labels.env:dev` --> The instance's name contains "howl" and
                                 it has the label "env" with its value
                                 containing "dev".
* `pageSize` - _optional_ - Number of instances to be returned in the response. If 0 or less, defaults
to the server's maximum allowed page size.
* `pageToken` - _optional_ - If non-empty, `page_token` should contain a
next_page_token from a
previous ListInstancesResponse.
* `parent` - _required_ - Required. The name of the project for which a list of instances is
requested. Values are of the form `projects/<project>`.
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Creates an instance and begins preparing it to begin serving. The<br/>
> returned long-running operation<br/>
> can be used to track the progress of preparing the new<br/>
> instance. The instance name is assigned by the caller. If the<br/>
> named instance already exists, `CreateInstance` returns<br/>
> `ALREADY_EXISTS`.<br/>
> <br/>
> Immediately upon completion of this request:<br/>
> <br/>
>   * The instance is readable via the API, with all requested attributes<br/>
>     but no allocated resources. Its state is `CREATING`.<br/>
> <br/>
> Until completion of the returned operation:<br/>
> <br/>
>   * Cancelling the operation renders the instance immediately unreadable<br/>
>     via the API.<br/>
>   * The instance can be deleted.<br/>
>   * All other attempts to modify the instance are rejected.<br/>
> <br/>
> Upon completion of the returned operation:<br/>
> <br/>
>   * Billing for all successfully-allocated resources begins (some types<br/>
>     may have lower than the requested levels).<br/>
>   * Databases can be created in the instance.<br/>
>   * The instance's allocated resource levels are readable via the API.<br/>
>   * The instance's state becomes `READY`.<br/>
> <br/>
> The returned long-running operation will<br/>
> have a name of the format `<instance_name>/operations/<operation_id>` and<br/>
> can be used to track creation of the instance.  The<br/>
> metadata field type is<br/>
> CreateInstanceMetadata.<br/>
> The response field type is<br/>
> Instance, if successful.

*Tags:* `projects`

#### Input Parameters
* `parent` - _required_ - Required. The name of the project in which to create the instance. Values
are of the form `projects/<project>`.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Gets the access control policy for a database resource.<br/>
> Returns an empty policy if a database exists but does<br/>
> not have a policy set.<br/>
> <br/>
> Authorization requires `spanner.databases.getIamPolicy` permission on<br/>
> resource.

*Tags:* `projects`

#### Input Parameters
* `resource` - _required_ - REQUIRED: The Cloud Spanner resource for which the policy is being retrieved. The format is `projects/<project ID>/instances/<instance ID>` for instance resources and `projects/<project ID>/instances/<instance ID>/databases/<database ID>` for database resources.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Sets the access control policy on a database resource.<br/>
> Replaces any existing policy.<br/>
> <br/>
> Authorization requires `spanner.databases.setIamPolicy`<br/>
> permission on resource.

*Tags:* `projects`

#### Input Parameters
* `resource` - _required_ - REQUIRED: The Cloud Spanner resource for which the policy is being set. The format is `projects/<project ID>/instances/<instance ID>` for instance resources and `projects/<project ID>/instances/<instance ID>/databases/<database ID>` for databases resources.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Returns permissions that the caller has on the specified database resource.<br/>
> <br/>
> Attempting this RPC on a non-existent Cloud Spanner database will<br/>
> result in a NOT_FOUND error if the user has<br/>
> `spanner.databases.list` permission on the containing Cloud<br/>
> Spanner instance. Otherwise returns an empty set of permissions.

*Tags:* `projects`

#### Input Parameters
* `resource` - _required_ - REQUIRED: The Cloud Spanner resource for which permissions are being tested. The format is `projects/<project ID>/instances/<instance ID>` for instance resources and `projects/<project ID>/instances/<instance ID>/databases/<database ID>` for database resources.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Begins a new transaction. This step can often be skipped:<br/>
> Read, ExecuteSql and<br/>
> Commit can begin a new transaction as a<br/>
> side-effect.

*Tags:* `projects`

#### Input Parameters
* `session` - _required_ - Required. The session in which the transaction runs.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Commits a transaction. The request includes the mutations to be<br/>
> applied to rows in the database.<br/>
> <br/>
> `Commit` might return an `ABORTED` error. This can occur at any time;<br/>
> commonly, the cause is conflicts with concurrent<br/>
> transactions. However, it can also happen for a variety of other<br/>
> reasons. If `Commit` returns `ABORTED`, the caller should re-attempt<br/>
> the transaction from the beginning, re-using the same session.

*Tags:* `projects`

#### Input Parameters
* `session` - _required_ - Required. The session in which the transaction to be committed is running.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Executes a batch of SQL DML statements. This method allows many statements<br/>
> to be run with lower latency than submitting them sequentially with<br/>
> ExecuteSql.<br/>
> <br/>
> Statements are executed in order, sequentially.<br/>
> ExecuteBatchDmlResponse will contain a<br/>
> ResultSet for each DML statement that has successfully executed. If a<br/>
> statement fails, its error status will be returned as part of the<br/>
> ExecuteBatchDmlResponse. Execution will<br/>
> stop at the first failed statement; the remaining statements will not run.<br/>
> <br/>
> ExecuteBatchDml is expected to return an OK status with a response even if<br/>
> there was an error while processing one of the DML statements. Clients must<br/>
> inspect response.status to determine if there were any errors while<br/>
> processing the request.<br/>
> <br/>
> See more details in<br/>
> ExecuteBatchDmlRequest and<br/>
> ExecuteBatchDmlResponse.

*Tags:* `projects`

#### Input Parameters
* `session` - _required_ - Required. The session in which the DML statements should be performed.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Executes an SQL statement, returning all results in a single reply. This<br/>
> method cannot be used to return a result set larger than 10 MiB;<br/>
> if the query yields more data than that, the query fails with<br/>
> a `FAILED_PRECONDITION` error.<br/>
> <br/>
> Operations inside read-write transactions might return `ABORTED`. If<br/>
> this occurs, the application should restart the transaction from<br/>
> the beginning. See Transaction for more details.<br/>
> <br/>
> Larger result sets can be fetched in streaming fashion by calling<br/>
> ExecuteStreamingSql instead.

*Tags:* `projects`

#### Input Parameters
* `session` - _required_ - Required. The session in which the SQL query should be performed.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Like ExecuteSql, except returns the result<br/>
> set as a stream. Unlike ExecuteSql, there<br/>
> is no limit on the size of the returned result set. However, no<br/>
> individual row in the result set can exceed 100 MiB, and no<br/>
> column value can exceed 10 MiB.

*Tags:* `projects`

#### Input Parameters
* `session` - _required_ - Required. The session in which the SQL query should be performed.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Creates a set of partition tokens that can be used to execute a query<br/>
> operation in parallel.  Each of the returned partition tokens can be used<br/>
> by ExecuteStreamingSql to specify a subset<br/>
> of the query result to read.  The same session and read-only transaction<br/>
> must be used by the PartitionQueryRequest used to create the<br/>
> partition tokens and the ExecuteSqlRequests that use the partition tokens.<br/>
> <br/>
> Partition tokens become invalid when the session used to create them<br/>
> is deleted, is idle for too long, begins a new transaction, or becomes too<br/>
> old.  When any of these happen, it is not possible to resume the query, and<br/>
> the whole operation must be restarted from the beginning.

*Tags:* `projects`

#### Input Parameters
* `session` - _required_ - Required. The session used to create the partitions.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Creates a set of partition tokens that can be used to execute a read<br/>
> operation in parallel.  Each of the returned partition tokens can be used<br/>
> by StreamingRead to specify a subset of the read<br/>
> result to read.  The same session and read-only transaction must be used by<br/>
> the PartitionReadRequest used to create the partition tokens and the<br/>
> ReadRequests that use the partition tokens.  There are no ordering<br/>
> guarantees on rows returned among the returned partition tokens, or even<br/>
> within each individual StreamingRead call issued with a partition_token.<br/>
> <br/>
> Partition tokens become invalid when the session used to create them<br/>
> is deleted, is idle for too long, begins a new transaction, or becomes too<br/>
> old.  When any of these happen, it is not possible to resume the read, and<br/>
> the whole operation must be restarted from the beginning.

*Tags:* `projects`

#### Input Parameters
* `session` - _required_ - Required. The session used to create the partitions.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Reads rows from the database using key lookups and scans, as a<br/>
> simple key/value style alternative to<br/>
> ExecuteSql.  This method cannot be used to<br/>
> return a result set larger than 10 MiB; if the read matches more<br/>
> data than that, the read fails with a `FAILED_PRECONDITION`<br/>
> error.<br/>
> <br/>
> Reads inside read-write transactions might return `ABORTED`. If<br/>
> this occurs, the application should restart the transaction from<br/>
> the beginning. See Transaction for more details.<br/>
> <br/>
> Larger result sets can be yielded in streaming fashion by calling<br/>
> StreamingRead instead.

*Tags:* `projects`

#### Input Parameters
* `session` - _required_ - Required. The session in which the read should be performed.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Rolls back a transaction, releasing any locks it holds. It is a good<br/>
> idea to call this for any transaction that includes one or more<br/>
> Read or ExecuteSql requests and<br/>
> ultimately decides not to commit.<br/>
> <br/>
> `Rollback` returns `OK` if it successfully aborts the transaction, the<br/>
> transaction was already aborted, or the transaction is not<br/>
> found. `Rollback` never returns `ABORTED`.

*Tags:* `projects`

#### Input Parameters
* `session` - _required_ - Required. The session in which the transaction to roll back is running.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

### Like Read, except returns the result set as a<br/>
> stream. Unlike Read, there is no limit on the<br/>
> size of the returned result set. However, no individual row in<br/>
> the result set can exceed 100 MiB, and no column value can exceed<br/>
> 10 MiB.

*Tags:* `projects`

#### Input Parameters
* `session` - _required_ - Required. The session in which the read should be performed.
* `access_token` - _optional_ - OAuth access token.
* `alt` - _optional_ - Data format for response.
    Possible values: json, media, proto.
* `callback` - _optional_ - JSONP
* `fields` - _optional_ - Selector specifying which fields to include in a partial response.
* `key` - _optional_ - API key. Your API key identifies your project and provides you with API access, quota, and reports. Required unless you provide an OAuth 2.0 token.
* `oauth_token` - _optional_ - OAuth 2.0 token for the current user.
* `prettyPrint` - _optional_ - Returns response with indentations and line breaks.
* `quotaUser` - _optional_ - Available to use for quota purposes for server-side applications. Can be any arbitrary string assigned to a user, but should not exceed 40 characters.
* `uploadType` - _optional_ - Legacy upload protocol for media (e.g. "media", "multipart").
* `upload_protocol` - _optional_ - Upload protocol for media (e.g. "raw", "multipart").

## License

**flow**ground :- Telekom iPaaS / googleapis-com-spanner-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
