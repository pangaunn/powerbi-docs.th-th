---
title: คำถามที่ถามบ่อยของเกตเวย์ข้อมูลภายในองค์กร
description: นี่คือคำถามที่ถามบ่อยเกี่ยวกับเกตเวย์ข้อมูลภายในองค์กร ซึ่งรวบรวมคำถามที่ถามบ่อยสำหรับเกตเวย์ไว้ในที่เดียว
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 01/24/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: b4ecec3b2e53c2fea0fcbb7d78d1114da1a105ed
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/26/2018
ms.locfileid: "34299642"
---
# <a name="on-premises-data-gateway-faq"></a>คำถามที่ถามบ่อยของเกตเวย์ข้อมูลภายในองค์กร
<!-- Shared FAQ shared Include -->
[!INCLUDE [gateway-onprem-faq-shared-include](./includes/gateway-onprem-faq-shared-include.md)]

## <a name="analysis-services"></a>Analysis Services
**คำถาม:** ฉันสามารถใช้ msdmpump.dll เพื่อสร้างแมปชื่อผู้ใช้ที่มีผลบังคับใช้แบบกำหนดเองสำหรับ Analysis Services ได้หรือไม่?  
**คำตอบ:** ไม่ได้ ปัจจุบัน ระบบยังไม่สนับสนุนขั้นตอนนี้

**คำถาม:** ฉันสามารถใช้เกตเวย์เพื่อเชื่อมต่อกับตัวอย่าง (OLAP) แบบหลายมิติได้หรือไม่  
**คำตอบ:** ได้! เกตเวย์ข้อมูลในองค์กรสนับสนุนการเชื่อมต่อสดไปยังแบบจำลองทั้งตาราง Analysis Services และ Multidimensional (แบบหลายมิติ)

**คำถาม:** จะเกิดอะไรขึ้นถ้าฉันติดตั้งเกตเวย์บนคอมพิวเตอร์ในโดเมนอื่นนอกเหนือจากเซิร์ฟเวอร์ภายในองค์กรของฉันที่ใช้การรับรองความถูกต้องของ Windows?  
**คำตอบ:** ไม่รับประกันที่นี่ ทั้งหมดขึ้นอยู่กับความน่าเชื่อถือของความสัมพันธ์ระหว่างสองโดเมน ถ้าโดเมนทั้งสองอยู่ในแบบจำลองโดเมนที่เชื่อถือได้ เกตเวย์อาจสามารถเชื่อมต่อไปยังเซิร์ฟเวอร์ Analysis Services และสามารถแก้ไขชื่อผู้ใช้ที่มีผลบังคับใช้ได้ ถ้าไม่ใช่เป็นเช่นนั้น คุณอาจไม่สามารถเข้าสู่ระบบได้

**คำถาม:** ฉันจะรู้ได้อย่างไรว่าชื่อผู้ใช้ที่มีผลบังคับใช้ใดที่กำลังถูกส่งผ่านไปยังเซิร์ฟเวอร์ Analysis Services ภายในองค์กรของฉัน?  
**คำตอบ:** เราตอบคำถามนี้ใน[บทความการแก้ไขปัญหา](service-gateway-onprem-tshoot.md)

**คำถาม:** ฉันมี 25 ฐานข้อมูลใน Analysis Services มีวิธีใดบ้างที่สามารถเปิดใช้งานฐานข้อมูลทั้งหมดในคราวเดียวสำหรับเกตเวย์นี้?  
**คำตอบ:** ไม่ได้ ขั้นตอนนี้อยู่ระหว่างพัฒนาและเรายังไม่มีกรอบเวลาที่แน่ชัด

## <a name="administration"></a>การดูแลระบบ
**คำถาม:** ฉันสามารถมีผู้ดูแลระบบมากกว่าหนึ่งรายสำหรับเกตเวย์ได้หรือไม่?  
**คำตอบ:** ได้! เมื่อคุณจัดการเกตเวย์หนึ่ง คุณสามารถไปที่แท็บของผู้ดูแลระบบเพื่อเพิ่มผู้ดูแลระบบเพิ่มเติม

**คำถาม:** ผู้ดูแลระบบเกตเวย์จำเป็นต้องเป็นผู้ดูแลระบบบนเครื่องที่ติดตั้งเกตเวย์หรือไม่?  
**คำตอบ:** ไม่ได้ ผู้ดูแลระบบเกตเวย์ใช้เพื่อจัดการเกตเวย์จากภายในบริการ

**คำถาม:** ฉันสามารถป้องกันไม่ให้ผู้ใช้ในองค์กรของฉันสร้างเกตเวย์ได้หรือไม่?  
**คำตอบ:** ไม่ได้ ขั้นตอนนี้อยู่ระหว่างพัฒนาและเรายังไม่มีกรอบเวลาที่แน่ชัด

