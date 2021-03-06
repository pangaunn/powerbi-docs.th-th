---
title: เปิดรายงานในมุมมองการอ่าน หรือมุมมองแก้ไข ในบริการของ Power BI
description: เปิดรายงาน Power BI ในมุมมองการอ่าน หรือมุมมองการแก้ไข
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: mihart
ms.openlocfilehash: fe1916b2b287dffd59bf4535cc07e13d10d01321
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/22/2018
ms.locfileid: "46565808"
---
# <a name="open-a-report-in-power-bi-service-apppowerbicom"></a>เปิดรายงานในบริการของ Power BI (app.powerbi.com)
รายงานมีในบริการของ Power BI, Power BI Desktop, Power BI สำหรับอุปกรณ์เคลื่อนที่ และแม้แต่ Power BI แบบฝังตัว บทความนี้ใช้กับการเปิดรายงานใน***บริการของ Power BI***

ในบริการของ Power BI มีสองโหมด เพื่อดูและโต้ตอบกับรายงาน: [มุมมองการอ่าน และมุมมองการแก้ไข](end-user-reading-view.md) มุมมองการอ่านมีให้สำหรับผู้ใช้ทั้งหมด และถูกออกแบบมาโดยเฉพาะสำหรับ*ผู้บริโภค*รายงาน ในขณะที่มุมมองการแก้ไขมีให้เฉพาะ*ผู้สร้าง*และเจ้าของรายงานเท่านั้น 

## <a name="open-a-report-from-a-workspace-via-the-reports-content-view-list"></a>เปิดรายงานจากพื้นที่ทำงาน (ผ่านรายการเนื้อหา**รายงาน**)

1. เริ่มต้นในพื้นที่ทำงาน และเลือกแท็บ**รายงาน** จะแสดงรายงานทั้งหมดในพื้นที่ทำงานนั้น  
   
   ![แท็บรายงานของพื้นที่ทำงาน](./media/end-user-report-open/power-bi-open-report.png)
2. เลือกชื่อรายงานที่จะเปิดในมุมมองการอ่าน  
   
    ![รายงานในมุมมองการอ่าน](./media/end-user-report-open/power-bi-reading-view.png)
3. [คุณสามารถทำอะไรได้มากมาย ในมุมมองการอ่าน](end-user-reading-view.md)  รายงานตัวอย่างนี้มีหลายหน้า ดังนั้นให้เริ่มต้นสำรวจ โดยการเลือกทีละแท็บที่ด้านล่างของพื้นที่รายงาน 

## <a name="open-a-report-from-a-dashboard"></a>เปิดรายงานจากแดชบอร์ด
ยังมีอีกหลายวิธในการเปิดรายงาน เช่น คุณสามารถเริ่มจากแดชบอร์ด และเลือกไทล์ที่ถูกสร้างขึ้นจากรายงาน  การเลือกไทล์เปิดรายงานในมุมมองการอ่าน เพื่อทดลองทำตาม [เปิดตัวอย่างแดชบอร์ด การขายและการตลาด](../sample-datasets.md)

1. เปิดแดชบอร์ด และเลือกไทล์

   ถ้าคุณเลือกไทล์ที่[ถูกสร้างขึ้นด้วยการถามตอบ](../service-dashboard-pin-tile-from-q-and-a.md) หน้าจอถามตอบจะเปิดขึ้น ถ้าคุณเลือกไทล์ที่[ถูกสร้างขึ้นโดยใช้วิดเจ็ต**เพิ่มไทล์**](../service-dashboard-add-widget.md)บนแดชบอร์ด คุณจะเปิดตัวช่วยแก้ไขวิดเจ็ตนั้น  

2.  ในตัวอย่างนี้ เราได้เลือกไทล์แผนภูมิคอลัมน์ "จำนวนหน่วยรวม ตั้งแต่ต้นปีถึงปัจจุบัน..."

    ![แดชบอร์ดพร้อมไทล์ที่เลือก](./media/end-user-report-open/power-bi-dashboard.png)

3.  รายงานที่เกี่ยวข้องจะเปิดขึ้นในมุมมองการอ่าน โปรดสังเกตว่า เรากำลังอยู่บนหน้า "ประเภท ตั้งแต่ต้นปีถึงปัจจุบัน" นี่คือหน้ารายงานที่มีแผนภูมิคอลัมน์ที่เราเลือกจากแดชบอร์ด

    ![เปิดรายงานในมุมมองการอ่าน](./media/end-user-report-open/power-bi-report.png)

