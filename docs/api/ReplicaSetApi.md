# \ReplicaSetApi

All URIs are relative to *https://in-memory-db.de-fra.ionos.com*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**ReplicasetsDelete**](ReplicaSetApi.md#ReplicasetsDelete) | **Delete** /replicasets/{replicasetId} | Delete ReplicaSet|
|[**ReplicasetsFindById**](ReplicaSetApi.md#ReplicasetsFindById) | **Get** /replicasets/{replicasetId} | Retrieve ReplicaSet|
|[**ReplicasetsGet**](ReplicaSetApi.md#ReplicasetsGet) | **Get** /replicasets | Retrieve all ReplicaSet|
|[**ReplicasetsPost**](ReplicaSetApi.md#ReplicasetsPost) | **Post** /replicasets | Create ReplicaSet|
|[**ReplicasetsPut**](ReplicaSetApi.md#ReplicasetsPut) | **Put** /replicasets/{replicasetId} | Ensure ReplicaSet|



## ReplicasetsDelete

```go
var result  = ReplicasetsDelete(ctx, replicasetId)
                      .Execute()
```

Delete ReplicaSet



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
    replicasetId := "1046e9bf-dbc0-5bd3-9291-713d36ab77e9" // string | The ID (UUID) of the ReplicaSet.

    configuration := ionoscloud.NewConfiguration("USERNAME", "PASSWORD", "TOKEN", "HOST_URL")
    apiClient := ionoscloud.NewAPIClient(configuration)
    resp, err := apiClient.ReplicaSetApi.ReplicasetsDelete(context.Background(), replicasetId).Execute()
    if err != nil {
        fmt.Fprintf(os.Stderr, "Error when calling `ReplicaSetApi.ReplicasetsDelete``: %v\n", err)
        fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", resp)
    }
}
```

### Path Parameters


|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
|**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.|
|**replicasetId** | **string** | The ID (UUID) of the ReplicaSet. | |

### Other Parameters

Other parameters are passed through a pointer to an apiReplicasetsDeleteRequest struct via the builder pattern


|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|

### Return type

 (empty response body)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


### URLs Configuration per Operation
Each operation can use different server URL defined using `OperationServers` map in the `Configuration`.
An operation is uniquely identified by `"ReplicaSetApiService.ReplicasetsDelete"` string.
Similar rules for overriding default operation server index and variables apply by using `sw.ContextOperationServerIndices` and `sw.ContextOperationServerVariables` context maps.

```golang
ctx := context.WithValue(context.Background(), {packageName}.ContextOperationServerIndices, map[string]int{
    "ReplicaSetApiService.ReplicasetsDelete": 2,
})
ctx = context.WithValue(context.Background(), {packageName}.ContextOperationServerVariables, map[string]map[string]string{
    "ReplicaSetApiService.ReplicasetsDelete": {
    "port": "8443",
},
})
```


## ReplicasetsFindById

```go
var result ReplicaSetRead = ReplicasetsFindById(ctx, replicasetId)
                      .Execute()
```

Retrieve ReplicaSet



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
    replicasetId := "1046e9bf-dbc0-5bd3-9291-713d36ab77e9" // string | The ID (UUID) of the ReplicaSet.

    configuration := ionoscloud.NewConfiguration("USERNAME", "PASSWORD", "TOKEN", "HOST_URL")
    apiClient := ionoscloud.NewAPIClient(configuration)
    resource, resp, err := apiClient.ReplicaSetApi.ReplicasetsFindById(context.Background(), replicasetId).Execute()
    if err != nil {
        fmt.Fprintf(os.Stderr, "Error when calling `ReplicaSetApi.ReplicasetsFindById``: %v\n", err)
        fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", resp)
    }
    // response from `ReplicasetsFindById`: ReplicaSetRead
    fmt.Fprintf(os.Stdout, "Response from `ReplicaSetApi.ReplicasetsFindById`: %v\n", resource)
}
```

### Path Parameters


|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
|**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.|
|**replicasetId** | **string** | The ID (UUID) of the ReplicaSet. | |

### Other Parameters

Other parameters are passed through a pointer to an apiReplicasetsFindByIdRequest struct via the builder pattern


|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|

### Return type

[**ReplicaSetRead**](../models/ReplicaSetRead.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


### URLs Configuration per Operation
Each operation can use different server URL defined using `OperationServers` map in the `Configuration`.
An operation is uniquely identified by `"ReplicaSetApiService.ReplicasetsFindById"` string.
Similar rules for overriding default operation server index and variables apply by using `sw.ContextOperationServerIndices` and `sw.ContextOperationServerVariables` context maps.

```golang
ctx := context.WithValue(context.Background(), {packageName}.ContextOperationServerIndices, map[string]int{
    "ReplicaSetApiService.ReplicasetsFindById": 2,
})
ctx = context.WithValue(context.Background(), {packageName}.ContextOperationServerVariables, map[string]map[string]string{
    "ReplicaSetApiService.ReplicasetsFindById": {
    "port": "8443",
},
})
```


## ReplicasetsGet

```go
var result ReplicaSetReadList = ReplicasetsGet(ctx)
                      .Offset(offset)
                      .Limit(limit)
                      .FilterName(filterName)
                      .Execute()
```

Retrieve all ReplicaSet



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
    offset := int32(0) // int32 | The first element (of the total list of elements) to include in the response. Use together with limit for pagination. (optional) (default to 0)
    limit := int32(100) // int32 | The maximum number of elements to return. Use together with offset for pagination. (optional) (default to 100)
    filterName := "filterName_example" // string | Response filter to list only items contain the specified name. The value is case insensitive and matched on the 'displayName' field.  (optional)

    configuration := ionoscloud.NewConfiguration("USERNAME", "PASSWORD", "TOKEN", "HOST_URL")
    apiClient := ionoscloud.NewAPIClient(configuration)
    resource, resp, err := apiClient.ReplicaSetApi.ReplicasetsGet(context.Background()).Offset(offset).Limit(limit).FilterName(filterName).Execute()
    if err != nil {
        fmt.Fprintf(os.Stderr, "Error when calling `ReplicaSetApi.ReplicasetsGet``: %v\n", err)
        fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", resp)
    }
    // response from `ReplicasetsGet`: ReplicaSetReadList
    fmt.Fprintf(os.Stdout, "Response from `ReplicaSetApi.ReplicasetsGet`: %v\n", resource)
}
```

### Path Parameters



### Other Parameters

Other parameters are passed through a pointer to an apiReplicasetsGetRequest struct via the builder pattern


|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **offset** | **int32** | The first element (of the total list of elements) to include in the response. Use together with limit for pagination. | [default to 0]|
| **limit** | **int32** | The maximum number of elements to return. Use together with offset for pagination. | [default to 100]|
| **filterName** | **string** | Response filter to list only items contain the specified name. The value is case insensitive and matched on the &#39;displayName&#39; field.  | |

### Return type

[**ReplicaSetReadList**](../models/ReplicaSetReadList.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


### URLs Configuration per Operation
Each operation can use different server URL defined using `OperationServers` map in the `Configuration`.
An operation is uniquely identified by `"ReplicaSetApiService.ReplicasetsGet"` string.
Similar rules for overriding default operation server index and variables apply by using `sw.ContextOperationServerIndices` and `sw.ContextOperationServerVariables` context maps.

```golang
ctx := context.WithValue(context.Background(), {packageName}.ContextOperationServerIndices, map[string]int{
    "ReplicaSetApiService.ReplicasetsGet": 2,
})
ctx = context.WithValue(context.Background(), {packageName}.ContextOperationServerVariables, map[string]map[string]string{
    "ReplicaSetApiService.ReplicasetsGet": {
    "port": "8443",
},
})
```


## ReplicasetsPost

```go
var result ReplicaSetRead = ReplicasetsPost(ctx)
                      .ReplicaSetCreate(replicaSetCreate)
                      .Execute()