**คำถาม:** ฉันสามารถรับข้อมูลการใช้งานและสถิติของเกตเวย์ในองค์กรของฉันได้หรือไม่?  
**คำตอบ:** ไม่ได้ ขั้นตอนนี้อยู่ระหว่างพัฒนาและเรายังไม่มีกรอบเวลาที่แน่ชัด

## <a name="power-bi"></a>Power BI
**คำถาม:** ฉันจำเป็นต้องอัปเกรดเกตเวย์ส่วนบุคคลหรือไม่?
**คำตอบ:** ไม่ คุณสามารถใช้เกตเวย์ส่วนบุคคลสำหรับ Power BI ได้

**คำถาม:** ไทล์ในแดชบอร์ดใน Power BI จะรีเฟรชบ่อยแค่ไหนเมื่อเชื่อมต่อผ่านเกตเวย์ข้อมูลในองค์กร?  
**คำตอบ:** ประมาณสิบนาที การเชื่อมต่อ DirectQuery เป็นประมาณนั้น ซึ่งไม่ได้หมายความว่าไทล์ออกการแบบสอบถามไปยัง (คิวรี่) เซิร์ฟเวอร์ภายในองค์กรของคุณและแสดงข้อมูลใหม่ทุก ๆ 10 นาที

**คำถาม:** สามารถฉันอัปโหลดเวิร์กบุ๊ก Excel ด้วยแบบจำลองข้อมูล Power Pivot ที่เชื่อมต่อกับแหล่งข้อมูลภายในองค์กรได้หรือไม่? ฉันต้องใช้เกตเวย์สำหรับสถานการณ์สมมตินี้หรือไม่?  
**คำตอบ:** ใช่ คุณสามารถอัปโหลดเวิร์กบุ๊กได้ และไม่ คุณไม่จำเป็นต้องมีเกตเวย์ แต่เนื่องจากข้อมูลจะอยู่ในแบบจำลองข้อมูล Excel รายงานใน Power BI ที่ยึดตามเวิร์กบุ๊ก xcel จะไม่สามารถใช้งานสดได้ เพื่อให้รีเฟรชรายงานใน Power BI แต่ละครั้งคุณจะต้องอัปโหลดเวิร์กบุ๊กที่อัปเดตแล้วอีกครั้ง หรือใช้เกตเวย์ที่มีการรีเฟรชตามกำหนดการ

**คำถาม:** ถ้าผู้ใช้แชร์แดชบอร์ดที่มีการเชื่อมต่อ DirectQuery ผู้ใช้อื่น ๆ เหล่านั้นจะสามารถดูข้อมูลได้หรือไม่ แม้ว่าพวกเขาอาจไม่มีสิทธิ์การเข้าใช้งานเดียวกัน  
**คำตอบ:** สำหรับแดชบอร์ดที่เชื่อมต่อกับ Analysis Services ผู้ใช้จะเห็นเฉพาะข้อมูลที่พวกเขามีสิทธิ์เข้าถึงได้ ถ้าผู้ใช้ไม่มีสิทธิ์การเข้าใช้เดียวกัน พวกเขาจะไม่สามารถดูข้อมูลใด ๆ ได้ สำหรับแหล่งข้อมูลอื่น ๆ ผู้ใช้ทั้งหมดจะแชร์ข้อมูลประจำตัวที่ป้อนเข้าไปโดยผู้ดูแลระบบสำหรับแหล่งข้อมูลนั้น

**คำถาม:** เหตุใดฉันจึงไม่สามารถเชื่อมต่อเซิร์ฟเวอร์ Oracle ของฉันได้?  
**คำตอบ:** คุณอาจจำเป็นต้องติดตั้ง Oracle Client และกำหนดค่าไฟล์ tnsnames.ora ด้วยข้อมูลเซิร์ฟเวอร์ที่เหมาะสมเพื่อให้สามารถเชื่อมต่อกับเซิร์ฟเวอร์ Oracle ของคุณได้ นี่คือการติดตั้งแยกต่างหากภายนอกเกตเวย์ สำหรับข้อมูลเพิ่มเติม ดู[ติดตั้ง Oracle Client](service-gateway-onprem-manage-oracle.md#installing-the-oracle-client)

**คำถาม:** เกตเวย์จะทำงานกับ ExpressRoute ได้หรือไม่?  
**คำตอบ:** ได้ สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ Power BI และ ExpressRoute ดู[Power BI และ ExpressRoute](service-admin-power-bi-expressroute.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เกตเวย์ข้อมูลภายในองค์กร](service-gateway-onprem.md)  
[เกตเวย์ข้อมูลในองค์กรในเชิงลึก](service-gateway-onprem-indepth.md)  
[การแก้ไขปัญหาเกตเวย์ข้อมูลในองค์กร](service-gateway-onprem-tshoot.md)  
มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)

