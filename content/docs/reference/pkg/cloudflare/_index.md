---
title: "Cloudflare"
title_tag: "cloudflare.Cloudflare"
meta_desc: "A Pulumi package for creating and managing Cloudflare cloud resources."
menu:
    reference:
        parent: API Reference
---

<!-- WARNING: this file was generated by Pulumi Docs Generator. -->
<!-- Do not edit by hand unless you're certain you know what you are doing! -->

A Pulumi package for creating and managing Cloudflare cloud resources.

<h2 id="resources">Resources</h2>
<ul class="api">
    <li><a href="accessapplication" title="AccessApplication"><span class="symbol resource"></span>AccessApplication</a></li>
    <li><a href="accessgroup" title="AccessGroup"><span class="symbol resource"></span>AccessGroup</a></li>
    <li><a href="accessidentityprovider" title="AccessIdentityProvider"><span class="symbol resource"></span>AccessIdentityProvider</a></li>
    <li><a href="accessmutualtlscertificate" title="AccessMutualTlsCertificate"><span class="symbol resource"></span>AccessMutualTlsCertificate</a></li>
    <li><a href="accesspolicy" title="AccessPolicy"><span class="symbol resource"></span>AccessPolicy</a></li>
    <li><a href="accessrule" title="AccessRule"><span class="symbol resource"></span>AccessRule</a></li>
    <li><a href="accessservicetoken" title="AccessServiceToken"><span class="symbol resource"></span>AccessServiceToken</a></li>
    <li><a href="accountmember" title="AccountMember"><span class="symbol resource"></span>AccountMember</a></li>
    <li><a href="apitoken" title="ApiToken"><span class="symbol resource"></span>ApiToken</a></li>
    <li><a href="argo" title="Argo"><span class="symbol resource"></span>Argo</a></li>
    <li><a href="argotunnel" title="ArgoTunnel"><span class="symbol resource"></span>ArgoTunnel</a></li>
    <li><a href="authenticatedoriginpulls" title="AuthenticatedOriginPulls"><span class="symbol resource"></span>AuthenticatedOriginPulls</a></li>
    <li><a href="authenticatedoriginpullscertificate" title="AuthenticatedOriginPullsCertificate"><span class="symbol resource"></span>AuthenticatedOriginPullsCertificate</a></li>
    <li><a href="byoipprefix" title="ByoIpPrefix"><span class="symbol resource"></span>ByoIpPrefix</a></li>
    <li><a href="certificatepack" title="CertificatePack"><span class="symbol resource"></span>CertificatePack</a></li>
    <li><a href="customhostname" title="CustomHostname"><span class="symbol resource"></span>CustomHostname</a></li>
    <li><a href="customhostnamefallbackorigin" title="CustomHostnameFallbackOrigin"><span class="symbol resource"></span>CustomHostnameFallbackOrigin</a></li>
    <li><a href="custompages" title="CustomPages"><span class="symbol resource"></span>CustomPages</a></li>
    <li><a href="customssl" title="CustomSsl"><span class="symbol resource"></span>CustomSsl</a></li>
    <li><a href="filter" title="Filter"><span class="symbol resource"></span>Filter</a></li>
    <li><a href="firewallrule" title="FirewallRule"><span class="symbol resource"></span>FirewallRule</a></li>
    <li><a href="healthcheck" title="Healthcheck"><span class="symbol resource"></span>Healthcheck</a></li>
    <li><a href="iplist" title="IpList"><span class="symbol resource"></span>IpList</a></li>
    <li><a href="loadbalancer" title="LoadBalancer"><span class="symbol resource"></span>LoadBalancer</a></li>
    <li><a href="loadbalancermonitor" title="LoadBalancerMonitor"><span class="symbol resource"></span>LoadBalancerMonitor</a></li>
    <li><a href="loadbalancerpool" title="LoadBalancerPool"><span class="symbol resource"></span>LoadBalancerPool</a></li>
    <li><a href="logpushownershipchallenge" title="LogPushOwnershipChallenge"><span class="symbol resource"></span>LogPushOwnershipChallenge</a></li>
    <li><a href="logpullretention" title="LogpullRetention"><span class="symbol resource"></span>LogpullRetention</a></li>
    <li><a href="logpushjob" title="LogpushJob"><span class="symbol resource"></span>LogpushJob</a></li>
    <li><a href="magicfirewallruleset" title="MagicFirewallRuleset"><span class="symbol resource"></span>MagicFirewallRuleset</a></li>
    <li><a href="origincacertificate" title="OriginCaCertificate"><span class="symbol resource"></span>OriginCaCertificate</a></li>
    <li><a href="pagerule" title="PageRule"><span class="symbol resource"></span>PageRule</a></li>
    <li><a href="provider" title="Provider"><span class="symbol resource"></span>Provider</a></li>
    <li><a href="ratelimit" title="RateLimit"><span class="symbol resource"></span>RateLimit</a></li>
    <li><a href="record" title="Record"><span class="symbol resource"></span>Record</a></li>
    <li><a href="spectrumapplication" title="SpectrumApplication"><span class="symbol resource"></span>SpectrumApplication</a></li>
    <li><a href="wafgroup" title="WafGroup"><span class="symbol resource"></span>WafGroup</a></li>
    <li><a href="wafoverride" title="WafOverride"><span class="symbol resource"></span>WafOverride</a></li>
    <li><a href="wafpackage" title="WafPackage"><span class="symbol resource"></span>WafPackage</a></li>
    <li><a href="wafrule" title="WafRule"><span class="symbol resource"></span>WafRule</a></li>
    <li><a href="workercrontrigger" title="WorkerCronTrigger"><span class="symbol resource"></span>WorkerCronTrigger</a></li>
    <li><a href="workerroute" title="WorkerRoute"><span class="symbol resource"></span>WorkerRoute</a></li>
    <li><a href="workerscript" title="WorkerScript"><span class="symbol resource"></span>WorkerScript</a></li>
    <li><a href="workerskv" title="WorkersKv"><span class="symbol resource"></span>WorkersKv</a></li>
    <li><a href="workerskvnamespace" title="WorkersKvNamespace"><span class="symbol resource"></span>WorkersKvNamespace</a></li>
    <li><a href="zone" title="Zone"><span class="symbol resource"></span>Zone</a></li>
    <li><a href="zonednssec" title="ZoneDnssec"><span class="symbol resource"></span>ZoneDnssec</a></li>
    <li><a href="zonelockdown" title="ZoneLockdown"><span class="symbol resource"></span>ZoneLockdown</a></li>
    <li><a href="zonesettingsoverride" title="ZoneSettingsOverride"><span class="symbol resource"></span>ZoneSettingsOverride</a></li>
