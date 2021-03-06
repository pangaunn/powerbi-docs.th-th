---
title: จัดรูปแบบตารางใน Power BI Desktop ตามเงื่อนไข
description: นำการจัดรูปแบบแบบกำหนดเองลงในตาราง
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 08/06/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 324a9b7f8a3718c6da0efb7533751d88dd717bcf
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2018
ms.locfileid: "44728099"
---
# <a name="conditional-formatting-in-tables"></a>การจัดรูปแบบตามเงื่อนไขในตาราง 
ด้วยการจัดรูปแบบตามเงื่อนไขสำหรับตาราง คุณสามารถระบุสีพื้นหลังของเซลล์ตามค่าของเซลล์ หรือตามค่าอื่นหรือเขตข้อมูลอื่น รวมถึงการไล่ระดับสี คุณยังสามารถแสดงค่าเซลล์ ด้วยแถบข้อมูล 

การเข้าถึงรูปแบบตามเงื่อนไข ในแอ่ง**ช่องข้อมูล**ของพื้นที่**การแสดงภาพ**ใน Power BI Desktop เลือกลูกศรชี้ลงข้าง ๆ ค่าในแอ่ง**ค่า**เดียวกับที่คุณต้องการจัดรูปแบบ (หรือคลิกขวาที่ช่องข้อมูล) คุณสามารถจัดการการจัดรูปแบบตามเงื่อนไขสำหรับช่องข้อมูลในพื้นที่**ค่า**ของแอ่ง**ช่องข้อมูล**ได้เท่านั้น

![เมนูการจัดรูปแบบตามเงื่อนไข](media/desktop-conditional-table-formatting/table-formatting-0-popup-menu.png)

ส่วนต่อไปนี้อธิบายแต่ละตัวเลือกการจัดรูปแบบตามเงื่อนไขเหล่านี้ สามารถรวมตัวเลือกหนึ่งหรือหลายตัวเลือกในคอลัมน์เดียวของตารางได้

> [!NOTE]
> เมื่อนำไปใช้กับตาราง การจัดรูปแบบตามเงื่อนไขจะแทนที่สไตล์ตารางแบบกำหนดเองใด ๆ ที่ใช้กับเซลล์ที่ถูกจัดรูปแบบตามเงื่อนไข

เพื่อเอาการจัดรูปแบบตามเงื่อนไขออกจากวิชวล เพียงแค่คลิกขวาที่เขตข้อมูลอีกครั้ง เลือก**ลบการจัดรูปแบบตามเงื่อนไขออก** และเลือกชนิดของการจัดรูปแบบที่จะเอาออก

![เมนูลบการจัดรูปแบบตามเงื่อนไขออก](media/desktop-conditional-table-formatting/table-formatting-1-remove.png)

## <a name="background-color-scales"></a>สเกลสีพื้นหลัง

เลือก**จัดรูปแบบตามเงื่อนไข** แล้วเลือก**สเกลสีพื้นหลัง**จะแสดงกล่องโต้ตอบต่อไปนี้

![กล่องโต้ตอบสเกลสีพื้นหลัง](media/desktop-conditional-table-formatting/table-formatting-1-default-dialog.png)

คุณสามารถเลือกเขตข้อมูลจากรูปแบบข้อมูลของคุณที่จะใช้สีตามได้ โดยการตั้งค่า**สีตาม**กับเขตข้อมูลนั้น นอกจากนี้ คุณสามารถระบุชนิดการรวมสำหรับเขตข้อมูลที่เลือกด้วยค่า**การสรุปข้อมูล**ได้ เขตข้อมูลที่จะระบายสี จะระบุในเขตข้อมูล**ใช้สีกับ** เพื่อให้คุณสามารถติดตาม คุณสามารถใช้การจัดรูปแบบตามเงื่อนไขกับเขตข้อมูลข้อความและวันที่ได้ ตราบใดที่คุณเลือกค่าตัวเลขเป็นพื้นฐานของการจัดรูปแบบ

