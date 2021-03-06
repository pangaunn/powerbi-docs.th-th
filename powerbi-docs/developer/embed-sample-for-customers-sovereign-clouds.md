---
title: การฝังเนื้อหา Power BI ลงในแอปพลิเคชันสำหรับลูกค้าของคุณบนบริการคลาวด์แบบ sovereign
description: เรียนรู้วิธีการรวม หรือฝัง แดชบอร์ด ไทล์ หรือรายงาน ลงในเว็บแอปด้วย Power BI API สำหรับลูกค้าของคุณ
author: markingmyname
ms.author: maghan
manager: kfile
ms.service: powerbi
ms.component: powerbi-service
ms.topic: tutorial
ms.date: 07/26/2018
ms.openlocfilehash: c9e38f3ca1c8ee43ab9d51d621dfc7d835c39db1
ms.sourcegitcommit: 767c0d770e32e91ff28a176f79595fab523f69eb
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/02/2018
ms.locfileid: "48039450"
---
# <a name="tutorial-embed-a-power-bi-dashboard-tile-or-report-into-your-application-for-sovereign-clouds"></a>คำแนะนำการใช้งาน: ฝังในแดชบอร์ด ไทล์ หรือรายงาน Power BI ลงในแอปพลิเคชันสำหรับคลาวด์แบบ sovereign
เรียนรู้วิธีการรวม หรือฝัง แดชบอร์ด ไทล์ หรือ รายงาน ลงในแอปบนเว็บด้วย Power BI .NET SDK ตลอดจด Power BI JavaScript API สำหรับลูกค้าของคุณ นี่คือสถานการณ์ทั่วไปของ ISV

Power BI ยังสนับสนุนคลาวด์แบบ sovereign (ส่วนตัว)

Sovereign cloud ได้แก่:

* U.S. ชุมชน Cloud สำหรับรัฐบาล (GCC)

* U. S. ผู้รับเหมากองทัพ (DoDCON)

* U. S. กองทัพ (DoD)

* คลาวด์ Power BI สำหรับประเทศเยอรมนี

* Power BI สำหรับคลาวด์ประเทศจีน

![แดชบอร์ดแบบฝังตัว](media/embed-sample-for-customers/powerbi-embed-dashboard.png)

