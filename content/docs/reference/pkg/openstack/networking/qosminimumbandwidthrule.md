
---
title: "QosMinimumBandwidthRule"
title_tag: "openstack.networking.QosMinimumBandwidthRule"
meta_desc: "Documentation for the openstack.networking.QosMinimumBandwidthRule resource with examples, input properties, output properties, lookup functions, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Manages a V2 Neutron QoS minimum bandwidth rule resource within OpenStack.

{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}


### Create a QoS Policy with some minimum bandwidth rule


{{< example csharp >}}

```csharp
using Pulumi;
using OpenStack = Pulumi.OpenStack;

class MyStack : Stack
{
    public MyStack()
    {
        var qosPolicy1 = new OpenStack.Networking.QosPolicy("qosPolicy1", new OpenStack.Networking.QosPolicyArgs
        {
            Description = "min_kbps",
        });
        var minimumBandwidthRule1 = new OpenStack.Networking.QosMinimumBandwidthRule("minimumBandwidthRule1", new OpenStack.Networking.QosMinimumBandwidthRuleArgs
        {
            MinKbps = 200,
            QosPolicyId = qosPolicy1.Id,
        });
    }

}
```


{{< /example >}}


{{< example go >}}

```go
package main

import (
	"github.com/pulumi/pulumi-openstack/sdk/v2/go/openstack/networking"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		qosPolicy1, err := networking.NewQosPolicy(ctx, "qosPolicy1", &networking.QosPolicyArgs{
			Description: pulumi.String("min_kbps"),
		})
		if err != nil {
			return err
		}
		_, err = networking.NewQosMinimumBandwidthRule(ctx, "minimumBandwidthRule1", &networking.QosMinimumBandwidthRuleArgs{
			MinKbps:     pulumi.Int(200),
			QosPolicyId: qosPolicy1.ID(),
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
import pulumi_openstack as openstack

qos_policy1 = openstack.networking.QosPolicy("qosPolicy1", description="min_kbps")
minimum_bandwidth_rule1 = openstack.networking.QosMinimumBandwidthRule("minimumBandwidthRule1",
    min_kbps=200,
    qos_policy_id=qos_policy1.id)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as openstack from "@pulumi/openstack";

const qosPolicy1 = new openstack.networking.QosPolicy("qos_policy_1", {
    description: "min_kbps",
});
const minimumBandwidthRule1 = new openstack.networking.QosMinimumBandwidthRule("minimum_bandwidth_rule_1", {
    minKbps: 200,
    qosPolicyId: qosPolicy1.id,
});
```


{{< /example >}}





{{% /examples %}}




## Create a QosMinimumBandwidthRule Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">QosMinimumBandwidthRule</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">QosMinimumBandwidthRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nx">QosMinimumBandwidthRule</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">direction</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">min_kbps</span><span class="p">:</span> <span class="nx">Optional[int]</span> = None<span class="p">, </span><span class="nx">qos_policy_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">region</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewQosMinimumBandwidthRule</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p"> </span><span class="nx"><a href="#inputs">QosMinimumBandwidthRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">QosMinimumBandwidthRule</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">QosMinimumBandwidthRule</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="#inputs">QosMinimumBandwidthRuleArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span class="property-type"><a href="#inputs">QosMinimumBandwidthRuleArgs</a></span>
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
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span>
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
        <span class="property-type"><a href="#inputs">QosMinimumBandwidthRuleArgs</a></span>
    </dt>
    <dd>
      The arguments to resource properties.
    </dd><dt
        class="property-optional" title="Optional">
        <span>opts</span>
        <span class="property-indicator"></span>
        <span class="property-type"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span>
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
        <span class="property-type"><a href="#inputs">QosMinimumBandwidthRuleArgs</a></span>
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

## QosMinimumBandwidthRule Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Programming Model docs.

### Inputs

