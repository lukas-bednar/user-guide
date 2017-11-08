## Top Level API Objects

* [v1.VirtualMachine](definitions.md#v1-virtualmachine)
* [v1.VirtualMachineList](definitions.md#v1-virtualmachinelist)
* [v1.Migration](definitions.md#v1-migration)
* [v1.MigrationList](definitions.md#v1-migrationlist)
* [v1.VirtualMachineReplicaSet](definitions.md#v1-virtualmachinereplicaset)
* [v1.VirtualMachineReplicaSetList](definitions.md#v1-virtualmachinereplicasetlist)


<a name="definitions"></a>
## Definitions

<a name="v1-apigroup"></a>
### v1.APIGroup
APIGroup contains the name, the supported versions, and the preferred version of a group.


|Name|Description|Schema|
|---|---|---|
|**apiVersion**  <br>*optional*|APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources|string|
|**kind**  <br>*optional*|Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds|string|
|**name**  <br>*required*|name is the name of the group.|string|
|**preferredVersion**  <br>*optional*|preferredVersion is the version preferred by the API server, which probably is the storage version.|[v1.GroupVersionForDiscovery](definitions.md#v1-groupversionfordiscovery)|
|**serverAddressByClientCIDRs**  <br>*required*|a map of client CIDR to server address that is serving this group. This is to help clients reach servers in the most network-efficient way possible. Clients can use the appropriate server address as per the CIDR that they match. In case of multiple matches, clients should use the longest matching CIDR. The server returns only those CIDRs that it thinks that the client can match. For example: the master will return an internal IP CIDR only, if the client reaches the server using an internal IP. Server looks at X-Forwarded-For header or X-Real-Ip header or request.RemoteAddr (in that order) to get the client IP.|< [v1.ServerAddressByClientCIDR](definitions.md#v1-serveraddressbyclientcidr) > array|
|**versions**  <br>*required*|versions are the versions supported in this group.|< [v1.GroupVersionForDiscovery](definitions.md#v1-groupversionfordiscovery) > array|


<a name="v1-apiresource"></a>
### v1.APIResource
APIResource specifies the name of a resource and whether it is namespaced.


|Name|Description|Schema|
|---|---|---|
|**categories**  <br>*optional*|categories is a list of the grouped resources this resource belongs to (e.g. 'all')|< string > array|
|**kind**  <br>*required*|kind is the kind for the resource (e.g. 'Foo' is the kind for a resource 'foo')|string|
|**name**  <br>*required*|name is the plural name of the resource.|string|
|**namespaced**  <br>*required*|namespaced indicates if a resource is namespaced or not.|boolean|
|**shortNames**  <br>*optional*|shortNames is a list of suggested short names of the resource.|< string > array|
|**singularName**  <br>*required*|singularName is the singular name of the resource.  This allows clients to handle plural and singular opaquely. The singularName is more correct for reporting status on a single item and both singular and plural are allowed from the kubectl CLI interface.|string|
|**verbs**  <br>*required*|verbs is a list of supported kube verbs (this includes get, list, watch, create, update, patch, delete, deletecollection, and proxy)|< string > array|


<a name="v1-apiresourcelist"></a>
### v1.APIResourceList
APIResourceList is a list of APIResource, it is used to expose the name of the resources supported in a specific group and version, and if the resource is namespaced.


|Name|Description|Schema|
|---|---|---|
|**apiVersion**  <br>*optional*|APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources|string|
|**groupVersion**  <br>*required*|groupVersion is the group and version this APIResourceList is for.|string|
|**kind**  <br>*optional*|Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds|string|
|**resources**  <br>*required*|resources contains the name of the resources and if they are namespaced.|< [v1.APIResource](definitions.md#v1-apiresource) > array|


<a name="v1-address"></a>
### v1.Address

|Name|Schema|
|---|---|
|**bus**  <br>*required*|string|
|**domain**  <br>*required*|string|
|**function**  <br>*required*|string|
|**slot**  <br>*required*|string|
|**type**  <br>*required*|string|


<a name="v1-affinity"></a>
### v1.Affinity
Affinity groups all the affinity rules related to a VM


|Name|Description|Schema|
|---|---|---|
|**nodeAffinity**  <br>*optional*|Host affinity support|[v1.NodeAffinity](definitions.md#v1-nodeaffinity)|


<a name="v1-alias"></a>
### v1.Alias

|Name|Schema|
|---|---|
|**name**  <br>*required*|string|


<a name="v1-ballooning"></a>
### v1.Ballooning

|Name|Schema|
|---|---|
|**model**  <br>*required*|string|


<a name="v1-boot"></a>
### v1.Boot

|Name|Schema|
|---|---|
|**dev**  <br>*required*|string|


<a name="v1-bootmenu"></a>
### v1.BootMenu

|Name|Schema|
|---|---|
|**enabled**  <br>*optional*|boolean|
|**timeout**  <br>*optional*|integer (integer)|


<a name="v1-bootorder"></a>
### v1.BootOrder

|Name|Schema|
|---|---|
|**order**  <br>*required*|integer (integer)|


<a name="v1-channel"></a>
### v1.Channel

|Name|Schema|
|---|---|
|**source**  <br>*optional*|[v1.ChannelSource](definitions.md#v1-channelsource)|
|**target**  <br>*optional*|[v1.ChannelTarget](definitions.md#v1-channeltarget)|
|**type**  <br>*required*|string|


<a name="v1-channelsource"></a>
### v1.ChannelSource

|Name|Schema|
|---|---|
|**mode**  <br>*required*|string|
|**path**  <br>*required*|string|


<a name="v1-channeltarget"></a>
### v1.ChannelTarget

|Name|Schema|
|---|---|
|**address**  <br>*optional*|string|
|**name**  <br>*optional*|string|
|**port**  <br>*optional*|integer (integer)|
|**type**  <br>*required*|string|


<a name="v1-cloudinitdatasourcenocloud"></a>
### v1.CloudInitDataSourceNoCloud
http://cloudinit.readthedocs.io/en/latest/topics/datasources/nocloud.html


|Name|Description|Schema|
|---|---|---|
|**metaDataBase64**  <br>*required*|The NoCloud cloud-init metadata as a base64 encoded string|string|
|**userDataBase64**  <br>*required*|The NoCloud cloud-init userdata as a base64 encoded string|string|
|**userDataSecretRef**  <br>*required*|Reference to a k8s secret that contains NoCloud userdata|string|


<a name="v1-cloudinitspec"></a>
### v1.CloudInitSpec
Only one of the fields in the CloudInitSpec can be set


|Name|Description|Schema|
|---|---|---|
|**nocloud**  <br>*required*|Nocloud DataSource|[v1.CloudInitDataSourceNoCloud](definitions.md#v1-cloudinitdatasourcenocloud)|


<a name="v1-console"></a>
### v1.Console

|Name|Schema|
|---|---|
|**target**  <br>*optional*|[v1.ConsoleTarget](definitions.md#v1-consoletarget)|
|**type**  <br>*required*|string|


<a name="v1-consoletarget"></a>
### v1.ConsoleTarget

|Name|Schema|
|---|---|
|**port**  <br>*optional*|integer (integer)|
|**type**  <br>*optional*|string|


<a name="v1-devices"></a>
### v1.Devices

|Name|Schema|
|---|---|
|**channels**  <br>*optional*|< [v1.Channel](definitions.md#v1-channel) > array|
|**consoles**  <br>*optional*|< [v1.Console](definitions.md#v1-console) > array|
|**disks**  <br>*optional*|< [v1.Disk](definitions.md#v1-disk) > array|
|**emulator**  <br>*optional*|string|
|**graphics**  <br>*optional*|< [v1.Graphics](definitions.md#v1-graphics) > array|
|**interfaces**  <br>*optional*|< [v1.Interface](definitions.md#v1-interface) > array|
|**memballoon**  <br>*optional*|[v1.Ballooning](definitions.md#v1-ballooning)|
|**serials**  <br>*optional*|< [v1.Serial](definitions.md#v1-serial) > array|
|**video**  <br>*optional*|< [v1.Video](definitions.md#v1-video) > array|


<a name="v1-disk"></a>
### v1.Disk

|Name|Schema|
|---|---|
|**auth**  <br>*optional*|[v1.DiskAuth](definitions.md#v1-diskauth)|
|**cloudinit**  <br>*optional*|[v1.CloudInitSpec](definitions.md#v1-cloudinitspec)|
|**device**  <br>*required*|string|
|**driver**  <br>*optional*|[v1.DiskDriver](definitions.md#v1-diskdriver)|
|**readOnly**  <br>*optional*|[v1.ReadOnly](definitions.md#v1-readonly)|
|**serial**  <br>*optional*|string|
|**snapshot**  <br>*optional*|string|
|**source**  <br>*required*|[v1.DiskSource](definitions.md#v1-disksource)|
|**target**  <br>*required*|[v1.DiskTarget](definitions.md#v1-disktarget)|
|**type**  <br>*required*|string|


<a name="v1-diskauth"></a>
### v1.DiskAuth

|Name|Schema|
|---|---|
|**secret**  <br>*optional*|[v1.DiskSecret](definitions.md#v1-disksecret)|
|**username**  <br>*required*|string|


<a name="v1-diskdriver"></a>
### v1.DiskDriver

|Name|Schema|
|---|---|
|**cache**  <br>*optional*|string|
|**errorPolicy**  <br>*optional*|string|
|**io**  <br>*optional*|string|
|**name**  <br>*optional*|string|
|**type**  <br>*optional*|string|


<a name="v1-disksecret"></a>
### v1.DiskSecret

|Name|Schema|
|---|---|
|**type**  <br>*required*|string|
|**usage**  <br>*required*|string|


<a name="v1-disksource"></a>
### v1.DiskSource

|Name|Schema|
|---|---|
|**file**  <br>*optional*|string|
|**host**  <br>*optional*|[v1.DiskSourceHost](definitions.md#v1-disksourcehost)|
|**name**  <br>*optional*|string|
|**protocol**  <br>*optional*|string|
|**startupPolicy**  <br>*optional*|string|


<a name="v1-disksourcehost"></a>
### v1.DiskSourceHost

|Name|Schema|
|---|---|
|**name**  <br>*required*|string|
|**port**  <br>*optional*|string|


<a name="v1-disktarget"></a>
### v1.DiskTarget

|Name|Schema|
|---|---|
|**bus**  <br>*optional*|string|
|**dev**  <br>*required*|string|


<a name="v1-domainspec"></a>
### v1.DomainSpec

|Name|Schema|
|---|---|
|**clock**  <br>*optional*|[v1.Clock](definitions.md#v1-clock)|
|**devices**  <br>*required*|[v1.Devices](definitions.md#v1-devices)|
|**memory**  <br>*required*|[v1.Memory](definitions.md#v1-memory)|
|**os**  <br>*required*|[v1.OS](definitions.md#v1-os)|
|**sysInfo**  <br>*optional*|[v1.SysInfo](definitions.md#v1-sysinfo)|
|**type**  <br>*required*|string|


<a name="v1-entry"></a>
### v1.Entry

|Name|Schema|
|---|---|
|**name**  <br>*required*|string|
|**value**  <br>*required*|string|


<a name="v1-filterref"></a>
### v1.FilterRef

|Name|Schema|
|---|---|
|**filter**  <br>*required*|string|


<a name="v1-graphics"></a>
### v1.Graphics

|Name|Schema|
|---|---|
|**autoPort**  <br>*optional*|string|
|**defaultMode**  <br>*optional*|string|
|**listen**  <br>*optional*|[v1.Listen](definitions.md#v1-listen)|
|**passwdValidTo**  <br>*optional*|string|
|**port**  <br>*optional*|integer (int32)|
|**tlsPort**  <br>*optional*|integer (int32)|
|**type**  <br>*required*|string|


<a name="v1-groupversionfordiscovery"></a>
### v1.GroupVersionForDiscovery
GroupVersion contains the "group/version" and "version" string of a version. It is made a struct to keep extensibility.


|Name|Description|Schema|
|---|---|---|
|**groupVersion**  <br>*required*|groupVersion specifies the API group and version in the form "group/version"|string|
|**version**  <br>*required*|version specifies the version in the form of "version". This is to save the clients the trouble of splitting the GroupVersion.|string|


<a name="v1-initializer"></a>
### v1.Initializer
Initializer is information about an initializer that has not yet completed.


|Name|Description|Schema|
|---|---|---|
|**name**  <br>*required*|name of the process that is responsible for initializing this object.|string|


<a name="v1-initializers"></a>
### v1.Initializers
Initializers tracks the progress of initialization.


|Name|Description|Schema|
|---|---|---|
|**pending**  <br>*required*|Pending is a list of initializers that must execute in order before this object is visible. When the last pending initializer is removed, and no failing result is set, the initializers struct will be set to nil and the object is considered as initialized and visible to all clients.|< [v1.Initializer](definitions.md#v1-initializer) > array|
|**result**  <br>*optional*|If result is set with the Failure field, the object will be persisted to storage and then deleted, ensuring that other clients can observe the deletion.|[v1.Status](definitions.md#v1-status)|


<a name="v1-interface"></a>
### v1.Interface

|Name|Schema|
|---|---|
|**address**  <br>*optional*|[v1.Address](definitions.md#v1-address)|
|**alias**  <br>*optional*|[v1.Alias](definitions.md#v1-alias)|
|**bandwidth**  <br>*optional*|[v1.BandWidth](definitions.md#v1-bandwidth)|
|**boot**  <br>*optional*|[v1.BootOrder](definitions.md#v1-bootorder)|
|**filterRef**  <br>*optional*|[v1.FilterRef](definitions.md#v1-filterref)|
|**link**  <br>*optional*|[v1.LinkState](definitions.md#v1-linkstate)|
|**mac**  <br>*optional*|[v1.MAC](definitions.md#v1-mac)|
|**model**  <br>*optional*|[v1.Model](definitions.md#v1-model)|
|**source**  <br>*required*|[v1.InterfaceSource](definitions.md#v1-interfacesource)|
|**target**  <br>*optional*|[v1.InterfaceTarget](definitions.md#v1-interfacetarget)|
|**type**  <br>*required*|string|


<a name="v1-interfacesource"></a>
### v1.InterfaceSource

|Name|Schema|
|---|---|
|**bridge**  <br>*optional*|string|
|**device**  <br>*optional*|string|
|**network**  <br>*optional*|string|


<a name="v1-interfacetarget"></a>
### v1.InterfaceTarget

|Name|Schema|
|---|---|
|**dev**  <br>*required*|string|


<a name="v1-labelselector"></a>
### v1.LabelSelector
A label selector is a label query over a set of resources. The result of matchLabels and matchExpressions are ANDed. An empty label selector matches all objects. A null label selector matches no objects.


|Name|Description|Schema|
|---|---|---|
|**matchExpressions**  <br>*optional*|matchExpressions is a list of label selector requirements. The requirements are ANDed.|< [v1.LabelSelectorRequirement](definitions.md#v1-labelselectorrequirement) > array|
|**matchLabels**  <br>*optional*|matchLabels is a map of {key,value} pairs. A single {key,value} in the matchLabels map is equivalent to an element of matchExpressions, whose key field is "key", the operator is "In", and the values array contains only "value". The requirements are ANDed.|object|


<a name="v1-labelselectorrequirement"></a>
### v1.LabelSelectorRequirement
A label selector requirement is a selector that contains values, a key, and an operator that relates the key and values.


|Name|Description|Schema|
|---|---|---|
|**key**  <br>*required*|key is the label key that the selector applies to.|string|
|**operator**  <br>*required*|operator represents a key's relationship to a set of values. Valid operators ard In, NotIn, Exists and DoesNotExist.|string|
|**values**  <br>*optional*|values is an array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. This array is replaced during a strategic merge patch.|< string > array|


<a name="v1-linkstate"></a>
### v1.LinkState

|Name|Schema|
|---|---|
|**state**  <br>*required*|string|


<a name="v1-listmeta"></a>
### v1.ListMeta
ListMeta describes metadata that synthetic resources must have, including lists and various status objects. A resource may have only one of {ObjectMeta, ListMeta}.


|Name|Description|Schema|
|---|---|---|
|**resourceVersion**  <br>*optional*|String that identifies the server's internal version of this object that can be used by clients to determine when objects have changed. Value must be treated as opaque by clients and passed unmodified back to the server. Populated by the system. Read-only. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#concurrency-control-and-consistency|string|
|**selfLink**  <br>*optional*|SelfLink is a URL representing this object. Populated by the system. Read-only.|string|


<a name="v1-listen"></a>
### v1.Listen

|Name|Schema|
|---|---|
|**address**  <br>*optional*|string|
|**network**  <br>*optional*|string|
|**type**  <br>*required*|string|


<a name="v1-mac"></a>
### v1.MAC

|Name|Schema|
|---|---|
|**address**  <br>*required*|string|


<a name="v1-memory"></a>
### v1.Memory

|Name|Schema|
|---|---|
|**unit**  <br>*required*|string|
|**value**  <br>*required*|integer (integer)|


<a name="v1-migration"></a>
### v1.Migration
A Migration is a job that moves a Virtual Machine from one node to another


|Name|Description|Schema|
|---|---|---|
|**apiVersion**  <br>*optional*|APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources|string|
|**kind**  <br>*optional*|Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds|string|
|**metadata**  <br>*optional*||[v1.ObjectMeta](definitions.md#v1-objectmeta)|
|**spec**  <br>*optional*||[v1.MigrationSpec](definitions.md#v1-migrationspec)|
|**status**  <br>*optional*||[v1.MigrationStatus](definitions.md#v1-migrationstatus)|


<a name="v1-migrationlist"></a>
### v1.MigrationList
A list of Migrations


|Name|Description|Schema|
|---|---|---|
|**apiVersion**  <br>*optional*|APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources|string|
|**items**  <br>*required*||< [v1.Migration](definitions.md#v1-migration) > array|
|**kind**  <br>*optional*|Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds|string|
|**metadata**  <br>*optional*||[v1.ListMeta](definitions.md#v1-listmeta)|


<a name="v1-migrationspec"></a>
### v1.MigrationSpec
MigrationSpec is a description of a VM Migration
For example "destinationNodeName": "testvm" will migrate a VM called "testvm" in the namespace "default"


|Name|Description|Schema|
|---|---|---|
|**nodeSelector**  <br>*optional*|Criteria to use when selecting the destination for the migration<br>for example, to select by the hostname, specify `kubernetes.io/hostname: master`<br>other possible choices include the hardware required to run the vm or<br>or lableing of the nodes to indicate their roles in larger applications.<br>examples:<br>disktype: ssd,<br>randomGenerator: /dev/random,<br>randomGenerator: superfastdevice,<br>app: mysql,<br>licensedForServiceX: true<br>Note that these selectors are additions to the node selectors on the VM itself and they must not exist on the VM.<br>If they are conflicting with the VM, no migration will be started.|object|
|**selector**  <br>*required*|Criterias for selecting the VM to migrate.<br>For example<br>selector:<br>  name: testvm<br>will select the VM `testvm` for migration|[v1.VMSelector](definitions.md#v1-vmselector)|


<a name="v1-migrationstatus"></a>
### v1.MigrationStatus
MigrationStatus is the last reported status of a VM Migratrion. Status may trail the actual
state of a migration.


|Name|Schema|
|---|---|
|**instance**  <br>*optional*|[types.UID](definitions.md#types-uid)|
|**phase**  <br>*optional*|string|


<a name="v1-model"></a>
### v1.Model

|Name|Schema|
|---|---|
|**type**  <br>*required*|string|


<a name="v1-nodeaffinity"></a>
### v1.NodeAffinity
Node affinity is a group of node affinity scheduling rules.


|Name|Description|Schema|
|---|---|---|
|**preferredDuringSchedulingIgnoredDuringExecution**  <br>*optional*|The scheduler will prefer to schedule pods to nodes that satisfy the affinity expressions specified by this field, but it may choose a node that violates one or more of the expressions. The node that is most preferred is the one with the greatest sum of weights, i.e. for each node that meets all of the scheduling requirements (resource request, requiredDuringScheduling affinity expressions, etc.), compute a sum by iterating through the elements of this field and adding "weight" to the sum if the node matches the corresponding matchExpressions; the node(s) with the highest sum are the most preferred.|< [v1.PreferredSchedulingTerm](definitions.md#v1-preferredschedulingterm) > array|
|**requiredDuringSchedulingIgnoredDuringExecution**  <br>*optional*|If the affinity requirements specified by this field are not met at scheduling time, the pod will not be scheduled onto the node. If the affinity requirements specified by this field cease to be met at some point during pod execution (e.g. due to an update), the system may or may not try to eventually evict the pod from its node.|[v1.NodeSelector](definitions.md#v1-nodeselector)|


<a name="v1-nodeselector"></a>
### v1.NodeSelector
A node selector represents the union of the results of one or more label queries over a set of nodes; that is, it represents the OR of the selectors represented by the node selector terms.


|Name|Description|Schema|
|---|---|---|
|**nodeSelectorTerms**  <br>*required*|Required. A list of node selector terms. The terms are ORed.|< [v1.NodeSelectorTerm](definitions.md#v1-nodeselectorterm) > array|


<a name="v1-nodeselectorrequirement"></a>
### v1.NodeSelectorRequirement
A node selector requirement is a selector that contains values, a key, and an operator that relates the key and values.


|Name|Description|Schema|
|---|---|---|
|**key**  <br>*required*|The label key that the selector applies to.|string|
|**operator**  <br>*required*|Represents a key's relationship to a set of values. Valid operators are In, NotIn, Exists, DoesNotExist. Gt, and Lt.|string|
|**values**  <br>*optional*|An array of string values. If the operator is In or NotIn, the values array must be non-empty. If the operator is Exists or DoesNotExist, the values array must be empty. If the operator is Gt or Lt, the values array must have a single element, which will be interpreted as an integer. This array is replaced during a strategic merge patch.|< string > array|


<a name="v1-nodeselectorterm"></a>
### v1.NodeSelectorTerm
A null or empty node selector term matches no objects.


|Name|Description|Schema|
|---|---|---|
|**matchExpressions**  <br>*required*|Required. A list of node selector requirements. The requirements are ANDed.|< [v1.NodeSelectorRequirement](definitions.md#v1-nodeselectorrequirement) > array|


<a name="v1-os"></a>
### v1.OS

|Name|Schema|
|---|---|
|**bios**  <br>*optional*|[v1.BIOS](definitions.md#v1-bios)|
|**bootMenu**  <br>*optional*|[v1.BootMenu](definitions.md#v1-bootmenu)|
|**bootOrder**  <br>*required*|< [v1.Boot](definitions.md#v1-boot) > array|
|**smBIOS**  <br>*optional*|[v1.SMBios](definitions.md#v1-smbios)|
|**type**  <br>*required*|[v1.OSType](definitions.md#v1-ostype)|


<a name="v1-ostype"></a>
### v1.OSType

|Name|Schema|
|---|---|
|**arch**  <br>*optional*|string|
|**machine**  <br>*optional*|string|
|**os**  <br>*required*|string|


<a name="v1-objectmeta"></a>
### v1.ObjectMeta
ObjectMeta is metadata that all persisted resources must have, which includes all objects users must create.


|Name|Description|Schema|
|---|---|---|
|**annotations**  <br>*optional*|Annotations is an unstructured key value map stored with a resource that may be set by external tools to store and retrieve arbitrary metadata. They are not queryable and should be preserved when modifying objects. More info: http://kubernetes.io/docs/user-guide/annotations|object|
|**clusterName**  <br>*optional*|The name of the cluster which the object belongs to. This is used to distinguish resources with same name and namespace in different clusters. This field is not set anywhere right now and apiserver is going to ignore it if set in create or update request.|string|
|**creationTimestamp**  <br>*optional*|CreationTimestamp is a timestamp representing the server time when this object was created. It is not guaranteed to be set in happens-before order across separate operations. Clients may not set this value. It is represented in RFC3339 form and is in UTC.<br><br>Populated by the system. Read-only. Null for lists. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#metadata|string|
|**deletionGracePeriodSeconds**  <br>*optional*|Number of seconds allowed for this object to gracefully terminate before it will be removed from the system. Only set when deletionTimestamp is also set. May only be shortened. Read-only.|integer (int64)|
|**deletionTimestamp**  <br>*optional*|DeletionTimestamp is RFC 3339 date and time at which this resource will be deleted. This field is set by the server when a graceful deletion is requested by the user, and is not directly settable by a client. The resource is expected to be deleted (no longer visible from resource lists, and not reachable by name) after the time in this field. Once set, this value may not be unset or be set further into the future, although it may be shortened or the resource may be deleted prior to this time. For example, a user may request that a pod is deleted in 30 seconds. The Kubelet will react by sending a graceful termination signal to the containers in the pod. After that 30 seconds, the Kubelet will send a hard termination signal (SIGKILL) to the container and after cleanup, remove the pod from the API. In the presence of network partitions, this object may still exist after this timestamp, until an administrator or automated process can determine the resource is fully terminated. If not set, graceful deletion of the object has not been requested.<br><br>Populated by the system when a graceful deletion is requested. Read-only. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#metadata|string|
|**finalizers**  <br>*optional*|Must be empty before the object is deleted from the registry. Each entry is an identifier for the responsible component that will remove the entry from the list. If the deletionTimestamp of the object is non-nil, entries in this list can only be removed.|< string > array|
|**generateName**  <br>*optional*|GenerateName is an optional prefix, used by the server, to generate a unique name ONLY IF the Name field has not been provided. If this field is used, the name returned to the client will be different than the name passed. This value will also be combined with a unique suffix. The provided value has the same validation rules as the Name field, and may be truncated by the length of the suffix required to make the value unique on the server.<br><br>If this field is specified and the generated name exists, the server will NOT return a 409 - instead, it will either return 201 Created or 500 with Reason ServerTimeout indicating a unique name could not be found in the time allotted, and the client should retry (optionally after the time indicated in the Retry-After header).<br><br>Applied only if Name is not specified. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#idempotency|string|
|**generation**  <br>*optional*|A sequence number representing a specific generation of the desired state. Populated by the system. Read-only.|integer (int64)|
|**initializers**  <br>*optional*|An initializer is a controller which enforces some system invariant at object creation time. This field is a list of initializers that have not yet acted on this object. If nil or empty, this object has been completely initialized. Otherwise, the object is considered uninitialized and is hidden (in list/watch and get calls) from clients that haven't explicitly asked to observe uninitialized objects.<br><br>When an object is created, the system will populate this list with the current set of initializers. Only privileged users may set or modify this list. Once it is empty, it may not be modified further by any user.|[v1.Initializers](definitions.md#v1-initializers)|
|**labels**  <br>*optional*|Map of string keys and values that can be used to organize and categorize (scope and select) objects. May match selectors of replication controllers and services. More info: http://kubernetes.io/docs/user-guide/labels|object|
|**name**  <br>*optional*|Name must be unique within a namespace. Is required when creating resources, although some resources may allow a client to request the generation of an appropriate name automatically. Name is primarily intended for creation idempotence and configuration definition. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/identifiers#names|string|
|**namespace**  <br>*optional*|Namespace defines the space within each name must be unique. An empty namespace is equivalent to the "default" namespace, but "default" is the canonical representation. Not all objects are required to be scoped to a namespace - the value of this field for those objects will be empty.<br><br>Must be a DNS_LABEL. Cannot be updated. More info: http://kubernetes.io/docs/user-guide/namespaces|string|
|**ownerReferences**  <br>*optional*|List of objects depended by this object. If ALL objects in the list have been deleted, this object will be garbage collected. If this object is managed by a controller, then an entry in this list will point to this controller, with the controller field set to true. There cannot be more than one managing controller.|< [v1.OwnerReference](definitions.md#v1-ownerreference) > array|
|**resourceVersion**  <br>*optional*|An opaque value that represents the internal version of this object that can be used by clients to determine when objects have changed. May be used for optimistic concurrency, change detection, and the watch operation on a resource or set of resources. Clients must treat these values as opaque and passed unmodified back to the server. They may only be valid for a particular resource or set of resources.<br><br>Populated by the system. Read-only. Value must be treated as opaque by clients and . More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#concurrency-control-and-consistency|string|
|**selfLink**  <br>*optional*|SelfLink is a URL representing this object. Populated by the system. Read-only.|string|
|**uid**  <br>*optional*|UID is the unique in time and space value for this object. It is typically generated by the server on successful creation of a resource and is not allowed to change on PUT operations.<br><br>Populated by the system. Read-only. More info: http://kubernetes.io/docs/user-guide/identifiers#uids|string|


<a name="v1-ownerreference"></a>
### v1.OwnerReference
OwnerReference contains enough information to let you identify an owning object. Currently, an owning object must be in the same namespace, so there is no namespace field.


|Name|Description|Schema|
|---|---|---|
|**apiVersion**  <br>*required*|API version of the referent.|string|
|**blockOwnerDeletion**  <br>*optional*|If true, AND if the owner has the "foregroundDeletion" finalizer, then the owner cannot be deleted from the key-value store until this reference is removed. Defaults to false. To set this field, a user needs "delete" permission of the owner, otherwise 422 (Unprocessable Entity) will be returned.|boolean|
|**controller**  <br>*optional*|If true, this reference points to the managing controller.|boolean|
|**kind**  <br>*required*|Kind of the referent. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds|string|
|**name**  <br>*required*|Name of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#names|string|
|**uid**  <br>*required*|UID of the referent. More info: http://kubernetes.io/docs/user-guide/identifiers#uids|string|


<a name="v1-preferredschedulingterm"></a>
### v1.PreferredSchedulingTerm
An empty preferred scheduling term matches all objects with implicit weight 0 (i.e. it's a no-op). A null preferred scheduling term matches no objects (i.e. is also a no-op).


|Name|Description|Schema|
|---|---|---|
|**preference**  <br>*required*|A node selector term, associated with the corresponding weight.|[v1.NodeSelectorTerm](definitions.md#v1-nodeselectorterm)|
|**weight**  <br>*required*|Weight associated with matching the corresponding nodeSelectorTerm, in the range 1-100.|integer (int32)|


<a name="v1-smbios"></a>
### v1.SMBios

|Name|Schema|
|---|---|
|**mode**  <br>*required*|string|


<a name="v1-serial"></a>
### v1.Serial

|Name|Schema|
|---|---|
|**target**  <br>*optional*|[v1.SerialTarget](definitions.md#v1-serialtarget)|
|**type**  <br>*required*|string|


<a name="v1-serialtarget"></a>
### v1.SerialTarget

|Name|Schema|
|---|---|
|**port**  <br>*optional*|integer (integer)|


<a name="v1-serveraddressbyclientcidr"></a>
### v1.ServerAddressByClientCIDR
ServerAddressByClientCIDR helps the client to determine the server address that they should use, depending on the clientCIDR that they match.


|Name|Description|Schema|
|---|---|---|
|**clientCIDR**  <br>*required*|The CIDR with which clients can match their IP to figure out the server address that they should use.|string|
|**serverAddress**  <br>*required*|Address of this server, suitable for a client that matches the above CIDR. This can be a hostname, hostname:port, IP or IP:port.|string|


<a name="v1-status"></a>
### v1.Status
Status is a return value for calls that don't return other objects.


|Name|Description|Schema|
|---|---|---|
|**apiVersion**  <br>*optional*|APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources|string|
|**code**  <br>*optional*|Suggested HTTP return code for this status, 0 if not set.|integer (int32)|
|**details**  <br>*optional*|Extended data associated with the reason.  Each reason may define its own extended details. This field is optional and the data returned is not guaranteed to conform to any schema except that defined by the reason type.|[v1.StatusDetails](definitions.md#v1-statusdetails)|
|**kind**  <br>*optional*|Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds|string|
|**message**  <br>*optional*|A human-readable description of the status of this operation.|string|
|**metadata**  <br>*optional*|Standard list metadata. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds|[v1.ListMeta](definitions.md#v1-listmeta)|
|**reason**  <br>*optional*|A machine-readable description of why this operation is in the "Failure" status. If this value is empty there is no information available. A Reason clarifies an HTTP status code but does not override it.|string|
|**status**  <br>*optional*|Status of the operation. One of: "Success" or "Failure". More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#spec-and-status|string|


<a name="v1-statuscause"></a>
### v1.StatusCause
StatusCause provides more information about an api.Status failure, including cases when multiple errors are encountered.


|Name|Description|Schema|
|---|---|---|
|**field**  <br>*optional*|The field of the resource that has caused this error, as named by its JSON serialization. May include dot and postfix notation for nested attributes. Arrays are zero-indexed.  Fields may appear more than once in an array of causes due to fields having multiple errors. Optional.<br><br>Examples:<br>  "name" - the field "name" on the current resource<br>  "items[0].name" - the field "name" on the first array entry in "items"|string|
|**message**  <br>*optional*|A human-readable description of the cause of the error.  This field may be presented as-is to a reader.|string|
|**reason**  <br>*optional*|A machine-readable description of the cause of the error. If this value is empty there is no information available.|string|


<a name="v1-statusdetails"></a>
### v1.StatusDetails
StatusDetails is a set of additional properties that MAY be set by the server to provide additional information about a response. The Reason field of a Status object defines what attributes will be set. Clients must ignore fields that do not match the defined type of each attribute, and should assume that any attribute may be empty, invalid, or under defined.


|Name|Description|Schema|
|---|---|---|
|**causes**  <br>*optional*|The Causes array includes more details associated with the StatusReason failure. Not all StatusReasons may provide detailed causes.|< [v1.StatusCause](definitions.md#v1-statuscause) > array|
|**group**  <br>*optional*|The group attribute of the resource associated with the status StatusReason.|string|
|**kind**  <br>*optional*|The kind attribute of the resource associated with the status StatusReason. On some operations may differ from the requested resource Kind. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds|string|
|**name**  <br>*optional*|The name attribute of the resource associated with the status StatusReason (when there is a single name which can be described).|string|
|**retryAfterSeconds**  <br>*optional*|If specified, the time in seconds before the operation should be retried. Some errors may indicate the client must take an alternate action - for those errors this field may indicate how long to wait before taking the alternate action.|integer (int32)|
|**uid**  <br>*optional*|UID of the resource. (when there is a single resource which can be described). More info: http://kubernetes.io/docs/user-guide/identifiers#uids|string|


<a name="v1-sysinfo"></a>
### v1.SysInfo

|Name|Schema|
|---|---|
|**baseBoard**  <br>*required*|< [v1.Entry](definitions.md#v1-entry) > array|
|**bios**  <br>*required*|< [v1.Entry](definitions.md#v1-entry) > array|
|**system**  <br>*required*|< [v1.Entry](definitions.md#v1-entry) > array|
|**type**  <br>*required*|string|


<a name="v1-vmcondition"></a>
### v1.VMCondition

|Name|Schema|
|---|---|
|**lastProbeTime**  <br>*optional*|string|
|**lastTransitionTime**  <br>*optional*|string|
|**message**  <br>*optional*|string|
|**reason**  <br>*optional*|string|
|**status**  <br>*required*|string|
|**type**  <br>*required*|string|


<a name="v1-vmgraphics"></a>
### v1.VMGraphics

|Name|Schema|
|---|---|
|**host**  <br>*required*|string|
|**port**  <br>*required*|integer (int32)|
|**type**  <br>*required*|string|


<a name="v1-vmreplicasetcondition"></a>
### v1.VMReplicaSetCondition

|Name|Schema|
|---|---|
|**lastProbeTime**  <br>*optional*|string|
|**lastTransitionTime**  <br>*optional*|string|
|**message**  <br>*optional*|string|
|**reason**  <br>*optional*|string|
|**status**  <br>*required*|string|
|**type**  <br>*required*|string|


<a name="v1-vmreplicasetspec"></a>
### v1.VMReplicaSetSpec

|Name|Description|Schema|
|---|---|---|
|**paused**  <br>*optional*|Indicates that the replica set is paused.<br>+optional|boolean|
|**replicas**  <br>*optional*|Number of desired pods. This is a pointer to distinguish between explicit<br>zero and not specified. Defaults to 1.<br>+optional|integer (int32)|
|**selector**  <br>*optional*|Label selector for pods. Existing ReplicaSets whose pods are<br>selected by this will be the ones affected by this deployment.<br>+optional|[v1.LabelSelector](definitions.md#v1-labelselector)|
|**template**  <br>*required*|Template describes the pods that will be created.|[v1.VMTemplateSpec](definitions.md#v1-vmtemplatespec)|


<a name="v1-vmreplicasetstatus"></a>
### v1.VMReplicaSetStatus

|Name|Description|Schema|
|---|---|---|
|**conditions**  <br>*required*||< [v1.VMReplicaSetCondition](definitions.md#v1-vmreplicasetcondition) > array|
|**readyReplicas**  <br>*optional*|The number of ready replicas for this replica set.<br>+optional|integer (int32)|
|**replicas**  <br>*optional*|Total number of non-terminated pods targeted by this deployment (their labels match the selector).<br>+optional|integer (int32)|


<a name="v1-vmselector"></a>
### v1.VMSelector

|Name|Description|Schema|
|---|---|---|
|**name**  <br>*required*|Name of the VM to migrate|string|


<a name="v1-vmspec"></a>
### v1.VMSpec
VMSpec is a description of a VM. Not to be confused with api.DomainSpec in virt-handler.
It is expected that v1.DomainSpec will be merged into this structure.


|Name|Description|Schema|
|---|---|---|
|**affinity**  <br>*optional*|If affinity is specifies, obey all the affinity rules|[v1.Affinity](definitions.md#v1-affinity)|
|**domain**  <br>*optional*|Domain is the actual libvirt domain.|[v1.DomainSpec](definitions.md#v1-domainspec)|
|**nodeSelector**  <br>*optional*|If labels are specified, only nodes marked with all of these labels are considered when scheduling the VM.|object|


<a name="v1-vmstatus"></a>
### v1.VMStatus
VMStatus represents information about the status of a VM. Status may trail the actual
state of a system.


|Name|Description|Schema|
|---|---|---|
|**conditions**  <br>*optional*|Conditions are specific points in VM's pod runtime.|< [v1.VMCondition](definitions.md#v1-vmcondition) > array|
|**graphics**  <br>*required*|Graphics represent the details of available graphical consoles.|< [v1.VMGraphics](definitions.md#v1-vmgraphics) > array|
|**migrationNodeName**  <br>*optional*|MigrationNodeName is the node where the VM is live migrating to.|string|
|**nodeName**  <br>*optional*|NodeName is the name where the VM is currently running.|string|
|**phase**  <br>*required*|Phase is the status of the VM in kubernetes world. It is not the VM status, but partially correlates to it.|string|


<a name="v1-vmtemplatespec"></a>
### v1.VMTemplateSpec

|Name|Description|Schema|
|---|---|---|
|**metadata**  <br>*optional*||[v1.ObjectMeta](definitions.md#v1-objectmeta)|
|**spec**  <br>*optional*|VM Spec contains the VM specification.|[v1.VMSpec](definitions.md#v1-vmspec)|


<a name="v1-video"></a>
### v1.Video

|Name|Schema|
|---|---|
|**heads**  <br>*optional*|integer (integer)|
|**ram**  <br>*optional*|integer (integer)|
|**type**  <br>*required*|string|
|**vRam**  <br>*optional*|integer (integer)|
|**vgaMem**  <br>*optional*|integer (integer)|


<a name="v1-virtualmachine"></a>
### v1.VirtualMachine
VirtualMachine is *the* VM Definition. It represents a virtual machine in the runtime environment of kubernetes.


|Name|Description|Schema|
|---|---|---|
|**apiVersion**  <br>*optional*|APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources|string|
|**kind**  <br>*optional*|Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds|string|
|**metadata**  <br>*optional*||[v1.ObjectMeta](definitions.md#v1-objectmeta)|
|**spec**  <br>*optional*|VM Spec contains the VM specification.|[v1.VMSpec](definitions.md#v1-vmspec)|
|**status**  <br>*required*|Status is the high level overview of how the VM is doing. It contains information available to controllers and users.|[v1.VMStatus](definitions.md#v1-vmstatus)|


<a name="v1-virtualmachinelist"></a>
### v1.VirtualMachineList
VirtualMachineList is a list of VirtualMachines


|Name|Description|Schema|
|---|---|---|
|**apiVersion**  <br>*optional*|APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources|string|
|**items**  <br>*required*||< [v1.VirtualMachine](definitions.md#v1-virtualmachine) > array|
|**kind**  <br>*optional*|Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds|string|
|**metadata**  <br>*optional*||[v1.ListMeta](definitions.md#v1-listmeta)|


<a name="v1-virtualmachinereplicaset"></a>
### v1.VirtualMachineReplicaSet
VM is *the* VM Definition. It represents a virtual machine in the runtime environment of kubernetes.


|Name|Description|Schema|
|---|---|---|
|**apiVersion**  <br>*optional*|APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources|string|
|**kind**  <br>*optional*|Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds|string|
|**metadata**  <br>*optional*||[v1.ObjectMeta](definitions.md#v1-objectmeta)|
|**spec**  <br>*optional*|VM Spec contains the VM specification.|[v1.VMReplicaSetSpec](definitions.md#v1-vmreplicasetspec)|
|**status**  <br>*required*|Status is the high level overview of how the VM is doing. It contains information available to controllers and users.|[v1.VMReplicaSetStatus](definitions.md#v1-vmreplicasetstatus)|


<a name="v1-virtualmachinereplicasetlist"></a>
### v1.VirtualMachineReplicaSetList
VMList is a list of VMs


|Name|Description|Schema|
|---|---|---|
|**apiVersion**  <br>*optional*|APIVersion defines the versioned schema of this representation of an object. Servers should convert recognized schemas to the latest internal value, and may reject unrecognized values. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#resources|string|
|**items**  <br>*required*||< [v1.VirtualMachineReplicaSet](definitions.md#v1-virtualmachinereplicaset) > array|
|**kind**  <br>*optional*|Kind is a string value representing the REST resource this object represents. Servers may infer this from the endpoint the client submits requests to. Cannot be updated. In CamelCase. More info: https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds|string|
|**metadata**  <br>*optional*||[v1.ListMeta](definitions.md#v1-listmeta)|



