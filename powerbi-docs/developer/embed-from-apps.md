---
title: ฝังรายงานหรือแดชบอร์ดจากแอป
description: เรียนรู้วิธีการรวม หรือ ฝัง รายงานหรือแดชบอร์ด จากแอป Power BI และไม่ใช่ จากพื้นที่ทำงานแอป
author: markingmyname
ms.author: maghan
ms.date: 07/13/2018
ms.topic: how-to
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 2817ccb25fc9aa6d3e8150c776558366dcf0ccb6
ms.sourcegitcommit: 0c870a006e525447497e678484874a2f137b9abd
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/17/2018
ms.locfileid: "39088850"
---
# <a name="embed-reports-or-dashboards-from-apps"></a>ฝังรายงานหรือแดชบอร์ดจากแอป

ใน **Power BI** คุณสามารถสร้างแอปเพื่อรวม **แดชบอร์ด** และ **รายงาน** ที่เกี่ยวข้องเข้าด้วยกันทั้งหมดในที่เดียว จากนั้นเผยแพร่ไปยังกลุ่มบุคคลขนาดใหญ่ในองค์กรของคุณได้ การใช้งานแอปเหล่านั้นจะมีความเกี่ยวข้องเมื่อผู้ใช้ทั้งหมดของคุณคือผู้ใช้ Power BI เพื่อให้คุณสามารถแชร์เนื้อหากับบุคคลเหล่านั้นโดยใช้แอป Power BI ได้ เราต้องการแชร์ขั้นตอนที่รวดเร็วเกี่ยวกับวิธีการฝังเนื้อหาออกจากแอป Power BI ที่เผยแพร่ และลงในแอปพลิเคชันของบริษัทอื่น

## <a name="how-to-grab-report-embed-url-for-embedding"></a>วิธีการจับ URL ที่ฝังในรายงานสำหรับการฝัง

1. สร้างอินสแตนซ์ของแอปพลิเคชันในพื้นที่ทำงานผู้ใช้ ('พื้นที่ทำงานของฉัน') โดยการใช้ร่วมกันกับตัวคุณเอง หรือแนะนำให้ผู้ใช้อื่นเพื่อดำเนินการตามขั้นตอนนี้

2. เปิดรายงานของคุณที่ต้องการในบริการ Power BI

3. ไปที่ไฟล์ -> ฝังใน SharePoint Online และจับ URL ฝังรายงานจากที่นั่น (คุณสามารถดูสแนปช็อตด้านล่างได้) หรือติดต่อ GetReports/GetReport REST API และเขตข้อมูล embedURL ของรายงานที่เกี่ยวข้องออกจากการตอบสนอง (โปรดทราบว่า การเรียกใช้ REST ไม่ควรมีตัวระบุพื้นที่ทำงานเป็นส่วนหนึ่งของ URL เช่นเดียวกับแอปที่ได้รับข้อความสร้างอินสแตนซ์ในพื้นที่ทำงานของผู้ใช้)

4. ใช้ URL ฝังตัวดึงข้อมูลในขั้นตอนที่ 3 เพื่อใช้กับ JS SDK

    ![ฝังตัวสำหรับแอป](media/embed-from-apps/embed-from-app.png)

## <a name="how-to-grab-dashboard-embed-url-for-embedding"></a>วิธีการจับ URL ที่ฝังในแดชบอร์ดสำหรับการฝัง

1. สร้างอินสแตนซ์ของแอปพลิเคชันในพื้นที่ทำงานผู้ใช้ ('พื้นที่ทำงานของฉัน') โดยการใช้ร่วมกันกับตัวคุณเอง หรือแนะนำให้ผู้ใช้อื่นเพื่อดำเนินการตามขั้นตอนนี้

2. โทรหา GetDashboards REST API และแยกเขตข้อมูล embedURL แดชบอร์ดเกี่ยวข้องออกจากการตอบสนอง (โปรดทราบว่า การเรียกใช้ REST ไม่ควรมีตัวระบุพื้นที่ทำงานเป็นส่วนหนึ่งของ URL ตามที่แอปได้รับการสร้างอินสแตนซ์ในพื้นที่ทำงานของผู้ใช้)

3. ใช้ URL ฝังตัวดึงข้อมูลในขั้นตอนที่ 4 เพื่อใช้กับ JS SDK ของเรา

## <a name="next-steps"></a>ขั้นตอนถัดไป

นอกจากนี้ ยังตรวจสอบวิธีการฝังตัวจากพื้นที่ทำงานแอปสำหรับลูกค้าของบริษัทอื่นและองค์กรของคุณ

> [!div class="nextstepaction"]
>[ฝังตัวสำหรับลูกค้าของบริษัทอื่น](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[ฝังตัวสำหรับองค์กรของคุณ](embed-sample-for-your-organization.md)