![สีตามเขตข้อมูล](media/desktop-conditional-table-formatting/table-formatting-1-apply-color-to.png)

เพื่อใช้ค่าสีแบบไม่ต่อเนื่องสำหรับช่วงของค่าที่กำหนด เลือก**สีตามกฎ** เพื่อใช้สีต่อเนื่อง ปล่อยให้**สีตามกฎ**ไม่มีการเลือก 

![กล่องโต้ตอบสเกลสีพื้นหลัง](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-dialog.png)

### <a name="color-by-rules"></a>สีตามกฎ

เมื่อคุณเลือก**สีตามกฎ** คุณสามารถป้อนหนื่งหรือหลายช่วงของค่า โดยตั้งค่าสีสำหรับแต่ละช่วงได้  ค่าแต่ละช่วงเริ่มต้นจากเงื่อนไข*ถ้าค่า* เงื่อนไข*และ*ค่า และสี

![ช่วงค่าของสีตามกฎ](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-if-value.png)

เซลล์ตารางที่มีค่าในแต่ละช่วงถูกเติมด้วยสีที่กำหนด มีสามกฎในรูปต่อไปนี้

![ตัวอย่างสีตามกฎ](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules.png)

ตารางตัวอย่างตอนนี้มีลักษณะดังนี้:

![ตารางตัวอย่าง ด้วยสีตามกฎ](media/desktop-conditional-table-formatting/table-formatting-1-color-by-rules-table.png)


### <a name="color-minimum-to-maximum"></a>สีต่ำสุดถึงสูงสุด

คุณสามารถกำหนดค่า*ต่ำสุด*และ*สูงสุด*และสีค่านั้นได้ ถ้าคุณเลือกกล่อง**เลือกแยกจากกัน** คุณสามารถกำหนดค่า*ศูนย์กลาง*ที่เป็นทางเลือกได้เช่นกัน

![ปุ่มแยกจากกัน](media/desktop-conditional-table-formatting/table-formatting-1-diverging.png)

ตารางตัวอย่างตอนนี้มีลักษณะดังนี้:

![ตารางตัวอย่างที่มีสีที่แยกจากกัน](media/desktop-conditional-table-formatting/table-formatting-1-diverging-table.png)

## <a name="font-color-scales"></a>สเกลสีฟอนต์

เลือก**จัดรูปแบบตามเงื่อนไข** แล้วเลือก**สเกลสีฟอนต์** จะแสดงกล่องโต้ตอบต่อไปนี้ กล่องโต้ตอบนี้จะคล้ายกับกล่องโต้ตอบ**สเกลสีพื้นหลัง** แต่จะเปลี่ยนสีฟอนต์แทนที่จะเป็นสีพื้นหลังของเซลล์

![กล่องโต้ตอบสเกลสีฟอนต์](media/desktop-conditional-table-formatting/table-formatting-2-diverging.png)

ตารางตัวอย่างตอนนี้มีลักษณะดังนี้:

![ตารางตัวอย่างที่มีสเกลสีฟอนต์](media/desktop-conditional-table-formatting/table-formatting-2-table.png)

## <a name="data-bars"></a>แถบข้อมูล

เลือก**จัดรูปแบบตามเงื่อนไข** แล้วเลือก**แถบข้อมูล** จะแสดงกล่องโต้ตอบต่อไปนี้ 

![กล่องโต้ตอบแถบข้อมูล](media/desktop-conditional-table-formatting/table-formatting-3-default.png)

ตามค่าเริ่มต้น ตัวเลือก**แสดงแถบอย่างเดียว**จะไม่ได้เลือก ดังนั้น เซลล์ของตารางจะแสดงทั้งแถบและค่าจริง

![ตารางตัวอย่างที่มีแถบข้อมูลและค่า](media/desktop-conditional-table-formatting/table-formatting-3-default-table.png)

ถ้าเลือกตัวเลือก**แสดงแถบอย่างเดียว** เซลล์ของตารางจะแสดงเฉพาะแถบเท่านั้น

![ตารางตัวอย่างที่มีแถบข้อมูลเท่านั้น](media/desktop-conditional-table-formatting/table-formatting-3-default-table-bars.png)

