---
title: สร้างหน้าคำตอบของ Power BI แบบกำหนดเองสำหรับ Cortana
description: สร้างหน้าคำตอบแบบกำหนดเองสำหรับ Cortana ใน Power BI
services: powerbi
documentationcenter: ''
author: yaron
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/20/2017
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: c4816ede1ea5364e5db2156af747a3d05231d02a
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
---
# <a name="use-power-bi-service-or-power-bi-desktop-to-create-a-custom-answer-page-for-cortana"></a>ใช้บริการของ Power BI หรือ Power BI Desktop เพื่อสร้างหน้าคำตอบแบบกำหนดเองสำหรับ Cortana
ใช้ความสามารถเต็มของ Power BI เพื่อสร้างหน้ารายงานพิเศษ ที่เรียกว่า*หน้าคำตอบ Cortana* (และในบางครั้งเรียกว่า "การ์ดคำตอบ Cortana") ที่ออกแบบมาโดยเฉพาะเพื่อตอบคำถาม Cortana

![](media/service-cortana-answer-cards/power-bi-cortana.png)

> [!IMPORTANT]
> ถ้าคุณกำลังลองใช้ Cortana และ**แดชบอร์ด** Power BI ซึ่งยังเป็นคุณสมบัติตัวอย่าง คุณสามารถข้ามส่วนที่เหลือของบทความนี้ได้ ไม่ต้องมีการตั้งค่าใด ๆ เพื่อให้ Cortana สามารถค้นหาแดชบอร์ด Power BI ของคุณได้
> 
> 

## <a name="before-you-begin"></a>ก่อนที่คุณเริ่มต้น
เรามีเอกสาร 4 เอกสารที่แนะนำคุณเกี่ยวกับการตั้งค่า และใช้ Cortana สำหรับ Power BI ถ้าคุณยังไม่ได้อ่าน เราขอแนะนำให้ คุณเริ่มต้นอ่านบทความที่ 1 และบทความ 2 มีความสำคัญเป็นพิเศษ เพราะอธิบายขั้นตอนบางอย่างที่คุณจะต้องทำ ก่อนที่คุณสามารถเริ่มใช้หน้าคำตอบ Cortana

**บทความ 1** [เรียนรู้วิธีการที่ Cortana และ Power BI ทำงานร่วมกัน](service-cortana-intro.md)

**บทความ 2**:[สำหรับการค้นหารายงาน Power BI: เปิดใช้งานการทำงานร่วมกันระหว่าง Cortana - Power BI - Windows](service-cortana-enable.md)

**บทความ 3**: บทความนี้

**บทความ 4**:[แก้ไขปัญหา](service-cortana-troubleshoot.md)

## <a name="create-a-cortana-answer-page-designed-specifically-for-cortana"></a>สร้างหน้าคำตอบ Cortana ที่ออกแบบมาโดยเฉพาะสำหรับ Cortana
*หน้าคำตอบ Cortana* ในรายงานถูกปรับขนาดโดยเฉพาะสำหรับ Cortana เพื่อให้ Cortana สามารถแสดงในหน้าจอเป็นคำตอบของคำถาม  เพื่อสร้างหน้าที่มีคำตอบสำหรับ Cortana:

1. เราขอแนะนำให้เริ่มจาก[หน้ารายงานเปล่า](power-bi-report-add-page.md)
2. ในบานหน้าต่าง**การจัดรูปแบบการแสดงข้อมูล** เลือกไอคอนรูปลูกกลิ้งสี แล้วเลือก**ขนาดหน้า > ชนิด > Cortana**
   
    ![](media/service-cortana-answer-cards/pbi-cortana-page-size-new.png)
3. สร้างวิชวลหรือชุดของวิชวลที่คุณต้องการให้ปรากฏใน Cortana เพื่อเป็นคำตอบของคำถาม (หรือชุดของคำถาม) หนึ่ง
4. ตรวจสอบให้แน่ใจว่า วิชวลทั้งหมดอยู่ภายในเส้นขอบหน้า  ไม่บังคับ ปรับเปลี่ยนการตั้งค่าจอแสดงผล ป้ายชื่อข้อมูล สี และพื้นหลัง  
   
    ![](media/service-cortana-answer-cards/pbi_cortana_modify-new.png)
5. ตั้งชื่อหน้า และเพิ่มชื่อสำรอง  Cortana ใช้ชื่อเหล่านี้เมื่อค้นหาผลลัพธ์ ในบานหน้าต่าง**การจัดรูปแบบการแสดงข้อมูล** เลือกไอคอนรูปพู่กัน และเลือก**ข้อมูลเกี่ยวกับหน้า** เปิดใช้งานถามตอบสำหรับวิชวลนี้ โดยการเลื่อนแถบเลื่อนเพื่อ**เปิด**
   
    ![](media/service-cortana-answer-cards/pbi_cortana_names-newer.png)
   
   > [!TIP]
   > เพื่อปรับปรุงผลลัพธ์ หลีกเลี่ยงการใช้คำที่เป็นชื่อคอลัมน์
   > 
   > 
