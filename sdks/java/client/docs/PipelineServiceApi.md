# PipelineServiceApi

All URIs are relative to *http://localhost:2746*

Method | HTTP request | Description
------------- | ------------- | -------------
[**pipelineServiceDeletePipeline**](PipelineServiceApi.md#pipelineServiceDeletePipeline) | **DELETE** /api/v1/pipelines/{namespace}/{name} | 
[**pipelineServiceGetPipeline**](PipelineServiceApi.md#pipelineServiceGetPipeline) | **GET** /api/v1/pipelines/{namespace}/{name} | 
[**pipelineServiceListPipelines**](PipelineServiceApi.md#pipelineServiceListPipelines) | **GET** /api/v1/pipelines/{namespace} | 
[**pipelineServicePipelineLogs**](PipelineServiceApi.md#pipelineServicePipelineLogs) | **GET** /api/v1/stream/pipelines/{namespace}/logs | 
[**pipelineServiceRestartPipeline**](PipelineServiceApi.md#pipelineServiceRestartPipeline) | **POST** /api/v1/pipelines/{namespace}/{name}/restart | 
[**pipelineServiceWatchPipelines**](PipelineServiceApi.md#pipelineServiceWatchPipelines) | **GET** /api/v1/stream/pipelines/{namespace} | 
[**pipelineServiceWatchSteps**](PipelineServiceApi.md#pipelineServiceWatchSteps) | **GET** /api/v1/stream/steps/{namespace} | 


<a name="pipelineServiceDeletePipeline"></a>
# **pipelineServiceDeletePipeline**
> Object pipelineServiceDeletePipeline(namespace, name, deleteOptionsGracePeriodSeconds, deleteOptionsPreconditionsUid, deleteOptionsPreconditionsResourceVersion, deleteOptionsOrphanDependents, deleteOptionsPropagationPolicy, deleteOptionsDryRun)



### Example
```java
// Import classes:
import io.argoproj.workflow.ApiClient;
import io.argoproj.workflow.ApiException;
import io.argoproj.workflow.Configuration;
import io.argoproj.workflow.models.*;
import io.argoproj.workflow.apis.PipelineServiceApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:2746");

    PipelineServiceApi apiInstance = new PipelineServiceApi(defaultClient);
    String namespace = "namespace_example"; // String | 
    String name = "name_example"; // String | 
    String deleteOptionsGracePeriodSeconds = "deleteOptionsGracePeriodSeconds_example"; // String | The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. +optional.
    String deleteOptionsPreconditionsUid = "deleteOptionsPreconditionsUid_example"; // String | Specifies the target UID. +optional.
    String deleteOptionsPreconditionsResourceVersion = "deleteOptionsPreconditionsResourceVersion_example"; // String | Specifies the target ResourceVersion +optional.
    Boolean deleteOptionsOrphanDependents = true; // Boolean | Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the \"orphan\" finalizer will be added to/removed from the object's finalizers list. Either this field or PropagationPolicy may be set, but not both. +optional.
    String deleteOptionsPropagationPolicy = "deleteOptionsPropagationPolicy_example"; // String | Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. Acceptable values are: 'Orphan' - orphan the dependents; 'Background' - allow the garbage collector to delete the dependents in the background; 'Foreground' - a cascading policy that deletes all dependents in the foreground. +optional.
    List<String> deleteOptionsDryRun = Arrays.asList(); // List<String> | When present, indicates that modifications should not be persisted. An invalid or unrecognized dryRun directive will result in an error response and no further processing of the request. Valid values are: - All: all dry run stages will be processed +optional.
    try {
      Object result = apiInstance.pipelineServiceDeletePipeline(namespace, name, deleteOptionsGracePeriodSeconds, deleteOptionsPreconditionsUid, deleteOptionsPreconditionsResourceVersion, deleteOptionsOrphanDependents, deleteOptionsPropagationPolicy, deleteOptionsDryRun);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PipelineServiceApi#pipelineServiceDeletePipeline");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **String**|  |
 **name** | **String**|  |
 **deleteOptionsGracePeriodSeconds** | **String**| The duration in seconds before the object should be deleted. Value must be non-negative integer. The value zero indicates delete immediately. If this value is nil, the default grace period for the specified type will be used. Defaults to a per object value if not specified. zero means delete immediately. +optional. | [optional]
 **deleteOptionsPreconditionsUid** | **String**| Specifies the target UID. +optional. | [optional]
 **deleteOptionsPreconditionsResourceVersion** | **String**| Specifies the target ResourceVersion +optional. | [optional]
 **deleteOptionsOrphanDependents** | **Boolean**| Deprecated: please use the PropagationPolicy, this field will be deprecated in 1.7. Should the dependent objects be orphaned. If true/false, the \&quot;orphan\&quot; finalizer will be added to/removed from the object&#39;s finalizers list. Either this field or PropagationPolicy may be set, but not both. +optional. | [optional]
 **deleteOptionsPropagationPolicy** | **String**| Whether and how garbage collection will be performed. Either this field or OrphanDependents may be set, but not both. The default policy is decided by the existing finalizer set in the metadata.finalizers and the resource-specific default policy. Acceptable values are: &#39;Orphan&#39; - orphan the dependents; &#39;Background&#39; - allow the garbage collector to delete the dependents in the background; &#39;Foreground&#39; - a cascading policy that deletes all dependents in the foreground. +optional. | [optional]
 **deleteOptionsDryRun** | [**List&lt;String&gt;**](String.md)| When present, indicates that modifications should not be persisted. An invalid or unrecognized dryRun directive will result in an error response and no further processing of the request. Valid values are: - All: all dry run stages will be processed +optional. | [optional]

### Return type

**Object**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response. |  -  |
**0** | An unexpected error response. |  -  |

<a name="pipelineServiceGetPipeline"></a>
# **pipelineServiceGetPipeline**
> GithubComArgoprojLabsArgoDataflowApiV1alpha1Pipeline pipelineServiceGetPipeline(namespace, name, getOptionsResourceVersion)



### Example
```java
// Import classes:
import io.argoproj.workflow.ApiClient;
import io.argoproj.workflow.ApiException;
import io.argoproj.workflow.Configuration;
import io.argoproj.workflow.models.*;
import io.argoproj.workflow.apis.PipelineServiceApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:2746");

    PipelineServiceApi apiInstance = new PipelineServiceApi(defaultClient);
    String namespace = "namespace_example"; // String | 
    String name = "name_example"; // String | 
    String getOptionsResourceVersion = "getOptionsResourceVersion_example"; // String | resourceVersion sets a constraint on what resource versions a request may be served from. See https://kubernetes.io/docs/reference/using-api/api-concepts/#resource-versions for details.  Defaults to unset +optional
    try {
      GithubComArgoprojLabsArgoDataflowApiV1alpha1Pipeline result = apiInstance.pipelineServiceGetPipeline(namespace, name, getOptionsResourceVersion);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PipelineServiceApi#pipelineServiceGetPipeline");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **String**|  |
 **name** | **String**|  |
 **getOptionsResourceVersion** | **String**| resourceVersion sets a constraint on what resource versions a request may be served from. See https://kubernetes.io/docs/reference/using-api/api-concepts/#resource-versions for details.  Defaults to unset +optional | [optional]

### Return type

[**GithubComArgoprojLabsArgoDataflowApiV1alpha1Pipeline**](GithubComArgoprojLabsArgoDataflowApiV1alpha1Pipeline.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response. |  -  |
**0** | An unexpected error response. |  -  |

<a name="pipelineServiceListPipelines"></a>
# **pipelineServiceListPipelines**
> GithubComArgoprojLabsArgoDataflowApiV1alpha1PipelineList pipelineServiceListPipelines(namespace, listOptionsLabelSelector, listOptionsFieldSelector, listOptionsWatch, listOptionsAllowWatchBookmarks, listOptionsResourceVersion, listOptionsResourceVersionMatch, listOptionsTimeoutSeconds, listOptionsLimit, listOptionsContinue)



### Example
```java
// Import classes:
import io.argoproj.workflow.ApiClient;
import io.argoproj.workflow.ApiException;
import io.argoproj.workflow.Configuration;
import io.argoproj.workflow.models.*;
import io.argoproj.workflow.apis.PipelineServiceApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:2746");

    PipelineServiceApi apiInstance = new PipelineServiceApi(defaultClient);
    String namespace = "namespace_example"; // String | 
    String listOptionsLabelSelector = "listOptionsLabelSelector_example"; // String | A selector to restrict the list of returned objects by their labels. Defaults to everything. +optional.
    String listOptionsFieldSelector = "listOptionsFieldSelector_example"; // String | A selector to restrict the list of returned objects by their fields. Defaults to everything. +optional.
    Boolean listOptionsWatch = true; // Boolean | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. +optional.
    Boolean listOptionsAllowWatchBookmarks = true; // Boolean | allowWatchBookmarks requests watch events with type \"BOOKMARK\". Servers that do not implement bookmarks may ignore this flag and bookmarks are sent at the server's discretion. Clients should not assume bookmarks are returned at any specific interval, nor may they assume the server will send any BOOKMARK event during a session. If this is not a watch, this field is ignored. +optional.
    String listOptionsResourceVersion = "listOptionsResourceVersion_example"; // String | resourceVersion sets a constraint on what resource versions a request may be served from. See https://kubernetes.io/docs/reference/using-api/api-concepts/#resource-versions for details.  Defaults to unset +optional
    String listOptionsResourceVersionMatch = "listOptionsResourceVersionMatch_example"; // String | resourceVersionMatch determines how resourceVersion is applied to list calls. It is highly recommended that resourceVersionMatch be set for list calls where resourceVersion is set See https://kubernetes.io/docs/reference/using-api/api-concepts/#resource-versions for details.  Defaults to unset +optional
    String listOptionsTimeoutSeconds = "listOptionsTimeoutSeconds_example"; // String | Timeout for the list/watch call. This limits the duration of the call, regardless of any activity or inactivity. +optional.
    String listOptionsLimit = "listOptionsLimit_example"; // String | limit is a maximum number of responses to return for a list call. If more items exist, the server will set the `continue` field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.  The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned.
    String listOptionsContinue = "listOptionsContinue_example"; // String | The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server, the server will respond with a 410 ResourceExpired error together with a continue token. If the client needs a consistent list, it must restart their list without the continue field. Otherwise, the client may send another list request with the token received with the 410 error, the server will respond with a list starting from the next key, but from the latest snapshot, which is inconsistent from the previous list results - objects that are created, modified, or deleted after the first list request will be included in the response, as long as their keys are after the \"next key\".  This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications.
    try {
      GithubComArgoprojLabsArgoDataflowApiV1alpha1PipelineList result = apiInstance.pipelineServiceListPipelines(namespace, listOptionsLabelSelector, listOptionsFieldSelector, listOptionsWatch, listOptionsAllowWatchBookmarks, listOptionsResourceVersion, listOptionsResourceVersionMatch, listOptionsTimeoutSeconds, listOptionsLimit, listOptionsContinue);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PipelineServiceApi#pipelineServiceListPipelines");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **String**|  |
 **listOptionsLabelSelector** | **String**| A selector to restrict the list of returned objects by their labels. Defaults to everything. +optional. | [optional]
 **listOptionsFieldSelector** | **String**| A selector to restrict the list of returned objects by their fields. Defaults to everything. +optional. | [optional]
 **listOptionsWatch** | **Boolean**| Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. +optional. | [optional]
 **listOptionsAllowWatchBookmarks** | **Boolean**| allowWatchBookmarks requests watch events with type \&quot;BOOKMARK\&quot;. Servers that do not implement bookmarks may ignore this flag and bookmarks are sent at the server&#39;s discretion. Clients should not assume bookmarks are returned at any specific interval, nor may they assume the server will send any BOOKMARK event during a session. If this is not a watch, this field is ignored. +optional. | [optional]
 **listOptionsResourceVersion** | **String**| resourceVersion sets a constraint on what resource versions a request may be served from. See https://kubernetes.io/docs/reference/using-api/api-concepts/#resource-versions for details.  Defaults to unset +optional | [optional]
 **listOptionsResourceVersionMatch** | **String**| resourceVersionMatch determines how resourceVersion is applied to list calls. It is highly recommended that resourceVersionMatch be set for list calls where resourceVersion is set See https://kubernetes.io/docs/reference/using-api/api-concepts/#resource-versions for details.  Defaults to unset +optional | [optional]
 **listOptionsTimeoutSeconds** | **String**| Timeout for the list/watch call. This limits the duration of the call, regardless of any activity or inactivity. +optional. | [optional]
 **listOptionsLimit** | **String**| limit is a maximum number of responses to return for a list call. If more items exist, the server will set the &#x60;continue&#x60; field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.  The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned. | [optional]
 **listOptionsContinue** | **String**| The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server, the server will respond with a 410 ResourceExpired error together with a continue token. If the client needs a consistent list, it must restart their list without the continue field. Otherwise, the client may send another list request with the token received with the 410 error, the server will respond with a list starting from the next key, but from the latest snapshot, which is inconsistent from the previous list results - objects that are created, modified, or deleted after the first list request will be included in the response, as long as their keys are after the \&quot;next key\&quot;.  This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications. | [optional]

### Return type

[**GithubComArgoprojLabsArgoDataflowApiV1alpha1PipelineList**](GithubComArgoprojLabsArgoDataflowApiV1alpha1PipelineList.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response. |  -  |
**0** | An unexpected error response. |  -  |

<a name="pipelineServicePipelineLogs"></a>
# **pipelineServicePipelineLogs**
> StreamResultOfPipelineLogEntry pipelineServicePipelineLogs(namespace, name, stepName, grep, podLogOptionsContainer, podLogOptionsFollow, podLogOptionsPrevious, podLogOptionsSinceSeconds, podLogOptionsSinceTimeSeconds, podLogOptionsSinceTimeNanos, podLogOptionsTimestamps, podLogOptionsTailLines, podLogOptionsLimitBytes, podLogOptionsInsecureSkipTLSVerifyBackend)



### Example
```java
// Import classes:
import io.argoproj.workflow.ApiClient;
import io.argoproj.workflow.ApiException;
import io.argoproj.workflow.Configuration;
import io.argoproj.workflow.models.*;
import io.argoproj.workflow.apis.PipelineServiceApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:2746");

    PipelineServiceApi apiInstance = new PipelineServiceApi(defaultClient);
    String namespace = "namespace_example"; // String | 
    String name = "name_example"; // String | optional - only return entries for this pipeline.
    String stepName = "stepName_example"; // String | optional - only return entries for this step.
    String grep = "grep_example"; // String | optional - only return entries which match this expresssion.
    String podLogOptionsContainer = "podLogOptionsContainer_example"; // String | The container for which to stream logs. Defaults to only container if there is one container in the pod. +optional.
    Boolean podLogOptionsFollow = true; // Boolean | Follow the log stream of the pod. Defaults to false. +optional.
    Boolean podLogOptionsPrevious = true; // Boolean | Return previous terminated container logs. Defaults to false. +optional.
    String podLogOptionsSinceSeconds = "podLogOptionsSinceSeconds_example"; // String | A relative time in seconds before the current time from which to show logs. If this value precedes the time a pod was started, only logs since the pod start will be returned. If this value is in the future, no logs will be returned. Only one of sinceSeconds or sinceTime may be specified. +optional.
    String podLogOptionsSinceTimeSeconds = "podLogOptionsSinceTimeSeconds_example"; // String | Represents seconds of UTC time since Unix epoch 1970-01-01T00:00:00Z. Must be from 0001-01-01T00:00:00Z to 9999-12-31T23:59:59Z inclusive.
    Integer podLogOptionsSinceTimeNanos = 56; // Integer | Non-negative fractions of a second at nanosecond resolution. Negative second values with fractions must still have non-negative nanos values that count forward in time. Must be from 0 to 999,999,999 inclusive. This field may be limited in precision depending on context.
    Boolean podLogOptionsTimestamps = true; // Boolean | If true, add an RFC3339 or RFC3339Nano timestamp at the beginning of every line of log output. Defaults to false. +optional.
    String podLogOptionsTailLines = "podLogOptionsTailLines_example"; // String | If set, the number of lines from the end of the logs to show. If not specified, logs are shown from the creation of the container or sinceSeconds or sinceTime +optional.
    String podLogOptionsLimitBytes = "podLogOptionsLimitBytes_example"; // String | If set, the number of bytes to read from the server before terminating the log output. This may not display a complete final line of logging, and may return slightly more or slightly less than the specified limit. +optional.
    Boolean podLogOptionsInsecureSkipTLSVerifyBackend = true; // Boolean | insecureSkipTLSVerifyBackend indicates that the apiserver should not confirm the validity of the serving certificate of the backend it is connecting to.  This will make the HTTPS connection between the apiserver and the backend insecure. This means the apiserver cannot verify the log data it is receiving came from the real kubelet.  If the kubelet is configured to verify the apiserver's TLS credentials, it does not mean the connection to the real kubelet is vulnerable to a man in the middle attack (e.g. an attacker could not intercept the actual log data coming from the real kubelet). +optional.
    try {
      StreamResultOfPipelineLogEntry result = apiInstance.pipelineServicePipelineLogs(namespace, name, stepName, grep, podLogOptionsContainer, podLogOptionsFollow, podLogOptionsPrevious, podLogOptionsSinceSeconds, podLogOptionsSinceTimeSeconds, podLogOptionsSinceTimeNanos, podLogOptionsTimestamps, podLogOptionsTailLines, podLogOptionsLimitBytes, podLogOptionsInsecureSkipTLSVerifyBackend);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PipelineServiceApi#pipelineServicePipelineLogs");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **String**|  |
 **name** | **String**| optional - only return entries for this pipeline. | [optional]
 **stepName** | **String**| optional - only return entries for this step. | [optional]
 **grep** | **String**| optional - only return entries which match this expresssion. | [optional]
 **podLogOptionsContainer** | **String**| The container for which to stream logs. Defaults to only container if there is one container in the pod. +optional. | [optional]
 **podLogOptionsFollow** | **Boolean**| Follow the log stream of the pod. Defaults to false. +optional. | [optional]
 **podLogOptionsPrevious** | **Boolean**| Return previous terminated container logs. Defaults to false. +optional. | [optional]
 **podLogOptionsSinceSeconds** | **String**| A relative time in seconds before the current time from which to show logs. If this value precedes the time a pod was started, only logs since the pod start will be returned. If this value is in the future, no logs will be returned. Only one of sinceSeconds or sinceTime may be specified. +optional. | [optional]
 **podLogOptionsSinceTimeSeconds** | **String**| Represents seconds of UTC time since Unix epoch 1970-01-01T00:00:00Z. Must be from 0001-01-01T00:00:00Z to 9999-12-31T23:59:59Z inclusive. | [optional]
 **podLogOptionsSinceTimeNanos** | **Integer**| Non-negative fractions of a second at nanosecond resolution. Negative second values with fractions must still have non-negative nanos values that count forward in time. Must be from 0 to 999,999,999 inclusive. This field may be limited in precision depending on context. | [optional]
 **podLogOptionsTimestamps** | **Boolean**| If true, add an RFC3339 or RFC3339Nano timestamp at the beginning of every line of log output. Defaults to false. +optional. | [optional]
 **podLogOptionsTailLines** | **String**| If set, the number of lines from the end of the logs to show. If not specified, logs are shown from the creation of the container or sinceSeconds or sinceTime +optional. | [optional]
 **podLogOptionsLimitBytes** | **String**| If set, the number of bytes to read from the server before terminating the log output. This may not display a complete final line of logging, and may return slightly more or slightly less than the specified limit. +optional. | [optional]
 **podLogOptionsInsecureSkipTLSVerifyBackend** | **Boolean**| insecureSkipTLSVerifyBackend indicates that the apiserver should not confirm the validity of the serving certificate of the backend it is connecting to.  This will make the HTTPS connection between the apiserver and the backend insecure. This means the apiserver cannot verify the log data it is receiving came from the real kubelet.  If the kubelet is configured to verify the apiserver&#39;s TLS credentials, it does not mean the connection to the real kubelet is vulnerable to a man in the middle attack (e.g. an attacker could not intercept the actual log data coming from the real kubelet). +optional. | [optional]

### Return type

[**StreamResultOfPipelineLogEntry**](StreamResultOfPipelineLogEntry.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response.(streaming responses) |  -  |
**0** | An unexpected error response. |  -  |

<a name="pipelineServiceRestartPipeline"></a>
# **pipelineServiceRestartPipeline**
> Object pipelineServiceRestartPipeline(namespace, name)



### Example
```java
// Import classes:
import io.argoproj.workflow.ApiClient;
import io.argoproj.workflow.ApiException;
import io.argoproj.workflow.Configuration;
import io.argoproj.workflow.models.*;
import io.argoproj.workflow.apis.PipelineServiceApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:2746");

    PipelineServiceApi apiInstance = new PipelineServiceApi(defaultClient);
    String namespace = "namespace_example"; // String | 
    String name = "name_example"; // String | 
    try {
      Object result = apiInstance.pipelineServiceRestartPipeline(namespace, name);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PipelineServiceApi#pipelineServiceRestartPipeline");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **String**|  |
 **name** | **String**|  |

### Return type

**Object**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response. |  -  |
**0** | An unexpected error response. |  -  |

<a name="pipelineServiceWatchPipelines"></a>
# **pipelineServiceWatchPipelines**
> StreamResultOfPipelinePipelineWatchEvent pipelineServiceWatchPipelines(namespace, listOptionsLabelSelector, listOptionsFieldSelector, listOptionsWatch, listOptionsAllowWatchBookmarks, listOptionsResourceVersion, listOptionsResourceVersionMatch, listOptionsTimeoutSeconds, listOptionsLimit, listOptionsContinue)



### Example
```java
// Import classes:
import io.argoproj.workflow.ApiClient;
import io.argoproj.workflow.ApiException;
import io.argoproj.workflow.Configuration;
import io.argoproj.workflow.models.*;
import io.argoproj.workflow.apis.PipelineServiceApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:2746");

    PipelineServiceApi apiInstance = new PipelineServiceApi(defaultClient);
    String namespace = "namespace_example"; // String | 
    String listOptionsLabelSelector = "listOptionsLabelSelector_example"; // String | A selector to restrict the list of returned objects by their labels. Defaults to everything. +optional.
    String listOptionsFieldSelector = "listOptionsFieldSelector_example"; // String | A selector to restrict the list of returned objects by their fields. Defaults to everything. +optional.
    Boolean listOptionsWatch = true; // Boolean | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. +optional.
    Boolean listOptionsAllowWatchBookmarks = true; // Boolean | allowWatchBookmarks requests watch events with type \"BOOKMARK\". Servers that do not implement bookmarks may ignore this flag and bookmarks are sent at the server's discretion. Clients should not assume bookmarks are returned at any specific interval, nor may they assume the server will send any BOOKMARK event during a session. If this is not a watch, this field is ignored. +optional.
    String listOptionsResourceVersion = "listOptionsResourceVersion_example"; // String | resourceVersion sets a constraint on what resource versions a request may be served from. See https://kubernetes.io/docs/reference/using-api/api-concepts/#resource-versions for details.  Defaults to unset +optional
    String listOptionsResourceVersionMatch = "listOptionsResourceVersionMatch_example"; // String | resourceVersionMatch determines how resourceVersion is applied to list calls. It is highly recommended that resourceVersionMatch be set for list calls where resourceVersion is set See https://kubernetes.io/docs/reference/using-api/api-concepts/#resource-versions for details.  Defaults to unset +optional
    String listOptionsTimeoutSeconds = "listOptionsTimeoutSeconds_example"; // String | Timeout for the list/watch call. This limits the duration of the call, regardless of any activity or inactivity. +optional.
    String listOptionsLimit = "listOptionsLimit_example"; // String | limit is a maximum number of responses to return for a list call. If more items exist, the server will set the `continue` field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.  The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned.
    String listOptionsContinue = "listOptionsContinue_example"; // String | The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server, the server will respond with a 410 ResourceExpired error together with a continue token. If the client needs a consistent list, it must restart their list without the continue field. Otherwise, the client may send another list request with the token received with the 410 error, the server will respond with a list starting from the next key, but from the latest snapshot, which is inconsistent from the previous list results - objects that are created, modified, or deleted after the first list request will be included in the response, as long as their keys are after the \"next key\".  This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications.
    try {
      StreamResultOfPipelinePipelineWatchEvent result = apiInstance.pipelineServiceWatchPipelines(namespace, listOptionsLabelSelector, listOptionsFieldSelector, listOptionsWatch, listOptionsAllowWatchBookmarks, listOptionsResourceVersion, listOptionsResourceVersionMatch, listOptionsTimeoutSeconds, listOptionsLimit, listOptionsContinue);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PipelineServiceApi#pipelineServiceWatchPipelines");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **String**|  |
 **listOptionsLabelSelector** | **String**| A selector to restrict the list of returned objects by their labels. Defaults to everything. +optional. | [optional]
 **listOptionsFieldSelector** | **String**| A selector to restrict the list of returned objects by their fields. Defaults to everything. +optional. | [optional]
 **listOptionsWatch** | **Boolean**| Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. +optional. | [optional]
 **listOptionsAllowWatchBookmarks** | **Boolean**| allowWatchBookmarks requests watch events with type \&quot;BOOKMARK\&quot;. Servers that do not implement bookmarks may ignore this flag and bookmarks are sent at the server&#39;s discretion. Clients should not assume bookmarks are returned at any specific interval, nor may they assume the server will send any BOOKMARK event during a session. If this is not a watch, this field is ignored. +optional. | [optional]
 **listOptionsResourceVersion** | **String**| resourceVersion sets a constraint on what resource versions a request may be served from. See https://kubernetes.io/docs/reference/using-api/api-concepts/#resource-versions for details.  Defaults to unset +optional | [optional]
 **listOptionsResourceVersionMatch** | **String**| resourceVersionMatch determines how resourceVersion is applied to list calls. It is highly recommended that resourceVersionMatch be set for list calls where resourceVersion is set See https://kubernetes.io/docs/reference/using-api/api-concepts/#resource-versions for details.  Defaults to unset +optional | [optional]
 **listOptionsTimeoutSeconds** | **String**| Timeout for the list/watch call. This limits the duration of the call, regardless of any activity or inactivity. +optional. | [optional]
 **listOptionsLimit** | **String**| limit is a maximum number of responses to return for a list call. If more items exist, the server will set the &#x60;continue&#x60; field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.  The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned. | [optional]
 **listOptionsContinue** | **String**| The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server, the server will respond with a 410 ResourceExpired error together with a continue token. If the client needs a consistent list, it must restart their list without the continue field. Otherwise, the client may send another list request with the token received with the 410 error, the server will respond with a list starting from the next key, but from the latest snapshot, which is inconsistent from the previous list results - objects that are created, modified, or deleted after the first list request will be included in the response, as long as their keys are after the \&quot;next key\&quot;.  This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications. | [optional]

### Return type

[**StreamResultOfPipelinePipelineWatchEvent**](StreamResultOfPipelinePipelineWatchEvent.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response.(streaming responses) |  -  |
**0** | An unexpected error response. |  -  |

<a name="pipelineServiceWatchSteps"></a>
# **pipelineServiceWatchSteps**
> StreamResultOfPipelineStepWatchEvent pipelineServiceWatchSteps(namespace, listOptionsLabelSelector, listOptionsFieldSelector, listOptionsWatch, listOptionsAllowWatchBookmarks, listOptionsResourceVersion, listOptionsResourceVersionMatch, listOptionsTimeoutSeconds, listOptionsLimit, listOptionsContinue)



### Example
```java
// Import classes:
import io.argoproj.workflow.ApiClient;
import io.argoproj.workflow.ApiException;
import io.argoproj.workflow.Configuration;
import io.argoproj.workflow.models.*;
import io.argoproj.workflow.apis.PipelineServiceApi;

public class Example {
  public static void main(String[] args) {
    ApiClient defaultClient = Configuration.getDefaultApiClient();
    defaultClient.setBasePath("http://localhost:2746");

    PipelineServiceApi apiInstance = new PipelineServiceApi(defaultClient);
    String namespace = "namespace_example"; // String | 
    String listOptionsLabelSelector = "listOptionsLabelSelector_example"; // String | A selector to restrict the list of returned objects by their labels. Defaults to everything. +optional.
    String listOptionsFieldSelector = "listOptionsFieldSelector_example"; // String | A selector to restrict the list of returned objects by their fields. Defaults to everything. +optional.
    Boolean listOptionsWatch = true; // Boolean | Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. +optional.
    Boolean listOptionsAllowWatchBookmarks = true; // Boolean | allowWatchBookmarks requests watch events with type \"BOOKMARK\". Servers that do not implement bookmarks may ignore this flag and bookmarks are sent at the server's discretion. Clients should not assume bookmarks are returned at any specific interval, nor may they assume the server will send any BOOKMARK event during a session. If this is not a watch, this field is ignored. +optional.
    String listOptionsResourceVersion = "listOptionsResourceVersion_example"; // String | resourceVersion sets a constraint on what resource versions a request may be served from. See https://kubernetes.io/docs/reference/using-api/api-concepts/#resource-versions for details.  Defaults to unset +optional
    String listOptionsResourceVersionMatch = "listOptionsResourceVersionMatch_example"; // String | resourceVersionMatch determines how resourceVersion is applied to list calls. It is highly recommended that resourceVersionMatch be set for list calls where resourceVersion is set See https://kubernetes.io/docs/reference/using-api/api-concepts/#resource-versions for details.  Defaults to unset +optional
    String listOptionsTimeoutSeconds = "listOptionsTimeoutSeconds_example"; // String | Timeout for the list/watch call. This limits the duration of the call, regardless of any activity or inactivity. +optional.
    String listOptionsLimit = "listOptionsLimit_example"; // String | limit is a maximum number of responses to return for a list call. If more items exist, the server will set the `continue` field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.  The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned.
    String listOptionsContinue = "listOptionsContinue_example"; // String | The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server, the server will respond with a 410 ResourceExpired error together with a continue token. If the client needs a consistent list, it must restart their list without the continue field. Otherwise, the client may send another list request with the token received with the 410 error, the server will respond with a list starting from the next key, but from the latest snapshot, which is inconsistent from the previous list results - objects that are created, modified, or deleted after the first list request will be included in the response, as long as their keys are after the \"next key\".  This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications.
    try {
      StreamResultOfPipelineStepWatchEvent result = apiInstance.pipelineServiceWatchSteps(namespace, listOptionsLabelSelector, listOptionsFieldSelector, listOptionsWatch, listOptionsAllowWatchBookmarks, listOptionsResourceVersion, listOptionsResourceVersionMatch, listOptionsTimeoutSeconds, listOptionsLimit, listOptionsContinue);
      System.out.println(result);
    } catch (ApiException e) {
      System.err.println("Exception when calling PipelineServiceApi#pipelineServiceWatchSteps");
      System.err.println("Status code: " + e.getCode());
      System.err.println("Reason: " + e.getResponseBody());
      System.err.println("Response headers: " + e.getResponseHeaders());
      e.printStackTrace();
    }
  }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **namespace** | **String**|  |
 **listOptionsLabelSelector** | **String**| A selector to restrict the list of returned objects by their labels. Defaults to everything. +optional. | [optional]
 **listOptionsFieldSelector** | **String**| A selector to restrict the list of returned objects by their fields. Defaults to everything. +optional. | [optional]
 **listOptionsWatch** | **Boolean**| Watch for changes to the described resources and return them as a stream of add, update, and remove notifications. Specify resourceVersion. +optional. | [optional]
 **listOptionsAllowWatchBookmarks** | **Boolean**| allowWatchBookmarks requests watch events with type \&quot;BOOKMARK\&quot;. Servers that do not implement bookmarks may ignore this flag and bookmarks are sent at the server&#39;s discretion. Clients should not assume bookmarks are returned at any specific interval, nor may they assume the server will send any BOOKMARK event during a session. If this is not a watch, this field is ignored. +optional. | [optional]
 **listOptionsResourceVersion** | **String**| resourceVersion sets a constraint on what resource versions a request may be served from. See https://kubernetes.io/docs/reference/using-api/api-concepts/#resource-versions for details.  Defaults to unset +optional | [optional]
 **listOptionsResourceVersionMatch** | **String**| resourceVersionMatch determines how resourceVersion is applied to list calls. It is highly recommended that resourceVersionMatch be set for list calls where resourceVersion is set See https://kubernetes.io/docs/reference/using-api/api-concepts/#resource-versions for details.  Defaults to unset +optional | [optional]
 **listOptionsTimeoutSeconds** | **String**| Timeout for the list/watch call. This limits the duration of the call, regardless of any activity or inactivity. +optional. | [optional]
 **listOptionsLimit** | **String**| limit is a maximum number of responses to return for a list call. If more items exist, the server will set the &#x60;continue&#x60; field on the list metadata to a value that can be used with the same initial query to retrieve the next set of results. Setting a limit may return fewer than the requested amount of items (up to zero items) in the event all requested objects are filtered out and clients should only use the presence of the continue field to determine whether more results are available. Servers may choose not to support the limit argument and will return all of the available results. If limit is specified and the continue field is empty, clients may assume that no more results are available. This field is not supported if watch is true.  The server guarantees that the objects returned when using continue will be identical to issuing a single list call without a limit - that is, no objects created, modified, or deleted after the first request is issued will be included in any subsequent continued requests. This is sometimes referred to as a consistent snapshot, and ensures that a client that is using limit to receive smaller chunks of a very large result can ensure they see all possible objects. If objects are updated during a chunked list the version of the object that was present at the time the first list result was calculated is returned. | [optional]
 **listOptionsContinue** | **String**| The continue option should be set when retrieving more results from the server. Since this value is server defined, clients may only use the continue value from a previous query result with identical query parameters (except for the value of continue) and the server may reject a continue value it does not recognize. If the specified continue value is no longer valid whether due to expiration (generally five to fifteen minutes) or a configuration change on the server, the server will respond with a 410 ResourceExpired error together with a continue token. If the client needs a consistent list, it must restart their list without the continue field. Otherwise, the client may send another list request with the token received with the 410 error, the server will respond with a list starting from the next key, but from the latest snapshot, which is inconsistent from the previous list results - objects that are created, modified, or deleted after the first list request will be included in the response, as long as their keys are after the \&quot;next key\&quot;.  This field is not supported when watch is true. Clients may start a watch from the last resourceVersion value returned by the server and not miss any modifications. | [optional]

### Return type

[**StreamResultOfPipelineStepWatchEvent**](StreamResultOfPipelineStepWatchEvent.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response.(streaming responses) |  -  |
**0** | An unexpected error response. |  -  |

