
---
title: "MigrationConfig"
title_tag: "azure-native.servicebus.MigrationConfig"
meta_desc: "Documentation for the azure-native.servicebus.MigrationConfig resource with examples, input properties, output properties, lookup functions, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Single item in List or Get Migration Config operation
API Version: 2017-04-01.

{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}


### MigrationConfigurationsStartMigration


{{< example csharp >}}

```csharp
using Pulumi;
using AzureNative = Pulumi.AzureNative;

class MyStack : Stack
{
    public MyStack()
    {
        var migrationConfig = new AzureNative.ServiceBus.MigrationConfig("migrationConfig", new AzureNative.ServiceBus.MigrationConfigArgs
        {
            ConfigName = "$default",
            NamespaceName = "sdk-Namespace-41",
            PostMigrationName = "sdk-PostMigration-5919",
            ResourceGroupName = "ResourceGroup",
            TargetNamespace = "/subscriptions/SubscriptionId/resourceGroups/ResourceGroup/providers/Microsoft.ServiceBus/namespaces/sdk-Namespace-4028",
        });
    }

}

```


{{< /example >}}


{{< example go >}}


```go
package main

import (
	"fmt"

	servicebus "github.com/pulumi/pulumi-azure-native/sdk/go/azure/servicebus"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		_, err := servicebus.NewMigrationConfig(ctx, "migrationConfig", &servicebus.MigrationConfigArgs{
			ConfigName:        pulumi.String(fmt.Sprintf("%v%v", "$", "default")),
			NamespaceName:     pulumi.String("sdk-Namespace-41"),
			PostMigrationName: pulumi.String("sdk-PostMigration-5919"),
			ResourceGroupName: pulumi.String("ResourceGroup"),
			TargetNamespace:   pulumi.String("/subscriptions/SubscriptionId/resourceGroups/ResourceGroup/providers/Microsoft.ServiceBus/namespaces/sdk-Namespace-4028"),
		})
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
import pulumi_azure_native as azure_native

migration_config = azure_native.servicebus.MigrationConfig("migrationConfig",
    config_name="$default",
    namespace_name="sdk-Namespace-41",
    post_migration_name="sdk-PostMigration-5919",
    resource_group_name="ResourceGroup",
    target_namespace="/subscriptions/SubscriptionId/resourceGroups/ResourceGroup/providers/Microsoft.ServiceBus/namespaces/sdk-Namespace-4028")

```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as azure_native from "@pulumi/azure-native";

const migrationConfig = new azure_native.servicebus.MigrationConfig("migrationConfig", {
    configName: `$default`,
    namespaceName: "sdk-Namespace-41",
    postMigrationName: "sdk-PostMigration-5919",
    resourceGroupName: "ResourceGroup",
    targetNamespace: "/subscriptions/SubscriptionId/resourceGroups/ResourceGroup/providers/Microsoft.ServiceBus/namespaces/sdk-Namespace-4028",
});

