
---
title: "SshKey"
title_tag: "aws.transfer.SshKey"
meta_desc: "Documentation for the aws.transfer.SshKey resource with examples, input properties, output properties, lookup functions, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

Provides a AWS Transfer User SSH Key resource.

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
        var exampleServer = new Aws.Transfer.Server("exampleServer", new Aws.Transfer.ServerArgs
        {
            IdentityProviderType = "SERVICE_MANAGED",
            Tags = 
            {
                { "NAME", "tf-acc-test-transfer-server" },
            },
        });
        var exampleRole = new Aws.Iam.Role("exampleRole", new Aws.Iam.RoleArgs
        {
            AssumeRolePolicy = @"{
	""Version"": ""2012-10-17"",
	""Statement"": [
		{
		""Effect"": ""Allow"",
		""Principal"": {
			""Service"": ""transfer.amazonaws.com""
		},
		""Action"": ""sts:AssumeRole""
		}
	]
}
",
        });
        var exampleUser = new Aws.Transfer.User("exampleUser", new Aws.Transfer.UserArgs
        {
            ServerId = exampleServer.Id,
            UserName = "tftestuser",
            Role = exampleRole.Arn,
            Tags = 
            {
                { "NAME", "tftestuser" },
            },
        });
        var exampleSshKey = new Aws.Transfer.SshKey("exampleSshKey", new Aws.Transfer.SshKeyArgs
        {
            ServerId = exampleServer.Id,
            UserName = exampleUser.UserName,
            Body = "... SSH key ...",
        });
        var exampleRolePolicy = new Aws.Iam.RolePolicy("exampleRolePolicy", new Aws.Iam.RolePolicyArgs
        {
            Role = exampleRole.Id,
            Policy = @"{
	""Version"": ""2012-10-17"",
	""Statement"": [
		{
			""Sid"": ""AllowFullAccesstoS3"",
			""Effect"": ""Allow"",
			""Action"": [
				""s3:*""
			],
			""Resource"": ""*""
		}
	]
}
",
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

	"github.com/pulumi/pulumi-aws/sdk/v3/go/aws/iam"
	"github.com/pulumi/pulumi-aws/sdk/v3/go/aws/transfer"
	"github.com/pulumi/pulumi/sdk/v2/go/pulumi"
)

