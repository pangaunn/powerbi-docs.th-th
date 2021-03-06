---
title: สร้างและจัดการความสัมพันธ์ใน Power BI Desktop
description: สร้างและจัดการความสัมพันธ์ใน Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 06/05/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: f84e43a96243841b247530b5639f5f0c6ae1bb4f
ms.sourcegitcommit: fbb7924603f8915d07b5e6fc8f4d0c7f70c1a1e1
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/02/2018
ms.locfileid: "34813675"
---
# <a name="create-and-manage-relationships-in-power-bi-desktop"></a>สร้างและจัดการความสัมพันธ์ใน Power BI Desktop
เมื่อคุณนำเข้าหลายตาราง มีโอกาสที่คุณจะต้องทำการวิเคราะห์โดยใช้ข้อมูลจากตารางเหล่านั้นทั้งหมด ความสัมพันธ์ระหว่างตารางเหล่านั้นเป็นสิ่งจำเป็นสำหรับการคำนวณผลลัพธ์อย่างถูกต้อง และแสดงข้อมูลในรายงานของคุณอย่างถูกต้อง Power BI Desktop ทำให้สร้างความสัมพันธ์ดังกล่าวได้ง่ายขึ้น ในความเป็นจริง ในกรณีส่วนใหญ่คุณไม่จำเป็นต้องทำอะไร คุณลักษณะการตรวจหาอัตโนมัติทำได้สำหรับคุณ อย่างไรก็ตาม ในบางกรณีคุณอาจต้องสร้างความสัมพันธ์ด้วยตนเอง หรือคุณอาจจำเป็นต้องทำการเปลี่ยนแปลงบางอย่างสำหรับความสัมพันธ์นั้น ไม่ว่าด้วยใช้วิธีใด จำเป็นต้องทำความเข้าใจความสัมพันธ์ใน Power BI Desktop วิธีการสร้างและวิธีการแก้ไขใจความสัมพันธ์เหล่านี้

## <a name="autodetect-during-load"></a>ตรวจหาอัตโนมัติระหว่างการโหลด
ถ้าคุณสร้างแบบสอบถามสองตารางหรือมากกว่าในเวลาเดียวกัน เมื่อข้อมูลถูกโหลด Power BI Desktop จะพยายามทำการค้นหาและสร้างความสัมพันธ์สำหรับคุณ จำนวนสมาชิกในเซ็ต ทิศทางตัวกรองข้าม และคุณสมบัติที่ใช้งานอยู่จะถูกตั้งค่าโดยอัตโนมัติ ลักษณะของ Power BI Desktop ที่ชื่อคอลัมน์ในตารางที่คุณกำลังสอบถามเพื่อดูว่ามีความสัมพันธ์ใดที่อาจเกิดขึ้นได้บ้าง ถ้าไม่มี ความสัมพันธ์ดังกล่าวจะถูกสร้างขึ้นโดยอัตโนมัติ ถ้า Power BI Desktop ไม่สามารถกำหนดได้ด้วยความน่าเชื่อมั่นในระดับสูงว่ามีค่าที่ตรงกัน Power BI Desktop จะไม่สร้างความสัมพันธ์ขึ้นโดยอัตโนมัติ คุณยังคงสามารถใช้กล่องโต้ตอบการจัดการความสัมพันธ์เพื่อสร้างหรือแก้ไขความสัมพันธ์ได้

## <a name="create-a-relationship-by-using-autodetect"></a>สร้างความสัมพันธ์โดยใช้การตรวจหาอัตโนมัติ
ที่แถบ**หน้าแรก** คลิก**จัดการความสัมพันธ์** \> **ตรวจหาอัตโนมัติ**

![](media/desktop-create-and-manage-relationships/automaticrelationship.gif)

## <a name="create-a-relationship-manually"></a>สร้างความสัมพันธ์ด้วยตนเอง
1. ที่แถบ**หน้าแรก** คลิก**จัดการความสัมพันธ์** \> **ใหม่**
2. ในกล่องโต้ตอบ**สร้างความสัมพันธ์** ในรายการแบบเลื่อนลงแรกของตาราง เลือกตาราง จากนั้น เลือกคอลัมน์ที่คุณต้องการใช้ในความสัมพันธ์
3. ในการไปรายการแบบเลื่อนลงของตารางที่สอง เลือกตารางอื่นที่คุณต้องการในความสัมพันธ์ จาก นั้นเลือกคอลัมน์อื่นที่คุณต้องการใช้ แล้ว คลิก**ตกลง**

![](media/desktop-create-and-manage-relationships/manualrelationship2.gif)

ตามค่าเริ่มต้น Power BI Desktop จะกำหนดค่าจำนวนสมาชิกในเซ็ต (ทิศทาง) ทิศทางตัวกรองข้าม และคุณสมบัติที่ใช้งานอยู่โดยอัตโนมัติสำหรับความสัมพันธ์ใหม่ของคุณ อย่างไรก็ตาม คุณสามารถเปลี่ยนแปลงค่าเหล่านี้ถ้าจำเป็น เมื่อต้องการเรียนรู้เพิ่มเติม ดูหัวข้อการทำความเข้าใจตัวเลือกเพิ่มเติมในภายหลังในบทความนี้

โปรดทราบว่าคุณจะเห็นข้อผิดพลาดที่ระบุว่า *หนึ่งในคอลัมน์ต้องมีค่าที่ไม่ซ้ำ*ถ้าตารางที่เลือกสำหรับความสัมพันธ์ไม่มีค่าที่ไม่ซ้ำกัน อย่างน้อยหนึ่งตารางในความสัมพันธ์*ต้อง*มีรายการที่แตกต่างและไม่ซ้ำกันของค่าคีย์ ซึ่งเป็นข้อกำหนดทั่วไปสำหรับเทคโนโลยีฐานข้อมูลเชิงสัมพันธ์ทั้งหมด 

