---
title: กำหนดค่าการเข้าถึงเซิร์ฟเวอร์รายงานจากระยะไกล สำหรับแอปอุปกรณ์เคลื่อนที่ iOS ของ Power BI
description: เรียนรู้วิธีการกำหนดค่าแอปอุปกรณ์เคลื่อน iOS สำหรับเซิร์ฟเวอร์รายงานของคุณจากระยะไกล
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/22/2018
ms.author: maggies
ms.openlocfilehash: bbade67c9510b8d316364d991c09444712309514
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/26/2018
ms.locfileid: "34722189"
---
# <a name="configure-power-bi-ios-mobile-app-access-to-a-report-server-remotely"></a>กำหนดค่าการเข้าถึงเซิร์ฟเวอร์รายงานจากระยะไกล สำหรับแอปอุปกรณ์เคลื่อนที่ iOS ของ Power BI

ในบทความนี้ เรียนรู้วิธีการใช้เครื่องมือ MDM ขององค์กรของคุณเพื่อกำหนดค่าการเข้าถึงแอปอุปกรณ์เคลื่อนที่ iOS ของ Power BI ไปยังเซิร์ฟเวอร์รายงาน เมื่อต้องการตั้งค่า ผู้ดูแลระบบ IT สร้างนโยบายการกำหนดค่าแอปด้วยข้อมูลที่จำเป็นเพื่อที่จะส่งไปยังแอป 

 จากนั้น ผู้ใช้แอป Power BI สำหรับอุปกรณ์เคลื่อนที่ iOS สามารถเชื่อมต่อกับเซิร์ฟเวอร์รายงานขององค์กรได้ง่ายขึ้น เนื่องจากมีการกำหนดค่าการเชื่อมต่อเซิร์ฟเวอร์รายงานไว้แล้ว 


## <a name="create-the-app-configuration-policy-in-mdm-tool"></a>สร้างนโยบายการกำหนดค่าแอปในเครื่องมือ MDM 

ในฐานะผู้ดูแลระบบ ต่อไปนี้คือขั้นตอนที่คุณทำตามใน Microsoft Intune เพื่อสร้างนโยบายการกำหนดค่าแอป ขั้นตอนและประสบการณ์การสร้างนโยบายการกำหนดค่าแอปอาจแตกต่างกันในเครื่องมือ MDM อื่น ๆ 

1. เชื่อมต่อเครื่องมือ MDM ของคุณ 
2. สร้างและตั้งชื่อนโยบายการกำหนดค่าแอปใหม่ 
3. เลือกผู้ใช้ที่คุณจะแจกจ่ายนโยบายกำหนดค่าแอปนี้ไปให้ 
4. สร้างคู่คีย์-ค่า 

ตารางต่อไปนี้กล่าวถึงคู่ต่าง ๆ

|คีย์  |ชนิด  |คำอธิบาย  |
|---------|---------|---------|
| com.microsoft.powerbi.mobile.ServerURL | สตริง | URL เซิร์ฟเวอร์รายงาน </br> ควรเริ่มต้นด้วย http/https |
| com.microsoft.powerbi.mobile.ServerUsername | สตริง | [เป็นทางเลือก] </br> ชื่อผู้ใช้เพื่อใช้สำหรับการเชื่อมต่อเซิร์ฟเวอร์ </br> หากไม่มีชื่ออยู่ แอปจะปรากฏข้อควมให้ผู้ใช้ให้พิมพ์ชื่อผู้ใช้สำหรับการเชื่อมต่อ| 
| com.microsoft.powerbi.mobile.ServerDisplayName | สตริง | [เป็นทางเลือก] </br> ค่าเริ่มต้นเป็น "เซิร์ฟเวอร์รายงาน" </br> ชื่อที่เรียกง่ายที่ใช้ในแอปเพื่อเป็นตัวแทนเซิร์ฟเวอร์ | 
| com.microsoft.powerbi.mobile.OverrideServerDetails | บูลีน | ค่าเริ่มต้นเป็น True </br> ถ้าตั้งค่าเป็น "True" ขั้นตอนนี้จะแทนที่การกำหนดเซิร์ฟเวอร์รายงานใด ๆ ที่มีอยู่ในอุปกรณ์เคลื่อนที่ (เซิร์ฟเวอร์ที่มีอยู่ที่ได้รับการกำหนดค่าจะถูกลบไป) </br> การแทนการตั้งค่าเป็น True ยังช่วยป้องกันไม่ให้ผู้ใช้ลบการกำหนดค่านั้นด้วย </br> การตั้งค่าเป็น "False" จะเพิ่มค่าที่ส่ง โดยอปล่อยให้มีการใช้การตั้งค่าใด ๆ ที่มีอยู่ต่อไป </br> ถ้า URL เซิร์ฟเวอร์เดียวกันถูกกำหนดค่าแล้วในแอปอุปกรณ์เคลื่อนที่ แอปจะปล่อยให้เป็นค่าที่กำหนดดังกล่าวและไม่ขอให้ผู้ใช้รับรองความถูกต้องสำหรับเซิร์ฟเวอร์เดียวกันอีกครั้ง |

นี่คือตัวอย่างของการตั้งค่านโยบายการกำหนดค่าโดยใช้ Intune

![การตั้งค่าการกำหนดค่า Intune](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configuration-settings.png)

## <a name="end-users-connecting-to-a-report-server"></a>ผู้ใช้ปลายทางที่เชื่อมต่อกับเซิร์ฟเวอร์รายงาน

หลังจากที่คุณเผยแพร่นโยบายการกำหนดค่าแอป ผู้ใช้และอุปกรณ์ที่เป็นของรายการการแจกจ่ายที่กำหนดไว้สำหรับนโยบายนั้นจะมีประสบการณ์การใช้งานต่อไปนี้เมื่อพวกเขาเริ่มใช้งานแอปอุปกรณ์เคลื่อนที่ Power BI สำหรับ iOS 

1. พวกเขาจะเห็นข้อความว่าแอปสำหรับอุปกรณ์เคลื่อนที่ของตนได้กำหนดค่าสำหรับเซิร์ฟเวอร์รายงานแล้ว และแตะ **ลงชื่อเข้าใช้**

    ![ลงชื่อเข้าใช้เซิร์ฟเวอร์รายงาน](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-sign-in.png)

2.  บนหน้า**เชื่อมต่อกับเซิร์ฟเวอร์** รายละเอียดของเซิร์ฟเวอร์รายงานได้ถูกกรอกให้แล้ว ผู้ใช้แตะ**เชื่อมต่อ**

    ![รายละเอียดของเซิร์ฟเวอร์รายงานที่กรอกให้แล้ว](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configure-connect-server.png)

3. ผู้ใช้พิมพ์รหัสผ่านเพื่อรับรองความถูกต้อง จากนั้นแตะ**ลงชื่อเข้าใช้** 

    ![รายละเอียดของเซิร์ฟเวอร์รายงานที่กรอกให้แล้ว](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-address.png)

ตอนนี้ ผู้ใช้สามารถดูและโต้ตอบกับ KPI และรายงาน Power BI ที่จัดเก็บบนเซิร์ฟเวอร์รายงาน

## <a name="next-steps"></a>ขั้นตอนถัดไป
[ภาพรวมของผู้ดูแลระบบ](admin-handbook-overview.md)  
[ติดตั้ง Power BI Report Server](install-report-server.md)  

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)

