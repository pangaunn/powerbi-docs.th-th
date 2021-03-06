---
title: ใช้หน่วยวัดใน Power BI Desktop
description: หน่วยวัดใน Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 08/08/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: fad623b9472e2992ddb0a6d43cb8d669a1f14cf7
ms.sourcegitcommit: cce10e14c111e8a19f282ad6c032d802ebfec943
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/08/2018
ms.locfileid: "39658138"
---
# <a name="measures-in-power-bi-desktop"></a>หน่วยวัดใน Power BI Desktop

**Power BI Desktop** ช่วยให้คุณสร้างข้อมูลเชิงลึกในข้อมูลของคุณ ด้วยการคลิกเมาส์เพียงไม่กี่ครั้ง แต่ในบางครั้ง ข้อมูลดังกล่าวยังไม่รวมทุกอย่างที่คุณต้องใช้ตอบคำถาม บางคำถามที่สำคัญที่สุดของคุณ หน่วยวัดสามารถช่วยให้คุณไปถึงที่นั่น

หน่วยวัดจะใช้ในการวิเคราะห์ข้อมูลทั่วไปบางส่วน ตัวอย่าง ผลรวม ค่าเฉลี่ย ค่าต่ำสุด หรือสูงสุด จำนวน หรือการคำนวณขั้นสูงเพิ่มเติมที่คุณสร้างด้วยตนเองโดยใช้สูตร DAX ผลลัพธ์จากการคำนวณของหน่วยวัด จะเปลี่ยนแปลงตามการโต้ตอบกับรายงานของคุณ ช่วยให้คุณได้สำรวจข้อมูลเฉพาะกิจได้อย่างรวดเร็วและมีชีวิตชีวา ลองมาดูรายละเอียดกัน

## <a name="understanding-measures"></a>ทำความเข้าใจกับหน่วยวัด

ใน **Power BI Desktop** หน่วยวัดจะถูกสร้างและใช้งานใน**มุมมองรายงาน**หรือ**มุมมองข้อมูล** หน่วยวัดที่คุณสร้าง จะปรากฏในรายการเขตข้อมูลพร้อมไอคอนรูปเครื่องคิดเลข คุณสามารถตั้งชื่อหน่วยวัดเป็นอะไรก็ได้ที่คุณต้องการ และเพิ่มลงในการแสดงภาพใหม่หรือที่มีอยู่แล้ว เช่นเดียวกับเขตข้อมูลอื่น ๆ

![](media/desktop-measures/measuresinpbid_measinfieldlist.png)

> [!NOTE]
> นอกจากนี้คุณอาจจะสนใจ**การวัดผลด่วน** ซึ่งเป็นหน่วยวัดที่สร้างให้แล้ว ที่คุณสามารถเลือกใช้ได้ทันทีจากกล่องโต้ตอบ ซึ่งเป็นวิธีสร้างหน่วยวัดที่รวดเร็ว และยังเป็นวิธีที่ดีที่จะเรียนรู้ไวยากรณ์ DAX เนื่องจากสามารถดูสูตร DAX ที่สร้างขึ้นโดยอัตโนมัติได้ ลองดูบทความนี้: [การวัดผลด่วน](desktop-quick-measures.md)
> 
> 

## <a name="data-analysis-expressions"></a>Data Analysis Expressions

หน่วยวัดคำนวณผลลัพธ์จากสูตรคำนวน เมื่อคุณสร้างหน่วยวัดของคุณเอง คุณจะใช้ภาษาสูตร [Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx) (DAX) DAX มีไลบรารีของฟังก์ชัน ตัวดำเนินการ และโครงสร้างมากกว่า 200 ไลบรารีมีความยืดหยุ่นมากในการสร้างหน่วยวัดเพื่อคำนวณผลลัพธ์สำหรับการวิเคราะห์ข้อมูลใด ๆ ที่ต้องการ

สูตร DAX จะคล้ายกับสูตร Excel มาก DAX ยังมีหลายฟังก์ชันเหมือนกับ Excel เช่น DATE SUM และ LEFT แต่ฟังก์ชันของ DAX มีไว้เพื่อทำงานกับข้อมูลเชิงสัมพันธ์เช่นที่เรามีใน Power BI Desktop

## <a name="lets-look-at-an-example"></a>เรามาดูตัวอย่างกัน
Jan เป็นผู้จัดการฝ่ายขายที่ Contoso เธอถูกขอให้ทำประมาณการยอดขายสำหรับรอบบัญขีปีถัดไป Jan ตัดสินใจที่จะยึดตามการประมาณยอดขายของปีที่แล้ว ด้วยการเพิ่มขึ้นรายปีของอีกหกเปอร์เซ็นต์จากการส่งเสริมการขายต่าง ๆ ที่ถูกจัดกำหนดการในอีกหกเดือนถัดไป

