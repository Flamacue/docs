
---
title: "getConnectionPool"
title_tag: "aiven.getConnectionPool"
meta_desc: "Documentation for the aiven.getConnectionPool function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

## # Connection Pool Data Source

The Connection Pool data source provides information about the existing Aiven Connection Pool.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using Aiven = Pulumi.Aiven;

class MyStack : Stack
{
    public MyStack()
    {
        var mytestpool = Output.Create(Aiven.GetConnectionPool.InvokeAsync(new Aiven.GetConnectionPoolArgs
        {
            PoolName = "mypool",
            Project = aiven_project.Myproject.Project,
            ServiceName = aiven_service.Myservice.Service_name,
        }));
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-aiven/sdk/v3/go/aiven"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := aiven.LookupConnectionPool(ctx, &aiven.LookupConnectionPoolArgs{
			PoolName:    "mypool",
			Project:     aiven_project.Myproject.Project,
			ServiceName: aiven_service.Myservice.Service_name,
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
import pulumi_aiven as aiven

mytestpool = aiven.get_connection_pool(pool_name="mypool",
    project=aiven_project["myproject"]["project"],
    service_name=aiven_service["myservice"]["service_name"])
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aiven from "@pulumi/aiven";

const mytestpool = pulumi.all([aiven_project_myproject.project, aiven_service_myservice.serviceName]).apply(([project, serviceName]) => aiven.getConnectionPool({
    poolName: "mypool",
    project: project,
    serviceName: serviceName,
}, { async: true }));
```


{{< /example >}}





{{% /examples %}}




## Using getConnectionPool {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getConnectionPool<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetConnectionPoolArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetConnectionPoolResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_connection_pool(</span><span class="nx">connection_uri</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">database_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">pool_mode</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">pool_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">pool_size</span><span class="p">:</span> <span class="nx">Optional[int]</span> = None<span class="p">, </span><span class="nx">project</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">service_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">username</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetConnectionPoolResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupConnectionPool<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">LookupConnectionPoolArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">LookupConnectionPoolResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `LookupConnectionPool` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetConnectionPool </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetConnectionPoolResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetConnectionPoolArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="poolname_csharp">
<a href="#poolname_csharp" style="color: inherit; text-decoration: inherit;">Pool<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the name of the pool.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="project_csharp">
<a href="#project_csharp" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}and `service_name` - (Required) define the project and service the connection pool
belongs to. They should be defined using reference as shown above to set up dependencies
correctly. These properties cannot be changed once the service is created. Doing so will
result in the connection pool being deleted and new one created instead.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="servicename_csharp">
<a href="#servicename_csharp" style="color: inherit; text-decoration: inherit;">Service<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="connectionuri_csharp">
<a href="#connectionuri_csharp" style="color: inherit; text-decoration: inherit;">Connection<wbr>Uri</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is a computed property that tells the URI for connecting to the pool.
This value cannot be set, only read.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="databasename_csharp">
<a href="#databasename_csharp" style="color: inherit; text-decoration: inherit;">Database<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the name of the database the pool connects to. This should be
defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="poolmode_csharp">
<a href="#poolmode_csharp" style="color: inherit; text-decoration: inherit;">Pool<wbr>Mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the mode the pool operates in (session, transaction, statement).
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="poolsize_csharp">
<a href="#poolsize_csharp" style="color: inherit; text-decoration: inherit;">Pool<wbr>Size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}is the number of connections the pool may create towards the backend
server. This does not affect the number of incoming connections, which is always a much
larger number.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="username_csharp">
<a href="#username_csharp" style="color: inherit; text-decoration: inherit;">Username</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the name of the service user used to connect to the database. This should
be defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="poolname_go">
<a href="#poolname_go" style="color: inherit; text-decoration: inherit;">Pool<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the name of the pool.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="project_go">
<a href="#project_go" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}and `service_name` - (Required) define the project and service the connection pool
belongs to. They should be defined using reference as shown above to set up dependencies
correctly. These properties cannot be changed once the service is created. Doing so will
result in the connection pool being deleted and new one created instead.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="servicename_go">
<a href="#servicename_go" style="color: inherit; text-decoration: inherit;">Service<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="connectionuri_go">
<a href="#connectionuri_go" style="color: inherit; text-decoration: inherit;">Connection<wbr>Uri</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is a computed property that tells the URI for connecting to the pool.
This value cannot be set, only read.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="databasename_go">
<a href="#databasename_go" style="color: inherit; text-decoration: inherit;">Database<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the name of the database the pool connects to. This should be
defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="poolmode_go">
<a href="#poolmode_go" style="color: inherit; text-decoration: inherit;">Pool<wbr>Mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the mode the pool operates in (session, transaction, statement).
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="poolsize_go">
<a href="#poolsize_go" style="color: inherit; text-decoration: inherit;">Pool<wbr>Size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}is the number of connections the pool may create towards the backend
server. This does not affect the number of incoming connections, which is always a much
larger number.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="username_go">
<a href="#username_go" style="color: inherit; text-decoration: inherit;">Username</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the name of the service user used to connect to the database. This should
be defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="poolname_nodejs">
<a href="#poolname_nodejs" style="color: inherit; text-decoration: inherit;">pool<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the name of the pool.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="project_nodejs">
<a href="#project_nodejs" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}and `service_name` - (Required) define the project and service the connection pool
belongs to. They should be defined using reference as shown above to set up dependencies
correctly. These properties cannot be changed once the service is created. Doing so will
result in the connection pool being deleted and new one created instead.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="servicename_nodejs">
<a href="#servicename_nodejs" style="color: inherit; text-decoration: inherit;">service<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="connectionuri_nodejs">
<a href="#connectionuri_nodejs" style="color: inherit; text-decoration: inherit;">connection<wbr>Uri</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is a computed property that tells the URI for connecting to the pool.
This value cannot be set, only read.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="databasename_nodejs">
<a href="#databasename_nodejs" style="color: inherit; text-decoration: inherit;">database<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the name of the database the pool connects to. This should be
defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="poolmode_nodejs">
<a href="#poolmode_nodejs" style="color: inherit; text-decoration: inherit;">pool<wbr>Mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the mode the pool operates in (session, transaction, statement).
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="poolsize_nodejs">
<a href="#poolsize_nodejs" style="color: inherit; text-decoration: inherit;">pool<wbr>Size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}is the number of connections the pool may create towards the backend
server. This does not affect the number of incoming connections, which is always a much
larger number.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="username_nodejs">
<a href="#username_nodejs" style="color: inherit; text-decoration: inherit;">username</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the name of the service user used to connect to the database. This should
be defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="pool_name_python">
<a href="#pool_name_python" style="color: inherit; text-decoration: inherit;">pool_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}is the name of the pool.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="project_python">
<a href="#project_python" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}and `service_name` - (Required) define the project and service the connection pool
belongs to. They should be defined using reference as shown above to set up dependencies
correctly. These properties cannot be changed once the service is created. Doing so will
result in the connection pool being deleted and new one created instead.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="service_name_python">
<a href="#service_name_python" style="color: inherit; text-decoration: inherit;">service_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="connection_uri_python">
<a href="#connection_uri_python" style="color: inherit; text-decoration: inherit;">connection_<wbr>uri</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}is a computed property that tells the URI for connecting to the pool.
This value cannot be set, only read.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="database_name_python">
<a href="#database_name_python" style="color: inherit; text-decoration: inherit;">database_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}is the name of the database the pool connects to. This should be
defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="pool_mode_python">
<a href="#pool_mode_python" style="color: inherit; text-decoration: inherit;">pool_<wbr>mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}is the mode the pool operates in (session, transaction, statement).
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="pool_size_python">
<a href="#pool_size_python" style="color: inherit; text-decoration: inherit;">pool_<wbr>size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}is the number of connections the pool may create towards the backend
server. This does not affect the number of incoming connections, which is always a much
larger number.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="username_python">
<a href="#username_python" style="color: inherit; text-decoration: inherit;">username</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}is the name of the service user used to connect to the database. This should
be defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getConnectionPool Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="connectionuri_csharp">
<a href="#connectionuri_csharp" style="color: inherit; text-decoration: inherit;">Connection<wbr>Uri</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is a computed property that tells the URI for connecting to the pool.
This value cannot be set, only read.
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
        <span id="poolname_csharp">
<a href="#poolname_csharp" style="color: inherit; text-decoration: inherit;">Pool<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="project_csharp">
<a href="#project_csharp" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="servicename_csharp">
<a href="#servicename_csharp" style="color: inherit; text-decoration: inherit;">Service<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="databasename_csharp">
<a href="#databasename_csharp" style="color: inherit; text-decoration: inherit;">Database<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the name of the database the pool connects to. This should be
defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="poolmode_csharp">
<a href="#poolmode_csharp" style="color: inherit; text-decoration: inherit;">Pool<wbr>Mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the mode the pool operates in (session, transaction, statement).
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="poolsize_csharp">
<a href="#poolsize_csharp" style="color: inherit; text-decoration: inherit;">Pool<wbr>Size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}is the number of connections the pool may create towards the backend
server. This does not affect the number of incoming connections, which is always a much
larger number.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="username_csharp">
<a href="#username_csharp" style="color: inherit; text-decoration: inherit;">Username</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the name of the service user used to connect to the database. This should
be defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="connectionuri_go">
<a href="#connectionuri_go" style="color: inherit; text-decoration: inherit;">Connection<wbr>Uri</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is a computed property that tells the URI for connecting to the pool.
This value cannot be set, only read.
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
        <span id="poolname_go">
<a href="#poolname_go" style="color: inherit; text-decoration: inherit;">Pool<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="project_go">
<a href="#project_go" style="color: inherit; text-decoration: inherit;">Project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="servicename_go">
<a href="#servicename_go" style="color: inherit; text-decoration: inherit;">Service<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="databasename_go">
<a href="#databasename_go" style="color: inherit; text-decoration: inherit;">Database<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the name of the database the pool connects to. This should be
defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="poolmode_go">
<a href="#poolmode_go" style="color: inherit; text-decoration: inherit;">Pool<wbr>Mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the mode the pool operates in (session, transaction, statement).
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="poolsize_go">
<a href="#poolsize_go" style="color: inherit; text-decoration: inherit;">Pool<wbr>Size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}is the number of connections the pool may create towards the backend
server. This does not affect the number of incoming connections, which is always a much
larger number.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="username_go">
<a href="#username_go" style="color: inherit; text-decoration: inherit;">Username</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the name of the service user used to connect to the database. This should
be defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="connectionuri_nodejs">
<a href="#connectionuri_nodejs" style="color: inherit; text-decoration: inherit;">connection<wbr>Uri</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is a computed property that tells the URI for connecting to the pool.
This value cannot be set, only read.
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
        <span id="poolname_nodejs">
<a href="#poolname_nodejs" style="color: inherit; text-decoration: inherit;">pool<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="project_nodejs">
<a href="#project_nodejs" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="servicename_nodejs">
<a href="#servicename_nodejs" style="color: inherit; text-decoration: inherit;">service<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="databasename_nodejs">
<a href="#databasename_nodejs" style="color: inherit; text-decoration: inherit;">database<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the name of the database the pool connects to. This should be
defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="poolmode_nodejs">
<a href="#poolmode_nodejs" style="color: inherit; text-decoration: inherit;">pool<wbr>Mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the mode the pool operates in (session, transaction, statement).
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="poolsize_nodejs">
<a href="#poolsize_nodejs" style="color: inherit; text-decoration: inherit;">pool<wbr>Size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}is the number of connections the pool may create towards the backend
server. This does not affect the number of incoming connections, which is always a much
larger number.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="username_nodejs">
<a href="#username_nodejs" style="color: inherit; text-decoration: inherit;">username</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}is the name of the service user used to connect to the database. This should
be defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="connection_uri_python">
<a href="#connection_uri_python" style="color: inherit; text-decoration: inherit;">connection_<wbr>uri</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}is a computed property that tells the URI for connecting to the pool.
This value cannot be set, only read.
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
        <span id="pool_name_python">
<a href="#pool_name_python" style="color: inherit; text-decoration: inherit;">pool_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="project_python">
<a href="#project_python" style="color: inherit; text-decoration: inherit;">project</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="service_name_python">
<a href="#service_name_python" style="color: inherit; text-decoration: inherit;">service_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="database_name_python">
<a href="#database_name_python" style="color: inherit; text-decoration: inherit;">database_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}is the name of the database the pool connects to. This should be
defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="pool_mode_python">
<a href="#pool_mode_python" style="color: inherit; text-decoration: inherit;">pool_<wbr>mode</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}is the mode the pool operates in (session, transaction, statement).
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="pool_size_python">
<a href="#pool_size_python" style="color: inherit; text-decoration: inherit;">pool_<wbr>size</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}is the number of connections the pool may create towards the backend
server. This does not affect the number of incoming connections, which is always a much
larger number.
{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="username_python">
<a href="#username_python" style="color: inherit; text-decoration: inherit;">username</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}is the name of the service user used to connect to the database. This should
be defined using reference as shown above to set up dependencies correctly.
{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-aiven">https://github.com/pulumi/pulumi-aiven</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`aiven` Terraform Provider](https://github.com/aiven/terraform-provider-aiven).{{% /md %}}</dd>
</dl>

