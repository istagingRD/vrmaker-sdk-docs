# API

{% api-method method="get" host="https://evs-api.istaging.com/" path="api/v1/panorama" %}
{% api-method-summary %}
Get Panorama
{% endapi-method-summary %}

{% api-method-description %}
Get panorama list
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="tenant-token" type="string" required=true %}
Tenant's session token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="type" type="string" required=false %}
Pano / PanoCollection
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="string" required=false %}
ID's number \(required if type present\)
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
[
    {     
        "id": "abc123",     
        "downloadUrl": "https://example.com",    
        "resizeUrl": "https://resize.example.com"    
        "name": "demoPano",    
        "index": 0,    
        "cubemapReady": false,    
        "cubemapLink": "https://cdn.istaging.com/USER_ID/PANO_ID/panoramas/cubemap_%s_xyz.jpg",
        "cubemapLinkPreview": "https://cdn.istaging.com/USER_ID/PANO_ID/panoramas/cubemap_preview_xyz.jpg",
    },
    {     
        "id": "1234",     
        "downloadUrl": "https://example.com",    
        "resizeUrl": "https://resize.example.com"    
        "name": "demoPano02",    
        "index": 0,    
        "cubemapReady": false,    
        "cubemapLink": "https://cdn.istaging.com/USER_ID/PANO_ID/panoramas/cubemap_%s_xyz.jpg",
        "cubemapLinkPreview": "https://cdn.istaging.com/USER_ID/PANO_ID/panoramas/cubemap_preview_xyz.jpg"
    }
]
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "invalid format" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "unauthorized" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "server Error" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://evs-api.istaging.com/" path="api/v1/panorama" %}
{% api-method-summary %}
Create Panorama
{% endapi-method-summary %}

{% api-method-description %}
Create \(multiple\) Panorama 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="tenant-token" type="string" required=true %}
Tenant's session token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="panoramas" type="array" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="downloadUrl" type="string" required=true %}
Panorama Download Link
{% endapi-method-parameter %}

{% api-method-parameter name="index" type="integer" required=false %}
Panorama Index
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}
Panorama Name
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Success Create Panorama
{% endapi-method-response-example-description %}

```javascript
{ 
    "panoramas":
        [ 
            "id": "abc123", 
            "downloadUrl": "https://example.com",
            "resizeUrl": "https://resize.example.com"
            "name": "demoPano",
            "index": 0
        ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Invalid Format
{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "invalid format" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "unauthorized" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Server Error
{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "server Error" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```javascript
Body Parameters Example: 
{
    "panoramas": [
         {
             "name": "01",
             "downloadUrl": "www.url.com"
         },
         {
             "name": "02",
             "downloadUrl": "www.url.com",
             "index": 1
         }
     ]
}
```

{% api-method method="post" host="https://evs-api.istaging.com/" path="api/v1/panoCollection" %}
{% api-method-summary %}
Create PanoCollection
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="tenant-token" type="string" required=true %}
Tenant's session token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="panoramaIdList" type="array" required=false %}
Panorama ID List
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}
Name of this collection
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{ 
    "id": "01",
    "name": "panoCollection01"
    "ownerId": "Tenant01"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "invaild format" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "unauthorized" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "server error" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://evs-api.istaging.com/" path="api/v1/panoCollection" %}
{% api-method-summary %}
Get PanoCollection
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="tenant-token" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
[ 
    { 
        "id": "01", 
        "name": "panoCollection01" ,
        "ownerId": "tenant_01"
    }, { 
        "id": "02", 
        "name": "panoCollection01" ,
        "ownerId": "tenant_01"
    }
]
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "invaild format" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "unauthorized" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "server error" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://evs-api.istaging.com" path="/api/v1/platformAccount/signup" %}
{% api-method-summary %}
Create Platform Account
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="istaging-api-key" type="string" required=true %}
iStating API Key
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="password" type="string" required=true %}
Account's password
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Account's email
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Create Success
{% endapi-method-response-example-description %}

```javascript
{ "platformAccountToken": "xyz.123.abc" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Invalid Format
{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "invalid format" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Unauthorized
{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "unauthorized" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "server error" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://evs-api.istaging.com" path="/api/v1/tenant/signup" %}
{% api-method-summary %}
Signup Tenant
{% endapi-method-summary %}

{% api-method-description %}
Use platform account token to signup tenant account
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="platform-account-token" type="string" required=true %}
Platform account token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
Tenant's username
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
Tenant's Password
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Signup Tenant Success 
{% endapi-method-response-example-description %}

```javascript
{ "tenantToken": "xyz.123.abc" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Invalid Format
{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "invalid format" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Unauthorized
{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "unauthorized" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Server Error
{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "server error" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://evs-api.istaging.com" path="/api/v1/tenant/login" %}
{% api-method-summary %}
Tenant Login
{% endapi-method-summary %}

{% api-method-description %}
Tenant use username and password to login and to get token
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="password" type="string" required=true %}
Tenant's password
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
Tenant's Username
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Login Success
{% endapi-method-response-example-description %}

```javascript
{ "tenantToken": "xyz.123.abc" } 
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Invalid Format
{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "invalid format" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Unauthorized
{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "unauthorized" }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Server Error
{% endapi-method-response-example-description %}

```javascript
{ "errorMsg": "server error" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



