
---
title: "getAccessPoint"
title_tag: "aws.efs.getAccessPoint"
meta_desc: "Documentation for the aws.efs.getAccessPoint function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Provides information about an Elastic File System (EFS) Access Point.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using Aws = Pulumi.Aws;

class MyStack : Stack
{
    public MyStack()
    {
        var test = Output.Create(Aws.Efs.GetAccessPoint.InvokeAsync(new Aws.Efs.GetAccessPointArgs
        {
            AccessPointId = "fsap-12345678",
        }));
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-aws/sdk/v3/go/aws/efs"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := efs.LookupAccessPoint(ctx, &efs.LookupAccessPointArgs{
			AccessPointId: "fsap-12345678",
		}, nil)
		if err != nil {
			return err
		}
		return nil
	})
}
```


{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_aws as aws

test = aws.efs.get_access_point(access_point_id="fsap-12345678")
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const test = pulumi.output(aws.efs.getAccessPoint({
    accessPointId: "fsap-12345678",
}, { async: true }));
```


{{< /example >}}





{{% /examples %}}




## Using getAccessPoint {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getAccessPoint<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetAccessPointArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetAccessPointResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_access_point(</span><span class="nx">access_point_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">tags</span><span class="p">:</span> <span class="nx">Optional[Mapping[str, str]]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetAccessPointResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupAccessPoint<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">LookupAccessPointArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupAccessPointResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupAccessPoint` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetAccessPoint </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetAccessPointResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetAccessPointArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="accesspointid_csharp">
<a href="#accesspointid_csharp" style="color: inherit; text-decoration: inherit;">Access<wbr>Point<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID that identifies the file system.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="tags_csharp">
<a href="#tags_csharp" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, string&gt;</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="accesspointid_go">
<a href="#accesspointid_go" style="color: inherit; text-decoration: inherit;">Access<wbr>Point<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID that identifies the file system.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="tags_go">
<a href="#tags_go" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="accesspointid_nodejs">
<a href="#accesspointid_nodejs" style="color: inherit; text-decoration: inherit;">access<wbr>Point<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID that identifies the file system.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="tags_nodejs">
<a href="#tags_nodejs" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="access_point_id_python">
<a href="#access_point_id_python" style="color: inherit; text-decoration: inherit;">access_<wbr>point_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID that identifies the file system.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="tags_python">
<a href="#tags_python" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Mapping[str, str]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getAccessPoint Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="accesspointid_csharp">
<a href="#accesspointid_csharp" style="color: inherit; text-decoration: inherit;">Access<wbr>Point<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="arn_csharp">
<a href="#arn_csharp" style="color: inherit; text-decoration: inherit;">Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="filesystemarn_csharp">
<a href="#filesystemarn_csharp" style="color: inherit; text-decoration: inherit;">File<wbr>System<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="filesystemid_csharp">
<a href="#filesystemid_csharp" style="color: inherit; text-decoration: inherit;">File<wbr>System<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the file system for which the access point is intended.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ownerid_csharp">
<a href="#ownerid_csharp" style="color: inherit; text-decoration: inherit;">Owner<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="posixusers_csharp">
<a href="#posixusers_csharp" style="color: inherit; text-decoration: inherit;">Posix<wbr>Users</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccesspointposixuser">List&lt;Get<wbr>Access<wbr>Point<wbr>Posix<wbr>User&gt;</a></span>
    </dt>
    <dd>{{% md %}}Single element list containing operating system user and group applied to all file system requests made using the access point.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="rootdirectories_csharp">
<a href="#rootdirectories_csharp" style="color: inherit; text-decoration: inherit;">Root<wbr>Directories</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccesspointrootdirectory">List&lt;Get<wbr>Access<wbr>Point<wbr>Root<wbr>Directory&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_csharp">
<a href="#tags_csharp" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Dictionary&lt;string, string&gt;</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="accesspointid_go">
<a href="#accesspointid_go" style="color: inherit; text-decoration: inherit;">Access<wbr>Point<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="arn_go">
<a href="#arn_go" style="color: inherit; text-decoration: inherit;">Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="filesystemarn_go">
<a href="#filesystemarn_go" style="color: inherit; text-decoration: inherit;">File<wbr>System<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="filesystemid_go">
<a href="#filesystemid_go" style="color: inherit; text-decoration: inherit;">File<wbr>System<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the file system for which the access point is intended.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ownerid_go">
<a href="#ownerid_go" style="color: inherit; text-decoration: inherit;">Owner<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="posixusers_go">
<a href="#posixusers_go" style="color: inherit; text-decoration: inherit;">Posix<wbr>Users</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccesspointposixuser">[]Get<wbr>Access<wbr>Point<wbr>Posix<wbr>User</a></span>
    </dt>
    <dd>{{% md %}}Single element list containing operating system user and group applied to all file system requests made using the access point.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="rootdirectories_go">
