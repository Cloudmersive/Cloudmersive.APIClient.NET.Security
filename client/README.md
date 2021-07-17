# Cloudmersive.APIClient.NET.Security - the C# library for the securityapi

The security APIs help you detect and block security threats.

This C# SDK is for the [Cloudmersive Virus Scan API](https://www.cloudmersive.com/virus-api):

- API version: v1
- SDK version: 3.0.1
- Build package: io.swagger.codegen.languages.CSharpClientCodegen

<a name="frameworks-supported"></a>
## Frameworks supported
- .NET 4.0 or later
- Windows Phone 7.1 (Mango)

<a name="dependencies"></a>
## Dependencies
- [RestSharp](https://www.nuget.org/packages/RestSharp) - 105.1.0 or later
- [Json.NET](https://www.nuget.org/packages/Newtonsoft.Json/) - 7.0.0 or later
- [JsonSubTypes](https://www.nuget.org/packages/JsonSubTypes/) - 1.2.0 or later

The DLLs included in the package may not be the latest version. We recommend using [NuGet](https://docs.nuget.org/consume/installing-nuget) to obtain the latest version of the packages:
```
Install-Package RestSharp
Install-Package Newtonsoft.Json
Install-Package JsonSubTypes
```

NOTE: RestSharp versions greater than 105.1.0 have a bug which causes file uploads to fail. See [RestSharp#742](https://github.com/restsharp/RestSharp/issues/742)

<a name="installation"></a>
## Installation
Run the following command to generate the DLL
- [Mac/Linux] `/bin/sh build.sh`
- [Windows] `build.bat`

Then include the DLL (under the `bin` folder) in the C# project, and use the namespaces:
```csharp
using Cloudmersive.APIClient.NET.Security.Api;
using Cloudmersive.APIClient.NET.Security.Client;
using Cloudmersive.APIClient.NET.Security.Model;
```
<a name="packaging"></a>
## Packaging

A `.nuspec` is included with the project. You can follow the Nuget quickstart to [create](https://docs.microsoft.com/en-us/nuget/quickstart/create-and-publish-a-package#create-the-package) and [publish](https://docs.microsoft.com/en-us/nuget/quickstart/create-and-publish-a-package#publish-the-package) packages.

This `.nuspec` uses placeholders from the `.csproj`, so build the `.csproj` directly:

```
nuget pack -Build -OutputDirectory out Cloudmersive.APIClient.NET.Security.csproj
```

Then, publish to a [local feed](https://docs.microsoft.com/en-us/nuget/hosting-packages/local-feeds) or [other host](https://docs.microsoft.com/en-us/nuget/hosting-packages/overview) and consume the new package via Nuget as usual.

<a name="getting-started"></a>
## Getting Started

```csharp
using System;
using System.Diagnostics;
using Cloudmersive.APIClient.NET.Security.Api;
using Cloudmersive.APIClient.NET.Security.Client;
using Cloudmersive.APIClient.NET.Security.Model;

namespace Example
{
    public class Example
    {
        public void main()
        {

            // Configure API key authorization: Apikey
            Configuration.Default.ApiKey.Add("Apikey", "YOUR_API_KEY");
            // Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
            // Configuration.Default.ApiKeyPrefix.Add("Apikey", "Bearer");

            var apiInstance = new ContentThreatDetectionApi();
            var value = value_example;  // string | User-facing text input.

            try
            {
                // Automatically detect threats in an input string
                StringAutomaticThreatDetection result = apiInstance.ContentThreatDetectionAutomaticThreatDetectionString(value);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling ContentThreatDetectionApi.ContentThreatDetectionAutomaticThreatDetectionString: " + e.Message );
            }

        }
    }
}
```

<a name="documentation-for-api-endpoints"></a>
## Documentation for API Endpoints

All URIs are relative to *https://api.cloudmersive.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*ContentThreatDetectionApi* | [**ContentThreatDetectionAutomaticThreatDetectionString**](docs/ContentThreatDetectionApi.md#contentthreatdetectionautomaticthreatdetectionstring) | **POST** /security/threat-detection/content/automatic/detect/string | Automatically detect threats in an input string
*ContentThreatDetectionApi* | [**ContentThreatDetectionCheckSqlInjectionString**](docs/ContentThreatDetectionApi.md#contentthreatdetectionchecksqlinjectionstring) | **POST** /security/threat-detection/content/sql-injection/detect/string | Check text input for SQL Injection (SQLI) attacks
*ContentThreatDetectionApi* | [**ContentThreatDetectionCheckXxe**](docs/ContentThreatDetectionApi.md#contentthreatdetectioncheckxxe) | **POST** /security/threat-detection/content/xxe/detect/xml/string | Protect text input from XML External Entity (XXE) attacks
*ContentThreatDetectionApi* | [**ContentThreatDetectionDetectInsecureDeserializationJsonString**](docs/ContentThreatDetectionApi.md#contentthreatdetectiondetectinsecuredeserializationjsonstring) | **POST** /security/threat-detection/content/insecure-deserialization/json/detect/string | Detect Insecure Deserialization JSON (JID) attacks in a string
*ContentThreatDetectionApi* | [**ContentThreatDetectionProtectXss**](docs/ContentThreatDetectionApi.md#contentthreatdetectionprotectxss) | **POST** /security/threat-detection/content/xss/detect/string | Protect text input from Cross-Site-Scripting (XSS) attacks through normalization
*NetworkThreatDetectionApi* | [**NetworkThreatDetectionDetectSsrfUrl**](docs/NetworkThreatDetectionApi.md#networkthreatdetectiondetectssrfurl) | **POST** /security/threat-detection/network/url/ssrf/detect | Check a URL for Server-side Request Forgery (SSRF) threats
*NetworkThreatDetectionApi* | [**NetworkThreatDetectionIsBot**](docs/NetworkThreatDetectionApi.md#networkthreatdetectionisbot) | **POST** /security/threat-detection/network/ip/is-bot | Check if IP address is a Bot client threat
*NetworkThreatDetectionApi* | [**NetworkThreatDetectionIsThreat**](docs/NetworkThreatDetectionApi.md#networkthreatdetectionisthreat) | **POST** /security/threat-detection/network/ip/is-threat | Check if IP address is a known threat
*NetworkThreatDetectionApi* | [**NetworkThreatDetectionIsTorNode**](docs/NetworkThreatDetectionApi.md#networkthreatdetectionistornode) | **POST** /security/threat-detection/network/ip/is-tor-node | Check if IP address is a Tor node server


<a name="documentation-for-models"></a>
## Documentation for Models

 - [Model.IPThreatDetectionResponse](docs/IPThreatDetectionResponse.md)
 - [Model.StringAutomaticThreatDetection](docs/StringAutomaticThreatDetection.md)
 - [Model.StringInsecureDeserializationJsonDetection](docs/StringInsecureDeserializationJsonDetection.md)
 - [Model.StringSqlInjectionDetectionResult](docs/StringSqlInjectionDetectionResult.md)
 - [Model.StringXssProtectionResult](docs/StringXssProtectionResult.md)
 - [Model.StringXxeDetectionResult](docs/StringXxeDetectionResult.md)
 - [Model.ThreatDetectionBotCheckResponse](docs/ThreatDetectionBotCheckResponse.md)
 - [Model.ThreatDetectionTorNodeResponse](docs/ThreatDetectionTorNodeResponse.md)
 - [Model.UrlSsrfThreatDetectionRequestFull](docs/UrlSsrfThreatDetectionRequestFull.md)
 - [Model.UrlSsrfThreatDetectionResponseFull](docs/UrlSsrfThreatDetectionResponseFull.md)


<a name="documentation-for-authorization"></a>
## Documentation for Authorization

<a name="Apikey"></a>
### Apikey

- **Type**: API key
- **API key parameter name**: Apikey
- **Location**: HTTP header