The QosMinimumBandwidthRule resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="minkbps_csharp">
<a href="#minkbps_csharp" style="color: inherit; text-decoration: inherit;">Min<wbr>Kbps</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The minimum kilobits per second. Changing this updates the min kbps value of the existing
QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="qospolicyid_csharp">
<a href="#qospolicyid_csharp" style="color: inherit; text-decoration: inherit;">Qos<wbr>Policy<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The QoS policy reference. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="direction_csharp">
<a href="#direction_csharp" style="color: inherit; text-decoration: inherit;">Direction</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The direction of traffic. Defaults to "egress". Changing this updates the direction of the
existing QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="region_csharp">
<a href="#region_csharp" style="color: inherit; text-decoration: inherit;">Region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region in which to obtain the V2 Networking client.
A Networking client is needed to create a Neutron QoS minimum bandwidth rule. If omitted, the
`region` argument of the provider is used. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="minkbps_go">
<a href="#minkbps_go" style="color: inherit; text-decoration: inherit;">Min<wbr>Kbps</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The minimum kilobits per second. Changing this updates the min kbps value of the existing
QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="qospolicyid_go">
<a href="#qospolicyid_go" style="color: inherit; text-decoration: inherit;">Qos<wbr>Policy<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The QoS policy reference. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="direction_go">
<a href="#direction_go" style="color: inherit; text-decoration: inherit;">Direction</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The direction of traffic. Defaults to "egress". Changing this updates the direction of the
existing QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="region_go">
<a href="#region_go" style="color: inherit; text-decoration: inherit;">Region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region in which to obtain the V2 Networking client.
A Networking client is needed to create a Neutron QoS minimum bandwidth rule. If omitted, the
`region` argument of the provider is used. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="minkbps_nodejs">
<a href="#minkbps_nodejs" style="color: inherit; text-decoration: inherit;">min<wbr>Kbps</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The minimum kilobits per second. Changing this updates the min kbps value of the existing
QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="qospolicyid_nodejs">
<a href="#qospolicyid_nodejs" style="color: inherit; text-decoration: inherit;">qos<wbr>Policy<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The QoS policy reference. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="direction_nodejs">
<a href="#direction_nodejs" style="color: inherit; text-decoration: inherit;">direction</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The direction of traffic. Defaults to "egress". Changing this updates the direction of the
existing QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="region_nodejs">
<a href="#region_nodejs" style="color: inherit; text-decoration: inherit;">region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region in which to obtain the V2 Networking client.
A Networking client is needed to create a Neutron QoS minimum bandwidth rule. If omitted, the
`region` argument of the provider is used. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="min_kbps_python">
<a href="#min_kbps_python" style="color: inherit; text-decoration: inherit;">min_<wbr>kbps</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The minimum kilobits per second. Changing this updates the min kbps value of the existing
QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="qos_policy_id_python">
<a href="#qos_policy_id_python" style="color: inherit; text-decoration: inherit;">qos_<wbr>policy_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The QoS policy reference. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="direction_python">
<a href="#direction_python" style="color: inherit; text-decoration: inherit;">direction</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The direction of traffic. Defaults to "egress". Changing this updates the direction of the
existing QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="region_python">
<a href="#region_python" style="color: inherit; text-decoration: inherit;">region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The region in which to obtain the V2 Networking client.
A Networking client is needed to create a Neutron QoS minimum bandwidth rule. If omitted, the
`region` argument of the provider is used. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the QosMinimumBandwidthRule resource produces the following output properties:



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



## Look up an Existing QosMinimumBandwidthRule Resource {#look-up}