```

Create ReplicaSet



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
    replicaSetCreate := *openapiclient.NewReplicaSetCreate(*openapiclient.NewReplicaSet("In-Memory DB replica set", "7.2", int32(2), *openapiclient.NewResources(int32(4), int32(4), int32(123)), openapiclient.PersistenceMode("None"), openapiclient.EvictionPolicy("noeviction"), []openapiclient.Connection{*openapiclient.NewConnection("5a029f4a-72e5-11ec-90d6-0242ac120003", "2", "192.168.1.100/24")}, *openapiclient.NewUser("DatabaseAdmin", openapiclient.User_password{HashedPassword: openapiclient.NewHashedPassword("SHA-256", "5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8")}))) // ReplicaSetCreate | ReplicaSet to create.

    configuration := ionoscloud.NewConfiguration("USERNAME", "PASSWORD", "TOKEN", "HOST_URL")
    apiClient := ionoscloud.NewAPIClient(configuration)
    resource, resp, err := apiClient.ReplicaSetApi.ReplicasetsPost(context.Background()).ReplicaSetCreate(replicaSetCreate).Execute()
    if err != nil {
        fmt.Fprintf(os.Stderr, "Error when calling `ReplicaSetApi.ReplicasetsPost``: %v\n", err)
        fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", resp)
    }
    // response from `ReplicasetsPost`: ReplicaSetRead
    fmt.Fprintf(os.Stdout, "Response from `ReplicaSetApi.ReplicasetsPost`: %v\n", resource)
}
```

### Path Parameters



### Other Parameters

Other parameters are passed through a pointer to an apiReplicasetsPostRequest struct via the builder pattern


|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **replicaSetCreate** | [**ReplicaSetCreate**](../models/ReplicaSetCreate.md) | ReplicaSet to create. | |

### Return type

[**ReplicaSetRead**](../models/ReplicaSetRead.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


### URLs Configuration per Operation
Each operation can use different server URL defined using `OperationServers` map in the `Configuration`.
An operation is uniquely identified by `"ReplicaSetApiService.ReplicasetsPost"` string.
Similar rules for overriding default operation server index and variables apply by using `sw.ContextOperationServerIndices` and `sw.ContextOperationServerVariables` context maps.

```golang
ctx := context.WithValue(context.Background(), {packageName}.ContextOperationServerIndices, map[string]int{
    "ReplicaSetApiService.ReplicasetsPost": 2,
})
ctx = context.WithValue(context.Background(), {packageName}.ContextOperationServerVariables, map[string]map[string]string{
    "ReplicaSetApiService.ReplicasetsPost": {
    "port": "8443",
},
})
```


## ReplicasetsPut

```go
var result ReplicaSetRead = ReplicasetsPut(ctx, replicasetId)
                      .ReplicaSetEnsure(replicaSetEnsure)
                      .Execute()
