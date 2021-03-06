---
title: การฝังด้วย Power BI
description: Power BI มี API สำหรับฝังแดชบอร์ดและรายงานของคุณลงในแอปพลิเคชัน
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: overview
ms.date: 07/31/2018
ms.openlocfilehash: 2889345c5e4a5e93602c51baa27bf2c7e28e138f
ms.sourcegitcommit: 16098be04df05bc8e3d44a99b4d143b622759c59
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/07/2018
ms.locfileid: "39616039"
---
# <a name="embedding-with-power-bi"></a>การฝังด้วย Power BI

บริการ Power BI (SaaS) และบริการ Power BI Embedded ใน Azure (PaaS) มี API สำหรับการฝังสำหรับแดชบอร์ดและรายงาน ซึ่งหมายความว่าคุณมีชุดความสามารถและการเข้าถึงคุณลักษณะล่าสุดของ Power BI อย่างเช่น แดชบอร์ด เกตเวย์ และพื้นที่ทำงานแอปฯ เมื่อทำการฝังเนื้อหา

คุณสามารถเข้าถึง[เครื่องมือประสบการณ์การเตรียมความพร้อม](https://aka.ms/embedsetup) เพื่อเริ่มต้นใช้งานได้อย่างรวดเร็ว และดาวน์โหลดแอปพลิเคชันตัวอย่างได้

เลือกโซลูชันที่เหมาะกับคุณ:

* [การฝังตัวสำหรับองค์กรของคุณ](embedding.md#embedding-for-your-organization) ให้คุณสามารถขยายบริการของ Power BI เรียกใช้โซลูชัน[การฝังตัวสำหรับองค์กรของคุณ](https://aka.ms/embedsetup/UserOwnsData)
* [การฝังตัวสำหรับลูกค้าของคุณ](embedding.md#embedding-for-your-customers) จะมอบความสามารถในการฝังแดชบอร์ดและรายงานสำหรับผู้ใช้ที่ไม่มีบัญชี Power BI เรียกใช้โซลูชัน[การฝังตัวสำหรับลูกค้าของคุณ](https://aka.ms/embedsetup/AppOwnsData)

![ตัวอย่าง PBIE](media/what-can-you-do/what-can-you-do-02.png)

## <a name="using-apis"></a>การใช้งาน API

มีสองสถานการณ์หลักเมื่อมีการฝังเนื้อหา Power BI  การฝังสำหรับผู้ใช้ในองค์กรของคุณ (ที่มีใบอนุญาต Power BI) และการฝังสำหรับผู้ใช้และลูกค้าของคุณโดยที่พวกเขาไม่จำเป็นต้องมีใบอนุญาต Power BI Power BI REST API ใช้ได้สำหรับทั้งสองสถานการณ์

สำหรับลูกค้าและผู้ใช้ที่มีใบอนุญาต Power BI คุณสามารถฝังแดชบอร์ดและรายงานลงในแอปพลิเคชันแบบกำหนดเองโดยใช้ API เดียวกันเพื่อให้บริการแก่องค์กรหรือลูกค้าของคุณ ลูกค้าของคุณจะเห็นข้อมูลที่จัดการโดยแอปพลิเคชัน อีกเรื่องหนึ่งคือ สำหรับผู้ใช้ Power BI ในองค์กรของคุณ พวกเขาจะมีทางเลือกเพิ่มเติมในการดู*ข้อมูลของพวกเขา*ได้โดยตรงใน Power BI หรือบริบทของแอปพลิเคชันแบบฝัง คุณสามารถใช้ประโยชน์สูงสุดจาก JavaScript และ REST API สำหรับความต้องการในการฝังของคุณ

เมื่อต้องการดูตัวอย่างของวิธีการทำงานของการฝัง โปรดดู[ตัวอย่างการฝัง JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/)

## <a name="embedding-for-your-organization"></a>การฝังสำหรับองค์กรของคุณ

**การฝังตัวสำหรับองค์กรของคุณ** ให้คุณสามารถขยายบริการของ Power BI การฝังสำหรับองค์กรของคุณจำเป็นต้องให้ผู้ใช้แอปพลิเคชันของคุณลงชื่อเข้าใช้บริการของ Power BI เมื่อพวกเขาต้องการดูเนื้อหาของพวกเขา เมื่อบุคคลอื่นในองค์กรลงชื่อเข้าใช้ พวกเขาจะสามารถเข้าถึงแดชบอร์ดและรายงานที่พวกเขาเป็นเจ้าของ หรือที่แชร์กับบุคคลเหล่านั้นในบริการ Power BI เท่านั้น

*ตัวอย่างการฝังสำหรับองค์กรของคุณรวมถึงแอปพลิเคชันภายใน เช่น [SharePoint Online](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/), [การทำงานรวมกับ Microsoft Teams (คุณต้องมีสิทธิ์ผู้ดูแลระบบ) ](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/)และ [Microsoft Dynamics](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard)*

สำหรับการฝังสำหรับองค์กรของคุณ โปรดดูข้อมูลต่อไปนี้:

* [รวมรายงานลงในแอป](embed-sample-for-your-organization.md)

ความสามารถในการทำงานด้วยตนเอง เช่น แก้ไข บันทึก และอื่นๆ จะพร้อมใช้งานผ่าน [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript) เมื่อมีการฝังสำหรับผู้ใช้ Power BI

คุณสามารถใช้ [เครื่องมือประสบการณ์การเตรียมความพร้อม](https://aka.ms/embedsetup/UserOwnsData)เพื่อฝังสำหรับองค์กรของคุณ เพื่อเริ่มต้นอย่างรวดเร็วและดาวน์โหลดแอปพลิเคชันตัวอย่างที่จะพาคุณผ่านการรวมรายงานสำหรับองค์กรของคุณ

## <a name="embedding-for-your-customers"></a>การฝังสำหรับลูกค้าของคุณ

**การฝังสำหรับลูกค้าของคุณ**ช่วยให้คุณฝังแดชบอร์ดและรายงานสำหรับผู้ใช้ที่ไม่มีบัญชี Power BI การฝังสำหรับลูกค้าของคุณจะถูกเรียกว่า**Power BI Embedded** ด้วย

[Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md) เป็นบริการของ **Microsoft Azure** ที่ช่วยให้นักพัฒนาและผู้จำหน่ายซอฟต์แวร์อิสระ (ISV) ฝังภาพ รายงาน และแดชบอร์ดลงในแอปพลิเคชันในรูปแบบข้อมูลที่มีการวัดเป็นรายชั่วโมงตามความจุได้อย่างรวดเร็ว

![การฝังโฟลว์การฝังสำหรับลูกค้าของคุณ](media/embedding/powerbi-embed-flow.png)

Power BI Embedded มีประโยชน์สำหรับ ISV นักพัฒนาซอฟต์แวร์ และลูกค้า ตัวอย่างเช่น ISV สามารถเริ่มต้นสร้างภาพฟรีด้วย Power BI Desktop ISV สามารถบรรลุเวลาในการทำตลาดได้เร็วขึ้นโดยลดความพยายามในการพัฒนาเชิงวิเคราะห์ทางภาพให้เหลือน้อยที่สุดและโดดเด่นท่ามกลางการแข่งขันด้วยประสบการณ์ด้านข้อมูลที่แตกต่างกัน ISV ยังสามารถเลือกการชำระค่าบริการระดับ premium สำหรับค่าเพิ่มเติมที่สร้างโดยระบบการวิเคราะห์ที่ฝังมาด้วย

ด้วย Power BI Embedded ลูกค้าของคุณไม่จำเป็นต้องทราบอะไรเลยเกี่ยวกับ Power BI เพียงแค่คุณมีบัญชี Power BI Pro เพื่อสร้างแอปพลิเคชันแบบฝังตัวเท่านั้น บัญชี Power BI Pro ทำหน้าที่เป็นบัญชีหลักสำหรับแอปพลิเคชัน (ให้คิดว่านี่เป็นบัญชีพร็อกซี) นอกจากนี้บัญชี Power BI Pro ยังให้คุณสร้างโทเค็นแบบฝังสำหรับให้สิทธิ์เข้าถึงแดชบอร์ดและรายงานภายในบริการ Power BI ที่เป็นเจ้าของ/จัดการโดยแอปพลิเคชันของคุณ

นักพัฒนาที่ใช้ Power BI Embedded สามารถเน้นการสร้างความสามารถหลักของแอปพลิเคชันแทนที่จะใช้เวลาพัฒนาภาพและการวิเคราะห์ นักพัฒนาซอฟต์แวร์สามารถตอบสนองความต้องการด้านรายงานและแดชบอร์ดของลูกค้าได้อย่างรวดเร็วและสามารถฝังได้ง่ายด้วย API และ SDK ที่ได้รับการจัดทำขึ้นเป็นเอกสารอย่างครบถ้วน การเปิดใช้งานการสำรวจข้อมูลที่ค้นหาได้ง่ายในแอปทำให้ ISV ช่วยให้ลูกค้าทำการตัดสินใจได้อย่างรวดเร็วเนื่องจากมีข้อมูลจากอุปกรณ์

> [!IMPORTANT]
> แม้ว่าการฝังจะมีการขึ้นต่อกันบนบริการ Power BI แต่ไม่มีการขึ้นต่อกันบน Power BI สำหรับลูกค้าของคุณ พวกเขาจึงไม่ต้องลงทะเบียนใช้งาน Power BI เพื่อดูเนื้อหาที่ฝังในแอปของคุณ

เมื่อคุณพร้อมที่จะย้ายไปยังการผลิต ต้องกำหนดความจุเฉพาะให้กับพื้นที่ทำงานของแอป Power BI Embedded ใน Microsoft Azure มี [ความจุเฉพาะ](azure-pbie-create-capacity.md)ให้ใช้กับแอปพลิเคชันของคุณ

สำหรับข้อมูลเกี่ยวกับวิธีฝังเนื้อหาของคุณ โปรดดู[วิธีฝัง Power BI แดชบอร์ด รายงาน และไทล์](embed-sample-for-customers.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป

ตอนนี้คุณสามารถลองฝังเนื้อหา Power BI ไปยังแอปพลิเคชัน หรือลองฝังเนื้อหา Power BI สำหรับลูกค้าของคุณ

> [!div class="nextstepaction"]
> [ฝังตัวสำหรับองค์กรของคุณ](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Power BI Embedded คืออะไร](azure-pbie-what-is-power-bi-embedded.md)

> [!div class="nextstepaction"]
>[ฝังสำหรับลูกค้าของคุณ](embed-sample-for-customers.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)