</ul>

<h2 id="functions">Functions</h2>
<ul class="api">
    <li><a href="getapitokenpermissiongroups" title="GetApiTokenPermissionGroups"><span class="symbol function"></span>GetApiTokenPermissionGroups</a></li>
    <li><a href="getipranges" title="GetIpRanges"><span class="symbol function"></span>GetIpRanges</a></li>
    <li><a href="getwafgroups" title="GetWafGroups"><span class="symbol function"></span>GetWafGroups</a></li>
    <li><a href="getwafpackages" title="GetWafPackages"><span class="symbol function"></span>GetWafPackages</a></li>
    <li><a href="getwafrules" title="GetWafRules"><span class="symbol function"></span>GetWafRules</a></li>
    <li><a href="getzonednssec" title="GetZoneDnssec"><span class="symbol function"></span>GetZoneDnssec</a></li>
    <li><a href="getzones" title="GetZones"><span class="symbol function"></span>GetZones</a></li>
</ul>

<h2 id="package-details">Package Details</h2>
<dl class="package-details">
	<dt>Repository</dt>
	<dd><a href="https://github.com/pulumi/pulumi-cloudflare">https://github.com/pulumi/pulumi-cloudflare</a></dd>
	<dt>License</dt>
	<dd>Apache-2.0</dd>
	<dt>Notes</dt>
	<dd>{{% md %}}This Pulumi package is based on the [`cloudflare` Terraform Provider](https://github.com/cloudflare/terraform-provider-cloudflare).{{% /md %}}</dd>
	<dt>Version</dt>
	<dd>2.14.2</dd>
</dl>