<a href="#rootdirectories_go" style="color: inherit; text-decoration: inherit;">Root<wbr>Directories</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccesspointrootdirectory">[]Get<wbr>Access<wbr>Point<wbr>Root<wbr>Directory</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_go">
<a href="#tags_go" style="color: inherit; text-decoration: inherit;">Tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="accesspointid_nodejs">
<a href="#accesspointid_nodejs" style="color: inherit; text-decoration: inherit;">access<wbr>Point<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="arn_nodejs">
<a href="#arn_nodejs" style="color: inherit; text-decoration: inherit;">arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="filesystemarn_nodejs">
<a href="#filesystemarn_nodejs" style="color: inherit; text-decoration: inherit;">file<wbr>System<wbr>Arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="filesystemid_nodejs">
<a href="#filesystemid_nodejs" style="color: inherit; text-decoration: inherit;">file<wbr>System<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the file system for which the access point is intended.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="ownerid_nodejs">
<a href="#ownerid_nodejs" style="color: inherit; text-decoration: inherit;">owner<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="posixusers_nodejs">
<a href="#posixusers_nodejs" style="color: inherit; text-decoration: inherit;">posix<wbr>Users</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccesspointposixuser">Get<wbr>Access<wbr>Point<wbr>Posix<wbr>User[]</a></span>
    </dt>
    <dd>{{% md %}}Single element list containing operating system user and group applied to all file system requests made using the access point.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="rootdirectories_nodejs">
<a href="#rootdirectories_nodejs" style="color: inherit; text-decoration: inherit;">root<wbr>Directories</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccesspointrootdirectory">Get<wbr>Access<wbr>Point<wbr>Root<wbr>Directory[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_nodejs">
<a href="#tags_nodejs" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="access_point_id_python">
<a href="#access_point_id_python" style="color: inherit; text-decoration: inherit;">access_<wbr>point_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="arn_python">
<a href="#arn_python" style="color: inherit; text-decoration: inherit;">arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="file_system_arn_python">
<a href="#file_system_arn_python" style="color: inherit; text-decoration: inherit;">file_<wbr>system_<wbr>arn</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="file_system_id_python">
<a href="#file_system_id_python" style="color: inherit; text-decoration: inherit;">file_<wbr>system_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the file system for which the access point is intended.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="owner_id_python">
<a href="#owner_id_python" style="color: inherit; text-decoration: inherit;">owner_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="posix_users_python">
<a href="#posix_users_python" style="color: inherit; text-decoration: inherit;">posix_<wbr>users</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccesspointposixuser">Sequence[Get<wbr>Access<wbr>Point<wbr>Posix<wbr>User]</a></span>
    </dt>
    <dd>{{% md %}}Single element list containing operating system user and group applied to all file system requests made using the access point.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="root_directories_python">
<a href="#root_directories_python" style="color: inherit; text-decoration: inherit;">root_<wbr>directories</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccesspointrootdirectory">Sequence[Get<wbr>Access<wbr>Point<wbr>Root<wbr>Directory]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="tags_python">
<a href="#tags_python" style="color: inherit; text-decoration: inherit;">tags</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Mapping[str, str]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## Supporting Types


<h4 id="getaccesspointposixuser">Get<wbr>Access<wbr>Point<wbr>Posix<wbr>User</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="gid_csharp">
<a href="#gid_csharp" style="color: inherit; text-decoration: inherit;">Gid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Group ID
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="secondarygids_csharp">
<a href="#secondarygids_csharp" style="color: inherit; text-decoration: inherit;">Secondary<wbr>Gids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">List&lt;int&gt;</span>
    </dt>
    <dd>{{% md %}}Secondary group IDs
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="uid_csharp">
<a href="#uid_csharp" style="color: inherit; text-decoration: inherit;">Uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}User Id
* `root_directory`- Single element list containing information on the directory on the Amazon EFS file system that the access point provides access to.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="gid_go">
<a href="#gid_go" style="color: inherit; text-decoration: inherit;">Gid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Group ID
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="secondarygids_go">
<a href="#secondarygids_go" style="color: inherit; text-decoration: inherit;">Secondary<wbr>Gids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">[]int</span>
    </dt>
    <dd>{{% md %}}Secondary group IDs
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="uid_go">
<a href="#uid_go" style="color: inherit; text-decoration: inherit;">Uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}User Id
* `root_directory`- Single element list containing information on the directory on the Amazon EFS file system that the access point provides access to.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="gid_nodejs">
<a href="#gid_nodejs" style="color: inherit; text-decoration: inherit;">gid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Group ID
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="secondarygids_nodejs">
<a href="#secondarygids_nodejs" style="color: inherit; text-decoration: inherit;">secondary<wbr>Gids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number[]</span>
    </dt>
    <dd>{{% md %}}Secondary group IDs
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="uid_nodejs">
<a href="#uid_nodejs" style="color: inherit; text-decoration: inherit;">uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}User Id
* `root_directory`- Single element list containing information on the directory on the Amazon EFS file system that the access point provides access to.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="gid_python">
<a href="#gid_python" style="color: inherit; text-decoration: inherit;">gid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Group ID
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="secondary_gids_python">
<a href="#secondary_gids_python" style="color: inherit; text-decoration: inherit;">secondary_<wbr>gids</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">Sequence[int]</span>
    </dt>
    <dd>{{% md %}}Secondary group IDs
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="uid_python">
<a href="#uid_python" style="color: inherit; text-decoration: inherit;">uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}User Id
* `root_directory`- Single element list containing information on the directory on the Amazon EFS file system that the access point provides access to.
{{% /md %}}</dd></dl>
{{% /choosable %}}

