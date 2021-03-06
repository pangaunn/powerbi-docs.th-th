---
title: เชื่อมต่อกับ MailChimp ด้วย Power BI
description: MailChimp สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: f54841b77d79854334ddb6d93ccdc9b5926201ac
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/29/2018
ms.locfileid: "37136723"
---
# <a name="connect-to-mailchimp-with-power-bi"></a>เชื่อมต่อกับ MailChimp ด้วย Power BI
ชุดเนื้อหา Power BI จะดึงข้อมูลจากบัญชี MailChimp ของคุณและสร้างแดชบอร์ด ชุดรายงาน และชุดข้อมูล เพื่อให้คุณสามารถสำรวจข้อมูลของคุณได้ ดึงการวิเคราะห์เพื่อสร้าง[แดชบอร์ด MailChimp](https://powerbi.microsoft.com/integrations/mailchimp)และระบุแนวโน้มภายในของการส่งเสริมการขาย รายงาน และผู้สมัครใช้งานแต่ละรายการของคุณได้อย่างรวดเร็ว ข้อมูลจะถูกตั้งค่าการรีเฟรชเป็นรีเฟรชทุกวัน เพื่อแน่ใจว่าข้อมูลที่คุณกำลังตรวจติดตามอัปเดตแล้ว

เชื่อมต่อกับ[ชุดเนื้อหา MailChimp ](https://app.powerbi.com/getdata/services/mailchimp)สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
    ![](media/service-connect-to-mailchimp/pbi_getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-mailchimp/pbi_getservices.png)
3. เลือก**MailChimp** \> **รับ**
   
   ![](media/service-connect-to-mailchimp/mailchimp.png)
4. สำหรับวิธีการรับรองความถูกต้อง ให้เลือก **oAuth2** \> **ลงชื่อเข้าใช้**
   
    เมื่อถูกถาม ให้ใส่ข้อมูลประจำตัว MailChimp ของคุณและทำตามกระบวนการรับรองตัวตน
   
    ในครั้งแรกที่คุณเชื่อมต่อ จะปรากฏข้อความให้คุณอนุญาต Power BI ให้เข้าถึงบัญชีของคุณแบบอ่านอย่างเดียว เลือก**อนุญาต**เพื่อเริ่มกระบวนการนำเข้า ซึ่งอาจใช้เวลาสักครู่ทั้งนี้ขึ้นอยู่กับปริมาณของข้อมูลในบัญชีของคุณ
   
    ![](media/service-connect-to-mailchimp/allow.png)
5. หลังจากที่ Power BI นำเข้าข้อมูลแล้ว คุณจะเห็นแดชบอร์ด รายงาน และชุดข้อมูลใหม่ ในบานหน้าต่างนำทางด้านซ้ายมือ นี่คือแดชบอร์ดตามเริ่มต้นที่ Power BI สร้างขึ้นเพื่อแสดงข้อมูลของคุณ คุณสามารถปรับเปลี่ยนแดชบอร์ดนี้เพื่อแสดงข้อมูลของคุณด้วยวิธีใดก็ตามที่คุณต้องการ
   
   ![](media/service-connect-to-mailchimp/pbi_mailchimpnewdash.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานด้านใน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI คืออะไร](power-bi-overview.md)

[Power BI แนวคิดพื้นฐาน](service-basic-concepts.md)

