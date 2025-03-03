
---
title: "getClientInstallationProvider"
title_tag: "keycloak.saml.getClientInstallationProvider"
meta_desc: "Documentation for the keycloak.saml.getClientInstallationProvider function with examples, input properties, output properties, and supporting types."
---



<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

This data source can be used to retrieve Installation Provider of a SAML Client.


{{% examples %}}

## Example Usage

{{< chooser language "typescript,python,go,csharp" / >}}





{{< example csharp >}}

```csharp
using System.IO;
using Pulumi;
using Aws = Pulumi.Aws;
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
        var samlClient = new Keycloak.Saml.Client("samlClient", new Keycloak.Saml.ClientArgs
        {
            RealmId = realm.Id,
            ClientId = "test-saml-client",
            SignDocuments = false,
            SignAssertions = true,
            IncludeAuthnStatement = true,
            SigningCertificate = File.ReadAllText("saml-cert.pem"),
            SigningPrivateKey = File.ReadAllText("saml-key.pem"),
        });
        var samlIdpDescriptor = Output.Tuple(realm.Id, samlClient.Id).Apply(values =>
        {
            var realmId = values.Item1;
            var samlClientId = values.Item2;
            return Keycloak.Saml.GetClientInstallationProvider.InvokeAsync(new Keycloak.Saml.GetClientInstallationProviderArgs
            {
                RealmId = realmId,
                ClientId = samlClientId,
                ProviderId = "saml-idp-descriptor",
            });
        });
        var @default = new Aws.Iam.SamlProvider("default", new Aws.Iam.SamlProviderArgs
        {
            SamlMetadataDocument = samlIdpDescriptor.Apply(samlIdpDescriptor => samlIdpDescriptor.Value),
        });
    }

}
```


{{< /example >}}


{{< example go >}}

Coming soon!

{{< /example >}}


{{< example python >}}

```python
import pulumi
import pulumi_aws as aws
import pulumi_keycloak as keycloak

realm = keycloak.Realm("realm",
    realm="my-realm",
    enabled=True)
saml_client = keycloak.saml.Client("samlClient",
    realm_id=realm.id,
    client_id="test-saml-client",
    sign_documents=False,
    sign_assertions=True,
    include_authn_statement=True,
    signing_certificate=(lambda path: open(path).read())("saml-cert.pem"),
    signing_private_key=(lambda path: open(path).read())("saml-key.pem"))
saml_idp_descriptor = pulumi.Output.all(realm.id, saml_client.id).apply(lambda realmId, samlClientId: keycloak.saml.get_client_installation_provider(realm_id=realm_id,
    client_id=saml_client_id,
    provider_id="saml-idp-descriptor"))
default = aws.iam.SamlProvider("default", saml_metadata_document=saml_idp_descriptor.value)
```


{{< /example >}}


{{< example typescript >}}


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";
import * as keycloak from "@pulumi/keycloak";
import * from "fs";