<h4 id="getaccesspointrootdirectory">Get<wbr>Access<wbr>Point<wbr>Root<wbr>Directory</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="creationinfos_csharp">
<a href="#creationinfos_csharp" style="color: inherit; text-decoration: inherit;">Creation<wbr>Infos</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccesspointrootdirectorycreationinfo">List&lt;Get<wbr>Access<wbr>Point<wbr>Root<wbr>Directory<wbr>Creation<wbr>Info<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}Single element list containing information on the creation permissions of the directory
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="path_csharp">
<a href="#path_csharp" style="color: inherit; text-decoration: inherit;">Path</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Path exposed as the root directory
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="creationinfos_go">
<a href="#creationinfos_go" style="color: inherit; text-decoration: inherit;">Creation<wbr>Infos</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccesspointrootdirectorycreationinfo">[]Get<wbr>Access<wbr>Point<wbr>Root<wbr>Directory<wbr>Creation<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Single element list containing information on the creation permissions of the directory
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="path_go">
<a href="#path_go" style="color: inherit; text-decoration: inherit;">Path</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Path exposed as the root directory
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="creationinfos_nodejs">
<a href="#creationinfos_nodejs" style="color: inherit; text-decoration: inherit;">creation<wbr>Infos</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccesspointrootdirectorycreationinfo">Get<wbr>Access<wbr>Point<wbr>Root<wbr>Directory<wbr>Creation<wbr>Info[]</a></span>
    </dt>
    <dd>{{% md %}}Single element list containing information on the creation permissions of the directory
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="path_nodejs">
<a href="#path_nodejs" style="color: inherit; text-decoration: inherit;">path</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Path exposed as the root directory
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="creation_infos_python">
<a href="#creation_infos_python" style="color: inherit; text-decoration: inherit;">creation_<wbr>infos</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#getaccesspointrootdirectorycreationinfo">Sequence[Get<wbr>Access<wbr>Point<wbr>Root<wbr>Directory<wbr>Creation<wbr>Info<wbr>Args]</a></span>
    </dt>
    <dd>{{% md %}}Single element list containing information on the creation permissions of the directory
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="path_python">
<a href="#path_python" style="color: inherit; text-decoration: inherit;">path</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Path exposed as the root directory
{{% /md %}}</dd></dl>
{{% /choosable %}}

<h4 id="getaccesspointrootdirectorycreationinfo">Get<wbr>Access<wbr>Point<wbr>Root<wbr>Directory<wbr>Creation<wbr>Info</h4>



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="ownergid_csharp">
<a href="#ownergid_csharp" style="color: inherit; text-decoration: inherit;">Owner<wbr>Gid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}POSIX owner group ID
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="owneruid_csharp">
<a href="#owneruid_csharp" style="color: inherit; text-decoration: inherit;">Owner<wbr>Uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}POSIX owner user ID
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="permissions_csharp">
<a href="#permissions_csharp" style="color: inherit; text-decoration: inherit;">Permissions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}POSIX permissions mode
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="ownergid_go">
<a href="#ownergid_go" style="color: inherit; text-decoration: inherit;">Owner<wbr>Gid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}POSIX owner group ID
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="owneruid_go">
<a href="#owneruid_go" style="color: inherit; text-decoration: inherit;">Owner<wbr>Uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}POSIX owner user ID
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="permissions_go">
<a href="#permissions_go" style="color: inherit; text-decoration: inherit;">Permissions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}POSIX permissions mode
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="ownergid_nodejs">
<a href="#ownergid_nodejs" style="color: inherit; text-decoration: inherit;">owner<wbr>Gid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}POSIX owner group ID
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="owneruid_nodejs">
<a href="#owneruid_nodejs" style="color: inherit; text-decoration: inherit;">owner<wbr>Uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}POSIX owner user ID
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="permissions_nodejs">
<a href="#permissions_nodejs" style="color: inherit; text-decoration: inherit;">permissions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}POSIX permissions mode
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="owner_gid_python">
<a href="#owner_gid_python" style="color: inherit; text-decoration: inherit;">owner_<wbr>gid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}POSIX owner group ID
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="owner_uid_python">
<a href="#owner_uid_python" style="color: inherit; text-decoration: inherit;">owner_<wbr>uid</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}POSIX owner user ID
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="permissions_python">
<a href="#permissions_python" style="color: inherit; text-decoration: inherit;">permissions</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}POSIX permissions mode
{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-aws">https://github.com/pulumi/pulumi-aws</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`aws` Terraform Provider](https://github.com/terraform-providers/terraform-provider-aws).{{% /md %}}</dd>
</dl>

