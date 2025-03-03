
---
title: "Execution"
title_tag: "keycloak.authentication.Execution"
meta_desc: "Documentation for the keycloak.authentication.Execution resource with examples, input properties, output properties, lookup functions, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Allows for creating and managing an authentication execution within Keycloak.

An authentication execution is an action that the user or service may or may not take when authenticating through an authentication
flow.

> Due to limitations in the Keycloak API, the ordering of authentication executions within a flow must be specified using `depends_on`. Authentication executions that are created first will appear first within the flow.

{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using Pulumi;
using Keycloak = Pulumi.Keycloak;

class MyStack : Stack
{
    public MyStack()
    {
        var realm = new Keycloak.Realm("realm", new Keycloak.RealmArgs
        {
            Realm = "my-realm",
            Enabled = true,
        });
        var flow = new Keycloak.Authentication.Flow("flow", new Keycloak.Authentication.FlowArgs
        {
            RealmId = realm.Id,
            Alias = "my-flow-alias",
        });
        // first execution
        var executionOne = new Keycloak.Authentication.Execution("executionOne", new Keycloak.Authentication.ExecutionArgs
        {
            RealmId = realm.Id,
            ParentFlowAlias = flow.Alias,
            Authenticator = "auth-cookie",
            Requirement = "ALTERNATIVE",
        });
        // second execution
        var executionTwo = new Keycloak.Authentication.Execution("executionTwo", new Keycloak.Authentication.ExecutionArgs
        {
            RealmId = realm.Id,
            ParentFlowAlias = flow.Alias,
            Authenticator = "identity-provider-redirector",
            Requirement = "ALTERNATIVE",
        }, new CustomResourceOptions
        {
            DependsOn = 
            {
                executionOne,
            },
        });
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-keycloak/sdk/v3/go/keycloak"
	"github.com/pulumi/pulumi-keycloak/sdk/v3/go/keycloak/authentication"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		realm, err := keycloak.NewRealm(ctx, "realm", &keycloak.RealmArgs{
			Realm:   pulumi.String("my-realm"),
			Enabled: pulumi.Bool(true),
		})
		if err != nil {
			return err
		}
		flow, err := authentication.NewFlow(ctx, "flow", &authentication.FlowArgs{
			RealmId: realm.ID(),
			Alias:   pulumi.String("my-flow-alias"),
		})
		if err != nil {
			return err
		}
		executionOne, err := authentication.NewExecution(ctx, "executionOne", &authentication.ExecutionArgs{
			RealmId:         realm.ID(),
			ParentFlowAlias: flow.Alias,
			Authenticator:   pulumi.String("auth-cookie"),
			Requirement:     pulumi.String("ALTERNATIVE"),
		})
		if err != nil {
			return err
		}
		_, err = authentication.NewExecution(ctx, "executionTwo", &authentication.ExecutionArgs{
			RealmId:         realm.ID(),
			ParentFlowAlias: flow.Alias,
			Authenticator:   pulumi.String("identity-provider-redirector"),
			Requirement:     pulumi.String("ALTERNATIVE"),
		}, pulumi.DependsOn([]pulumi.Resource{
			executionOne,
		}))
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
import pulumi_keycloak as keycloak

realm = keycloak.Realm("realm",
    realm="my-realm",
    enabled=True)
flow = keycloak.authentication.Flow("flow",
    realm_id=realm.id,
    alias="my-flow-alias")
# first execution
execution_one = keycloak.authentication.Execution("executionOne",
    realm_id=realm.id,
    parent_flow_alias=flow.alias,
    authenticator="auth-cookie",
    requirement="ALTERNATIVE")
# second execution
execution_two = keycloak.authentication.Execution("executionTwo",
    realm_id=realm.id,
    parent_flow_alias=flow.alias,
    authenticator="identity-provider-redirector",
    requirement="ALTERNATIVE",
    opts=pulumi.ResourceOptions(depends_on=[execution_one]))
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as keycloak from "@pulumi/keycloak";

const realm = new keycloak.Realm("realm", {
    realm: "my-realm",
    enabled: true,
});
const flow = new keycloak.authentication.Flow("flow", {
    realmId: realm.id,
    alias: "my-flow-alias",
});
// first execution
const executionOne = new keycloak.authentication.Execution("executionOne", {
    realmId: realm.id,
    parentFlowAlias: flow.alias,
    authenticator: "auth-cookie",
    requirement: "ALTERNATIVE",
});
// second execution
const executionTwo = new keycloak.authentication.Execution("executionTwo", {
    realmId: realm.id,
    parentFlowAlias: flow.alias,
    authenticator: "identity-provider-redirector",
    requirement: "ALTERNATIVE",
}, {
    dependsOn: [executionOne],
});
```


{{< /example >}}





{{% /examples %}}




## Create a Execution Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">Execution</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">ExecutionArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nx">Execution</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">authenticator</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">parent_flow_alias</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">realm_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">requirement</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewExecution</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p"> </span><span class="nx"><a href="#inputs">ExecutionArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">Execution</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">Execution</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="#inputs">ExecutionArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language nodejs %}}

<dl class="resources-properties"><dt
        class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>
      The unique name of the resource.
    </dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">ExecutionArgs</a></span>
    </dt>
    <dd>
      The arguments to resource properties.
    </dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span>
    </dt>
    <dd>
      Bag of options to control resource&#39;s behavior.
    </dd></dl>

{{% /choosable %}}

{{% choosable language python %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>resource_name</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type">
            <a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">ResourceOptions</a>
        </span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>
{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-properties"><dt
        class="property-optional" title="Optional">
        <span>ctx</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span>
    </dt>
    <dd>
      Context object for the current deployment.
    </dd><dt
        class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>
      The unique name of the resource.
    </dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">ExecutionArgs</a></span>
    </dt>
    <dd>
      The arguments to resource properties.
    </dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span>
    </dt>
    <dd>
      Bag of options to control resource&#39;s behavior.
    </dd></dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-properties"><dt
        class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>
      The unique name of the resource.
    </dd><dt
        class="property-required" title="Required">
        <span>args</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="#inputs">ExecutionArgs</a></span>
    </dt>
    <dd>
      The arguments to resource properties.
    </dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span>
    </dt>
    <dd>
      Bag of options to control resource&#39;s behavior.
    </dd></dl>

{{% /choosable %}}

## Execution Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Programming Model docs.

### Inputs

The Execution resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="authenticator_csharp">
<a href="#authenticator_csharp" style="color: inherit; text-decoration: inherit;">Authenticator</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the authenticator. This can be found by experimenting with the GUI and looking at HTTP requests within the network tab of your browser's development tools.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="parentflowalias_csharp">
<a href="#parentflowalias_csharp" style="color: inherit; text-decoration: inherit;">Parent<wbr>Flow<wbr>Alias</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The alias of the flow this execution is attached to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="realmid_csharp">
<a href="#realmid_csharp" style="color: inherit; text-decoration: inherit;">Realm<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The realm the authentication execution exists in.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="requirement_csharp">
<a href="#requirement_csharp" style="color: inherit; text-decoration: inherit;">Requirement</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The requirement setting, which can be one of `REQUIRED`, `ALTERNATIVE`, `OPTIONAL`, `CONDITIONAL`, or `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="authenticator_go">
<a href="#authenticator_go" style="color: inherit; text-decoration: inherit;">Authenticator</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the authenticator. This can be found by experimenting with the GUI and looking at HTTP requests within the network tab of your browser's development tools.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="parentflowalias_go">
<a href="#parentflowalias_go" style="color: inherit; text-decoration: inherit;">Parent<wbr>Flow<wbr>Alias</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The alias of the flow this execution is attached to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="realmid_go">
<a href="#realmid_go" style="color: inherit; text-decoration: inherit;">Realm<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The realm the authentication execution exists in.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="requirement_go">
<a href="#requirement_go" style="color: inherit; text-decoration: inherit;">Requirement</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The requirement setting, which can be one of `REQUIRED`, `ALTERNATIVE`, `OPTIONAL`, `CONDITIONAL`, or `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="authenticator_nodejs">
<a href="#authenticator_nodejs" style="color: inherit; text-decoration: inherit;">authenticator</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the authenticator. This can be found by experimenting with the GUI and looking at HTTP requests within the network tab of your browser's development tools.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="parentflowalias_nodejs">
<a href="#parentflowalias_nodejs" style="color: inherit; text-decoration: inherit;">parent<wbr>Flow<wbr>Alias</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The alias of the flow this execution is attached to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="realmid_nodejs">
<a href="#realmid_nodejs" style="color: inherit; text-decoration: inherit;">realm<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The realm the authentication execution exists in.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="requirement_nodejs">
<a href="#requirement_nodejs" style="color: inherit; text-decoration: inherit;">requirement</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The requirement setting, which can be one of `REQUIRED`, `ALTERNATIVE`, `OPTIONAL`, `CONDITIONAL`, or `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="authenticator_python">
<a href="#authenticator_python" style="color: inherit; text-decoration: inherit;">authenticator</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the authenticator. This can be found by experimenting with the GUI and looking at HTTP requests within the network tab of your browser's development tools.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="parent_flow_alias_python">
<a href="#parent_flow_alias_python" style="color: inherit; text-decoration: inherit;">parent_<wbr>flow_<wbr>alias</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The alias of the flow this execution is attached to.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="realm_id_python">
<a href="#realm_id_python" style="color: inherit; text-decoration: inherit;">realm_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The realm the authentication execution exists in.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="requirement_python">
<a href="#requirement_python" style="color: inherit; text-decoration: inherit;">requirement</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The requirement setting, which can be one of `REQUIRED`, `ALTERNATIVE`, `OPTIONAL`, `CONDITIONAL`, or `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the Execution resource produces the following output properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_go">
<a href="#id_go" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_nodejs">
<a href="#id_nodejs" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_python">
<a href="#id_python" style="color: inherit; text-decoration: inherit;">id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd></dl>
{{% /choosable %}}



## Look up an Existing Execution Resource {#look-up}

Get an existing Execution resource's state with the given name, ID, and optional extra properties used to qualify the lookup.
{{< chooser language "typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span><span class="p">?:</span> <span class="nx">ExecutionState</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx">Execution</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@staticmethod</span>
<span class="k">def </span><span class="nf">get</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">authenticator</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">parent_flow_alias</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">realm_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">requirement</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">) -&gt;</span> Execution</code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetExecution<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p"> </span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span><span class="p"> *</span><span class="nx">ExecutionState</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">Execution</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx">Execution</span><span class="nf"> Get</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input-1.html">Input&lt;string&gt;</a></span><span class="p"> </span><span class="nx">id<span class="p">, </span><span class="nx">ExecutionState</span><span class="p">? </span><span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language nodejs %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>resource_name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Optional">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
</dl>
{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-properties">
    <dt class="property-required" title="Required">
        <span>name</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resulting resource.</dd>
    <dt class="property-required" title="Required">
        <span>id</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>The <em>unique</em> provider ID of the resource to lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>state</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>Any extra arguments used during the lookup.</dd>
    <dt class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

The following state arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_authenticator_csharp">
<a href="#state_authenticator_csharp" style="color: inherit; text-decoration: inherit;">Authenticator</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the authenticator. This can be found by experimenting with the GUI and looking at HTTP requests within the network tab of your browser's development tools.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_parentflowalias_csharp">
<a href="#state_parentflowalias_csharp" style="color: inherit; text-decoration: inherit;">Parent<wbr>Flow<wbr>Alias</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The alias of the flow this execution is attached to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_realmid_csharp">
<a href="#state_realmid_csharp" style="color: inherit; text-decoration: inherit;">Realm<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The realm the authentication execution exists in.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_requirement_csharp">
<a href="#state_requirement_csharp" style="color: inherit; text-decoration: inherit;">Requirement</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The requirement setting, which can be one of `REQUIRED`, `ALTERNATIVE`, `OPTIONAL`, `CONDITIONAL`, or `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_authenticator_go">
<a href="#state_authenticator_go" style="color: inherit; text-decoration: inherit;">Authenticator</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the authenticator. This can be found by experimenting with the GUI and looking at HTTP requests within the network tab of your browser's development tools.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_parentflowalias_go">
<a href="#state_parentflowalias_go" style="color: inherit; text-decoration: inherit;">Parent<wbr>Flow<wbr>Alias</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The alias of the flow this execution is attached to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_realmid_go">
<a href="#state_realmid_go" style="color: inherit; text-decoration: inherit;">Realm<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The realm the authentication execution exists in.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_requirement_go">
<a href="#state_requirement_go" style="color: inherit; text-decoration: inherit;">Requirement</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The requirement setting, which can be one of `REQUIRED`, `ALTERNATIVE`, `OPTIONAL`, `CONDITIONAL`, or `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_authenticator_nodejs">
<a href="#state_authenticator_nodejs" style="color: inherit; text-decoration: inherit;">authenticator</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the authenticator. This can be found by experimenting with the GUI and looking at HTTP requests within the network tab of your browser's development tools.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_parentflowalias_nodejs">
<a href="#state_parentflowalias_nodejs" style="color: inherit; text-decoration: inherit;">parent<wbr>Flow<wbr>Alias</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The alias of the flow this execution is attached to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_realmid_nodejs">
<a href="#state_realmid_nodejs" style="color: inherit; text-decoration: inherit;">realm<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The realm the authentication execution exists in.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_requirement_nodejs">
<a href="#state_requirement_nodejs" style="color: inherit; text-decoration: inherit;">requirement</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The requirement setting, which can be one of `REQUIRED`, `ALTERNATIVE`, `OPTIONAL`, `CONDITIONAL`, or `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_authenticator_python">
<a href="#state_authenticator_python" style="color: inherit; text-decoration: inherit;">authenticator</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the authenticator. This can be found by experimenting with the GUI and looking at HTTP requests within the network tab of your browser's development tools.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_parent_flow_alias_python">
<a href="#state_parent_flow_alias_python" style="color: inherit; text-decoration: inherit;">parent_<wbr>flow_<wbr>alias</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The alias of the flow this execution is attached to.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_realm_id_python">
<a href="#state_realm_id_python" style="color: inherit; text-decoration: inherit;">realm_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The realm the authentication execution exists in.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_requirement_python">
<a href="#state_requirement_python" style="color: inherit; text-decoration: inherit;">requirement</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The requirement setting, which can be one of `REQUIRED`, `ALTERNATIVE`, `OPTIONAL`, `CONDITIONAL`, or `DISABLED`. Defaults to `DISABLED`.
{{% /md %}}</dd></dl>
{{% /choosable %}}





## Import


Authentication executions can be imported using the formats`{{realmId}}/{{parentFlowAlias}}/{{authenticationExecutionId}}`. Examplebash

```sh
 $ pulumi import keycloak:authentication/execution:Execution keycloak_authentication_execution my-realm/my-flow/30559fcf-6fb8-45ea-8c46-2b86f46ebc17
```




<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-keycloak">https://github.com/pulumi/pulumi-keycloak</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`keycloak` Terraform Provider](https://github.com/mrparkers/terraform-provider-keycloak).{{% /md %}}</dd>
</dl>