const realm = new keycloak.Realm("realm", {
    realm: "my-realm",
    enabled: true,
});
const samlClient = new keycloak.saml.Client("samlClient", {
    realmId: realm.id,
    clientId: "test-saml-client",
    signDocuments: false,
    signAssertions: true,
    includeAuthnStatement: true,
    signingCertificate: fs.readFileSync("saml-cert.pem"),
    signingPrivateKey: fs.readFileSync("saml-key.pem"),
});
const samlIdpDescriptor = pulumi.all([realm.id, samlClient.id]).apply(([realmId, samlClientId]) => keycloak.saml.getClientInstallationProvider({
    realmId: realmId,
    clientId: samlClientId,
    providerId: "saml-idp-descriptor",
}));
const _default = new aws.iam.SamlProvider("default", {samlMetadataDocument: samlIdpDescriptor.value});
```


{{< /example >}}





{{% /examples %}}




## Using getClientInstallationProvider {#using}

{{< chooser language "typescript,python,go,csharp" / >}}


{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getClientInstallationProvider<span class="p">(</span><span class="nx">args</span><span class="p">:</span> <span class="nx">GetClientInstallationProviderArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p">?:</span> <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#InvokeOptions">InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="#result">GetClientInstallationProviderResult</a></span>></span></code></pre></div>
{{% /choosable %}}


{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span>get_client_installation_provider(</span><span class="nx">client_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">provider_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">realm_id</span><span class="p">:</span> <span class="nx">Optional[str]</span> = None<span class="p">, </span><span class="nx">opts</span><span class="p">:</span> <span class="nx"><a href="/docs/reference/pkg/python/pulumi/#pulumi.InvokeOptions">Optional[InvokeOptions]</a></span> = None<span class="p">) -&gt;</span> GetClientInstallationProviderResult</code></pre></div>
{{% /choosable %}}


{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetClientInstallationProvider<span class="p">(</span><span class="nx">ctx</span><span class="p"> *</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#Context">Context</a></span><span class="p">, </span><span class="nx">args</span><span class="p"> *</span><span class="nx">GetClientInstallationProviderArgs</span><span class="p">, </span><span class="nx">opts</span><span class="p"> ...</span><span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/v2/go/pulumi?tab=doc#InvokeOption">InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="#result">GetClientInstallationProviderResult</a></span>, error)</span></code></pre></div>

> Note: This function is named `GetClientInstallationProvider` in the Go SDK.

{{% /choosable %}}


{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetClientInstallationProvider </span><span class="p">{</span><span class="k">
    public static </span>Task&lt;<span class="nx"><a href="#result">GetClientInstallationProviderResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx">GetClientInstallationProviderArgs</span><span class="p"> </span><span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.InvokeOptions.html">InvokeOptions</a></span><span class="p">? </span><span class="nx">opts = null<span class="p">)</span><span class="p">
}</span></code></pre></div>
{{% /choosable %}}



The following arguments are supported:


{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="clientid_csharp">
<a href="#clientid_csharp" style="color: inherit; text-decoration: inherit;">Client<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the SAML client. The `id` attribute of a `keycloak_client` resource should be used here.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="providerid_csharp">
<a href="#providerid_csharp" style="color: inherit; text-decoration: inherit;">Provider<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the SAML installation provider. Could be one of `saml-idp-descriptor`, `keycloak-saml`, `saml-sp-descriptor`, `keycloak-saml-subsystem`, `mod-auth-mellon`, etc.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="realmid_csharp">
<a href="#realmid_csharp" style="color: inherit; text-decoration: inherit;">Realm<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The realm that the SAML client exists within.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="clientid_go">
<a href="#clientid_go" style="color: inherit; text-decoration: inherit;">Client<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the SAML client. The `id` attribute of a `keycloak_client` resource should be used here.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="providerid_go">
<a href="#providerid_go" style="color: inherit; text-decoration: inherit;">Provider<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the SAML installation provider. Could be one of `saml-idp-descriptor`, `keycloak-saml`, `saml-sp-descriptor`, `keycloak-saml-subsystem`, `mod-auth-mellon`, etc.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="realmid_go">
<a href="#realmid_go" style="color: inherit; text-decoration: inherit;">Realm<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The realm that the SAML client exists within.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="clientid_nodejs">
<a href="#clientid_nodejs" style="color: inherit; text-decoration: inherit;">client<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the SAML client. The `id` attribute of a `keycloak_client` resource should be used here.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="providerid_nodejs">
<a href="#providerid_nodejs" style="color: inherit; text-decoration: inherit;">provider<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the SAML installation provider. Could be one of `saml-idp-descriptor`, `keycloak-saml`, `saml-sp-descriptor`, `keycloak-saml-subsystem`, `mod-auth-mellon`, etc.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="realmid_nodejs">
<a href="#realmid_nodejs" style="color: inherit; text-decoration: inherit;">realm<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The realm that the SAML client exists within.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-required"
            title="Required">
        <span id="client_id_python">
<a href="#client_id_python" style="color: inherit; text-decoration: inherit;">client_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the SAML client. The `id` attribute of a `keycloak_client` resource should be used here.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="provider_id_python">
<a href="#provider_id_python" style="color: inherit; text-decoration: inherit;">provider_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the SAML installation provider. Could be one of `saml-idp-descriptor`, `keycloak-saml`, `saml-sp-descriptor`, `keycloak-saml-subsystem`, `mod-auth-mellon`, etc.
{{% /md %}}</dd><dt class="property-required"
            title="Required">
        <span id="realm_id_python">
<a href="#realm_id_python" style="color: inherit; text-decoration: inherit;">realm_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The realm that the SAML client exists within.
{{% /md %}}</dd></dl>
{{% /choosable %}}




## getClientInstallationProvider Result {#result}

The following output properties are available:



{{% choosable language csharp %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="clientid_csharp">
<a href="#clientid_csharp" style="color: inherit; text-decoration: inherit;">Client<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
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
        <span id="providerid_csharp">
<a href="#providerid_csharp" style="color: inherit; text-decoration: inherit;">Provider<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="realmid_csharp">
<a href="#realmid_csharp" style="color: inherit; text-decoration: inherit;">Realm<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="value_csharp">
<a href="#value_csharp" style="color: inherit; text-decoration: inherit;">Value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) The returned document needed for SAML installation.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language go %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="clientid_go">
<a href="#clientid_go" style="color: inherit; text-decoration: inherit;">Client<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
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
        <span id="providerid_go">
<a href="#providerid_go" style="color: inherit; text-decoration: inherit;">Provider<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="realmid_go">
<a href="#realmid_go" style="color: inherit; text-decoration: inherit;">Realm<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="value_go">
<a href="#value_go" style="color: inherit; text-decoration: inherit;">Value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) The returned document needed for SAML installation.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language nodejs %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="clientid_nodejs">
<a href="#clientid_nodejs" style="color: inherit; text-decoration: inherit;">client<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
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
        <span id="providerid_nodejs">
<a href="#providerid_nodejs" style="color: inherit; text-decoration: inherit;">provider<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="realmid_nodejs">
<a href="#realmid_nodejs" style="color: inherit; text-decoration: inherit;">realm<wbr>Id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="value_nodejs">
<a href="#value_nodejs" style="color: inherit; text-decoration: inherit;">value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Computed) The returned document needed for SAML installation.
{{% /md %}}</dd></dl>
{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-properties"><dt class="property-"
            title="">
        <span id="client_id_python">
<a href="#client_id_python" style="color: inherit; text-decoration: inherit;">client_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
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
        <span id="provider_id_python">
<a href="#provider_id_python" style="color: inherit; text-decoration: inherit;">provider_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="realm_id_python">
<a href="#realm_id_python" style="color: inherit; text-decoration: inherit;">realm_<wbr>id</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd><dt class="property-"
            title="">
        <span id="value_python">
<a href="#value_python" style="color: inherit; text-decoration: inherit;">value</a>
</span>
        <span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}(Computed) The returned document needed for SAML installation.
{{% /md %}}</dd></dl>
{{% /choosable %}}





<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-keycloak">https://github.com/pulumi/pulumi-keycloak</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`keycloak` Terraform Provider](https://github.com/mrparkers/terraform-provider-keycloak).{{% /md %}}</dd>
</dl>

