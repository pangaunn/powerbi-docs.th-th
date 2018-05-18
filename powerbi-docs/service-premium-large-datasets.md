---
title: Power BI Premium รองรับชุดข้อมูลขนาดใหญ่
description: Power BI Premium ขณะนีรองรับชุดข้อมูลสูงสุด 10 GB
services: powerbi
documentationcenter: ''
author: MarkMcGeeAtAquent
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
ms.date: 02/27/2018
ms.author: jocaplan
LocalizationGroup: Premium
ms.openlocfilehash: def06965692644c0328dae7a1d0ade8d13cc0d6c
ms.sourcegitcommit: 743e44fc8730fea0f7149916080b0c6d7eb6359d
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/28/2018
---
# <a name="power-bi-premium-support-for-large-datasets"></a>Power BI Premium รองรับชุดข้อมูลขนาดใหญ่

Power BI Premium รองรับการอัปโหลดไฟล์ชุดข้อมูล Power BI Desktop (.pbix) ที่มีขนาดสูงสุด 10 GB เมื่ออัปโหลดเสร็จ ชุดข้อมูลที่สามารถถูกรีเฟรชถึงขนาดสูงสุด 12 GB เมื่อต้องใช้ชุดข้อมูลขนาดใหญ่ ให้เผยแพร่ไปยังพื้นที่ทำงานที่กำหนดให้เป็นแบบความจุ premium
 
## <a name="best-practices"></a>แนวทางปฏิบัติที่ดีที่สุด

ส่วนนี้อธิบายแนวทางปฏิบัติที่ดีที่สุดสำหรับการทำงานกับชุดข้อมูลขนาดใหญ่

**รูปแบบขนาดใหญ่สามารถใช้ทรัพยากรมาก**ในความจุของคุณ เราขอแนะนำอย่างน้อย P1 SKU สำหรับแบบจำลองมีขนาดใหญ่กว่า 1 GB ตารางต่อไปนี้อธิบายถึง SKU ที่แนะนำสำหรับขนาด.pbix ต่าง ๆ


   |SKU  |ขนาดของ.pbix   |
   |---------|---------|
   |P1    | < 3 GB        |
   |P2    | < 6 GB        |
   |P3    | สูงสุด 10 GB   |



**ไฟล์.pbix ของคุณแสดงข้อมูลในสถานะที่มีการบีบอัดสูง** ข้อมูลจะมีแนวโน้มว่าจะขยายหลาย ๆ ครั้งเมื่อโหลดในหน่วยความจำ และจากที่นั่น อาจจะขยายหลายครั้งในระหว่างการรีเฟรชข้อมูล

**รีเฟรชตามกำหนดเวลาของชุดข้อมูลขนาดใหญ่สามารถใช้เวลานาน**และใช้ทรัพยากรมาก ดังนั้นอย่ากำหนดเวลาการรีเฟรชที่ซ้อนทับกันมากเกินไป โปรดสังเกตว่า การหมดเวลาของงานรีเฟรชตามกำหนดเวลาถูกเพิ่มเป็นสองเท่าเท่ากับสี่ชั่วโมงสำหรับชุดข้อมูลทั้งหมดในความจุนี้

**การโหลดรายงานเริ่มต้นของชุดข้อมูลขนาดใหญ่สามารถใช้เวลานาน** ถ้าระยะเวลาหนึ่งแล้วตั้งแต่ครั้งสุดท้ายที่ใช้ชุดข้อมูล เนื่องจากโมเดลถูกโหลดลงในหน่วยความจำของความจุพรีเมี่ยมของคุณ แถบโหลดสำหรับรายงานยาวการโหลดแสดงความคืบหน้าของการโหลด

**ถ้าคุณลบพื้นที่ทำงานจากความจุพรีเมี่ยม** แบบจำลอง รายงานที่เกี่ยวข้องทั้งหมดและแดชบอร์ดจะทำงานไม่ได้

**ในขณะที่หน่วยความจำและเวลาสำหรับแต่ละคิวรีสูงกว่าความจุพรีเมียม** ขอแนะนำคุณใช้ตัวกรองและตัวแบ่งส่วนข้อมูล เพื่อจำกัดใหรูปแสดงเฉพาะสิ่งที่จำเป็น

## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI Premium คืออะไร](service-premium.md)  
[บันทึกย่อประจำรุ่นของ Power BI Premium](service-premium-release-notes.md)  
[เอกสารทางเทคนิคเรื่อง Microsoft Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  
[เอกสารทางเทคนิคเรื่องการวางแผนการใช้ Power BI สำหรับองค์กร](https://aka.ms/pbienterprisedeploy)  
[เปิดใช้งานเวอร์ชันทดลองใช้ Extended Pro ](service-extended-pro-trial.md)  

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)