Get an existing QosMinimumBandwidthRule resource's state with the given name, ID, and optional extra properties used to qualify the lookup.
{{< chooser language "typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span><span class="p">?:</span> <span class="nx">QosMinimumBandwidthRuleState</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx">QosMinimumBandwidthRule</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@staticmethod</span>
<span class="k">def </span><span class="nf">get</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">direction</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">min_kbps</span><span class="p">:</span> <span class="nx">Optional[int]</span> = None<span class="p">, </span><span class="nx">qos_policy_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">region</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">) -&gt;</span> QosMinimumBandwidthRule</code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetQosMinimumBandwidthRule<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p"> </span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span><span class="p"> *</span><span class="nx">QosMinimumBandwidthRuleState</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">QosMinimumBandwidthRule</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx">QosMinimumBandwidthRule</span><span class="nf"> Get</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input-1.html">Input&lt;string&gt;</a></span><span class="p"> </span><span class="nx">id<span class="p">, </span><span class="nx">QosMinimumBandwidthRuleState</span><span class="p">? </span><span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span id="state_direction_csharp">
<a href="#state_direction_csharp" style="color: inherit; text-decoration: inherit;">Direction</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The direction of traffic. Defaults to "egress". Changing this updates the direction of the
existing QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_minkbps_csharp">
<a href="#state_minkbps_csharp" style="color: inherit; text-decoration: inherit;">Min<wbr>Kbps</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The minimum kilobits per second. Changing this updates the min kbps value of the existing
QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_qospolicyid_csharp">
<a href="#state_qospolicyid_csharp" style="color: inherit; text-decoration: inherit;">Qos<wbr>Policy<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The QoS policy reference. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_region_csharp">
<a href="#state_region_csharp" style="color: inherit; text-decoration: inherit;">Region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region in which to obtain the V2 Networking client.
A Networking client is needed to create a Neutron QoS minimum bandwidth rule. If omitted, the
`region` argument of the provider is used. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_direction_go">
<a href="#state_direction_go" style="color: inherit; text-decoration: inherit;">Direction</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The direction of traffic. Defaults to "egress". Changing this updates the direction of the
existing QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_minkbps_go">
<a href="#state_minkbps_go" style="color: inherit; text-decoration: inherit;">Min<wbr>Kbps</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The minimum kilobits per second. Changing this updates the min kbps value of the existing
QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_qospolicyid_go">
<a href="#state_qospolicyid_go" style="color: inherit; text-decoration: inherit;">Qos<wbr>Policy<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The QoS policy reference. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_region_go">
<a href="#state_region_go" style="color: inherit; text-decoration: inherit;">Region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region in which to obtain the V2 Networking client.
A Networking client is needed to create a Neutron QoS minimum bandwidth rule. If omitted, the
`region` argument of the provider is used. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_direction_nodejs">
<a href="#state_direction_nodejs" style="color: inherit; text-decoration: inherit;">direction</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The direction of traffic. Defaults to "egress". Changing this updates the direction of the
existing QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_minkbps_nodejs">
<a href="#state_minkbps_nodejs" style="color: inherit; text-decoration: inherit;">min<wbr>Kbps</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The minimum kilobits per second. Changing this updates the min kbps value of the existing
QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_qospolicyid_nodejs">
<a href="#state_qospolicyid_nodejs" style="color: inherit; text-decoration: inherit;">qos<wbr>Policy<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The QoS policy reference. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_region_nodejs">
<a href="#state_region_nodejs" style="color: inherit; text-decoration: inherit;">region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region in which to obtain the V2 Networking client.
A Networking client is needed to create a Neutron QoS minimum bandwidth rule. If omitted, the
`region` argument of the provider is used. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_direction_python">
<a href="#state_direction_python" style="color: inherit; text-decoration: inherit;">direction</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The direction of traffic. Defaults to "egress". Changing this updates the direction of the
existing QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_min_kbps_python">
<a href="#state_min_kbps_python" style="color: inherit; text-decoration: inherit;">min_<wbr>kbps</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The minimum kilobits per second. Changing this updates the min kbps value of the existing
QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_qos_policy_id_python">
<a href="#state_qos_policy_id_python" style="color: inherit; text-decoration: inherit;">qos_<wbr>policy_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The QoS policy reference. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_region_python">
<a href="#state_region_python" style="color: inherit; text-decoration: inherit;">region</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The region in which to obtain the V2 Networking client.
A Networking client is needed to create a Neutron QoS minimum bandwidth rule. If omitted, the
`region` argument of the provider is used. Changing this creates a new QoS minimum bandwidth rule.
{{% /md %}}</dd></dl>
{{% /choosable %}}





## Import


QoS minimum bandwidth rules can be imported using the `qos_policy_id/minimum_bandwidth_rule_id` format, e.g.

```sh
 $ pulumi import openstack:networking/qosMinimumBandwidthRule:QosMinimumBandwidthRule minimum_bandwidth_rule_1 d6ae28ce-fcb5-4180-aa62-d260a27e09ae/46dfb556-b92f-48ce-94c5-9a9e2140de94
```




<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-openstack">https://github.com/pulumi/pulumi-openstack</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`openstack` Terraform Provider](https://github.com/terraform-provider-openstack/terraform-provider-openstack).{{% /md %}}</dd>
</dl>

