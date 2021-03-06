# DescribeRegions {#doc_api_859430 .reference}

You can call the DescribeRegions API to query available regions.

## Debug {#apiExplorer .section}

Click [here](https://api.aliyun.com/#product=Slb&api=DescribeRegions) to perform a debug operation in OpenAPI Explorer and automatically generate an SDK code example.

## Request parameters {#parameters .section}

|Name|Type|Required?|Example value|Description|
|----|----|---------|-------------|-----------|
|Action|String|Yes|DescribeRegions|The action to perform. Valid value: **DescribeRegions**

 |
|RegionId|String|Yes|cn-hangzhou|The ID of the region

 |
|AcceptLanguage|String|No|zh-CN|Supported languages. Valid values:

 -   Chinese: zh-CN
-   English: en-US
-   Japanese: ja

 |

## Response parameters {#resultMapping .section}

|Name|Type|Example value|Description|
|----|----|-------------|-----------|
|Regions| | |A list of regions.

 |
|└RegionId|String|cn-beijing|The ID of the region

 |
|└LocalName|String|China \(Beijing\)|The name of the region

 |
|└RegionEndpoint|String|slb.aliyuncs.com|The endpoint address of the region

 |
|RequestId|String|1651FBB6-4FBF-49FF-A9F5-DF5D696C7EC6|The ID of the request

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

https://slb.aliyuncs.com/?Action=DescribeRegions
&<CommonParameters>

```

Normal response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeRegionsResponse>
  <RequestId>3CCA93B7-9590-42D6-8118-9CE3383558A9</RequestId>
  <Regions>
    <Region>
      <RegionId>ap-southeast-1</RegionId>
      <RegionEndpoint>slb.aliyuncs.com</RegionEndpoint>
      <LocalName>Singapore</LocalName>
    </Region>
    <Region>
      <RegionId>eu-central-1</RegionId>
      <RegionEndpoint>slb.eu-central-1.aliyuncs.com</RegionEndpoint>
      <LocalName>Germany (Frankfurt)</LocalName>
    </Region>
    <Region>
      <RegionId>ap-southeast-5</RegionId>
      <RegionEndpoint>slb.ap-southeast-5.aliyuncs.com</RegionEndpoint>
      <LocalName>Indonesia (Jakarta)</LocalName>
    </Region>
    <Region>
      <RegionId>cn-qingdao</RegionId>
      <RegionEndpoint>slb.aliyuncs.com</RegionEndpoint>
      <LocalName>China (Qingdao)</LocalName>
    </Region>
    <Region>
      <RegionId>us-east-1</RegionId>
      <RegionEndpoint>slb.aliyuncs.com</RegionEndpoint>
      <LocalName>US (Virginia)</LocalName>
    </Region>
    <Region>
      <RegionId>ap-south-1</RegionId>
      <RegionEndpoint>slb.ap-south-1.aliyuncs.com</RegionEndpoint>
      <LocalName>India (Mumbai)</LocalName>
    </Region>
    <Region>
      <RegionId>cn-beijing</RegionId>
      <RegionEndpoint>slb.aliyuncs.com</RegionEndpoint>
      <LocalName>China (Beijing)</LocalName>
    </Region>
    <Region>
      <RegionId>cn-shanghai</RegionId>
      <RegionEndpoint>slb.aliyuncs.com</RegionEndpoint>
      <LocalName>China (Shanghai)</LocalName>
    </Region>
    <Region>
      <RegionId>ap-northeast-1</RegionId>
      <RegionEndpoint>slb.ap-northeast-1.aliyuncs.com</RegionEndpoint>
      <LocalName>Japan (Tokyo)</LocalName>
    </Region>
    <Region>
      <RegionId>cn-huhehaote</RegionId>
      <RegionEndpoint>slb.cn-huhehaote.aliyuncs.com</RegionEndpoint>
      <LocalName>China (Hohhot)</LocalName>
    </Region>
    <Region>
      <RegionId>cn-shenzhen</RegionId>
      <RegionEndpoint>slb.aliyuncs.com</RegionEndpoint>
      <LocalName>China (Shenzhen)</LocalName>
    </Region>
    <Region>
      <RegionId>ap-southeast-2</RegionId>
      <RegionEndpoint>slb.ap-southeast-2.aliyuncs.com</RegionEndpoint>
      <LocalName>Australia (Sydney)</LocalName>
    </Region>
    <Region>
      <RegionId>cn-hongkong</RegionId>
      <RegionEndpoint>slb.aliyuncs.com</RegionEndpoint>
      <LocalName>Hong Kong</LocalName>
    </Region>
    <Region>
      <RegionId>us-west-1</RegionId>
      <RegionEndpoint>slb.aliyuncs.com</RegionEndpoint>
      <LocalName>US (Silicon Valley)</LocalName>
    </Region>
    <Region>
      <RegionId>eu-west-1</RegionId>
      <RegionEndpoint>slb.eu-west-1.aliyuncs.com</RegionEndpoint>
      <LocalName>UK (London)</LocalName>
    </Region>
    <Region>
      <RegionId>me-east-1</RegionId>
      <RegionEndpoint>slb.me-east-1.aliyuncs.com</RegionEndpoint>
      <LocalName>UAE (Dubai)</LocalName>
    </Region>
    <Region>
      <RegionId>cn-zhangjiakou</RegionId>
      <RegionEndpoint>slb.cn-zhangjiakou.aliyuncs.com</RegionEndpoint>
      <LocalName>China (Zhangjiakou)</LocalName>
    </Region>
    <Region>
      <RegionId>cn-hangzhou</RegionId>
      <RegionEndpoint>slb.aliyuncs.com</RegionEndpoint>
      <LocalName>China (Hangzhou)</LocalName>
    </Region>
    <Region>
      <RegionId>ap-southeast-3</RegionId>
      <RegionEndpoint>slb.ap-southeast-3.aliyuncs.com</RegionEndpoint>
      <LocalName>Malaysia (Kuala Lumpur)</LocalName>
    </Region>
  </Regions>
</DescribeRegionsResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"3CCA93B7-9590-42D6-8118-9CE3383558A9",
	"Regions":{
		"Region":[
			{
				"RegionId":"ap-southeast-1",
				"RegionEndpoint":"slb.aliyuncs.com",
				"LocalName":"Singapore"
			},
			{
				"RegionId":"eu-central-1",
				"RegionEndpoint":"slb.eu-central-1.aliyuncs.com",
				"LocalName":"Germany (Frankfurt)"
			},
			{
				"RegionId":"ap-southeast-5",
				"RegionEndpoint":"slb.ap-southeast-5.aliyuncs.com",
				"LocalName":"Indonesia (Jakarta)"
			},
			{
				"RegionId":"cn-qingdao",
				"RegionEndpoint":"slb.aliyuncs.com",
				"LocalName":"China (Qingdao)"
			},
			{
				"RegionId":"us-east-1",
				"RegionEndpoint":"slb.aliyuncs.com",
				"LocalName":"US (Virginia)"
			},
			{
				"RegionId":"ap-south-1",
				"RegionEndpoint":"slb.ap-south-1.aliyuncs.com",
				"LocalName":"India (Mumbai)"
			},
			{
				"RegionId":"cn-beijing",
				"RegionEndpoint":"slb.aliyuncs.com",
				"LocalName":"China (Beijing)"
			},
			{
				"RegionId":"cn-shanghai",
				"RegionEndpoint":"slb.aliyuncs.com",
				"LocalName":"China (Shanghai)"
			},
			{
				"RegionId":"ap-northeast-1",
				"RegionEndpoint":"slb.ap-northeast-1.aliyuncs.com",
				"LocalName":"Japan (Tokyo)"
			},
			{
				"RegionId":"cn-huhehaote",
				"RegionEndpoint":"slb.cn-huhehaote.aliyuncs.com",
				"LocalName":"China (Hohhot)"
			},
			{
				"RegionId":"cn-shenzhen",
				"RegionEndpoint":"slb.aliyuncs.com",
				"LocalName":"China (Shenzhen)"
			},
			{
				"RegionId":"ap-southeast-2",
				"RegionEndpoint":"slb.ap-southeast-2.aliyuncs.com",
				"LocalName":"Australia (Sydney)"
			},
			{
				"RegionId":"cn-hongkong",
				"RegionEndpoint":"slb.aliyuncs.com",
				"LocalName":"Hong Kong"
			},
			{
				"RegionId":"us-west-1",
				"RegionEndpoint":"slb.aliyuncs.com",
				"LocalName":"US (Silicon Valley)"
			},
			{
				"RegionId":"eu-west-1",
				"RegionEndpoint":"slb.eu-west-1.aliyuncs.com",
				"LocalName":"UK (London)"
			},
			{
				"RegionId":"me-east-1",
				"RegionEndpoint":"slb.me-east-1.aliyuncs.com",
				"LocalName":"UAE (Dubai)"
			},
			{
				"RegionId":"cn-zhangjiakou",
				"RegionEndpoint":"slb.cn-zhangjiakou.aliyuncs.com",
				"LocalName":"China (Zhangjiakou)"
			},
			{
				"RegionId":"cn-hangzhou",
				"RegionEndpoint":"slb.aliyuncs.com",
				"LocalName":"China (Hangzhou)"
			},
			{
				"RegionId":"ap-southeast-3",
				"RegionEndpoint":"slb.ap-southeast-3.aliyuncs.com",
				"LocalName":"Malaysia (Kuala Lumpur)"
			}
		]
	}
}
```

Error response example

`JSON` format

``` {#json_return_failed_demo}
{
	"Message":"The specified parameter is not valid.",
	"RequestId":"0669D684-69D8-408E-A4FA-B9011E0F4E66",
	"HostId":"slb-pop.aliyuncs.com",
	"Code":"InvalidParameter"
}
```

## Error codes { .section}

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidParameter| |The parameter Bandwidth is invalid. Please check that the parameter is correct.|
|400|InvalidParameter|Illegal parameter, query.namespace is not auth.|The parameter Bandwidth is invalid. Please check that the parameter is correct.|

[Click here to view the error codes.](https://error-center.aliyun.com/status/product/Slb)

