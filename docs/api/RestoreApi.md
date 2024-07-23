# \RestoreApi

All URIs are relative to *https://in-memory-db.de-fra.ionos.com*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**SnapshotsRestoresFindById**](RestoreApi.md#SnapshotsRestoresFindById) | **Get** /snapshots/{snapshotId}/restores/{restoreId} | Retrieve Restore|
|[**SnapshotsRestoresGet**](RestoreApi.md#SnapshotsRestoresGet) | **Get** /snapshots/{snapshotId}/restores | Retrieve all Restore|
|[**SnapshotsRestoresPost**](RestoreApi.md#SnapshotsRestoresPost) | **Post** /snapshots/{snapshotId}/restores | Create Restore|



## SnapshotsRestoresFindById

```go
var result RestoreRead = SnapshotsRestoresFindById(ctx, snapshotId, restoreId)
                      .Execute()
```

Retrieve Restore



### Example

```go
package main

import (
    "context"
    "fmt"
    "os"

    ionoscloud "github.com/ionos-cloud/sdk-go-dbaas-in-memory-db"
)

func main() {
    snapshotId := "a8784665-3d99-5464-af32-30a2967f58e7" // string | The ID (UUID) of the Snapshot.
    restoreId := "39fe1580-552b-5182-8939-a3ac6c38f94c" // string | The ID (UUID) of the Restore.

    configuration := ionoscloud.NewConfiguration("USERNAME", "PASSWORD", "TOKEN", "HOST_URL")
    apiClient := ionoscloud.NewAPIClient(configuration)
    resource, resp, err := apiClient.RestoreApi.SnapshotsRestoresFindById(context.Background(), snapshotId, restoreId).Execute()
    if err != nil {
        fmt.Fprintf(os.Stderr, "Error when calling `RestoreApi.SnapshotsRestoresFindById``: %v\n", err)
        fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", resp)
    }
    // response from `SnapshotsRestoresFindById`: RestoreRead
    fmt.Fprintf(os.Stdout, "Response from `RestoreApi.SnapshotsRestoresFindById`: %v\n", resource)
}
```

### Path Parameters


|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
|**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.|
|**snapshotId** | **string** | The ID (UUID) of the Snapshot. | |
|**restoreId** | **string** | The ID (UUID) of the Restore. | |

### Other Parameters

Other parameters are passed through a pointer to an apiSnapshotsRestoresFindByIdRequest struct via the builder pattern


|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|

### Return type

[**RestoreRead**](../models/RestoreRead.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


### URLs Configuration per Operation
Each operation can use different server URL defined using `OperationServers` map in the `Configuration`.
An operation is uniquely identified by `"RestoreApiService.SnapshotsRestoresFindById"` string.
Similar rules for overriding default operation server index and variables apply by using `sw.ContextOperationServerIndices` and `sw.ContextOperationServerVariables` context maps.

```golang
ctx := context.WithValue(context.Background(), {packageName}.ContextOperationServerIndices, map[string]int{
    "RestoreApiService.SnapshotsRestoresFindById": 2,
})
ctx = context.WithValue(context.Background(), {packageName}.ContextOperationServerVariables, map[string]map[string]string{
    "RestoreApiService.SnapshotsRestoresFindById": {
    "port": "8443",
},
})
```


## SnapshotsRestoresGet

```go
var result RestoreReadList = SnapshotsRestoresGet(ctx, snapshotId)
                      .Offset(offset)
                      .Limit(limit)
                      .FilterName(filterName)
                      .Execute()
```

Retrieve all Restore



### Example

```go
package main

import (
    "context"
    "fmt"
    "os"

    ionoscloud "github.com/ionos-cloud/sdk-go-dbaas-in-memory-db"
)