เมื่อต้องการเริ่มต้นการฝึกปฏิบัตินี้ คุณต้องการ**บัญชี Power BI** ถ้าคุณยังไม่มีบัญชีผู้ใช้ ขึ้นอยู่กับชนิดของบริการคลาวด์แบบ sovereign คุณสามารถ[ลงทะเบียนบัญชี Power BI สำหรับรัฐบาลสหรัฐ](../service-govus-signup.md) หรือ [บัญชี Power BI สำหรับผู้ใช้คลาวด์เยอรมนี](https://powerbi.microsoft.com/power-bi-germany/?ru=https%3A%2F%2Fapp.powerbi.de%2F%3FnoSignUpCheck%3D1) หรือ [Power BI สำหรับผู้ใช้คลาวด์ประเทศจีน](http://www.21vbluecloud.com/powerbi/)

> [!NOTE]
> กำลังมองหาวิธีฝังแดชบอร์ดสำหรับองค์กรของคุณแทน ดูที่ [รวมแดชบอร์ดลงในแอปสำหรับองค์กรของคุณ](integrate-dashboard.md)
>

เพื่อรวมแดชบอร์ดลงในเว็บแอป คุณใช้ **Power BI** API และ**โทเค็นการเข้าถึง**สำหรับรับรองตัวตนกับ Azure Active Directory (AD) เพื่อรับแดชบอร์ด หลังจากนั้น คุณโหลดแดชบอร์ดโดยใช้โทเค็นแบบฝังตัว **Power BI** API ให้การเข้าถึงทางการเขียนโปรแกรมสำหรับทรัพยากร **Power BI** เฉพาะ สำหรับข้อมูลเพิ่มเติม ดู[ Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/), [Power BI .NET SDK](https://github.com/Microsoft/PowerBI-CSharp) และ [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

## <a name="download-the-sample"></a>ดาวน์โหลดตัวอย่าง
บทความนี้แสดงโค้ดที่ใช้ใน [ตัวอย่างการฝังตัวสำหรับลูกค้าของคุณ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data/PowerBIEmbedded_AppOwnsData) บน GitHub ถ้าต้องการทำตามการฝึกปฏิบัตินี้ คุณสามารถดาวน์โหลดตัวอย่าง

* ชุมชน Cloud สำหรับส่วนราชการ (GCC):
    1. เขียนทับแฟ้ม Cloud.config ด้วยเนื้อหา GCCCloud.config
    2. อัปเดต clientid (รหัสไคลเอ็นต์ของเนทิฟแอป), groupid, ผู้ใช้ (ผู้ใช้หลักของคุณ) และรหัสผ่านในแฟ้ม Web.config
    3. เพิ่มพารามิเตอร์ GCC ในแฟ้ม web.config ดังนี้

```xml
<add key="authorityUrl" value="https://login.windows.net/common/oauth2/authorize/" />
<add key="resourceUrl" value="https://analysis.usgovcloudapi.net/powerbi/api" />
<add key="apiUrl" value="https://api.powerbigov.us/" />
<add key="embedUrlBase" value="https://app.powerbigov.us" />
```

* ผู้รับจ้างทางการทหาร (DoDCON):
    1. เขียนทับแฟ้ม Cloud.config ด้วยเนื้อหา TBCloud.config
    2. อัปเดต clientid (รหัสไคลเอ็นต์ของเนทิฟแอป), groupid, ผู้ใช้ (ผู้ใช้หลักของคุณ) และรหัสผ่านในแฟ้ม Web.config
    3. เพิ่มพารามิเตอร์ DoDCON ในแฟ้ม web.config ดังนี้

```xml
<add key="authorityUrl" value="https://login.windows.net/common/oauth2/authorize/" />
<add key="resourceUrl" value="https://high.analysis.usgovcloudapi.net/powerbi/api" />
<add key="apiUrl" value="https://api.high.powerbigov.us/" />
<add key="embedUrlBase" value="https://app.high.powerbigov.us" />
```

* กองทัพ (DoD):
    1. เขียนทับแฟ้ม Cloud.config ด้วยเนื้อหา PFCloud.config
    2. อัปเดต clientid (รหัสไคลเอ็นต์ของเนทิฟแอป), groupid, ผู้ใช้ (ผู้ใช้หลักของคุณ) และรหัสผ่านในแฟ้ม Web.config
    3. เพิ่มพารามิเตอร์ DoDCON ในแฟ้ม web.config ดังนี้

```xml
<add key="authorityUrl" value="https://login.windows.net/common/oauth2/authorize/" />
<add key="resourceUrl" value="https://mil.analysis.usgovcloudapi.net/powerbi/api" />
<add key="apiUrl" value="https://api.mil.powerbigov.us/" />
<add key="embedUrlBase" value="https://app.mil.powerbigov.us" />
```

* พารามิเตอร์ Power BI สำหรับคลาวด์ประเทศเยอรมนี
    1. เขียนทับแฟ้ม Cloud.config ด้วยเนื้อหา Power BI สำหรับ cloud Germany
    2. อัปเดต clientid (รหัสไคลเอ็นต์ของเนทิฟแอป), groupid, ผู้ใช้ (ผู้ใช้หลักของคุณ) และรหัสผ่านในแฟ้ม Web.config
    3. เพิ่มพารามิเตอร์ Power BI สำหรับคลาวด์เยอรมนีในแฟ้ม web.config ดังนี้

```xml
<add key="authorityUrl" value=https://login.microsoftonline.de/common/oauth2/authorize/" />
<add key="resourceUrl" value="https://analysis.cloudapi.de/powerbi/api" />
<add key="apiUrl" value="https://api.powerbi.de/" />
<add key="embedUrlBase" value="https://app.powerbi.de" />
```

* พารามิเตอร์ Power BI สำหรับคลาวด์ประเทศจีน
    1. เขียนทับแฟ้ม Cloud.config ด้วย[เนื้อหา Power BI สำหรับคลาวด์ประเทศจีน](https://github.com/Microsoft/PowerBI-Developer-Samples/blob/master/App%20Owns%20Data/PowerBIEmbedded_AppOwnsData/CloudConfigs/Power%20BI%20operated%20by%2021Vianet%20in%20China/Cloud.config)
    2. อัปเดต clientid (รหัสไคลเอ็นต์ของเนทิฟแอป), groupid, ผู้ใช้ (ผู้ใช้หลักของคุณ) และรหัสผ่านในแฟ้ม Web.config
    3. เพิ่มพารามิเตอร์ Power BI สำหรับคลาวด์ประเทศจีนในแฟ้ม web.config ดังนี้

```xml
<add key="authorityUrl" value=https://login.chinacloudapi.cn/common/oauth2/authorize/" />
<add key="resourceUrl" value="https://analysis.chinacloudapi.cn/powerbi/api" />
<add key="apiUrl" value="https://api.powerbi.cn/" />
<add key="embedUrlBase" value="https://app.powerbi.cn" />
```

## <a name="step-1---register-an-app-in-azure-ad"></a>ขั้นตอนที่ 1 - การลงทะเบียนแอปใน Azure AD
คุณจำเป็นต้องลงทะเบียนแอปพลิเคชันของคุณกับ Azure AD เพื่อเรียกใช้ REST API สำหรับข้อมูลเพิ่มเติม ดู[ลงทะเบียนแอป Azure AD เพื่อฝังเนื้อหา Power BI](register-app.md) เนื่องจากแต่ละ sovereign cloud มีหน่วยงานที่สังกัดแตกต่างกัน URL สำหรับลงทะเบียนแอปพลิเคชันของคุณจะแตกต่างกันออกไป

* ชุมชน Cloud สำหรับรัฐบาล (GCC) - https://app.powerbigov.us/apps 

* ผู้รับเหมากองทัพ (DoDCON) - https://app.high.powerbigov.us/apps 

* กองทัพ (DoD) - https://app.mil.powerbigov.us/apps

* Power BI สำหรับคลาวด์ประเทศเยอรมน - ี https://app.powerbi.de/apps

* Power BI สำหรับคลาวด์ประเทศจีน - https://app.powerbi.cn/apps

ถ้าคุณดาวน์โหลด [ตัวอย่างการฝังตัวสำหรับลูกค้าของคุณ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) คุณใช้ **Client ID** ที่คุณได้รับหลังจากลงทะเบียน เพื่อให้ตัวอย่างสามารถรับรองตัวตนกับ Azure AD เพื่อกำหนดค่าของตัวอย่าง เปลี่ยนค่า **clientId** ในไฟล์ *web.config*


## <a name="step-2---get-an-access-token-from-azure-ad"></a>ขั้นตอนที่ 2 - รับโทเค็นเพื่อเข้า จาก Azure AD
ภายในแอปพลิเคชันของคุณ คุณจะต้องรับ **โทเค็นการเข้าถึง** จาก Azure AD ก่อนที่คุณสามารถเรียกใช้ Power BI REST API ได้ สำหรับข้อมูลเพิ่มเติม ให้ดู[การรับรองตัวตนผู้ใช้และรับโทเค็นการเข้า Azure AD สำหรับแอป Power BI ของคุณ](get-azuread-access-token.md) เนื่องจากแต่ละ sovereign cloud มีหน่วยงานที่สังกัดแตกต่างกัน URL สำหรับรับโทเค็นการเข้าถึงของแอปพลิเคชันคุณจะแตกต่างกันออกไป

* ชุมชน Cloud สำหรับรัฐบาล (GCC) - https://login.microsoftonline.com

* ผู้รับเหมากองทัพ (DoDCON) - http://login.microsoftonline.us

* กองทัพ (DoD) - https://login.microsoftonline.us

* Power BI สำหรับคลาวด์ประเทศเยอรมน - ี https://login.microsoftonline.de

* Power BI สำหรับคลาวด์ประเทศจีน - https://login.microsoftonline.cn

คุณสามารถดูตัวอย่างโค้ดของเนื้อหาแต่ละขั้นตอนได้ใน **Controllers\HomeController.cs**

## <a name="step-3---get-a-content-item"></a>ขั้นตอนที่ 3 รับเนื้อหา
เมื่อต้องฝังเนื้อหา Power BI ของคุณ คุณจะจำเป็นต้องทำสิ่งสองสิ่งนี้ให้แน่ใจว่า การฝังตัวนั้นถูกต้อง ถึงแม้ว่าขั้นตอนเหล่านี้สามารถทำได้ใน REST API โดยตรง แอปพลิเคชันตัวอย่าง และตัวอย่างนี้จะใช้ .NET SDK

### <a name="create-the-power-bi-client-with-your-access-token"></a>สร้างไคลเอ็นต์ Power BI ด้วยโทเค็นการเข้าของคุณ
ด้วยโทเค็นการเข้าของคุณ คุณสามารถสร้างวัตถุไคลเอ็นต์ Power BI ซึ่งทำให้คุณสามารถโต้ตอบกับ Power BI API ทำได้โดยนำ AccessToken ไปใส่ไว้ในวัตถุ *Microsoft.Rest.TokenCredentials*

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. This is used to call the Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to embed items.
}
```

### <a name="get-the-content-item-you-want-to-embed"></a>รับเนื้อหาที่คุณต้องการฝังตัว
คุณใช้วัตถุไคลเอ็นต์ Power BI เพื่อดึงเอาตัวอ้างอิงไปยังเนื้อหา ที่คุณต้องการฝังตัว คุณสามารถฝังแดชบอร์ด ไทล์ หรือรายงาน นี่คือตัวอย่างของวิธีการดึง แดชบอร์ด ไทล์ หรือรายงานตัวแรกจากพื้นที่ทำงานที่ระบุไว้

มีตัวอย่างนี้ให้ใน **Controllers\HomeController.cs** ของ[ตัวอย่าง แอปเป็นเจ้าของข้อมูล](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

**แดชบอร์ด**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();
```

**ไทล์**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// To retrieve the tile, you first need to retrieve the dashboard.

// You need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();

// Get a list of tiles from a specific dashboard
ODataResponseListTile tiles = client.Dashboards.GetTilesInGroup(GroupId, dashboard.Id);

// Get the first tile in the group.
Tile tile = tiles.Value.FirstOrDefault();
```

**รายงาน**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You need to provide the GroupID where the dashboard resides.
ODataResponseListReport reports = client.Reports.GetReportsInGroupAsync(GroupId);

// Get the first report in the group.
Report report = reports.Value.FirstOrDefault();
```

### <a name="create-the-embed-token"></a>สร้างโทเค็นแบบฝังตัว
โทเค็นแบบฝังตัวจะต้องถูกสร้างขึ้น ซึ่งสามารถใช้ได้จาก JavaScript API โทเค็นแบบฝังตัวจะเป็นแบบเฉพาะเจาะจงกับรายการที่คุณจะฝัง ซึ่งหมายความว่า ทุกครั้งที่คุณต้องการฝังเนื้อหาของ Power BI ชิ้นหนึ่ง คุณต้องสร้างโทเค็นใหม่ขึ้นมา สำหรับข้อมูลเพิ่มเติม รวมไปถึง **accessLevel** ที่จะใช้ ดู[โทเค็นที่ฝัง](https://docs.microsoft.com/rest/api/power-bi/embedtoken)

> [!IMPORTANT]
> เนื่องจากโทเค็นแบบฝังตัวมีไว้สำหรับการทดสอบของนักพัฒนาเท่านั้น จำนวนโทเค็นแบบฝังตัวที่บัญชีหลักของ Power BI สร้างได้ มีได้จำกัด [ต้องซื้อความจุ](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical) สำหรับสถานการณ์ที่มีการฝังในโปรดักชั่น ไม่จำกัดจำนวนโทเค็นแบบฝังตัวที่สร้างเมื่อซื้อความจุแล้ว

มีตัวอย่างนี้ อยู่ใน **Controllers\HomeController.cs** ของ[ตัวอย่างการฝังตัวสำหรับองค์กรของคุณ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

ตัวอย่างต่อไปนี้ ถือว่ามีการสร้างคลาสสำหรับ **EmbedConfig** และ **TileEmbedConfig** อยู่ก่อนแล้ว ตัวอย่างมีให้ใน **Models\EmbedConfig.cs** และ **Models\TileEmbedConfig.cs**

**แดชบอร์ด**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Dashboards.GenerateTokenInGroup(GroupId, dashboard.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = dashboard.EmbedUrl,
    Id = dashboard.Id
};
```

**ไทล์**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token for a tile.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Tiles.GenerateTokenInGroup(GroupId, dashboard.Id, tile.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new TileEmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = tile.EmbedUrl,
    Id = tile.Id,
    dashboardId = dashboard.Id
};
```

**รายงาน**

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Reports.GenerateTokenInGroup(GroupId, report.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = report.EmbedUrl,
    Id = report.Id
};
```
## <a name="step-4---load-an-item-using-javascript"></a>ขั้นตอนที่ 4 - โหลดเนื้อหาโดยใช้ JavaScript
คุณสามารถใช้ JavaScript เพื่อโหลดแดชบอร์ดลงใน องค์ประกอบ div บนเว็บเพจของคุณ ตัวอย่างนี้ใช้รูปแบบ EmbedConfig/TileEmbedConfig พร้อมกับมุมมองสำหรับแดชบอร์ด ไทล์ หรือรายงาน สำหรับตัวอย่างแบบเต็มของการใช้ JavaScript API คุณสามารถใช้ [ตัวอย่างแบบฝังตัวของ Microsoft Power BI](https://microsoft.github.io/PowerBI-JavaScript/demo)

ตัวอย่างเป็นแอปพลิเคชันแบบนี้ มีอยู่ใน[ตัวอย่างการฝังตัวสำหรับองค์กรของคุณ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

**Views\Home\EmbedDashboard.cshtml**

```csharp
<script src="~/scripts/powerbi.js"></script>
<div id="dashboardContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read dashboard Id from Model
    var embedDashboardId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'dashboard',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedDashboardId
    };

    // Get a reference to the embedded dashboard HTML element
    var dashboardContainer = $('#dashboardContainer')[0];

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);
</script>
```

**Views\Home\EmbedTile.cshtml**

```csharp
<script src="~/scripts/powerbi.js"></script>
<div id="tileContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read tile Id from Model
    var embedTileId = "@Model.Id";

    // Read dashboard Id from Model
    var embedDashboardeId = "@Model.dashboardId";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedTileId,
        dashboardId: embedDashboardeId
    };

    // Get a reference to the embedded tile HTML element
    var tileContainer = $('#tileContainer')[0];

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);
</script>
```

**Views\Home\EmbedReport.cshtml**

```csharp
<script src="~/scripts/powerbi.js"></script>
<div id="reportContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read report Id from Model
    var embedReportId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedReportId,
        permissions: models.Permissions.All,
        settings: {
            filterPaneEnabled: true,
            navContentPaneEnabled: true
        }
    };

    // Get a reference to the embedded report HTML element
    var reportContainer = $('#reportContainer')[0];

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);
</script>
```

## <a name="next-steps"></a>ขั้นตอนถัดไป

* มีตัวอย่างแอปพลิเคชันบน GitHub ให้คุณได้ศึกษา ตัวอย่างต่างๆ ข้างบนมาจากตัวอย่างนั้น สำหรับข้อมูลเพิ่มเติม ให้ดูการ[ฝังตัวเพื่อตัวอย่างขององค์กรของคุณ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)
* สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ JavaScript API โปรดอ้างอิงจาก [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)
* สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ Power BI สำหรับคลาวด์ประเทศเยอรมนี โปรดอ้างอิงจาก [Power BI สำหรับคลาวด์ประเทศเยอรมนี คำถามที่ถามบ่อย](https://docs.microsoft.com/power-bi/service-govde-faq)
* [วิธีการย้ายเนื้อหาจาก Power BI Workspace Collection ไปยัง Power BI](migrate-from-powerbi-embedded.md)

ข้อจำกัดและข้อควรพิจารณา
* บัญชีผู้ใช้ GCC สนับสนุนเฉพาะความสามารถ P และ EM เท่านั้น

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)

