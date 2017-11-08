
<a name="paths"></a>
## Operations

<a name="func1"></a>
### GET /apis/kubevirt.io

#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`


<a name="getapiresources"></a>
### Get KubeVirt API Resources
```
GET /apis/kubevirt.io/v1alpha1
```


#### Description
Get KubeVirt API Resources


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`


<a name="kubeconnectionhealthzfunc"></a>
### Health endpoint
```
GET /apis/kubevirt.io/v1alpha1/healthz
```


#### Description
Health endpoint


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Consumes

* `application/json`


#### Produces

* `application/json`


<a name="listmigrationforallnamespaces"></a>
### Get a list of all Migration objects.
```
GET /apis/kubevirt.io/v1alpha1/migrations
```


#### Description
Get a list of all Migration objects.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Query**|**fieldSelector**  <br>*optional*|A selector to restrict the list of returned objects by their fields. Defaults to everything.|string|
|**Query**|**labelSelector**  <br>*optional*|A selector to restrict the list of returned objects by their labels. Defaults to everything|string|
|**Query**|**resourceVersion**  <br>*optional*|When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.|string|
|**Query**|**timeoutSeconds**  <br>*optional*|TimeoutSeconds for the list/watch call.|integer|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`
* `application/yaml`


<a name="createnamespacedmigration"></a>
### Create a Migration object.
```
POST /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/migrations
```