```


{{< /example >}}





{{% /examples %}}




## Create a MigrationConfig Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">MigrationConfig</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">MigrationConfigArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nx">MigrationConfig</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">config_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">namespace_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">post_migration_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">resource_group_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">target_namespace</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewMigrationConfig</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p"> </span><span class="nx"><a href="#inputs">MigrationConfigArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">MigrationConfig</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">MigrationConfig</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="#inputs">MigrationConfigArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span class="property-type"><a href="#inputs">MigrationConfigArgs</a></span>
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
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">Context</a></span>
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
        <span class="property-type"><a href="#inputs">MigrationConfigArgs</a></span>
    </dt>
    <dd>
      The arguments to resource properties.
    </dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span>
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
        <span class="property-type"><a href="#inputs">MigrationConfigArgs</a></span>
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

## MigrationConfig Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Programming Model docs.

### Inputs

The MigrationConfig resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="namespacename_csharp">
<a href="#namespacename_csharp" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The namespace name{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="postmigrationname_csharp">
<a href="#postmigrationname_csharp" style="color: inherit; text-decoration: inherit;">Post<wbr>Migration<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name to access Standard Namespace after migration{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_csharp">
<a href="#resourcegroupname_csharp" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Resource group within the Azure subscription.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="targetnamespace_csharp">
<a href="#targetnamespace_csharp" style="color: inherit; text-decoration: inherit;">Target<wbr>Namespace</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Existing premium Namespace ARM Id name which has no entities, will be used for migration{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="configname_csharp">
<a href="#configname_csharp" style="color: inherit; text-decoration: inherit;">Config<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The configuration name. Should always be "$default".{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="namespacename_go">
<a href="#namespacename_go" style="color: inherit; text-decoration: inherit;">Namespace<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The namespace name{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="postmigrationname_go">
<a href="#postmigrationname_go" style="color: inherit; text-decoration: inherit;">Post<wbr>Migration<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name to access Standard Namespace after migration{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_go">
<a href="#resourcegroupname_go" style="color: inherit; text-decoration: inherit;">Resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Resource group within the Azure subscription.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="targetnamespace_go">
<a href="#targetnamespace_go" style="color: inherit; text-decoration: inherit;">Target<wbr>Namespace</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Existing premium Namespace ARM Id name which has no entities, will be used for migration{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="configname_go">
<a href="#configname_go" style="color: inherit; text-decoration: inherit;">Config<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The configuration name. Should always be "$default".{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="namespacename_nodejs">
<a href="#namespacename_nodejs" style="color: inherit; text-decoration: inherit;">namespace<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The namespace name{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="postmigrationname_nodejs">
<a href="#postmigrationname_nodejs" style="color: inherit; text-decoration: inherit;">post<wbr>Migration<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name to access Standard Namespace after migration{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resourcegroupname_nodejs">
<a href="#resourcegroupname_nodejs" style="color: inherit; text-decoration: inherit;">resource<wbr>Group<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the Resource group within the Azure subscription.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="targetnamespace_nodejs">
<a href="#targetnamespace_nodejs" style="color: inherit; text-decoration: inherit;">target<wbr>Namespace</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Existing premium Namespace ARM Id name which has no entities, will be used for migration{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="configname_nodejs">
<a href="#configname_nodejs" style="color: inherit; text-decoration: inherit;">config<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The configuration name. Should always be "$default".{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="namespace_name_python">
<a href="#namespace_name_python" style="color: inherit; text-decoration: inherit;">namespace_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The namespace name{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="post_migration_name_python">
<a href="#post_migration_name_python" style="color: inherit; text-decoration: inherit;">post_<wbr>migration_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name to access Standard Namespace after migration{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="resource_group_name_python">
<a href="#resource_group_name_python" style="color: inherit; text-decoration: inherit;">resource_<wbr>group_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the Resource group within the Azure subscription.{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="target_namespace_python">
<a href="#target_namespace_python" style="color: inherit; text-decoration: inherit;">target_<wbr>namespace</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Existing premium Namespace ARM Id name which has no entities, will be used for migration{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="config_name_python">
<a href="#config_name_python" style="color: inherit; text-decoration: inherit;">config_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The configuration name. Should always be "$default".{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the MigrationConfig resource produces the following output properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="id_csharp">
<a href="#id_csharp" style="color: inherit; text-decoration: inherit;">Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="migrationstate_csharp">
<a href="#migrationstate_csharp" style="color: inherit; text-decoration: inherit;">Migration<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}State in which Standard to Premium Migration is, possible values : Unknown, Reverting, Completing, Initiating, Syncing, Active{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_csharp">
<a href="#name_csharp" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource name{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="pendingreplicationoperationscount_csharp">
<a href="#pendingreplicationoperationscount_csharp" style="color: inherit; text-decoration: inherit;">Pending<wbr>Replication<wbr>Operations<wbr>Count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">double</span>
    </dt>
    <dd>{{% md %}}Number of entities pending to be replicated.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="provisioningstate_csharp">
<a href="#provisioningstate_csharp" style="color: inherit; text-decoration: inherit;">Provisioning<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Provisioning state of Migration Configuration {{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_csharp">
<a href="#type_csharp" style="color: inherit; text-decoration: inherit;">Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource type{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="migrationstate_go">
<a href="#migrationstate_go" style="color: inherit; text-decoration: inherit;">Migration<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}State in which Standard to Premium Migration is, possible values : Unknown, Reverting, Completing, Initiating, Syncing, Active{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_go">
<a href="#name_go" style="color: inherit; text-decoration: inherit;">Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource name{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="pendingreplicationoperationscount_go">
<a href="#pendingreplicationoperationscount_go" style="color: inherit; text-decoration: inherit;">Pending<wbr>Replication<wbr>Operations<wbr>Count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">float64</span>
    </dt>
    <dd>{{% md %}}Number of entities pending to be replicated.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="provisioningstate_go">
<a href="#provisioningstate_go" style="color: inherit; text-decoration: inherit;">Provisioning<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Provisioning state of Migration Configuration {{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_go">
<a href="#type_go" style="color: inherit; text-decoration: inherit;">Type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource type{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="migrationstate_nodejs">
<a href="#migrationstate_nodejs" style="color: inherit; text-decoration: inherit;">migration<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}State in which Standard to Premium Migration is, possible values : Unknown, Reverting, Completing, Initiating, Syncing, Active{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_nodejs">
<a href="#name_nodejs" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource name{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="pendingreplicationoperationscount_nodejs">
<a href="#pendingreplicationoperationscount_nodejs" style="color: inherit; text-decoration: inherit;">pending<wbr>Replication<wbr>Operations<wbr>Count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Number of entities pending to be replicated.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="provisioningstate_nodejs">
<a href="#provisioningstate_nodejs" style="color: inherit; text-decoration: inherit;">provisioning<wbr>State</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Provisioning state of Migration Configuration {{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_nodejs">
<a href="#type_nodejs" style="color: inherit; text-decoration: inherit;">type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Resource type{{% /md %}}</dd></dl>
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
    <dd>{{% md %}}The provider-assigned unique ID for this managed resource.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="migration_state_python">
<a href="#migration_state_python" style="color: inherit; text-decoration: inherit;">migration_<wbr>state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}State in which Standard to Premium Migration is, possible values : Unknown, Reverting, Completing, Initiating, Syncing, Active{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="name_python">
<a href="#name_python" style="color: inherit; text-decoration: inherit;">name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Resource name{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="pending_replication_operations_count_python">
<a href="#pending_replication_operations_count_python" style="color: inherit; text-decoration: inherit;">pending_<wbr>replication_<wbr>operations_<wbr>count</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Number of entities pending to be replicated.{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="provisioning_state_python">
<a href="#provisioning_state_python" style="color: inherit; text-decoration: inherit;">provisioning_<wbr>state</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Provisioning state of Migration Configuration {{% /md %}}</dd><dt class="property-"
            title="">
        <span id="type_python">
<a href="#type_python" style="color: inherit; text-decoration: inherit;">type</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Resource type{{% /md %}}</dd></dl>
{{% /choosable %}}






## Import


An existing resource can be imported using its type token, name, and identifier, e.g.

```sh
$ pulumi import azure-native:servicebus:MigrationConfig sdk-Namespace-41 /subscriptions/SubscriptionId/resourceGroups/ResourceGroup/providers/Microsoft.ServiceBus/namespaces/sdk-Namespace-41/migrationConfigs/$default 
```




<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-azure-native">https://github.com/pulumi/pulumi-azure-native</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
</dl>