ถ้าคุณพบข้อผิดพลาดนั้น มีสองสามวิธีในการแก้ไขปัญหา:

* ใช้ "การลบแถวที่ซ้ำกัน" เพื่อสร้างคอลัมน์ที่มีค่าที่ไม่ซ้ำกัน ข้อด้อยของวิธีการนี้คือ คุณจะสูญเสียข้อมูลเมื่อแถวที่ซ้ำกันถูกลบออกไป และโดยมากแล้ว คีย์ (แถว) ที่ทำซ้ำจะทำด้วยเหตุผลที่ดีเสมอ
* เพิ่มตารางที่มีตัวกลางประกอบด้วยรายการของค่าคีย์ที่แตกต่างกันไปยังแบบจำลอง ซึ่งจากนั้นจะถูกเชื่อมโยงไปยังทั้งสองคอลัมน์ต้นฉบับในความสัมพันธ์ดังกล่าว

สำหรับข้อมูลรายละเอียดเพิ่มเติม ดู[บล็อกโพสต์](https://blogs.technet.microsoft.com/cansql/2016/12/19/relationships-in-power-bi-fixing-one-of-the-columns-must-have-unique-values-error-message/)ที่กล่าวถึงส่วนนี้ในรายละเอียด


## <a name="edit-a-relationship"></a>แก้ไขความสัมพันธ์
1. ที่แถบ**หน้าแรก** คลิก**จัดการความสัมพันธ์**
2. ที่กล่องโต้ตอบ**จัดการความสัมพันธ์** เลือกความสัมพันธ์ จาก นั้นคลิก**แก้ไข**

## <a name="configure-additional-options"></a>ตัวเลือกเพิ่มเติมสำหรับการกำหนดค่า
เมื่อคุณสร้างหรือแก้ไขความสัมพันธ์ คุณสามารถกำหนดค่าตัวเลือกเพิ่มเติมได้  ตามค่าเริ่มต้น ตัวเลือกเพิ่มเติมจะกำหนดค่าโดยอัตโนมัติโดยยึดตามค่าการคาดเดาที่ดีที่สุด ซึ่งอาจแตกต่างกันสำหรับแต่ละความสัมพันธ์ที่ยึดตามข้อมูลในคอลัมน์

## <a name="cardinality"></a>จำนวนสมาชิกในเซ็ต
**หลายจำนวนต่อหนึ่ง (\*: 1)** -นี่คือประเภทที่ใช้มากที่สุด เป็นประเภทค่าเริ่มต้น ซึ่งหมายความว่าคอลัมน์ในตารางหนึ่งสามารถมีมากกว่าหนึ่งค่าตัวอย่าง และตารางอื่นที่เกี่ยวข้องที่รู้จักกันว่าเป็นตารางการค้นหา มักจะมีเพียงหนึ่งค่าตัวอย่าง

**หนึ่ง (1:1)** - ซึ่งหมายความว่าคอลัมน์ในตารางหนึ่งมีเพียงหนึ่งค่าตัวอย่างของค่าใดค่าหนึ่ง และตารางอื่นที่เกี่ยวข้องมีเพียงหนึ่งค่าตัวอย่างของค่าใดค่าหนึ่ง

สำหรับรายละเอียดเพิ่มเติมเกี่ยวกับเวลาเมื่อต้องเปลี่ยนจำนวนสมาชิกในเซ็ต ดูส่วนการทำความเข้าใจตัวเลือกเพิ่มเติมในภายหลังในบทความนี้

## <a name="cross-filter-direction"></a>ทิศทางตัวกรองข้าม
**ทั้งสองอย่าง**-นี่คือทิศทางเริ่มต้นที่พบบ่อยที่สุด ซึ่งหมายความว่า สำหรับวัตถุประสงค์ในการกรอง จะมีการใช้งานทั้งสองตารางเหมือนกับว่าเป็นตารางเดียว  ซึ่งใช้งานได้ดีกับตารางเดียวที่มีหมายเลขของตารางการค้นหาที่ล้อมรอบอยู่  ตัวอย่างคือตารางที่เกิดขึ้นจริงสำหรับการขายที่มีตารางการค้นหาสำหรับแผนก  ซึ่งมักจะเรียกว่าการกำหนดค่าเค้าร่างดาว (จากตารางศูนย์กลางที่มีตารางการค้นหาหลายครั้ง)  อย่างไรก็ตาม ถ้าคุณมีอย่างน้อยสองตารางที่มีตารางการค้นหาด้วย (มีบางตารางที่เหมือนกัน) คุณไม่ต้องใช้การตั้งค่าแบบ ทั้งสอง  เมื่อต้องการใช้ตัวอย่างก่อนหน้าต่อไป ในกรณีนี้ คุณจะมีตารางงบประมาณการขายที่จะบันทึกงบประมาณเป้าหมายสำหรับแต่ละแผนกด้วย  และตารางแผนกจะเชื่อมต่อกับทั้งตารางการขายและตารางงบประมาณ  หลีกเลี่ยงการตั้งค่าทั้งสองสำหรับการกำหนดค่าชนิดนี้

**เดียว**- ซึ่งหมายความว่า ตัวเลือกในการกรองในตารางการที่เชื่อมต่อทำงานบนตารางที่จะมีการรวมค่า ถ้าคุณนำเข้า Power Pivot ใน Excel 2013 หรือแบบจำลองข้อมูลก่อนหน้า ความสัมพันธ์ทั้งหมดจะมีทิศทางเดียว 

สำหรับรายละเอียดเพิ่มเติมเกี่ยวกับเวลาเมื่อต้องเปลี่ยนทิศทางตัวกรองข้าม ดูส่วนการทำความเข้าใจตัวเลือกเพิ่มเติมในภายหลังในบทความนี้

## <a name="make-this-relationship-active"></a>เปิดใช้งานความสัมพันธ์นี้
เมื่อเลือกส่วนนี้ หมายความว่าความสัมพันธ์ทำหน้าที่เป็นการเปิดใช้งาน เป็นความสัมพันธ์เริ่มต้น  ในกรณีไม่มีมากกว่าหนึ่งความสัมพันธ์ระหว่างตารางสองตาราง ความสัมพันธ์ที่ใช้งานอยู่มีวิธีสำหรับ Power BI Desktop เพื่อสร้างการแสดงภาพที่มีทั้งสองตารางโดยอัตโนมัติ

สำหรับรายละเอียดเพิ่มเติมเกี่ยวกับเวลาเมื่อต้องเปิดใช้งานความสัมพันธ์ใดความสัมพันธ์หนึ่ง ดูส่วนการทำความเข้าใจตัวเลือกเพิ่มเติมในภายหลังในบทความนี้

## <a name="understanding-relationships"></a>ทำความเข้าใจความสัมพันธ์
เมื่อคุณเชื่อมต่อสองตารางเข้ากับความสัมพันธ์ หนึ่ง คุณสามารถทำงานกับข้อมูลในทั้งสองตารางได้ในตารางเดียว ทำให้คุณไม่ต้องกังวลเกี่ยวกับรายละเอียดความสัมพันธ์หรือบีบตารางเหล่านั้นลงในตารางเดียวก่อนที่นำเข้า  ในหลายสถานการณ์ Power BI Desktop สามารถสร้างความสัมพันธ์ให้กับคุณได้อัตโนมัติ ซึ่งทำให้คุณอาจไม่ต้องสร้างความสัมพันธ์ด้วยตนเอง อย่างไรก็ตาม ถ้า Power BI Desktop ไม่สามารถกำหนดได้ด้วยความแน่นอนระดับสูงว่าความสัมพันธ์ระหว่างตารางสองตารางนนั้นควรมีอยู่ Power BI Desktop จะไม่สร้างความสัมพันธ์โดยอัตโนมัติ ในกรณีดังกล่าว คุณจะต้องสร้างความสัมพันธ์   

เรามาเรียนรู้ในบทช่วยสอนสักเล็กน้อยเพื่อแสดงให้คุณเห็นว่าความสัมพันธ์ทำงานอย่างไรใน Power BI Desktop

>[!TIP]
>คุณสามารถเรียนรู้บทเรียนนี้ให้เสร็จสมบูรณ์ได้ด้วยตัวเอง คัดลอกตาราง ProjectHours ด้านล่างลงในแผ่นงาน Excel เลือกเซลล์ทั้งหมด คลิก**แทรก** \> **ตาราง** ในกล่องโต้ตอบ**สร้างตาราง** เพียงคลิก**ตกลง** จากนั้นที่**ชื่อตาราง** พิมพ์**ProjectHours** ทำเหมือนกันสำหรับตาราง CompanyProject คุณสามารถนำเข้าข้อมูลนั้น โดยใช้**รับข้อมูล**ใน Power BI Desktop ได้ เลือกสมุดงานและตารางของคุณเป็นแหล่งข้อมูล

ตารางแรกนี้ นั่นคือ ProjectHours เป็นบันทึกของตั๋วงานที่บันทึกจำนวนชั่วโมงที่บุคคลหนึ่งทำงานในโครงการใดโครงการหนึ่ง  

**ProjectHours**

| **ตั๋ว** | **SubmittedBy** | **ชั่วโมง** | **โครงการ** | **DateSubmit** |
| ---:|:--- | ---:|:--- | ---:|
| 1001 |Brewer, Alan |22 |สีฟ้า |1/1/2013 |
| 1002 |Brewer, Alan |26 |สีแดง |2/1/2013 |
| 1003 |Ito, Shu |34 |เหลือง |12/4/2012 |
| 1004 |Brewer, Alan |13 |ส้ม |1/2/2012 |
| 1005 |Bowen, Eli |29 |ม่วง |10/1/2013 |
| 1006 |Bento, Nuno |35 |เขียว |2/1/2013 |
| 1007 |Hamilton, David |10 |เหลือง |10/1/2013 |
| 1008 |Han, Mu |28 |ส้ม |1/2/2012 |
| 1009 |Ito, Shu |22 |ม่วง |2/1/2013 |
| 1010 |Bowen, Eli |28 |เขียว |10/1/2013 |
| 1011 |Bowen, Eli |9 |สีฟ้า |10/15/2013 |

ตารางที่สองนี้นั่นคือ CompanyProject เป็น รายการของโครงการที่มีการกำหนดลำดับความสำคัญเป็น A, B หรือ c 

**CompanyProject**

| **ProjName** | **ลำดับความสำคัญ** |
| --- | --- |
| สีฟ้า |A |
| สีแดง |B |
| เขียว |C |
| เหลือง |C |
| ม่วง |B |
| ส้ม |C |

โปรดสังเกตว่าแต่ละตารางมีหนึ่งคอลัมน์โครงการ แต่ละรายการจะมีชื่อต่างกันเล็กน้อย แต่ดูเหมือนว่ามีค่าเดียวกัน ซึ่งนั่นเป็นสิ่งสำคัญ แล้วเราจะกลับมาดูอีกครั้งในอีกสักครู่

หลังจากที่เรามีสองตารางที่นำเข้ามาในหนึ่งแบบจำลอง เราลองสร้างรายงานกัน สิ่งแรกที่เราต้องการสร้างคือ จำนวนชั่วโมงที่ยื่นตามลำดับความสำคัญโครงการ ดังนั้นเราเลือก**ลำดับความสำคัญ**และ**ชั่วโมง**จากช่องข้อมูล

 ![](media/desktop-create-and-manage-relationships/candmrel_reportfiltersnorel.png)

ถ้าเราดูที่ตารางของเราในพื้นที่รายงาน คุณจะเห็นจำนวนชั่วโมงเป็น **256.00** สำหรับแต่ละโครงการ และนั่นเป็นผลรวมด้วย เห็นได้ชัดเจนว่าานั่นไม่ถูกต้อง ทำไม? เนื่องจากเราไม่สามารถคำนวณผลรวมของค่าจากหนึ่งตารางได้ (ตารางชั่วโมงในโครงการ) แบ่งส่วนโดยค่าในตารางอื่น (ลำดับความสำคัญในตาราง CompanyProject) โดยไม่มีความสัมพันธ์ระหว่างตารางสองตาราง

ดังนั้น เรามาลองสร้างความสัมพันธ์ระหว่างสองตารางเหล่านี้

คุณจำคอลัมน์ที่เราเห็นในทั้งสองตารางที่มีหนึ่งชื่อโครงการแต่มีค่าที่มีลักษณะเหมือนกันได้หรือไม่? เรากำลังจะใช้สองคอลัมน์เหล่านี้ในการสร้างความสัมพันธ์ระหว่างตารางของเรา

ทำไมใช้คอลัมน์เหล่านี้? ถ้าเราดูที่คอลัมน์โครงการในตาราง ProjectHours เราจะเห็นค่า เช่น สีฟ้า สีแดง สีเหลือง สีส้ม และอื่น ๆ ที่จริงแล้วเราเห็นแถวหลายแถวที่มีค่าเดียวกัน ผลคือ เรามีค่าสีมากมายสำหรับ Project

ถ้าเราดูที่คอลัมน์ ProjName ในตาราง CompanyProject เราจะเห็นว่ามีเพียงหนึ่งค่าสีสำหรับแต่ละค่าสำหรับโครงการ แต่ละค่าสีในตารางนี้เป็นค่าเฉพาะและมีความสำคัญ เนื่องจากเราสามารถสร้างความสัมพันธ์ระหว่างตารางสองตารางนี้ได้ ในกรณีนี้เป็นความสัมพันธ์แบบกลุ่มต่อหนึ่ง ในความสัมพันธ์แบบกลุ่มต่อกลุ่ม-ต่อ-หนึ่ง อย่างน้อยหนึ่งคอลัมน์ในหนึ่งตารางต้องประกอบด้วยค่าที่ไม่ซ้ำ มีตัวเลือกเพิ่มเติมสำหรับบางความสัมพันธ์ และเราจะดูตัวเลือกเหล่านี้ในภายหลัง แต่ในตอนนี้ ลองสร้างความสัมพันธ์ระหว่างคอลัมน์โครงการในแต่ละตารางจากทั้งสองตารางของเรา

### <a name="to-create-the-new-relationship"></a>การสร้างความสัมพันธ์ใหม่
1. คลิก**จัดการความสัมพันธ์**์
2. ใน**จัดการความสัมพันธ์** คลิก**ใหม่** ซึ่งจะเปิดกล่องโต้ตอบ**สร้างความสัมพันธ์** ที่เราสามารถเลือกตาราง คอลัมน์ และการตั้งค่าเพิ่มเติมที่เราต้องการสำหรับความสัมพันธ์ของเราได้
3. ในตารางแรก เลือก**ProjectHours** และเลือกคำ**โครงการ**คอลัมน์ นี่คือด้านที่เป็นกลุ่มของความสัมพันธ์ของเรา
4. ในตารางที่สอง เลือก**CompanyProject**แล้วเลือกคำ**ProjName**คอลัมน์ นี่คือด้านที่เป็นหนึ่งความสัมพันธ์ของเรา  
5. ทำต่อไปและคลิก**ตกลง**ในทั้งกล่องโต้ตอบ**สร้างความสัมพันธ์**และกล่องโต้ตอบ**การจัดการความสัมพันธ์**

![](media/desktop-create-and-manage-relationships/candmrel_create_compproj.png)

เพื่อให้สามารถเปิดเผยได้เต็มรูปแบบ คุณต้องสร้างความสัมพันธ์นี้ด้วยวิธีที่ยาก คุณไม่สามารถเพียงแค่คลิกปุ่มตรวจหาอัตโนมัติในกล่องโต้ตอบการจัดการความสัมพันธ์ อันที่จริง การตรวจหาอัตโนมัติจะต้องดำเนินการดังกล่าวแล้วสำหรับคุณเมื่อคุณโหลดข้อมูลหากทั้งสองคอลัมน์ที่มีชื่อเดียวกัน แต่ความท้าทายในที่ีนี้คืออะไร?

ตอนนี้เรามาดูที่ตารางในพื้นที่รายงานของเราอีกครั้ง

 ![](media/desktop-create-and-manage-relationships/candmrel_reportfilterswithrel.png)

ตอนนี้ดูดีขึ้นมากเลย ใช่หรือไม่?

เมื่อเราหาผลรวมของค่าชั่วโมงตามลำดับความสำคัญ Power BI Desktop จะค้นหาทุก ๆ ค่าสีตัวอย่างที่ไม่ซ้ำกันในตารางการค้นหา CompanyProject จากนั้นจะมองหาสำหรับทุก ๆ ตัวอย่างที่มีอยู่สำหรับแต่ละค่าในตาราง CompanyProject และคำนวณผลรวมทั้งหมดสำหรับแต่ละค่าที่ไม่ซ้ำกัน

การทำเช่นนี้ทำได้ค่อนข้างง่าย ด้วยตรวจหาอัตโนมัติคุณอาจไม่ต้องทำขั้นตอนนี้มากนัก

## <a name="understanding-additional-options"></a>การทำความเข้าใจตัวเลือกเพิ่มเติม
เมื่อมีการสร้างความสัมพันธ์ไม่ว่าด้วยตรวจหาอัตโนมัติหรือ่คุณสร้างขึ้นด้วยตนเอง Power BI Desktop จะกำหนดค่าตัวเลือกเพิ่มเติมที่ยึดตามข้อมูลในตารางของคุณโดยอัตโนมัติ คุณสามารถกำหนดค่าคุณสมบัติความสัมพันธ์เพิ่มเติมเหล่านี้ที่อยู่ในส่วนต่ำสุดของกล่องโต้ตอบความสัมพันธ์การสร้าง/แก้ไขได้

 ![](media/desktop-create-and-manage-relationships/candmrel_advancedoptions2.png)

ตามที่ได้กล่าว ขั้นตอนเหล่านี้จะถูกตั้งค่าโดยอัตโนมัติตามปกติแล้ว และคุณไม่จำเป็นต้องทำอะไร อย่างไรก็ตาม มีหลายสถานการณ์ที่คุณอาจต้องการกำหนดค่าตัวเลือกเหล่านี้ด้วยตัวคุณเอง

## <a name="future-updates-to-the-data-require-a-different-cardinality"></a>การอัปเดตในอนาคตไปยังข้อมูลที่จำเป็นสำหรับจำนวนสมาชิกในเซ็ตต่าง ๆ
โดยปกติแล่ว Power BI Desktop สามารถกำหนดจำนวนสมาชิกในเซ็ตที่ดีที่สุดสำหรับความสัมพันธ์ได้โดยอัตโนมัติ  ถ้าคุณต้องการแทนที่การตั้งค่าโดยอัตโนมัติเนื่องจากคุณทราบว่าข้อมูลจะเปลี่ยนแปลงในอนาคต คุณสามารถเลือกได้ที่การควบคุมจำนวนสมาชิกในเซ็ต มาดูตัวอย่างที่เราจำเป็นต้องเลือกจำนวนสมาชิกในเซ็ตที่แตกต่างกัน

ตาราง CompanyProjectPriority ด้านล่างคือ รายการและลำดับความสำคัญของโครงการทั้งหมดของบริษัท ตาราง ProjectBudget คือ ชุดของโครงการที่ได้รับอนุมัติงบประมาณ

**ProjectBudget**

| **โครงการที่อนุมัติ** | **BudgetAllocation** | **AllocationDate** |
|:--- | ---:| ---:|
| สีฟ้า |40,000 |12/1/2012 |
| สีแดง |100,000 |12/1/2012 |
| เขียว |50,000 |12/1/2012 |

**CompanyProjectPriority**

| **โครงการ** | **ลำดับความสำคัญ** |
| --- | --- |
| สีฟ้า |A |
| สีแดง |B |
| เขียว |C |
| เหลือง |C |
| ม่วง |B |
| ส้ม |C |

ถ้าเราสร้างความสัมพันธ์ระหว่างคอลัมน์โครงการในตาราง CompanyProjectPriority และ ApprovedProjects คอลัมน์ในตาราง ProjectBudget ดังนี้:

 ![](media/desktop-create-and-manage-relationships/candmrel_create_compproj_appproj2.png)

จำนวนสมาชิกในเซ็ตจะถูกตั้งค่าเป็นแบบหนึ่งต่อหนึ่ง (1:1) โดยอัตโนมัติ และการกรองไขว้เป็นแบบ ทั้งสอง (ตามที่แสดง)  ทั้งนี้เนื่องจากสำหรับ Power BI Desktop แล้ว การรวมกันที่ดีที่สุดของสองตารางจะมีลักษณะดังนี้:

| **โครงการ** | **ลำดับความสำคัญ** | **BudgetAllocation** | **AllocationDate** |
|:--- | --- | ---:| ---:|
| สีฟ้า |A |40,000 |12/1/2012 |
| สีแดง |B |100,000 |12/1/2012 |
| เขียว |C |50,000 |12/1/2012 |
| เหลือง |C |<br /> |<br /> |
| ม่วง |B |<br /> |<br /> |
| ส้ม |C |<br /> |<br /> |

มีความสัมพันธ์แบบหนึ่งต่อหนึ่งระหว่างสองตารางของเราเนื่องจากไม่มีค่าที่ไม่ซ้ำกันในคอลัมน์โครงการของตารางที่รวมกัน คอลัมน์โครงการจะไม่ซ้ำกันเนื่องจากแต่ละค่าเกิดขึ้นเพียงครั้งเดียว ดังนั้น เราสามารถรวมแถวต่าง ๆ จากสองตารางโดยตรงโดยไม่ต้องทำซ้ำได้

แต่สมมติว่าคุณทราบว่าข้อมูลจะเปลี่ยนในครั้งถัดไปที่คุณทำการรีเฟรช ในขณะนี้ ตาราง ProjectBudget เวอร์ชั่นรีเฟรชมีแถวเพิ่มเติมสำหรับสีฟ้าและสีแดง:

**ProjectBudget**

| **โครงการที่อนุมัติ** | **BudgetAllocation** | **AllocationDate** |
| --- | ---:| ---:|
| สีฟ้า |40,000 |12/1/2012 |
| สีแดง |100,000 |12/1/2012 |
| เขียว |50,000 |12/1/2012 |
| สีฟ้า |80,000 |6/1/2013 |
| สีแดง |90,000 |6/1/2013 |

 ซึ่งหมายความว่า การรวมกันที่ดีที่สุดของทั้งสองตารางในขณะนี้มีลักษณะดังนี้: 

| **โครงการ** | **ลำดับความสำคัญ** | **BudgetAllocation** | **AllocationDate** |
| --- | --- | ---:| ---:|
| สีฟ้า |A |40,000 |12/1/2012 |
| สีแดง |B |100,000 |12/1/2012 |
| เขียว |C |50,000 |12/1/2012 |
| เหลือง |C |<br /> |<br /> |
| ม่วง |B |<br /> |<br /> |
| ส้ม |C |<br /> |<br /> |
| สีฟ้า |A |80000 |6/1/2013 |
| สีแดง |B |90000 |6/1/2013 |

ในตารางรวมใหมนี้่ คอลัมน์โครงการจะมีค่าที่ซ้ำกัน  ทั้งสองตารางต้นฉบับจะไม่มีความสัมพันธ์แบบหนึ่งต่อหนึ่งเมื่อมีการรีเฟรชตาราง ในกรณีนี เนื่องจากเราทราบว่าการปรับปรุงเหล่านั้นในอนาคตจะทำให้คอลัมน์โครงการมีรายการที่ซ้ำกัน เราต้องการตั้งค่าจำนวนนับเป็น กลุ่ม-ต่อ-หนึ่ง (\*: 1) โดยหลายด้านบน ProjectBudget และหนึ่งบนด้าน CompanyProjectPriority

## <a name="adjusting-cross-filter-direction-for-a-complex-set-of-tables-and-relationships"></a>ปรับทิศทางตัวกรองข้ามสำหรับชุดที่ซับซ้อนของตารางและความสัมพันธ์ต่าง ๆ
สำหรับความสัมพันธ์ส่วนใหญ่ ทิศทางตัวกรองข้ามถูกตั้งค่าเป็น 'ทั้งสอง'  อย่างไรก็ตาม มีบางสถานการณ์ที่คุณอาจจำเป็นต้องตั้งค่านี้แตกต่างจากค่าเริ่มต้น เช่น ถ้าคุณกำลังนำเข้าแบบจำลองจาก Power Pivot จากเวอร์ชั่นที่เก่ากว่า โดยที่ทุกความสัมพันธ์ถูกตั้งค่าเป็นทิศทางเดียว 

ในการตั้งค่าแบบ ทั้งสอง จะเปิดใช้งาน Power BI Desktop เพื่อจัดการกับข้อมูลทั้งหมดของตารางที่เชื่อมต่อกันในแบบเป็นตารางเดียว  อย่างไรก็ตาม มีบางสถานการณ์ที่ Power BI Desktop ไม่สามารถตั้งค่าทิศทางตัวกรองข้ามของความสัมพันธ์เป็น 'ทั้งสอง' ได้ และยังทำให้ชุดของค่าเริ่มต้นที่ชัดเจนพร้อมใช้งานสำหรับการรายงาน ถ้าทิศทางตัวกรองข้ามของความสัมพันธ์ไม่ได้ตั้งค่าเป็นแบบ ทั้งสอง โดยปกติแล้วจะเป็นเพราะระบบสร้างค่าที่ไม่ชัดเจน  ถ้าการตั้งค่าตัวกรองข้ามที่เป็นค่าเริ่มต้นใช้ไม่ได้สำหรับคุณ ลองตั้งค่าไปยังเฉพาะตารางหรือแบบทั้งสอง

การกรองไขว้ทิศทางเดียวใช้งานได้สำหรับหลายสถานการณ์  อันที่จริงแล้ว ถ้าคุณได้นำเข้าแบบจำลองจาก Power Pivot ใน Excel 2013 หรือเวอร์ชันก่อนหน้า ความสัมพันธ์ทั้งหมดจะถูกตั้งค่าเป็นทิศทางเดียว  ทิศทางเดียวหมายความว่า ตัวเลือกการกรองข้อมูลที่เชื่อมต่อตารางทำงานบนตารางที่เกิดการรวมกันขึ้น  บางครั้ง การทำความเข้าใจเกี่ยวกับการกรองไขว้อาจเป็นเรื่องยากเล็กน้อย ดังนั้นให้ลองดูที่ตัวอย่าง

 ![](media/desktop-create-and-manage-relationships/candmrel_singledircrossfiltering.png)

ด้วยการกรองไขว้ทิศทางเดียว หากคุณสร้างรายงานที่สรุปจำนวนชั่วโมงของโครงการ คุณจะสามารถเลือกที่จะสรุป (หรือกรอง) ตาม โครงการของบริษัท ลำดับความสำคัญ พนักงานของบริษัท หรือเมืองได้   ถ้าอย่างไรก็ตาม คุณต้องการนับจำนวนพนักงานต่อโครงการ (คำถามที่พบน้อย) จะไม่สามารถทำได้ คุณจะได้รับเป็นคอลัมน์ที่มีค่าที่เหมือนกันทั้งหมด  ในตัวอย่างด้านล่าง ความสัมพันธ์ทั้งสองของทิศทางการกรองไขว้ถูกตั้งค่าเป็นทิศทางเดียวไปทางตาราง ProjectHours:

 ![](media/desktop-create-and-manage-relationships/candmrel_repcrossfiltersingle.png)

ข้อกำหนดตัวกรองจะจัดเรียงต่อเนื่องจาก CompanyProject ไปยัง CompanyEmployee (ดังที่แสดงในรูปด้านล่าง) แต่ข้อกำหนดตัวกรองดังกล่าวจะไม่จัดเรียงไปถึง CompanyEmployee  อย่างไรก็ตาม ถ้าคุณตั้งค่าทิศทางการกรองไขว้เป็น ทั้งสอง คุณจะสามารถใช้งานได้  การตั้งค่าแบบทั้งสองทำให้ข้อกำหนดตัวกรองจัดเรียงไปจนถึงพนักงาน

 ![](media/desktop-create-and-manage-relationships/candmrel_bidircrossfiltering.png)

ด้วยทิศทางตัวกรองไขว้ที่ตั้งค่าเป็นแบบทั้งสอง ตอนนี้รายงานของเราจะปรากฏขึ้นอย่างถูกต้อง:

 ![](media/desktop-create-and-manage-relationships/candmrel_repcrossfilterbi.png)

ทิศทางการกรองไขว้แบบ ทั้งสอง ใช้ได้ดีีกับรูปแบบของความสัมพันธ์ของตารางที่มีลักษณะเหมือนรูปแบบด้านบน ซึ่งมักเรียกว่า เค้าร่างดาว ดังนี้:

 ![](media/desktop-create-and-manage-relationships/candmrel_crossfilterstarschema.png)

ทิศทางการกรองไขว้ไม่ทำงานได้ดีกับรูปแบบที่พบเห็นได้ทั่วไปมากกว่า ซึ่งมักจะพบในฐานข้อมูลเช่นในไดอะแกรมนี้:

 ![](media/desktop-create-and-manage-relationships/candmrel_crossfilterwithloops.png)

ถ้าคุณมีรูปแบบตารางดังนี้ นั่นคือเป็นการวนรอบ การกรองไขว้จะอาจสร้างชุดที่ไม่ชัดเจนของความสัมพันธ์ได้ เช่น ถ้าคุณหาผลรวมของค่าช่องข้อมูลจาก ตาราง X จากนั้นเลือกการกรองตามช่องข้อมูลบน ตาราง Y ดังนั้นจะไม่ชัดเจนว่าตัวกรองควรเดินทาง ผ่านตารางด้านบนหรือด้านล่างตาราง ตัวอย่างทั่วไปของรูปแบบชนิดนี้จะ มี ตาราง X เป็นตารางยอดขายที่มีข้อมูลจริง และตาราง Y เป็นข้อมูลงบประมาณ ดังนั้น ตารางตรงกลางเป็นตารางการค้นหาที่ทั้งสองตารางใช้ เช่น แผนกหรือภูมิภาค 

เช่นเดียวกับความสัมพันธ์ที่ใช้งานอยู่/ไม่ได้ใช้งาน Power BI Desktop จะไม่อนุญาตให้ความสัมพันธ์กับการตั้งค่าเป็นแบบทั้งสองหากมีการสร้างความไม่ชัดเจนในรายงาน มีหลายวิธีที่แตกต่างกันที่คุณสามารถจัดการกับปรากฏการณ์นี้ และต่อไปนี้เป็นสองแนวทางที่ใช้กันทั่วไปมากที่สุด:

* ลบหรือทำเครื่องหมายความสัมพันธ์เป็น ไม่ได้ใช้งาน เพื่อลดความไม่ชัดเจน จากนั้นคุณอาจสามารถตั้งค่าความสัมพันธ์ระหว่างการกรองไขว้เป็นแบบ ทั้งสอง ได้
* นำเข้าหนึ่งตารางสองครั้ง (โดยที่ครั้งที่สองเป็นชื่ออื่น) เพื่อกำจัดการวนรอบ  ซึ่งทำให้ได้รูปแบบของความสัมพันธ์อย่างเค้าร่างดาว  ด้วยเค้าร่างดาว ความสัมพันธ์ทั้งหมดสามารถตั้งค่าเป็นแบบ ทั้งสอง ได้

## <a name="wrong-active-relationship"></a>ความสัมพันธ์ที่ใช้งานอยู่ไม่ถูกต้อง
เมื่อ Power BI Desktop สร้างความสัมพันธ์โดยอัตโนมัติ ในบางครั้งจะพบมากกว่าหนึ่งความสัมพันธ์ระหว่างตารางสองตาราง  เมื่อเกิดกรณีนี้ขึ้น มีเพียงหนึ่งความสัมพันธ์เท่านั้นที่จะมีการตั้งค่าเป็น ใช้งานอยู่  ความสัมพันธ์ที่ใช้งานอยู่ทำหน้าที่เป็นความสัมพันธ์เริ่มต้นเพื่อให้เมื่อคุณเลือกช่องข้อมูลจากสองตารางที่แตกต่างกันได้ Power BI Desktop สามารถสร้างภาพโดยอัตโนมัติสำหรับคุณได้  อย่างไรก็ตาม ในบางกรณี ความสัมพันธ์ที่เลือกโดยอัตโนมัติอาจไม่ถูกต้อง  คุณสามารถใช้กล่องโต้ตอบ การจัดการความสัมพันธ์ เพื่อตั้งค่าความสัมพันธ์เป็นใช้งานอยู่ หรือไม่ได้ใช้งาน หรือคุณสามารถตั้งค่าความสัมพันธ์ที่ใช้งานอยู่ในกล่องโต้ตอบ การแก้ไขความสัมพันธ์ 

เพื่อให้แน่ใจว่ามีความสัมพันธ์ที่เป็นค่าเริ่มต้น Power BI Desktop อนุญาตเฉพาะความสัมพันธ์ที่ใช้งานอยู่ความสัมพันธ์เดียวระหว่างสองตารางในเวลาที่กำหนด  ดังนั้น คุณต้องตั้งค่าความสัมพันธ์ปัจจุบันเป็น ไม่ได้ใช้งาน ก่อน และจากนั้น ตั้งค่าความสัมพันธ์ที่คุณต้องการให้เป็น ทำงานอยู่

มาลองดูตัวอย่างกัน ตารางแรกนี้เป็น ProjectTickets และตารางถัดไปเป็น EmployeeRole

**ProjectTickets**

| **ตั๋ว** | **OpenedBy** | **SubmittedBy** | **ชั่วโมง** | **โครงการ** | **DateSubmit** |
| ---:|:--- |:--- | ---:|:--- | ---:|
| 1001 |Perham, Tom |Brewer, Alan |22 |สีฟ้า |1/1/2013 |
| 1002 |Roman, Daniel |Brewer, Alan |26 |สีแดง |2/1/2013 |
| 1003 |Roth, Daniel |Ito, Shu |34 |เหลือง |12/4/2012 |
| 1004 |Perham, Tom |Brewer, Alan |13 |ส้ม |1/2/2012 |
| 1005 |Roman, Daniel |Bowen, Eli |29 |ม่วง |10/1/2013 |
| 1006 |Roth, Daniel |Bento, Nuno |35 |เขียว |2/1/2013 |
| 1007 |Roth, Daniel |Hamilton, David |10 |เหลือง |10/1/2013 |
| 1008 |Perham, Tom |Han, Mu |28 |ส้ม |1/2/2012 |
| 1009 |Roman, Daniel |Ito, Shu |22 |ม่วง |2/1/2013 |
| 1010 |Roth, Daniel |Bowen, Eli |28 |เขียว |10/1/2013 |
| 1011 |Perham, Tom |Bowen, Eli |9 |สีฟ้า |10/15/2013 |

**EmployeeRole**

| **พนักงาน** | **บทบาท** |
| --- | --- |
| Bento, Nuno |ผู้จัดการโครงการ |
| Bowen, Eli |ลูกค้าเป้าหมายของโครงการ |
| Brewer, Alan |ผู้จัดการโครงการ |
| Hamilton, David |ลูกค้าเป้าหมายของโครงการ |
| Han, Mu |ลูกค้าเป้าหมายของโครงการ |
| Ito, Shu |ลูกค้าเป้าหมายของโครงการ |
| Perham, Tom |ผู้สนับสนุนโครงการ |
| Roman, Daniel |ผู้สนับสนุนโครงการ |
| Roth, Daniel |ผู้สนับสนุนโครงการ |

จริง ๆ แล้วมีอยู่สองความสัมพันธ์ในนี้ หนึ่งคือ ความสัมพันธ์ระหว่าง SubmittedBy ในตาราง ProjectTickets และพนักงานในตาราง EmployeeRole และอีกความสัมพันธ์คือ ระหว่าง OpenedBy ในตาราง ProjectTickets และพนักงานในตาราง EmployeeRole

 ![](media/desktop-create-and-manage-relationships/candmrel_activerelview.png)

ถ้าเราเพิ่มความสัมพันธ์ทั้งสองไปยังรูปแบบ (โดยเพิ่ม OpenedBy ก่อน) จากนั้นกล่องโต้ตอบจัดการความสัมพันธ์จะแสดงว่า OpenedBy กำลังใช้งานอยู่:

 ![](media/desktop-create-and-manage-relationships/candmrel_managerelactive.png)

ตอนนี้ ถ้าเราสร้างรายงานที่ใช้เขตข้อมูลบทบาท และพนักงานจาก EmployeeRole และเขตข้อมูลชั่วโมงจาก ProjectTickets ในการแสดงภาพของตารางในพื้นที่รายงาน เราจะเห็นเฉพาะผู้สนับสนุนโครงการเท่านั้น เนื่องจากมีเพียงพวกเขาเท่านั้นที่เปิดตั๋วโครงการ

 ![](media/desktop-create-and-manage-relationships/candmrel_repcrossfilteractive.png)

เราสามารถเปลี่ยนความสัมพันธ์ที่กำลังใช้งาน และได้ SubmittedBy แทนที่จะเป็น OpenedBy ในการจัดการความสัมพันธ์ เรายกเลิกการทำเครื่องหมายที่ความสัมพันธ์ ProjectTickets(OpenedBy) ไปยัง EmployeeRole(Employee) และจากนั้น เราทำเครื่องหมายที่ความสัมพันธ์ ProjectTickets(SubmittedBy) ไปยัง EmployeeRole(Employee)

![](media/desktop-create-and-manage-relationships/candmrel_managerelactivesubmittedby.png)

## <a name="see-all-of-your-relationships-in-relationship-view"></a>ดูความสัมพันธ์ทั้งหมดของคุณในมุมมองความสัมพันธ์
บางครั้ง รูปแบบของคุณมีหลายตารางและมีความสัมพันธ์ระหว่างกันที่ซับซ้อน มุมมองความสัมพันธ์ใน Power BI Desktop แสดงความสัมพันธ์ทั้งหมดในรูปแบบของคุณ ทิศทางของความสัมพันธ์นั้น และจำนวนนับ ในไดอะแกรมที่ง่ายต่อความเข้าใจและสามารถกำหนดเองได้ เมื่อต้องการเรียนรู้เพิ่มเติม ดู[มุมมองความสัมพันธ์ใน Power BI Desktop](desktop-relationship-view.md)

