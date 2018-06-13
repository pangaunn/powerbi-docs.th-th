---
title: เชื่อมต่อกับ Zendesk ด้วย Power BI
description: Zendesk สำหรับ Power BI
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 52adef9d30ec269e6e3a954632a54814b241623d
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815323"
---
# <a name="connect-to-zendesk-with-power-bi"></a>เชื่อมต่อกับ Zendesk ด้วย Power BI
ชุดเนื้อหา Zendesk นำเสนอแดชบอร์ด Power BI และชุดของรายงาน Power BI ที่มีข้อมูลเชิงลึกเกี่ยวกับปริมาณตั๋วและประสิทธิภาพการทำงานของบริษัทตัวแทน คุณสามารถใช้แดชบอร์ดและรายงานที่มีให้ได้ หรือปรับแต่งเพื่อไฮไลท์ข้อมูลที่คุณสนใจมากที่สุด  ข้อมูลจะรีเฟรชโดยอัตโนมัติหนึ่งครั้งต่อวัน 

เชื่อมต่อไปยัง[ชุดเนื้อหา Zendesk](https://app.powerbi.com/getdata/services/zendesk)หรืออ่านเพิ่มเติมเกี่ยวกับการ[รวม Zendesk](https://powerbi.microsoft.com/integrations/zendesk)กับ Power BI

>[!NOTE]
>จำเป็นต้องมีบัญชีผู้ดูแลระบบ Zendesk เพื่อเชื่อมต่อ รายละเอียดเพิ่มเติมเกี่ยวกับ[ข้อกำหนด](#Requirements)ที่ด้านล่าง

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือก**รับข้อมูล**ที่ด้านล่างของแผงนำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-zendesk/pbi_getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-zendesk/pbi_getservices.png) 
3. เลือก**Zendesk** \> **รับ**
   
   ![](media/service-connect-to-zendesk/zendesk.png)
4. ให้ URL ที่เชื่อมโยงกับบัญชีของคุณ นี่จะเป็นในรูปแบบ**https://company.zendesk.com**ดูรายละเอียดบน[ค้นหาพารามิเตอร์เหล่านี้](#FindingParams)ที่ด้านล่าง
   
   ![](media/service-connect-to-zendesk/pbi_zendeskconnect.png)
5. เมื่อมีข้อความปรากฏ ใส่ข้อมูลประจำตัวของ Zendesk  เลือก**oAuth 2**เป็นกลไกการรับรองความถูกต้อง แล้วคลิก**ลงชื่อเข้าใช้** ทำตามขั้นตอนการรับรองความถูกต้อง Zendesk (ถ้าคุณลงชื่อเข้าใช้ Zendesk อยู่แล้วในเบราว์เซอร์ของคุณ คุณอาจไม่ได้รับข้อความปรากฏให้ใส่ข้อมูลประจำตัว)
   
   > [!NOTE]
   > คุณต้องเชื่อมต่อกับบัญชีผู้ดูแลระบบ Zendesk สำหรับชุดเนื้อหานี้ 
   > 
   > 
   
   ![](media/service-connect-to-zendesk/pbi_zendesksignin.png)
6. คลิก**อนุญาต**เพื่ออนุญาตให้ Power BI เข้าถึงข้อมูล Zendesk ของคุณ
   
   ![](media/service-connect-to-zendesk/zendesk2.jpg)
7. คลิก **เชื่อมต่อ** เพื่อเริ่มกระบวนการนำเข้า หลังจาก Power BI นำเข้าข้อมูล คุณเห็นแดชบอร์ด รายงาน และชุดข้อมูลใหม่ในแผงนำทางด้านซ้าย รายการใหม่จะถูกทำเครื่องหมายด้วย เครื่องหมายดอกจันสีเหลือง\*
   
   ![](media/service-connect-to-zendesk/pbi_zendeskdash.png)

**ฉันต้องทำอะไรต่อ?**

* ลอง[ถามคำถามในกล่องถามตอบ](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานพื้นฐาน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
ชุดเนื้อหา Power BI ประกอบด้วยข้อมูลต่อไปนี้:  

* ผู้ใช้ (ผู้ใช้ปลายทางและตัวแทน)  
* องค์กร  
* กลุ่ม  
* ตั๋ว  

นอกจากนี้ยังมีชุดของหน่วยวัดที่มีการคำนวณ เช่น เวลาเฉลี่ยในการรอและจำนวนตั๋วที่ได้รับการแก้ไขใน 7 วันที่ผ่าน รายการทั้งหมดจะรวมอยู่ในชุดเนื้อหา

<a name="Requirements"></a>

## <a name="system-requirements"></a>ข้อกำหนดของระบบ
บัญชีผู้ดูแลระบบ Zendesk จำเป็นสำหรับการเข้าถึงชุดเนื้อหา Zendesk ถ้าคุณตัวแทนหรือเป็นผู้ใช้ปลายทาง และคุณสนใจดูข้อมูล Zendesk ของคุณ โปรดเพิ่มคำแนะนำและตรวจทานตัวเชื่อมต่อ Zendesk ในการ[Power BI Desktop](desktop-connect-to-data.md)

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>การค้นหาพารามิเตอร์
URL ของ Zendesk ของคุณจะเหมือนกับ URL ที่คุณใช้เพื่อลงชื่อเข้าใช้บัญชี Zendesk ของคุณ ถ้าคุณไม่แน่ใจใน URL ของ Zendesk ของคุณ คุณสามารถใช้ตัว[ช่วยเหลือในการเข้าสู่ระบบ](https://www.zendesk.com/login/) สำหรับ Zendesk ได้

## <a name="troubleshooting"></a>การแก้ไขปัญหา
ถ้าคุณมีปัญหาในการเชื่อมต่อ กรุณาตรวจสอบ URL ของ Zendesk ของคุณ และยืนยันว่าคุณกำลังใช้บัญชีผู้ดูแลระบบ Zendesk

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [เริ่มต้นใช้งาน Power BI](service-get-started.md)
* [รับข้อมูล](service-get-data.md)