4. ยังคงอยู่ในมุมมองการอ่าน หรือเลือก**แก้ไขรายงาน**เพื่อเปิดรายงานในมุมมองการแก้ไข อย่าลืมว่า เฉพาะบุคคลที่มีสิทธิ์แก้ไขรายงานเท่านั้น ที่สามารถเปิดในมุมมองการแก้ไขได้

    ![ตัวแก้ไขรายงานที่แสดงไอคอนแก้ไขรายงาน](./media/end-user-report-open/power-bi-edit-report.png)

## <a name="create-a-brand-new-report-from-a-dataset"></a>สร้างรายงานใหม่จากชุดข้อมูล
และอีกหนึ่งวิธีของการเปิดรายงาน คือจากชุดข้อมูล เมื่อคุณเริ่มจากชุดข้อมูล พื้นที่รายงานจะว่างเปล่า ดังนั้นจึงขอแนะนำวิธีนี้สำหรับ*ผู้สร้าง*รายงาน ที่สนใจจะสร้างรายงานใหม่จากชุดข้อมูลที่พวกเขามี เหมือนกับตัวอย่างด้านบน เพื่อทดลองตาม ดาวน์โหลด[ตัวอย่างแอป การขายและการตลาด](../sample-datasets.md)

1. เริ่มต้นในพื้นที่ทำงานที่มีชุดข้อมูลที่คุณต้องการใช้เป็นพื้นฐานสำหรับรายงาน

   ![แถบนำทางด้านซ้ายแสดงพื้นที่ทำงานแอป](./media/end-user-report-open/power-bi-workspace.png)

2. เลือกแท็บ**ชุดข้อมูล** จะแสดงรายการของชุดข้อมูลทั้งหมดในพื้นที่ทำงานนั้น ซึ่งเรียกว่า รายการเนื้อหา**ชุดข้อมูล**
   
   ![รายการของชุดข้อมูล](./media/end-user-report-open/power-bi-dataset.png)

1. ค้นหาชุดข้อมูล และเลือกไอคอน**สร้างรายงาน** เพื่อเปิดชุดข้อมูลในมุมมองการแก้ไข ถ้าคุณไม่มีสิทธิ์แก้ไขชุดข้อมูล คุณจะไม่สามารถเปิดได้ 
   
    ![ชุดข้อมูลที่มีไอคอนสร้างรายงาน](./media/end-user-report-open/power-bi-create-report.png)

3. ชุดข้อมูลเปิดขึ้นในตัวแก้ไขรายงาน คุณจะเห็นเขตข้อมูลแสดงอยู่ทางด้านขวา กำลังรอให้คุณเริ่มต้นสำรวจ และสร้างการแสดงภาพ 

   ![พื้นที่รายงาน](./media/end-user-report-open/power-bi-blank-canvas.png)

##  <a name="still-more-ways-to-open-a-report"></a>ยังคงวิธีอื่น ๆ ในการเปิดรายงาน
เมื่อคุณใช้บริการของ Power BI ต่าง ๆ ได้คล่องแล้ว คุณจะรู้ว่าเวิร์กโฟลว์การทำงานแบบไหนที่ดีที่สุดสำหรับคุณ สองสามวิธีอื่น ๆ ในการเข้าถึงรายงาน:
- จากการบานหน้าต่างนำทางด้านซ้าย ใช้**รายการโปรด**, **ล่าสุด**, **แอป** และ**แชร์กับฉัน** 
- ใช้[เนื้อหาที่เกี่ยวข้องกับมุมมอง](end-user-related.md)
- ในอีเมล เมื่อมีใคร[แชร์ให้กับคุณ](../service-share-reports.md) หรือคุณ[ตั้งค่าการแจ้งเตือน](../service-set-data-alerts.md)    
- จาก[ศูนย์การแจ้งเตือน](end-user-notification-center.md)ของคุณ    
- และอื่น ๆ อีกมากมาย

## <a name="next-steps"></a>ขั้นตอนถัดไป
อ่านเพิ่มเติมเกี่ยวกับ[รายงานใน Power BI](end-user-reports.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)  

