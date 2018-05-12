---
title: ใช้คอลัมน์จากการคำนวณใน Power BI Desktop
description: คอลัมน์จากการคำนวณใน Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
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
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 2a92426061b37753c529b84a1de6b8068cb3bc5f
ms.sourcegitcommit: 3f2f254f6e8d18137bae879ddea0784e56b66895
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/26/2018
---
# <a name="using-calculated-columns-in-power-bi-desktop"></a>ใช้คอลัมน์จากการคำนวณใน Power BI Desktop
คุณสามารถใช้คอลัมน์จากการคำนวณเพื่อเพิ่มข้อมูลใหม่ลงในตารางที่มีอยู่แล้วในแบบจำลองของคุณ แต่แทนที่จะทำแบบสอบถามและโหลดค่าลงในคอลัมน์ใหม่ของคุณจากแหล่งข้อมูล คุณสามารถสร้างสูตรนิพจน์การวิเคราะห์ข้อมูล (DAX) ที่กำหนดค่าของคอลัมน์ได้ ใน Power BI Desktop คอลัมน์จากการคำนวณถูกสร้างขึ้นโดยใช้คุณลักษณะคอลัมน์ใหม่ในมุมมองรายงาน

ต่างจากคอลัมน์แบบกำหนดเองที่สร้างขึ้นเป็นส่วนหนึ่งของแบบสอบถามโดยเพิ่มคอลัมน์แบบกำหนดเองในตัวแก้ไขแบบสอบถาม คอลัมน์จากการคำนวณที่สร้างขึ้นในมุมมองรายงานหรือมุมมองข้อมูลจะอิงตามข้อมูลที่คุณได้โหลดลงในแบบจำลองแล้ว ตัวอย่างเช่น คุณอาจเลือกเชื่อมค่าจากคอลัมน์ที่แตกต่างกันสองคอลัมน์ในตารางที่เกี่ยวข้องเข้าด้วยกันในตารางสองตารางที่แตกต่างกันแต่เกี่ยวข้องกัน ดำเนินการบวกเพิ่มหรือแยกสตริงย่อย

คอลัมน์จากการคำนวณที่คุณสร้างขึ้นปรากฏในรายการเขตข้อมูลเช่นเดียวกับเขตข้อมูลอื่น ๆ แต่คอลัมน์เหล่านี้จะมีไอคอนพิเศษที่แสดงว่าค่านั้นเป็นผลลัพธ์ของสูตร คุณสามารถตั้งชื่อคอลัมน์ของคุณได้ตามต้องการ และเพิ่มคอลัมน์เหล่านั้นลงในการจัดรูปแบบการแสดงข้อมูลในรายงานเช่นเดียวกับเขตข้อมูลอื่น ๆ

![](media/desktop-calculated-columns/calccolinpbid_fields.png)

