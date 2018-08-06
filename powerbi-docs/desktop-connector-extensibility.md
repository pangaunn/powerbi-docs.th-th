---
title: การขยายของตัวเชื่อมต่อใน Power BI
description: ความสามารถในการขยายตัวของตัวเชื่อมต่อ คุณลักษณะ การตั้งค่าความปลอดภัย และตัวเชื่อมต่อที่ผ่านการรับรอง
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/25/2018
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: c63357df043ff6a646562d398a07d8042dd5a0ee
ms.sourcegitcommit: 7fb0b68203877ff01f29724f0d1761d023075445
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/26/2018
ms.locfileid: "39256598"
---
# <a name="connector-extensibility-in-power-bi"></a>การขยายของตัวเชื่อมต่อใน Power BI

ลูกค้าและนักพัฒนาซอฟต์แวร์สามารถขยายแหล่งข้อมูลที่สามารถเชื่อมต่อได้หลายวิธีใน Power BI ตัวอย่างเช่น การใช้ตัวเชื่อมต่อที่มีอยู่และแหล่งข้อมูลทั่วไป (เช่น ODBC, OData, Oledb, Web, CSV, XML, JSON) นอกเหนือจากแหล่งข้อมูลดังกล่าวแล้ว นักพัฒนาซอฟต์แวร์สามารถสร้างส่วนขยายข้อมูลที่เรียกว่า **ตัวเชื่อมต่อแบบกำหนดเอง** และรับรองตัวเชื่อมต่อเพื่อทำให้เป็น **ตัวเชื่อมต่อที่ผ่านการรับรอง**

ความสามารถในการใช้ **ตัวเชื่อมต่อแบบกำหนดเอง** จะถูกเปิดใช้งานโดยใช้สวิตช์คุณลักษณะสำหรับ Power BI ในเวอร์ชันก่อนหน้า ขณะนี้มีเมนูที่ช่วยให้คุณสามารถควบคุมระดับของรหัสแบบกำหนดเองที่คุณต้องการอนุญาตให้ทำงานในระบบของคุณได้อย่างปลอดภัย: ตัวเชื่อมต่อแบบกำหนดเองทั้งหมด หรือเฉพาะตัวเชื่อมที่ได้รับการรับรองและแจกจ่ายโดย Microsoft ในกล่องโต้ตอบ**การรับข้อมูล**

## <a name="custom-connectors"></a>ตัวเชื่อมต่อแบบกำหนดเอง

**ตัวเชื่อมต่อแบบกำหนดเอง**สามารถเป็นไปได้หลากหลายตั้งแต่ API ขนาดเล็กที่มีความสำคัญต่อธุรกิจของคุณไปจนถึงบริการเฉพาะทางอุตสาหกรรมขนาดใหญ่ที่ Microsoft ไม่ได้นำมาใช้ ตัวเชื่อมต่อส่วนใหญ่เหล่านี้จะถูกแจกจ่ายโดยผู้ขายเอง และหากคุณต้องการเชื่อมต่อข้อมูลเฉพาะ คุณควรติดต่อผู้ขาย

เมื่อต้องใช้เป็น**ตัวเชื่อมต่อแบบกำหนดเอง** ให้ใส่ตัวเชื่อมต่อดังกล่าวไว้ใน *\[เอกสาร] \\โฟลเดอร์ \\ตัวเชื่อมต่อแบบกำหนดเอง* ใน Power BI Desktop และปรับการตั้งค่าความปลอดภัยตามที่อธิบายไว้ในส่วนต่อไปนี้

คุณไม่จำเป็นต้องปรับการตั้งค่าความปลอดภัยเพื่อใช้ **ตัวเชื่อมต่อที่ได้รับการรับรอง**

## <a name="data-extension-security"></a>การรักษาความปลอดภัยส่วนขยายข้อมูล

เมื่อต้องเปลี่ยนการตั้งค่าความปลอดภัยส่วนขยายข้อมูล ให้เลือก**ไฟล์ > ตัวเลือกและการตั้งค่า > ตัวเลือก > ความปลอดภัย**ใน **Power BI Desktop**

![ควบคุมว่าคุณต้องการจะโหลดตัวเชื่อมต่อแบบกำหนดเองหรือไม่ด้วยตัวเลือกการรักษาความปลอดภัยส่วนขยายข้อมูล](media/desktop-connector-extensibility/data-extension-security-1.png)

ภายใต้**ส่วนขยายข้อมูล**คุณสามารถเลือกระดับความปลอดภัยได้จากสองระดับ:

* (แนะนำ) อนุญาตให้โหลดเฉพาะส่วนขยายที่รับรองเท่านั้น
* (ไม่แนะนำ) อนุญาตให้โหลดส่วนขยายโหลดโดยไม่มีคำเตือน

หากคุณวางแผนที่จะใช้ **ตัวเชื่อมต่อแบบกำหนดเอง** หรือตัวเชื่อมต่อที่คุณหรือบุคคลที่สามได้พัฒนาและแจกจ่าย คุณต้องเลือก(ไม่แนะนำ) อนุญาตให้โหลดส่วนขยายโหลดโดยไม่มีคำเตือน เราไม่แนะนำให้ตั้งค่าการรักษาความปลอดภัยเช่นนี้ เว้นแต่คุณจะวางแผนเรียกใช้งาน **ตัวเชื่อมต่อแบบกำหนดเอง**

ในการตั้งค่าความปลอดภัย **(แนะนำ)** หากมีตัวเชื่อมต่อแบบกำหนดเองในระบบของคุณ ข้อผิดพลาดจะแสดงขึ้นเพื่ออธิบายตัวเชื่อมต่อที่ไม่สามารถโหลดได้เนื่องจากความปลอดภัย

![กล่องโต้ตอบจะอธิบายตัวเชื่อมต่อแบบกำหนดเองที่ไม่สามารถโหลดได้เนื่องจากการตั้งค่าความปลอดภัย ในกรณีนี้คือ TripPin](media/desktop-connector-extensibility/data-extension-security-2.png)

หากต้องการแก้ปัญหาข้อผิดพลาดและใช้ตัวเชื่อมต่อเหล่านี้ คุณต้องเปลี่ยนการตั้งค่าความปลอดภัยของคุณเป็นการตั้งค่า **(ไม่แนะนำ)** ตามที่อธิบายไว้ก่อนหน้านี้ และเริ่มต้น **Power BI Desktop** ใหม่

## <a name="certified-connectors"></a>ตัวเชื่อมต่อที่ผ่านการรับรอง

ส่วนย่อยของส่วนขยายข้อมูลที่จำกัดจะถือว่าได้รับ**การรับรอง**และตัวเชื่อมต่อที่ผ่านการรับรองดังกล่าวจะพร้อมใช้งานกล้อโต้ตอบ **การรับข้อมูล** แต่ฝ่ายที่รับผิดชอบในการบำรุงรักษาและการสนับสนุนยังคงเป็นนักพัฒนาบุคคลที่สามที่สร้างตัวเชื่อมต่อขึ้น ในขณะที่ Microsoft แจกจ่ายตัวเชื่อมต่อเหล่านี้ เราจะไม่รับผิดชอบต่อประสิทธิภาพหรือฟังก์ชันการทำงานที่ต่อเนื่องของตัวเชื่อมต่อดังกล่าว

หากคุณต้องการให้ตัวเชื่อมต่อแบบกำหนดเองได้รับการรับรอง โปรดติดต่อผู้ขายของคุณให้ติดต่อกับ Microsoft