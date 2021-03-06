---
title: การใช้ตารางที่มีการคำนวณใน Power BI Desktop
description: ตารางที่มีการคำนวณใน Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: e35c842af47bac9dfd6667ecfa885a8df8a8785c
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2018
ms.locfileid: "39328108"
---
# <a name="using-calculated-tables-in-power-bi-desktop"></a>การใช้ตารางที่มีการคำนวณใน Power BI Desktop
เมื่อใช้ตารางที่มีการคำนวณ คุณสามารถเพิ่มตารางใหม่ลงในรูปแบบข้อมูล แต่แทนที่จะคิวรีและโหลดค่าจากแหล่งข้อมูลลงไปยังคอลัมน์ใหม่ในตาราง คุณสามารถสร้างสูตร Data Analysis Expressions (DAX) ที่ใช้กำหนดค่าของตาราง ใน Power BI Desktop ตารางที่มีการคำนวณ สร้างขึ้นด้วยคุณลักษณะ ตารางใหม่ ในมุมมองรายงาน หรือมุมมองข้อมูล

ส่วนใหญ่แล้ว คุณจะนำเข้าข้อมูลลงในรูปแบบข้อมูลของคุณจากแหล่งข้อมูลภายนอก แต่ว่าตารางที่มีการคำนวณก็มีข้อดีบางอย่าง ตารางที่มีการคำนวณเป็นตัวเลือกที่ดีที่สุดเมื่อต้องการคำนวณตัวเลขหรือข้อมูลระหว่างทาง และคุณต้องการเก็บผลลัพธ์นั้นให้เป็นส่วนหนึ่งของรูปแบบ แทนที่จะคำนวณใหม่ตลอดหรือเป็นส่วนหนึ่งของคิวรี

ต่างกับตารางที่สร้างขึ้นจากคิวรี ตารางที่มีการคำนวณสร้างขึ้นใน มุมมองรายงาน หรือ มุมมองข้อมูล จะอาศัยข้อมูลที่คุณได้โหลดลงในรูปแบบเรียบร้อยแล้ว ตัวอย่างเช่น คุณอาจเลือกยูเนียน หรือทำ cross join ตารางสองตาราง

เช่นเดียวกับตารางปกติ ตารางที่มีการคำนวณสามารถมีความสัมพันธ์กับตารางอื่น ๆ คอลัมน์ในตารางที่มีการคำนวนของคุณ มีชนิดของข้อมูล การจัดรูปแบบ และสามารถจัดประเภทข้อมูล คุณสามารถตั้งชื่อคอลัมน์เป็นอะไรก็ได้ที่คุณต้องการ และเพิ่มลงในภาพรายงานได้เช่นเดียวกับเขตข้อมูลอื่น ๆ ตารางที่มีการคำนวณ จะคำนวณใหม่หากตารางใด ๆ ที่มันดึงข้อมูลมา มีการรีเฟรช หรือปรับปรุงในทางใดทางหนึ่ง

ตารางที่มีการคำนวณ คำนวนผลลัพธ์โดยใช้ [Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx) (DAX) ซึ่งเป็นภาษาสำหรับสูตรที่ออกแบบเพื่อทำงานร่วมกับข้อมูลเชิงสัมพันธ์เช่นใน Power BI Desktop DAX มีไลบรารีของ ฟังก์ชัน ตัวดำเนินการ และโครงสร้าง มากกว่า 200 รายการ จึงยืดหยุ่นรองรับการวิเคราะห์ข้อมูลทุกรูปแบบที่คุณต้องการ

## <a name="lets-look-at-an-example"></a>เราลองมาดูตัวอย่างกัน
Jeff ซึ่งเป็นผู้จัดการโครงการที่ Contoso มีตารางของพนักงานในภูมิภาคตะวันตกเฉียงเหนือ และอีกตารางสำหรับพนักงานในภูมิภาคตะวันตกเฉียงใต้ Jeff ต้องการรวมสองตารางเข้าเป็นตารางเดียว

**NorthwestEmployees**

 ![](media/desktop-calculated-tables/calctables_nwempl.png)

**SoutwestEmployees**

 ![](media/desktop-calculated-tables/calctables_swempl.png)

การนำตารางทั้งสอง มารวมกันด้วยตารางที่มีการคำนวน เป็นเรื่องที่ค่อนข้างง่าย ถึงแม้ว่า Jeff จะสามารถสร้างตารางที่มีการการคำนวณในมุมมองรายงานหรือมุมมองข้อมูล การสร้างในมุมมองข้อมูลทำได้ง่ายกว่า เพราะเขาสามารถเห็นตารางใหม่ของเขาได้ทันที

ใน**มุมมองข้อมูล** บนแท็บ**การวางรูปแบบ** Jeff คลิกไปที่ **สร้างตาราง** แถบสูตรจะปรากฏขึ้น

 ![](media/desktop-calculated-tables/calctables_formulabarempty.png)

แล้ว Jeff ก็ใส่สูตรต่อไปนี้:

 ![](media/desktop-calculated-tables/calctables_formulabarformula.png)

ตารางใหม่ที่ชื่อ Western Region Employees ก็จะถูกสร้างขึ้น

 ![](media/desktop-calculated-tables/calctables_westregionempl.png)

ตารางพนักงานในภูมิภาคตะวันตกใหม่ของ Jeff จะปรากฏในรายการเขตข้อมูล เหมือนกับตารางอื่น ๆ เขาสามารถสร้างความสัมพันธ์กับตารางอื่น เพิ่มคอลัมน์และการวัดที่มีการคำนวณ และเพิ่มเขตข้อมูลใด ๆ ของตารางลงในรายงาน ได้เช่นเดียวกับตารางอื่น

 ![](media/desktop-calculated-tables/calctables_fieldlist.png)

## <a name="functions-for-calculated-tables"></a>ฟังก์ชันสำหรับตารางที่มีการคำนวณ
ตารางที่มีการคำนวณ สามารถกำหนดโดยนิพจน์ DAX ใดก็ได้ที่ส่งค่ากลับมาเป็นตาราง รวมถึงส่งค่าการอ้างอิงไปตารางอื่น ตัวอย่างเช่น:

 ![](media/desktop-calculated-tables/calctables_formulabarsimpleformula.png)

คุณสามารถใช้ตารางที่มีการคำนวณ ด้วย DAX เพื่อแก้ปัญหาการวิเคราะห์ได้มากมาย เราได้แค่แนะนำ ตารางที่มีการคำนวณ แบบสั้น ๆ ที่นี่เท่านั้น เมื่อคุณเริ่มทำงานกับตารางที่มีการคำนวณ ต่อไปนี้ตัวอย่างของฟังก์ชันตารางของ DAX ที่ใช้บ่อย ที่อาจเป็นประโยชน์กับคุณ:

* DISTINCT
* VALUES
* CROSSJOIN
* UNION
* NATURALINNERJOIN
* NATURALLEFTOUTERJOIN
* INTERSECT
* CALENDAR
* CALENDARAUTO

ดู[แหล่งอ้างอิงฟังก์ชัน DAX](https://msdn.microsoft.com/ee634396.aspx) สำหรับฟังก์ชันเหล่านี้และฟังก์ชันอื่น ๆ ของ DAX ที่ส่งค่ากลับมาเป็นตาราง