#### Description
Create a Migration object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Body**|**body**  <br>*required*||[v1.Migration](definitions.md#v1-migration)|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Consumes

* `application/json`
* `application/yaml`


#### Produces

* `application/json`
* `application/yaml`


<a name="listnamespacedmigrationlist"></a>
### Get a list of Migration objects.
```
GET /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/migrations
```


#### Description
Get a list of Migration objects.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Query**|**exact**  <br>*optional*|Should the export be exact. Exact export maintains cluster-specific fields like 'Namespace'|boolean|
|**Query**|**export**  <br>*optional*|Should this value be exported. Export strips fields that a user can not specify.|boolean|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`
* `application/yaml`


<a name="deletecollectionnamespacedmigration"></a>
### Delete a collection of Migration objects.
```
DELETE /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/migrations
```


#### Description
Delete a collection of Migration objects.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Query**|**fieldSelector**  <br>*optional*|A selector to restrict the list of returned objects by their fields. Defaults to everything.|string|
|**Query**|**labelSelector**  <br>*optional*|A selector to restrict the list of returned objects by their labels. Defaults to everything|string|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`
* `application/yaml`


<a name="readnamespacedmigration"></a>
### Get a Migration object.
```
GET /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/migrations/{name}
```


#### Description
Get a Migration object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**name**  <br>*required*|Name of the resource|string|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Query**|**exact**  <br>*optional*|Should the export be exact. Exact export maintains cluster-specific fields like 'Namespace'|boolean|
|**Query**|**export**  <br>*optional*|Should this value be exported. Export strips fields that a user can not specify.|boolean|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`
* `application/yaml`


<a name="replacenamespacedmigration"></a>
### Update a Migration object.
```
PUT /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/migrations/{name}
```


#### Description
Update a Migration object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**name**  <br>*required*|Name of the resource|string|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Body**|**body**  <br>*required*||[v1.Migration](definitions.md#v1-migration)|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Consumes

* `application/json`
* `application/yaml`


#### Produces

* `application/json`
* `application/yaml`


<a name="deletenamespacedmigration"></a>
### Delete a Migration object.
```
DELETE /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/migrations/{name}
```


#### Description
Delete a Migration object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**name**  <br>*required*|Name of the resource|string|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Consumes

* `application/json`
* `application/yaml`


#### Produces

* `application/json`
* `application/yaml`


<a name="updatenamespacedmigration"></a>
### Patch a Migration object.
```
PATCH /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/migrations/{name}
```


#### Description
Patch a Migration object.


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json-patch+json`


<a name="createnamespacedvirtualmachinereplicaset"></a>
### Create a VirtualMachineReplicaSet object.
```
POST /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachinereplicasets
```


#### Description
Create a VirtualMachineReplicaSet object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Body**|**body**  <br>*required*||[v1.VirtualMachineReplicaSet](definitions.md#v1-virtualmachinereplicaset)|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Consumes

* `application/json`
* `application/yaml`


#### Produces

* `application/json`
* `application/yaml`


<a name="listnamespacedvirtualmachinereplicasetlist"></a>
### Get a list of VirtualMachineReplicaSet objects.
```
GET /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachinereplicasets
```


#### Description
Get a list of VirtualMachineReplicaSet objects.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Query**|**exact**  <br>*optional*|Should the export be exact. Exact export maintains cluster-specific fields like 'Namespace'|boolean|
|**Query**|**export**  <br>*optional*|Should this value be exported. Export strips fields that a user can not specify.|boolean|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`
* `application/yaml`


<a name="deletecollectionnamespacedvirtualmachinereplicaset"></a>
### Delete a collection of VirtualMachineReplicaSet objects.
```
DELETE /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachinereplicasets
```


#### Description
Delete a collection of VirtualMachineReplicaSet objects.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Query**|**fieldSelector**  <br>*optional*|A selector to restrict the list of returned objects by their fields. Defaults to everything.|string|
|**Query**|**labelSelector**  <br>*optional*|A selector to restrict the list of returned objects by their labels. Defaults to everything|string|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`
* `application/yaml`


<a name="readnamespacedvirtualmachinereplicaset"></a>
### Get a VirtualMachineReplicaSet object.
```
GET /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachinereplicasets/{name}
```


#### Description
Get a VirtualMachineReplicaSet object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**name**  <br>*required*|Name of the resource|string|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Query**|**exact**  <br>*optional*|Should the export be exact. Exact export maintains cluster-specific fields like 'Namespace'|boolean|
|**Query**|**export**  <br>*optional*|Should this value be exported. Export strips fields that a user can not specify.|boolean|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`
* `application/yaml`


<a name="replacenamespacedvirtualmachinereplicaset"></a>
### Update a VirtualMachineReplicaSet object.
```
PUT /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachinereplicasets/{name}
```


#### Description
Update a VirtualMachineReplicaSet object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**name**  <br>*required*|Name of the resource|string|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Body**|**body**  <br>*required*||[v1.VirtualMachineReplicaSet](definitions.md#v1-virtualmachinereplicaset)|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Consumes

* `application/json`
* `application/yaml`


#### Produces

* `application/json`
* `application/yaml`


<a name="deletenamespacedvirtualmachinereplicaset"></a>
### Delete a VirtualMachineReplicaSet object.
```
DELETE /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachinereplicasets/{name}
```


#### Description
Delete a VirtualMachineReplicaSet object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**name**  <br>*required*|Name of the resource|string|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Consumes

* `application/json`
* `application/yaml`


#### Produces

* `application/json`
* `application/yaml`


<a name="updatenamespacedvirtualmachinereplicaset"></a>
### Patch a VirtualMachineReplicaSet object.
```
PATCH /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachinereplicasets/{name}
```


#### Description
Patch a VirtualMachineReplicaSet object.


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json-patch+json`


<a name="createnamespacedvirtualmachine"></a>
### Create a VirtualMachine object.
```
POST /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachines
```


#### Description
Create a VirtualMachine object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Body**|**body**  <br>*required*||[v1.VirtualMachine](definitions.md#v1-virtualmachine)|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Consumes

* `application/json`
* `application/yaml`


#### Produces

* `application/json`
* `application/yaml`


<a name="listnamespacedvirtualmachinelist"></a>
### Get a list of VirtualMachine objects.
```
GET /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachines
```


#### Description
Get a list of VirtualMachine objects.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Query**|**exact**  <br>*optional*|Should the export be exact. Exact export maintains cluster-specific fields like 'Namespace'|boolean|
|**Query**|**export**  <br>*optional*|Should this value be exported. Export strips fields that a user can not specify.|boolean|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`
* `application/yaml`


<a name="deletecollectionnamespacedvirtualmachine"></a>
### Delete a collection of VirtualMachine objects.
```
DELETE /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachines
```


#### Description
Delete a collection of VirtualMachine objects.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Query**|**fieldSelector**  <br>*optional*|A selector to restrict the list of returned objects by their fields. Defaults to everything.|string|
|**Query**|**labelSelector**  <br>*optional*|A selector to restrict the list of returned objects by their labels. Defaults to everything|string|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`
* `application/yaml`


<a name="readnamespacedvirtualmachine"></a>
### Get a VirtualMachine object.
```
GET /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachines/{name}
```


#### Description
Get a VirtualMachine object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**name**  <br>*required*|Name of the resource|string|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Query**|**exact**  <br>*optional*|Should the export be exact. Exact export maintains cluster-specific fields like 'Namespace'|boolean|
|**Query**|**export**  <br>*optional*|Should this value be exported. Export strips fields that a user can not specify.|boolean|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`
* `application/yaml`


<a name="replacenamespacedvirtualmachine"></a>
### Update a VirtualMachine object.
```
PUT /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachines/{name}
```


#### Description
Update a VirtualMachine object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**name**  <br>*required*|Name of the resource|string|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Body**|**body**  <br>*required*||[v1.VirtualMachine](definitions.md#v1-virtualmachine)|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Consumes

* `application/json`
* `application/yaml`


#### Produces

* `application/json`
* `application/yaml`


<a name="deletenamespacedvirtualmachine"></a>
### Delete a VirtualMachine object.
```
DELETE /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachines/{name}
```


#### Description
Delete a VirtualMachine object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**name**  <br>*required*|Name of the resource|string|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Consumes

* `application/json`
* `application/yaml`


#### Produces

* `application/json`
* `application/yaml`


<a name="updatenamespacedvirtualmachine"></a>
### Patch a VirtualMachine object.
```
PATCH /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachines/{name}
```


#### Description
Patch a VirtualMachine object.


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json-patch+json`


<a name="console"></a>
### Open a websocket connection to a serial console on the specified VM.
```
GET /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachines/{name}/console
```


#### Description
Open a websocket connection to a serial console on the specified VM.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**name**  <br>*required*|Name of the resource|string|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Query**|**console**  <br>*optional*|Name of the serial console to connect to|string|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


<a name="spice"></a>
### Returns a remote-viewer configuration file. Run `man 1 remote-viewer` to learn more about the configuration format.
```
GET /apis/kubevirt.io/v1alpha1/namespaces/{namespace}/virtualmachines/{name}/spice
```


#### Description
Returns a remote-viewer configuration file. Run `man 1 remote-viewer` to learn more about the configuration format.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**name**  <br>*required*|Name of the resource|string|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `text/plain`
* `application/json`
* `application/yaml`


<a name="listvirtualmachinereplicasetforallnamespaces"></a>
### Get a list of all VirtualMachineReplicaSet objects.
```
GET /apis/kubevirt.io/v1alpha1/virtualmachinereplicasets
```


#### Description
Get a list of all VirtualMachineReplicaSet objects.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Query**|**fieldSelector**  <br>*optional*|A selector to restrict the list of returned objects by their fields. Defaults to everything.|string|
|**Query**|**labelSelector**  <br>*optional*|A selector to restrict the list of returned objects by their labels. Defaults to everything|string|
|**Query**|**resourceVersion**  <br>*optional*|When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.|string|
|**Query**|**timeoutSeconds**  <br>*optional*|TimeoutSeconds for the list/watch call.|integer|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`
* `application/yaml`


<a name="listvirtualmachineforallnamespaces"></a>
### Get a list of all VirtualMachine objects.
```
GET /apis/kubevirt.io/v1alpha1/virtualmachines
```


#### Description
Get a list of all VirtualMachine objects.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Query**|**fieldSelector**  <br>*optional*|A selector to restrict the list of returned objects by their fields. Defaults to everything.|string|
|**Query**|**labelSelector**  <br>*optional*|A selector to restrict the list of returned objects by their labels. Defaults to everything|string|
|**Query**|**resourceVersion**  <br>*optional*|When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.|string|
|**Query**|**timeoutSeconds**  <br>*optional*|TimeoutSeconds for the list/watch call.|integer|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`
* `application/yaml`


<a name="watchmigrationlistforallnamespaces"></a>
### Watch a MigrationList object.
```
GET /apis/kubevirt.io/v1alpha1/watch/migrations
```


#### Description
Watch a MigrationList object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Query**|**fieldSelector**  <br>*optional*|A selector to restrict the list of returned objects by their fields. Defaults to everything.|string|
|**Query**|**labelSelector**  <br>*optional*|A selector to restrict the list of returned objects by their labels. Defaults to everything|string|
|**Query**|**resourceVersion**  <br>*optional*|When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.|string|
|**Query**|**timeoutSeconds**  <br>*optional*|TimeoutSeconds for the list/watch call.|integer|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`


<a name="watchnamespacedmigration"></a>
### Watch a Migration object.
```
GET /apis/kubevirt.io/v1alpha1/watch/namespaces/{namespace}/migrations
```


#### Description
Watch a Migration object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Query**|**fieldSelector**  <br>*optional*|A selector to restrict the list of returned objects by their fields. Defaults to everything.|string|
|**Query**|**labelSelector**  <br>*optional*|A selector to restrict the list of returned objects by their labels. Defaults to everything|string|
|**Query**|**resourceVersion**  <br>*optional*|When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.|string|
|**Query**|**timeoutSeconds**  <br>*optional*|TimeoutSeconds for the list/watch call.|integer|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`


<a name="watchnamespacedvirtualmachinereplicaset"></a>
### Watch a VirtualMachineReplicaSet object.
```
GET /apis/kubevirt.io/v1alpha1/watch/namespaces/{namespace}/virtualmachinereplicasets
```


#### Description
Watch a VirtualMachineReplicaSet object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Query**|**fieldSelector**  <br>*optional*|A selector to restrict the list of returned objects by their fields. Defaults to everything.|string|
|**Query**|**labelSelector**  <br>*optional*|A selector to restrict the list of returned objects by their labels. Defaults to everything|string|
|**Query**|**resourceVersion**  <br>*optional*|When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.|string|
|**Query**|**timeoutSeconds**  <br>*optional*|TimeoutSeconds for the list/watch call.|integer|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`


<a name="watchnamespacedvirtualmachine"></a>
### Watch a VirtualMachine object.
```
GET /apis/kubevirt.io/v1alpha1/watch/namespaces/{namespace}/virtualmachines
```


#### Description
Watch a VirtualMachine object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Path**|**namespace**  <br>*required*|Object name and auth scope, such as for teams and projects|string|
|**Query**|**fieldSelector**  <br>*optional*|A selector to restrict the list of returned objects by their fields. Defaults to everything.|string|
|**Query**|**labelSelector**  <br>*optional*|A selector to restrict the list of returned objects by their labels. Defaults to everything|string|
|**Query**|**resourceVersion**  <br>*optional*|When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.|string|
|**Query**|**timeoutSeconds**  <br>*optional*|TimeoutSeconds for the list/watch call.|integer|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`


<a name="watchvirtualmachinereplicasetlistforallnamespaces"></a>
### Watch a VirtualMachineReplicaSetList object.
```
GET /apis/kubevirt.io/v1alpha1/watch/virtualmachinereplicasets
```


#### Description
Watch a VirtualMachineReplicaSetList object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Query**|**fieldSelector**  <br>*optional*|A selector to restrict the list of returned objects by their fields. Defaults to everything.|string|
|**Query**|**labelSelector**  <br>*optional*|A selector to restrict the list of returned objects by their labels. Defaults to everything|string|
|**Query**|**resourceVersion**  <br>*optional*|When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.|string|
|**Query**|**timeoutSeconds**  <br>*optional*|TimeoutSeconds for the list/watch call.|integer|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`


<a name="watchvirtualmachinelistforallnamespaces"></a>
### Watch a VirtualMachineList object.
```
GET /apis/kubevirt.io/v1alpha1/watch/virtualmachines
```


#### Description
Watch a VirtualMachineList object.


#### Parameters

|Type|Name|Description|Schema|
|---|---|---|---|
|**Query**|**fieldSelector**  <br>*optional*|A selector to restrict the list of returned objects by their fields. Defaults to everything.|string|
|**Query**|**labelSelector**  <br>*optional*|A selector to restrict the list of returned objects by their labels. Defaults to everything|string|
|**Query**|**resourceVersion**  <br>*optional*|When specified with a watch call, shows changes that occur after that particular version of a resource. Defaults to changes from the beginning of history.|string|
|**Query**|**timeoutSeconds**  <br>*optional*|TimeoutSeconds for the list/watch call.|integer|


#### Responses

|HTTP Code|Description|Schema|
|---|---|---|
|**200**|OK|No Content|


#### Produces

* `application/json`