func main() {
	pulumi.Run(func(ctx *pulumi.Context) error {
		exampleServer, err := transfer.NewServer(ctx, "exampleServer", &transfer.ServerArgs{
			IdentityProviderType: pulumi.String("SERVICE_MANAGED"),
			Tags: pulumi.StringMap{
				"NAME": pulumi.String("tf-acc-test-transfer-server"),
			},
		})
		if err != nil {
			return err
		}
		exampleRole, err := iam.NewRole(ctx, "exampleRole", &iam.RoleArgs{
			AssumeRolePolicy: pulumi.String(fmt.Sprintf("%v%v%v%v%v%v%v%v%v%v%v%v", "{\n", "	\"Version\": \"2012-10-17\",\n", "	\"Statement\": [\n", "		{\n", "		\"Effect\": \"Allow\",\n", "		\"Principal\": {\n", "			\"Service\": \"transfer.amazonaws.com\"\n", "		},\n", "		\"Action\": \"sts:AssumeRole\"\n", "		}\n", "	]\n", "}\n")),
		})
		if err != nil {
			return err
		}
		exampleUser, err := transfer.NewUser(ctx, "exampleUser", &transfer.UserArgs{
			ServerId: exampleServer.ID(),
			UserName: pulumi.String("tftestuser"),
			Role:     exampleRole.Arn,
			Tags: pulumi.StringMap{
				"NAME": pulumi.String("tftestuser"),
			},
		})
		if err != nil {
			return err
		}
		_, err = transfer.NewSshKey(ctx, "exampleSshKey", &transfer.SshKeyArgs{
			ServerId: exampleServer.ID(),
			UserName: exampleUser.UserName,
			Body:     pulumi.String("... SSH key ..."),
		})
		if err != nil {
			return err
		}
		_, err = iam.NewRolePolicy(ctx, "exampleRolePolicy", &iam.RolePolicyArgs{
			Role: exampleRole.ID(),
			Policy: pulumi.String(fmt.Sprintf("%v%v%v%v%v%v%v%v%v%v%v%v%v", "{\n", "	\"Version\": \"2012-10-17\",\n", "	\"Statement\": [\n", "		{\n", "			\"Sid\": \"AllowFullAccesstoS3\",\n", "			\"Effect\": \"Allow\",\n", "			\"Action\": [\n", "				\"s3:*\"\n", "			],\n", "			\"Resource\": \"*\"\n", "		}\n", "	]\n", "}\n")),
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
import pulumi_aws as aws

example_server = aws.transfer.Server("exampleServer",
    identity_provider_type="SERVICE_MANAGED",
    tags={
        "NAME": "tf-acc-test-transfer-server",
    })
example_role = aws.iam.Role("exampleRole", assume_role_policy="""{
	"Version": "2012-10-17",
	"Statement": [
		{
		"Effect": "Allow",
		"Principal": {
			"Service": "transfer.amazonaws.com"
		},
		"Action": "sts:AssumeRole"
		}
	]
}
""")
example_user = aws.transfer.User("exampleUser",
    server_id=example_server.id,
    user_name="tftestuser",
    role=example_role.arn,
    tags={
        "NAME": "tftestuser",
    })
example_ssh_key = aws.transfer.SshKey("exampleSshKey",
    server_id=example_server.id,
    user_name=example_user.user_name,
    body="... SSH key ...")
example_role_policy = aws.iam.RolePolicy("exampleRolePolicy",
    role=example_role.id,
    policy="""{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Sid": "AllowFullAccesstoS3",
			"Effect": "Allow",
			"Action": [
				"s3:*"
			],
			"Resource": "*"
		}
	]
}
""")
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleServer = new aws.transfer.Server("exampleServer", {
    identityProviderType: "SERVICE_MANAGED",
    tags: {
        NAME: "tf-acc-test-transfer-server",
    },
});
const exampleRole = new aws.iam.Role("exampleRole", {assumeRolePolicy: `{
	"Version": "2012-10-17",
	"Statement": [
		{
		"Effect": "Allow",
		"Principal": {
			"Service": "transfer.amazonaws.com"
		},
		"Action": "sts:AssumeRole"
		}
	]
}
`});
const exampleUser = new aws.transfer.User("exampleUser", {
    serverId: exampleServer.id,
    userName: "tftestuser",
    role: exampleRole.arn,
    tags: {
        NAME: "tftestuser",
    },
});
const exampleSshKey = new aws.transfer.SshKey("exampleSshKey", {
    serverId: exampleServer.id,
    userName: exampleUser.userName,
    body: "... SSH key ...",
});
const exampleRolePolicy = new aws.iam.RolePolicy("exampleRolePolicy", {
    role: exampleRole.id,
    policy: `{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Sid": "AllowFullAccesstoS3",
			"Effect": "Allow",
			"Action": [
				"s3:*"
			],
			"Resource": "*"
		}
	]
}
`,
});
```


{{< /example >}}





{{% /examples %}}




## Create a SshKey Resource {#create}
{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx">SshKey</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p">:</span> <span class="nx"><a href="#inputs">SshKeyArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nx">SshKey</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">body</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">server_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">user_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span><span class="nx">NewSshKey</span><span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">args</span><span class="p"> </span><span class="nx"><a href="#inputs">SshKeyArgs</a></span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">SshKey</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx">SshKey</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="#inputs">SshKeyArgs</a></span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span class="property-type"><a href="#inputs">SshKeyArgs</a></span>
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
        <span class="property-type"><a href="#inputs">SshKeyArgs</a></span>
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
        <span class="property-type"><a href="#inputs">SshKeyArgs</a></span>
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

## SshKey Resource Properties {#properties}

To learn more about resource properties and how to use them, see [Inputs and Outputs]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) in the Programming Model docs.

### Inputs

The SshKey resource accepts the following [input]({{< relref "/docs/intro/concepts/inputs-outputs" >}}) properties:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="body_csharp">
<a href="#body_csharp" style="color: inherit; text-decoration: inherit;">Body</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public key portion of an SSH key pair.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="serverid_csharp">
<a href="#serverid_csharp" style="color: inherit; text-decoration: inherit;">Server<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Server ID of the Transfer Server (e.g. `s-12345678`)
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="username_csharp">
<a href="#username_csharp" style="color: inherit; text-decoration: inherit;">User<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the user account that is assigned to one or more servers.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="body_go">
<a href="#body_go" style="color: inherit; text-decoration: inherit;">Body</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public key portion of an SSH key pair.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="serverid_go">
<a href="#serverid_go" style="color: inherit; text-decoration: inherit;">Server<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Server ID of the Transfer Server (e.g. `s-12345678`)
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="username_go">
<a href="#username_go" style="color: inherit; text-decoration: inherit;">User<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the user account that is assigned to one or more servers.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="body_nodejs">
<a href="#body_nodejs" style="color: inherit; text-decoration: inherit;">body</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public key portion of an SSH key pair.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="serverid_nodejs">
<a href="#serverid_nodejs" style="color: inherit; text-decoration: inherit;">server<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Server ID of the Transfer Server (e.g. `s-12345678`)
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="username_nodejs">
<a href="#username_nodejs" style="color: inherit; text-decoration: inherit;">user<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the user account that is assigned to one or more servers.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="body_python">
<a href="#body_python" style="color: inherit; text-decoration: inherit;">body</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public key portion of an SSH key pair.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="server_id_python">
<a href="#server_id_python" style="color: inherit; text-decoration: inherit;">server_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Server ID of the Transfer Server (e.g. `s-12345678`)
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="user_name_python">
<a href="#user_name_python" style="color: inherit; text-decoration: inherit;">user_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the user account that is assigned to one or more servers.
{{% /md %}}</dd></dl>
{{% /choosable %}}


### Outputs

All [input](#inputs) properties are implicitly available as output properties. Additionally, the SshKey resource produces the following output properties:



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



## Look up an Existing SshKey Resource {#look-up}

Get an existing SshKey resource's state with the given name, ID, and optional extra properties used to qualify the lookup.
{{< chooser language "typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span><span class="p">:</span> <span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">Input&lt;ID&gt;</a></span><span class="p">, </span><span class="nx">state</span><span class="p">?:</span> <span class="nx">SshKeyState</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">CustomResourceOptions</a></span><span class="p">): </span><span class="nx">SshKey</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class=nd>@staticmethod</span>
<span class="k">def </span><span class="nf">get</span><span class="p">(</span><span class="nx">resource_name</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">id</span><span class="p">:</span> <span class="nx">str</span><span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.ResourceOptions">Optional[ResourceOptions]</a></span> = None<span class="p">, </span><span class="nx">body</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">server_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">user_name</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">) -&gt;</span> SshKey</code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetSshKey<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">name</span><span class="p"> </span><span class="nx">string</span><span class="p">, </span><span class="nx">id</span><span class="p"> </span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#IDInput">IDInput</a></span><span class="p">, </span><span class="nx">state</span><span class="p"> *</span><span class="nx">SshKeyState</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v3/go/pulumi?tab=doc#ResourceOption">ResourceOption</a></span><span class="p">) (*<span class="nx">SshKey</span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx">SshKey</span><span class="nf"> Get</span><span class="p">(</span><span class="nx">string</span><span class="p"> </span><span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input-1.html">Input&lt;string&gt;</a></span><span class="p"> </span><span class="nx">id<span class="p">, </span><span class="nx">SshKeyState</span><span class="p">? </span><span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">CustomResourceOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
        <span id="state_body_csharp">
<a href="#state_body_csharp" style="color: inherit; text-decoration: inherit;">Body</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public key portion of an SSH key pair.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_serverid_csharp">
<a href="#state_serverid_csharp" style="color: inherit; text-decoration: inherit;">Server<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Server ID of the Transfer Server (e.g. `s-12345678`)
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_username_csharp">
<a href="#state_username_csharp" style="color: inherit; text-decoration: inherit;">User<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the user account that is assigned to one or more servers.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_body_go">
<a href="#state_body_go" style="color: inherit; text-decoration: inherit;">Body</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public key portion of an SSH key pair.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_serverid_go">
<a href="#state_serverid_go" style="color: inherit; text-decoration: inherit;">Server<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Server ID of the Transfer Server (e.g. `s-12345678`)
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_username_go">
<a href="#state_username_go" style="color: inherit; text-decoration: inherit;">User<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the user account that is assigned to one or more servers.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_body_nodejs">
<a href="#state_body_nodejs" style="color: inherit; text-decoration: inherit;">body</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public key portion of an SSH key pair.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_serverid_nodejs">
<a href="#state_serverid_nodejs" style="color: inherit; text-decoration: inherit;">server<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Server ID of the Transfer Server (e.g. `s-12345678`)
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_username_nodejs">
<a href="#state_username_nodejs" style="color: inherit; text-decoration: inherit;">user<wbr>Name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the user account that is assigned to one or more servers.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-optional"
            title="Optional">
        <span id="state_body_python">
<a href="#state_body_python" style="color: inherit; text-decoration: inherit;">body</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public key portion of an SSH key pair.
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_server_id_python">
<a href="#state_server_id_python" style="color: inherit; text-decoration: inherit;">server_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Server ID of the Transfer Server (e.g. `s-12345678`)
{{% /md %}}</dd><dt class="property-optional"
            title="Optional">
        <span id="state_user_name_python">
<a href="#state_user_name_python" style="color: inherit; text-decoration: inherit;">user_<wbr>name</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the user account that is assigned to one or more servers.
{{% /md %}}</dd></dl>
{{% /choosable %}}





## Import


Transfer SSH Public Key can be imported using the `server_id` and `user_name` and `ssh_public_key_id` separated by `/`.

```sh
 $ pulumi import aws:transfer/sshKey:SshKey bar s-12345678/test-username/key-12345
```




<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-aws">https://github.com/pulumi/pulumi-aws</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`aws` Terraform Provider](https://github.com/terraform-providers/terraform-provider-aws).{{% /md %}}</dd>
</dl>