คอลัมน์จากการคำนวณจะคำนวณผลลัพธ์โดยใช้ [สูตรนิพจน์การวิเคราะห์ข้อมูล](https://msdn.microsoft.com/library/gg413422.aspx) (DAX) ซึ่งเป็นภาษาสูตรที่มีไว้เพื่อทำงานกับข้อมูลเชิงสัมพันธ์อย่างเช่นใน Power BI Desktop DAX มีไลบรารีที่มีมากกว่า 200 ฟังก์ชัน ตัวดำเนินการ และรหัสโครง สร้างที่ทำให้มีความยืดหยุ่นมากในการสร้างสูตรเพื่อคำนวณผลลัพธ์เฉพาะสำหรับความต้องการที่เกี่ยวกับการวิเคราะห์ข้อมูลใดๆ เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับ DAX โปรดดูที่ส่วนเรียนรู้เพิ่มเติมตรงส่วนท้ายของบทความนี้

สูตร DAX จะคล้ายกับสูตร Excel อันที่จริงแล้ว DAX มีหลายฟังก์ชันที่เหมือนกันกับ Excel อย่างไรก็ตาม ฟังก์ชัน DAX มีไว้เพื่อทำงานบนข้อมูลที่แบ่งเป็นส่วนๆ หรือกรองแบบมีการโต้ตอบในรายงาน เช่น ใน Power BI Desktop ต่างจาก Excel ซึ่ง่คุณสามารถมีสูตรที่แตกต่างกันสำหรับแต่ละแถวในตาราง ในกรณีที่คุณสร้างสูตร DAX สำหรับคอลัมน์ใหม่ จะมีการคำนวณผลลัพธ์สำหรับทุกแถวในตาราง ค่าของคอลัมน์จะถูกคำนวณใหม่ตามที่จำเป็น เช่น เมื่อมีการรีเฟรชข้อมูลเบื้องต้นและมีการเปลี่ยนแปลงค่า

## <a name="lets-look-at-an-example"></a>มาลองดูตัวอย่างกัน
Jeff เป็นผู้จัดการจัดส่งที่ Contoso เขาต้องการสร้างรายงานที่แสดงจำนวนการจัดส่งไปที่เมืองที่แตกต่างกัน เขามีตารางภูมิศาสตร์ที่มีเขตข้อมูลแยกต่างหากสำหรับเมืองและรัฐ แต่ Jeff ต้องการให้รายงานของเขาแสดง City, State เป็นค่าเดี่ยวบนแถวเดียวกัน ในตอนนี้ ตารางภูมิศาสตร์ของ Jeff ไม่มีเขตข้อมูลที่เขาต้องการ

![](media/desktop-calculated-columns/calccolinpbid_cityandstatefields.png)

แต่ด้วยคอลัมน์จากการคำนวณ Jeff จึงสามารถนำหรือเชื่อมข้อมูลเมืองจากคอลัมน์ City เข้ามาไว้ด้วยกันกับรัฐจากคอลัมน์ State ได้อย่างง่ายดาย

Jeff คลิกขวาที่ตารางภูมิศาสตร์ และจากนั้น ก็คลิกที่คอลัมน์ใหม่ แล้วใส่สูตร DAX ดังต่อไปนี้ลงในแถบสูตร:

![](media/desktop-calculated-columns/calccolinpbid_formula.png)

สูตรนี้เพียงแค่สร้างคอลัมน์ใหม่ที่ชื่อว่า CityState ขึ้นมา และสำหรับแต่ละแถวในตารางภูมิศาสตร์ ก็จะใช้ค่าจากคอลัมน์ City เพิ่มเครื่องหมายจุลภาคและช่องว่าง แล้วจึงเชื่อมค่าจากคอลัมน์ State เข้าไว้ด้วยกัน

Jeff มีเขตข้อมูลที่เขาต้องการ

![](media/desktop-calculated-columns/calccolinpbid_citystatefield.png)

เขาสามารถเพิ่มเขตข้อมูลในพื้นที่รายงานของเขาพร้อมกับจำนวนการจัดส่ง ได้อย่างรวดเร็วและใช้พยายามที่น้อยที่สุด ตอนนี้ Jeff มีเขตข้อมูล City, State ที่เขาสามารถเพิ่มเพื่อจัดรูปแบบการแสดงข้อมูลไม่ว่าชนิดใดก็ตาม Jeff เห็นว่า เมื่อเขาสร้างการแสดงภาพแผนที่ Power BI Desktop ก็จะทราบได้แม้กระทั่งวิธีการอ่านค่า City, State ในคอลัมน์ใหม่ของเขา

![](media/desktop-calculated-columns/calccolinpbid_citystatemap.png)

## <a name="learn-more"></a>เรียนรู้เพิ่มเติม
ในที่นี้ เราเพียงแค่แนะนำคอลัมน์จากการคำนวณอย่างรวดเร็วเท่านั้น โปรดแน่ใจว่าได้ศึกษา [บทช่วยสอนสร้างคอลัมน์จากการคำนวณใน Power BI Desktop](desktop-tutorial-create-calculated-columns.md) ที่คุณสามารถดาวน์โหลดไฟล์ตัวอย่างและได้รับบทเรียนทีละขั้นตอนเกี่ยวกับวิธีการสร้างคอลัมน์เพิ่มเติมแล้ว 

เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับ DAX โปรดดูที่ [พื้นฐาน DAX ใน Power BI Desktop](desktop-quickstart-learn-dax-basics.md)

เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับคอลัมน์ที่คุณสร้างขึ้นเป็นส่วนหนึ่งของแบบสอบถาม โปรดดทีู่ส่วนสร้างคอลัมน์แบบกำหนดเองใน [งานแบบสอบถามทั่วไปใน Power BI Desktop](desktop-common-query-tasks.md)  