6. ไม่บังคับ ถ้ารายงานของคุณมีตัวกรองระดับหน้า คุณอาจต้องการตั้งค่า**จะต้องมีตัวเลือกเดี่ยว** Cortana จะแสดงรายงานนี้เป็นคำตอบ ถ้ามีรายการกรองรายการเดียวเท่านั้นที่ระบุในคำถาม **จะต้องมีตัวเลือกเดี่ยว** สามารถพบได้ด้านล่างของบานหน้าต่าง**ตัวกรอง**
   
   > [!NOTE]
   > คุณไม่จำเป็นต้องตั้งค่า**จะต้องมีตัวเลือกเดี่ยว** เพื่อให้ Cortana แสดงรายงานที่มีตัวกรองระดับหน้า  ตัวอย่างเช่น "แสดงยอดขายสำหรับ Charlotte Lindseys" จะแสดงหน้าคำตอบโดยไม่คำนึงถึงค่าของ จะต้องมีตัวเลือกเดี่ยว
   > 
   > 
   
     ![](media/service-cortana-answer-cards/pbi-cortana-single-selection-new.png)
   
      ตัวอย่างเช่น ถ้าคุณขอให้ Cortana:
   
   * “แสดงยอดขายตามชื่อร้านค้า” หน้าคำตอบนี้จะไม่ปรากฏเนื่องจากคุณไม่มีรายการใด ๆ ในตัวกรองระดับหน้า
   * “แสดงยอดขายสำหรับ Cary Lindseys และ Charlotte Lindseys” หน้าคำตอบนี้จะไม่ปรากฏ เนื่องจากคุณระบุมากกว่าหนึ่งรายการจากตัวกรองระดับหน้า
   * “แสดงยอดขายสำหรับ Charlotte Lindseys” จะแสดงคำตอบเป็นหน้านี้
     
     = "แสดงยอดขาย" หน้าคำตอบจะไม่ปรากฏขึ้น เนื่องจากคุณไม่ได้มีรายการใด ๆ ในตัวกรองระดับหน้า

> [!IMPORTANT]
> ก่อนที่หน้าคำตอบ Cortana ของคุณ สามารถเข้าถึงได้โดย Cortana คุณจะจำเป็นต้อง[เปิดใช้งานชุดข้อมูลสำหรับ Cortana](service-cortana-enable.md)
> 
> 

## <a name="how-does-cortana-order-the-results"></a>Cortana เรียงลำดับผลลัพธ์อย่างไร?
ผลลัพธ์ที่มีคะแนนคำตอบสูง (เช่นตรงกันชื่อหน้าที่ระบุทั้งหมด) จะปรากฏขึ้นเป็นอันดับแรก ในฐานะที่เป็นรายการที่*ใกล้เคียงกันมากที่สุด*ใน Cortana รายการที่ใกล้เคียงกันมากที่สุด อาจปรากฏขึ้นหลายรายการ ถ้ามีหลายหน้าคำตอบ Cortana ใน Power BI คะแนนคำตอบระดับกลาง หรือระดับต่ำ เช่นคำตอบที่ไม่มาจากชื่อของหน้าคำตอบ หรือคำถามที่ใช้คำที่ Power BI ไม่เข้าใจ จะแสดงอยู่เป็นลิงก์ข้างใต้ รายการที่ใกล้เคียงกันมากที่สุด ใน Cortana

> [!NOTE]
> เมื่อมีชุดข้อมูลใหม่ หรือมีหน้าคำตอบ Cortana แบบกำหนดเองเพิ่มไปยัง Power BI และเปิดใช้งานสำหรับ Cortana สามารถใช้เวลาถึง 30 นาทีก่อนที่ผลลัพธ์จะเริ่มปรากฏใน Cortana เข้าสู่และออกจากระบบ Windows 10 หรือรีสตาร์ตกระบวนการ Cortana ใน Windows 10 จะทำให้เนื้อหาใหม่ปรากฏขึ้นทันทีได้
> 
> 

## <a name="next-steps"></a>ขั้นตอนถัดไป
[ใช้ Cortana กับ Power BI](service-cortana-intro.md)

ยังคงไม่สามารถทำให้ Cortana ทำงานร่วมกับ Power BI ได้?  ลอง[ตัวแก้ไขปัญหา Cortana](service-cortana-troubleshoot.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)