เมื่อต้องรายงานการประมาณ Jan นำเข้าข้อมูลยอดขายของปีที่แล้วลงใน Power BI Desktop เธอพบเขตข้อมูล SalesAmount ในตาราง Reseller Sales เนื่องจากการนำเข้ามีแค่ยอดขายสำหรับปีที่แล้ว Jan จึงเปลี่ยนชื่อเขตข้อมูล SalesAmount เป็น Last Years Sales จากนั้น Jan ลาก Last Years Sales ลงบนพื้นที่รายงาน จะปรากฏขึ้นเป็นค่าเดียวในแผนภูมิ โดยเป็นค่าผลรวมของยอดขายของทุกตัวแทนจำหน่ายจากปีที่แล้ว

Jan สังเกตว่าถึงแม้ว่าเธอไม่ได้ระบุการคำนวณเอง แตก็่มีการระบุโดยอัตโนมัติ Power BI Desktop สร้างหน่วยวัดของตนเอง โดยการรวมค่าทั้งหมดของ ยอดขายปีที่แล้ว

แต่ Jan ต้องการหน่วยวัดเพื่อคำนวณประมาณการสำหรับปีหน้า ซึ่งจะอาศัยยอดขายของปีที่แล้วคูณด้วย 1.06 สำหรับความคาดหวังว่าธุรกิจจะเติบโต 6 เปอร์เซ็นต์ สำหรับการคำนวณนี้ เธอจะสร้างหน่วยวัดของเธอเอง โดยใช้คุณลักษณะหน่วยวัดใหม่ เธอสร้างหน่วยวัดใหม่ จากนั้นใส่สูตร DAX ต่อไปนี้:

    Projected Sales = SUM('Sales'[Last Years Sales])*1.06

จากนั้น Jan ลากหน่วยวัดใหม่ที่ชื่อ Projected Sales ลงในแผนภูมิ

![](media/desktop-measures/measuresinpbid_lastyearsales.png)

Jan ตอนนี้มีหน่วยวัดที่ใช้คำนวณประมาณการยอดขายได้อย่างรวดเร็วและไม่ต้องใช้ความพยายามมากนัก Jan สามารถวิเคราะห์การคาดการณ์ของเธอต่อ โดยการกรองเฉพาะตัวแทนจำหน่าย หรือโดยการเพิ่มเขตข้อมูลอื่นลงในรายงานของเธอ

## <a name="data-categories-for-measures"></a>ประเภทข้อมูลสำหรับหน่วยวัด

คุณยังสามารถเลือกประเภทข้อมูลสำหรับหน่วยวัด 

เหนือสิ่งอื่น สิ่งนี้จะช่วยให้คุณสามารถใช้หน่วยวัดเพื่อสร้าง URL แบบไดนามิก และทำเครื่องหมายประเภทข้อมูลเป็น URL เว็บ 

คุณสามารถสร้างตารางที่แสดงการวัดเป็น URL เว็บ และสามารถคลิกที่ URL ที่ถูกสร้างขึ้นตามการเลือกของคุณ ซึ่งจะเป็นประโยชน์โดยเฉพาะอย่างยิ่งเมื่อคุณต้องการเชื่อมโยงกับรายงาน Power BI อื่น ๆ ด้วย[พารามิเตอร์ตัวกรอง URL](service-url-filters.md)

## <a name="learn-more"></a>เรียนรู้เพิ่มเติม
เราแค่แนะนำคุณเรื่องหน่วยวัดอย่างสั้น ๆ ที่นี่เท่านั้น แต่ยังมีทรัพยากรอีกมากที่ช่วยคุณสร้างหน่วยวัดของตัวเอง ลองไปดู [บทช่วยสอน: สร้างหน่วยวัดของคุณเองใน Power BI Desktop](desktop-tutorial-create-measures.md) ที่ซึ่งคุณสามารถดาวน์โหลดไฟล์ตัวอย่าง และได้รับบทเรียนทีละขั้นตอนเกี่ยวกับวิธีการสร้างหน่วยวัดเพิ่มเติมได้  

ถ้าต้องการเจาะลึกลงไปใน DAX อีก ลองไปดูที่[พื้นฐาน DAX ใน Power BI Desktop](desktop-quickstart-learn-dax-basics.md) [อ้างอิง Data Analysis Expressions](https://msdn.microsoft.com/library/gg413422.aspx) ให้บทความที่ละเอียดของแต่ละ ฟังก์ชัน ไวยากรณ์ ตัวดำเนินการ และข้อกำหนดการตั้งชื่อ DAX มีอยู่แล้วใน Power Pivot ใน Excel และ SQL Server Analysis Services มาหลายปี ดังนั้นจึงมีทรัพยากรที่ยอดเยี่ยมอื่น ๆ อีกมากพร้อมใช้งานเช่นกัน อย่าลืมดู [Wiki DAX Resource Center](http://social.technet.microsoft.com/wiki/contents/articles/1088.dax-resource-center.aspx) ที่มีสมาชิกที่มีชื่อเสียงของชุมชน BI แชร์ความรู้ DAX ของพวกเขา



