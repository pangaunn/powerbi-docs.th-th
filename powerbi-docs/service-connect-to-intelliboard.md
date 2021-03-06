---
title: เชื่อมต่อกับ IntelliBoard ด้วย Power BI
description: IntelliBoard สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: db6361974fdbe7956979ac106e5cad5717f99d33
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/29/2018
ms.locfileid: "37135087"
---
# <a name="connect-to-intelliboard-with-power-bi"></a>เชื่อมต่อกับ IntelliBoard ด้วย Power BI
IntelliBoard เสนอการเข้าใช้งานข้อมูลระบบการจัดการการเรียนรู้ Moodle ที่ใช้งานง่ายผ่านบริการการรายงาน ชุดเนื้อหา IntelliBoard สำหรับ Power BI นำเสนอการวิเคราะห์เพิ่มเติม รวมถึงการวัดในหลักสูตรของคุณ ผู้ใช้ที่ลงทะเบียน ประสิทธิภาพการทำงานโดยรวม และกิจกรรม LMS ของคุณ

เชื่อมต่อไปยัง[ชุดเนื้อหา IntelliBoard](https://app.powerbi.com/getdata/services/intelliboard) สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ  
   
    ![](media/service-connect-to-intelliboard/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**  
   
    ![](media/service-connect-to-intelliboard/services.png)
3. เลือก**IntelliBoard** จากนั้นเลือก**รับ**  
   
    ![](media/service-connect-to-intelliboard/intelliboard.png)
4. เลือก**OAuth 2**แล้วเลือก**ลงชื่อเข้าใช้** เมื่อได้รับข้อความปรากฏ ใส่ข้อมูลประจำตัว IntelliBoard ของคุณ
   
    ![](media/service-connect-to-intelliboard/creds.png)
   
    ![](media/service-connect-to-intelliboard/creds2.png)
5. เมื่อเชื่อมต่อแล้ว แดชบอร์ด รายงาน และชุดข้อมูลจะโหลดโดยอัตโนมัติสามารถ เมื่อเสร็จสมบูรณ์ ไทล์ที่จะอัปเดตด้วยข้อมูลจากบัญชี IntelliBoard ของคุณ
   
    ![](media/service-connect-to-intelliboard/dashboard.png)

**ฉันต้องทำอะไรต่อ?**

* ลอง[ถามคำถามในกล่อง Q&A](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานด้านใน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
ชุดเนื้อหานี้ประกอบด้วยข้อมูลจากตารางต่อไปนี้:  

    - กิจกรรม  
    - ตัวแทน  
    - รับรอง  
    - ประเทศ  
    - CoursesProgress  
    - การลงทะเบียน
    - ภาษา  
    - แพลตฟอร์ม  
    - ผลรวม  
    - UsersProgress    

## <a name="system-requirements"></a>ข้อกำหนดของระบบ
จำเป็นต้องมีบัญชี IntelliBoard ที่มีสิทธิ์การใช้งานตารางข้างต้นเพื่อสร้างตัวอย่างประกอบชุดเนื้อหานี้

## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI คืออะไร](power-bi-overview.md)

[Power BI แนวคิดพื้นฐาน](service-basic-concepts.md)

