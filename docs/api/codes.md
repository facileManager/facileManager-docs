## Return Codes

The following table lists all of the return codes that are returned from the REST APIs.

| Return Code | Code Number | Description |
|-------------|-------------|-------------|
| Success | 200 | The request was successful. |
| Success | 201 | The request was fulfilled and the new resource was created. |
| Success | 204 | The request was fulfilled and the resource was deleted. |
| Bad Request | 400 | The request was not understood by the server due to incorrect syntax. |
| Unauthorized | 401 | The request requires user authentication. |
| Forbidden | 403 | The request requires additional user privileges. |
| Not Found | 404 | The server did not find anything that matches the request. |
| Not Allowed | 405 | The method is not allowed. |
| Bad Request | 1004 | The request was unsuccessful because the record already exists. |
| Bad Request | 2000 | Something was wrong with the request (rare). |
| Dryrun | 3000 | The dryrun was successful. |

### fmDNS-specific

The following table lists additional return codes that are related to the fmDNS module only.

| Return Code | Code Number | Description |
|-------------|-------------|-------------|
| Success | 202 | The request was fulfilled and the new resource was created except for the PTR. |
| Success | 205 | The request was fulfilled and the resource was deleted except for the PTR. |
| Forbidden | 1000 | The user is not privileged to manage records. |
| Forbidden | 1001 | The user is not privileged to access this zone. |
| Forbidden | 1002 | The user is not privileged to manage records this type of record. |
| Forbidden | 1003 | The user is not privileged to reload zones. |
