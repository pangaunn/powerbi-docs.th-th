---
title: เชื่อมต่อกับ Lithium ด้วย Power BI
description: Lithium สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6cbd67a9c35726830fc862326d9a015b96952b83
ms.sourcegitcommit: fbb7924603f8915d07b5e6fc8f4d0c7f70c1a1e1
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/02/2018
ms.locfileid: "37136306"
---
# <a name="connect-to-lithium-with-power-bi"></a>เชื่อมต่อกับ Lithium ด้วย Power BI
Lithium สร้างความสัมพันธ์ที่น่าเชื่อถือระหว่างแบรนด์ที่ดีที่สุดในโลกกับลูกค้าของตน ช่วยให้ผู้คนได้รับคำตอบสำหรับคำถามและแชร์ประสบการณ์การใช้งานของตน ด้วยการเชื่อมต่อชุดเนื้อหา Lithium ไปยัง Power BI คุณสามารถวัดหน่วยวัดหลักเกี่ยวกับชุมชนออนไลน์ของคุณได้ เพื่อช่วยขับเคลื่อนการขาย ลดต้นทุนการบริการ และเพิ่มความซื่อสัตย์ต่อแบรนด์ 

เชื่อมต่อไปยัง[ชุดเนื้อหา Lithium](https://app.powerbi.com/getdata/services/lithium) สำหรับ Power BI

>[!NOTE]
>ชุดเนื้อหา Power BI ใช้ Lithium API การเรียกใช้ API มากเกินไปอาจมีค่าธรรมเนียมเพิ่มเติมจาก Lithium โปรดตรวจสอบกับผู้ดูแลระบบ Lithium ของคุณ

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-lithium/pbi_getdata.png) 
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-lithium/pbi_getservices.png) 
3. เลือก**Lithium** \> **รับ**
   
   ![](media/service-connect-to-lithium/lithiumconnect.png)
4. ใส่ URL ของชุมชน Lithium ของคุณ ซึ่งจะอยู่ในรูปแบบ *https://community.yoursite.com*
   
   ![](media/service-connect-to-lithium/params.png)
5. เมื่อมีข้อความปรากฏ ใส่ข้อมูลประจำตัวของ Lithium เลือก**oAuth 2**เป็นกลไกการรับรองความถูกต้อง แล้วคลิก**ลงชื่อเข้าใช้**และทำตามขั้นตอนการรับรองความถูกต้อง Lithium
   
   ![](media/service-connect-to-lithium/creds.png)
   
   ![](media/service-connect-to-lithium/creds2.png)
6. เมื่อขั้นตอนการเข้าสู่ระบบเสร็จสมบูรณ์ ระบบจะเริ่มกระบวนการนำเข้า เมื่อเสร็จสิ้น แดชบอร์ดใหม่ รายงาน และแบบจำลองจะปรากฏในบานหน้าต่างนำทาง เลือกแดชบอร์ดเพื่อดูข้อมูลที่นำเข้าของคุณ
   
    ![](media/service-connect-to-lithium/lithium.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานด้านใน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="system-requirements"></a>ข้อกำหนดของระบบ
ชุดเนื้อหา Lithium ต้องมีชุมชน Lithium v15.9 หรือเวอร์ชันสูงกว่า โปรดตรวจสอบกับผู้ดูแลระบบ Lithium ของคุณเพื่อยืนยัน

## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI คืออะไร](power-bi-overview.md)

[Power BI แนวคิดพื้นฐาน](service-basic-concepts.md)