```

Ensure ReplicaSet



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
    replicasetId := "1046e9bf-dbc0-5bd3-9291-713d36ab77e9" // string | The ID (UUID) of the ReplicaSet.
    replicaSetEnsure := *openapiclient.NewReplicaSetEnsure("1046e9bf-dbc0-5bd3-9291-713d36ab77e9", *openapiclient.NewReplicaSet("In-Memory DB replica set", "7.2", int32(2), *openapiclient.NewResources(int32(4), int32(4), int32(123)), openapiclient.PersistenceMode("None"), openapiclient.EvictionPolicy("noeviction"), []openapiclient.Connection{*openapiclient.NewConnection("5a029f4a-72e5-11ec-90d6-0242ac120003", "2", "192.168.1.100/24")}, *openapiclient.NewUser("DatabaseAdmin", openapiclient.User_password{HashedPassword: openapiclient.NewHashedPassword("SHA-256", "5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8")}))) // ReplicaSetEnsure | update ReplicaSet

    configuration := ionoscloud.NewConfiguration("USERNAME", "PASSWORD", "TOKEN", "HOST_URL")
    apiClient := ionoscloud.NewAPIClient(configuration)
    resource, resp, err := apiClient.ReplicaSetApi.ReplicasetsPut(context.Background(), replicasetId).ReplicaSetEnsure(replicaSetEnsure).Execute()
    if err != nil {
        fmt.Fprintf(os.Stderr, "Error when calling `ReplicaSetApi.ReplicasetsPut``: %v\n", err)
        fmt.Fprintf(os.Stderr, "Full HTTP response: %v\n", resp)
    }
    // response from `ReplicasetsPut`: ReplicaSetRead
    fmt.Fprintf(os.Stdout, "Response from `ReplicaSetApi.ReplicasetsPut`: %v\n", resource)
}
```

### Path Parameters


|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
|**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.|
|**replicasetId** | **string** | The ID (UUID) of the ReplicaSet. | |

### Other Parameters

Other parameters are passed through a pointer to an apiReplicasetsPutRequest struct via the builder pattern


|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **replicaSetEnsure** | [**ReplicaSetEnsure**](../models/ReplicaSetEnsure.md) | update ReplicaSet | |

### Return type

[**ReplicaSetRead**](../models/ReplicaSetRead.md)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


### URLs Configuration per Operation
Each operation can use different server URL defined using `OperationServers` map in the `Configuration`.
An operation is uniquely identified by `"ReplicaSetApiService.ReplicasetsPut"` string.
Similar rules for overriding default operation server index and variables apply by using `sw.ContextOperationServerIndices` and `sw.ContextOperationServerVariables` context maps.

```golang
ctx := context.WithValue(context.Background(), {packageName}.ContextOperationServerIndices, map[string]int{
    "ReplicaSetApiService.ReplicasetsPut": 2,
})
ctx = context.WithValue(context.Background(), {packageName}.ContextOperationServerVariables, map[string]map[string]string{
    "ReplicaSetApiService.ReplicasetsPut": {
    "port": "8443",
},
})
```