## <a name="color-formatting-by-field-value"></a>การจัดรูปแบบสีโดยค่าของเขตข้อมูล

คุณสามารถใช้หน่วยวัดหรือคอลัมน์ที่ระบุสี โดยใช้ค่าข้อความหรือโค้ดฐานสิบหก เพื่อใช้สีนั้นกับพื้นหลังของสีฟอนต์ของตารางหรือวิชวลเมทริกซ์ คุณสามารถสร้างตรรกะที่กำหนดเองสำหรับเขตข้อมูลที่ระบุ และมีตรรกะที่ใช้สีที่ต้องการกับฟอนต์หรือพื้นหลัง

ตัวอย่าง ในตารางต่อไปนี้จะมีสีที่เกี่ยวข้องกับแต่ละรุ่นผลิตภัณฑ์ 

![เขตข้อมูล ProductName พร้อมกับชื่อสี](media/desktop-conditional-table-formatting/conditional-table-formatting_01.png)

เมื่อต้องการจัดรูปแบบเซลล์ตามค่าเขตข้อมูล เลือกกล่องโต้ตอบ**การจัดรูปแบบตามเงื่อนไข** โดยการคลิกขวาคอลัมน์*สี*สำหรับวิชวลนั้น และในกรณีนี้เลือก**สีพื้นหลัง**จากเมนู 

![เลือกสีพื้นหลังจากเมนู](media/desktop-conditional-table-formatting/conditional-table-formatting_02.png)

ในกล่องโต้ตอบที่ปรากฏขึ้น เลือก**ค่าเขตข้อมูล**ใน**การจัดรูปแบบโดย**พื้นทีดรอปดาวน์ ดังที่แสดงในรูปต่อไปนี้

![จัดรูปแบบโดยค่าเขตข้อมูล](media/desktop-conditional-table-formatting/conditional-table-formatting_03.png)

คุณสามารถทำซ้ำกระบวนการสำหรับสีฟอนต์ และผลลัพธ์ในวิชวลจะเป็นสีทึบในคอลัมน์**สี** ดังที่แสดงในหน้าจอต่อไปนี้ได้

![จัดรูปแบบโดยค่าเขตข้อมูล](media/desktop-conditional-table-formatting/conditional-table-formatting_04.png)

คุณยังสามารถสร้างการคำนวณ DAX ตามตรรกะทางธุรกิจ ที่แสดงผลรหัสฐานสิบหกอื่นตามเงื่อนไขที่คุณต้องการ ซึ่งโดยทั่วไปแล้วง่ายกว่าการสร้างกฎหลายกฎในกล่องโต้ตอบการจัดรูปแบบตามเงื่อนไข พิจารณาเขตข้อมูล*ColorKPI*ในรูปตัวอย่างต่อไปนี้

![การคำนวณ DAX](media/desktop-conditional-table-formatting/conditional-table-formatting_05.png)

จากนั้นคุณสามารถตั้งค่าเขตข้อมูลสำหรับ**สีพื้นหลัง**ในวิธีต่อไปนี้

![ตั้งค่าสีเขตข้อมูลตาม KPI](media/desktop-conditional-table-formatting/conditional-table-formatting_06.png)

และคุณอาจจะได้รับผลลัพธ์เช่นเมทริกซ์ต่อไปนี้

![วิชวลเมทริกซ์ด้วยค่า KPI ตามสี](media/desktop-conditional-table-formatting/conditional-table-formatting_07.png)

มีหลายรูปแบบเพิ่มเติมที่คุณสามารถสร้าง เพียงแค่ใช้จินตนาการของคุณและ DAX เล็กน้อย

## <a name="next-steps"></a>ขั้นตอนถัดไป
สำหรับข้อมูลเพิ่มเติม โปรดดูบทความต่อไปนี้:  

* [คำแนะนำและเคล็ดลับในการจัดรูปแบบสีใน Power BI](visuals/service-tips-and-tricks-for-color-formatting.md)  