func main() {
    snapshotId := "a8784665-3d99-5464-af32-30a2967f58e7" // string | The ID (UUID) of the Snapshot.
    offset := int32(0) // int32 | The first element (of the total list of elements) to include in the response. Use together with limit for pagination. (optional) (default to 0)
    limit := int32(100) // int32 | The maximum number of elements to return. Use together with offset for pagination. (optional) (default to 100)
    filterName := "filterName_example" // string | Response filter to list only items contain the specified name. The value is case insensitive and matched on the 'displayName' field.  (optional)

    configuration := ionoscloud.NewConfiguration("USERNAME", "PASSWORD", "TOKEN", "HOST_URL")
    apiClient := ionoscloud.NewAPIClient(configuration)
    resource, resp, err := apiClient.RestoreApi.SnapshotsRestoresGet(context.Background(), snapshotId).Offset(offset).Limit(limit).FilterName(filterName).Execute()
    if err != nil {
        fmt.Fprintf(os.Stderr, "Error when calling `RestoreApi.SnapshotsRestoresGet``: %v\n", err)
        fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", resp)
    }
    // response from `SnapshotsRestoresGet`: RestoreReadList
    fmt.Fprintf(os.Stdout, "Response from `RestoreApi.SnapshotsRestoresGet`: %v\n", resource)
}
```

### Path Parameters


|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
|**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.|
|**snapshotId** | **string** | The ID (UUID) of the Snapshot. | |

### Other Parameters

Other parameters are passed through a pointer to an apiSnapshotsRestoresGetRequest struct via the builder pattern


|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **offset** | **int32** | The first element (of the total list of elements) to include in the response. Use together with limit for pagination. | [default to 0]|
| **limit** | **int32** | The maximum number of elements to return. Use together with offset for pagination. | [default to 100]|
| **filterName** | **string** | Response filter to list only items contain the specified name. The value is case insensitive and matched on the &#39;displayName&#39; field.  | |

### Return type

[**RestoreReadList**](../models/RestoreReadList.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


### URLs Configuration per Operation
Each operation can use different server URL defined using `OperationServers` map in the `Configuration`.
An operation is uniquely identified by `"RestoreApiService.SnapshotsRestoresGet"` string.
Similar rules for overriding default operation server index and variables apply by using `sw.ContextOperationServerIndices` and `sw.ContextOperationServerVariables` context maps.

```golang
ctx := context.WithValue(context.Background(), {packageName}.ContextOperationServerIndices, map[string]int{
    "RestoreApiService.SnapshotsRestoresGet": 2,
})
ctx = context.WithValue(context.Background(), {packageName}.ContextOperationServerVariables, map[string]map[string]string{
    "RestoreApiService.SnapshotsRestoresGet": {
    "port": "8443",
},
})
```


## SnapshotsRestoresPost

```go
var result RestoreRead = SnapshotsRestoresPost(ctx, snapshotId)
                      .RestoreCreate(restoreCreate)
                      .Execute()
```

Create Restore



### Example

```go
package main

import (
    "context"
    "fmt"
    "os"

    ionoscloud "github.com/ionos-cloud/sdk-go-dbaas-in-memory-db"
)

func main() {
    snapshotId := "a8784665-3d99-5464-af32-30a2967f58e7" // string | The ID (UUID) of the Snapshot.
    restoreCreate := *openapiclient.NewRestoreCreate(*openapiclient.NewRestore("ReplicasetId_example")) // RestoreCreate | Restore to create.

    configuration := ionoscloud.NewConfiguration("USERNAME", "PASSWORD", "TOKEN", "HOST_URL")
    apiClient := ionoscloud.NewAPIClient(configuration)
    resource, resp, err := apiClient.RestoreApi.SnapshotsRestoresPost(context.Background(), snapshotId).RestoreCreate(restoreCreate).Execute()
    if err != nil {
        fmt.Fprintf(os.Stderr, "Error when calling `RestoreApi.SnapshotsRestoresPost``: %v\n", err)
        fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", resp)
    }
    // response from `SnapshotsRestoresPost`: RestoreRead
    fmt.Fprintf(os.Stdout, "Response from `RestoreApi.SnapshotsRestoresPost`: %v\n", resource)
}
```

### Path Parameters


|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
|**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.|
|**snapshotId** | **string** | The ID (UUID) of the Snapshot. | |

### Other Parameters

Other parameters are passed through a pointer to an apiSnapshotsRestoresPostRequest struct via the builder pattern


|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **restoreCreate** | [**RestoreCreate**](../models/RestoreCreate.md) | Restore to create. | |

### Return type

[**RestoreRead**](../models/RestoreRead.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


### URLs Configuration per Operation
Each operation can use different server URL defined using `OperationServers` map in the `Configuration`.
An operation is uniquely identified by `"RestoreApiService.SnapshotsRestoresPost"` string.
Similar rules for overriding default operation server index and variables apply by using `sw.ContextOperationServerIndices` and `sw.ContextOperationServerVariables` context maps.

```golang
ctx := context.WithValue(context.Background(), {packageName}.ContextOperationServerIndices, map[string]int{
    "RestoreApiService.SnapshotsRestoresPost": 2,
})
ctx = context.WithValue(context.Background(), {packageName}.ContextOperationServerVariables, map[string]map[string]string{
    "RestoreApiService.SnapshotsRestoresPost": {
    "port": "8443",
},
})
```

