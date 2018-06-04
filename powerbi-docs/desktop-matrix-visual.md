---
title: ใช้วิชวลเมทริกซ์ใน Power BI Desktop
description: เรียนรู้วิธีที่วิชวลเมทริกซ์ เปิดให้ใช้งานรูปแบบขั้นและการไฮไลต์ระดับแยกย่อยใน Power BI Desktop
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
ms.date: 02/05/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: de40c8ee25c5facc1c4396c807d38784c11e8bca
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
---
# <a name="use-the-matrix-visual-in-power-bi-desktop"></a>ใช้วิชวลเมทริกซ์ใน Power BI Desktop
ด้วยวิชวล**เมทริกซ์** คุณสามารถสร้างวิชวลเมทริกซ์ (บางครั้งเรียกว่า*ตาราง*) ในรายงาน **Power BI Desktop** และทำไฮไลต์เชื่อมโยงองค์ประกอบภายในเมทริกซ์ กับวิชวลอื่น ๆ นอกจากนี้ คุณยังสามารถเลือกแถว คอลัมน์ และแม้แต่ละเซลล์ และทำไฮไลต์เชื่อมโยง สุดท้าย เพื่อทำให้ใช้งานพื้นที่เค้าโครงได้ดียิ่งขึ้น วิชวลเมทริกซ์สนับสนุนรูปแบบขั้น

![](media/desktop-matrix-visual/matrix-visual_2a.png)

มีคุณลักษณะมากมายที่เกี่ยวข้องกับเมทริกซ์ และเราจะไปศึกษาในส่วนต่อ ๆ ไปของบทความนี้

> [!NOTE]
> เริ่มตั้งแต่การเผยแพร่ เดือนกรกฎาคม 2017 ของ **Power BI Desktop** วิชวลเมทริกซ์และตารางสะท้อนถึงสไตล์ (และสี) จาก**ธีมรายงาน**ที่นำมาใช้ ซึ่งอาจไม่ใช่สีที่คุณต้องการสำหรับวิชวลเมทริกซ์ของคุณ คุณสามารถเปลี่ยนได้ในการกำหนดค่า**ธีมรายงาน**ของคุณ ดู[**ใช้ธีมรายงานใน Power BI Desktop**](desktop-report-themes.md) สำหรับข้อมูลเพิ่มเติมเกี่ยวกับธีม
> 
> 

## <a name="understanding-how-power-bi-calculates-totals"></a>ทำความเข้าใจวิธีที่ Power BI คำนวณผลรวม

ก่อนที่จะกระโดดลงไปในเรื่อง วิธีใช้วิชวล**เมทริกซ์** จำเป็นต้องทำความเข้าใจวิธีที่ Power BI คำนวณค่าผลรวมและผลรวมย่อย ในตารางและเมทริกซ์ สำหรับแถวผลรวมและผลรวมย่อย หน่วยวัดจะคำนวนจากแถวทั้งหมดในข้อมูลเบื้องต้น - ซึ่ง*ไม่*เพียงแค่การบวกค่าในแถวมองเห็นได้ หรือแถวที่แสดงตรง ๆ นี่หมายความว่า คุณอาจได้ค่าผลรวมที่ต่างจากที่คุณคาดหวัง 

ลองดูวิชวล**เมทริกซ์**ต่อไปนี้ 

![](media/desktop-matrix-visual/matrix-visual_3.png)

ในตัวอย่างนี้ แต่ละแถวในของวิชวล**เมทริกซ์**ที่อยู่ทางด้านขวาสุดแสดง*ยอดรวม*สำหรับแต่ละคู่ของ พนักงานขาย/วันที่ แต่เนื่องจากพนักงานขายปรากฏในวันที่หลาย ๆ วัน ตัวเลขอาจปรากฏขึ้นมากกว่าหนึ่งครั้ง ดังนั้น ผลรวมที่ถูกต้องจากข้อมูลต้นแบบ กับการบวกง่าย ๆ ของค่าที่มองเห็น จะไม่เท่ากัน นี่คือรูปแบบที่พบบ่อย เมื่อค่าที่คุณกำลังรวมอยู่บนด้าน 'หนึ่ง' ของความสัมพันธ์แบบหนึ่งต่อกลุ่ม

เมื่อดูผลรวมและผลรวมย่อย จำไว้ว่า ค่าเหล่านั้นจะยึดตามข้อมูลเบื้องต้น และไม่ขึ้นกับค่าที่มองเห็นเท่านั้น 


## <a name="using-drill-down-with-the-matrix-visual"></a>ดูรายละเอียดแนวลึกกับวิชวลเมทริกซ์
ด้วยวิชวล**เมทริกซ์** คุณสามารถดูรายละเอียดหลายอย่างที่น่าสนใจ ที่ไม่เคยทำได้มาก่อน ซึ่งรวมถึงความสามารถในการดูรายละเอียดแนวลึก กับแถว คอลัมน์ และแม้กระทั่งแต่ละส่วนและเซลล์ เราลองมาดูว่าแต่ละอย่างนี้ทำงานอย่างไร

### <a name="drill-down-on-row-headers"></a>ดูรายละเอียดบนส่วนหัวของแถว
ในบานหน้าต่าง**การจัดรูปแบบการแสดงข้อมูล** เมื่อคุณเพิ่มหลายเขตข้อมูลลงในส่วน**แถว**ของ**เขตข้อมูล** คุณเปิดใช้งานแนวลึกบนแถวของวิชวลเมทริกซ์ ซึ่งเหมือนกับการสร้างลำดับชั้น ให้คุณสามารถเจาะลึก (และจากนั้นย้อนกลับขึ้นมา) ตามลำดับชั้น และวิเคราะห์ข้อมูลในแต่ละระดับ

ในรูปต่อไปนี้ ส่วน**แถว**ประกอบด้วย*ประเภท*และ*ประเภทย่อย* เป็นการสร้างการจัดกลุ่ม (หรือลำดับชั้น) ของแถวที่เราสามารถดูรายละเอียด

![](media/desktop-matrix-visual/matrix-visual_4.png)

เมื่อวิชวลนี้มีการจัดกลุ่มที่สร้างขึ้นในส่วน**แถว** วิชวลจะแสดงไอคอน*ดูรายละเอียด*และ*ขยาย* ที่มุมบนซ้ายของวิชวล

![](media/desktop-matrix-visual/matrix-visual_5.png)

คล้ายกับลักษณะการทำงาน ดูรายละเอียด และขยาย ในวิชวลอื่น ๆ การเลือกปุ่มเหล่านี้ให้เราสามารถเจาะลึก (หรือย้อนกลับ) ผ่านลำดับชั้น ในกรณีนี้ เราสามารถเจาะลึกจาก*ประเภท*ไปยัง*ประเภทย่อย* ดังที่แสดงในรูปต่อไปนี้ เมื่อเลือกไอคอนดูรายละเอียดหนึ่งระดับ (รูปส้อมแฉก) แล้ว

![](media/desktop-matrix-visual/matrix-visual_6.png)

นอกจากการใช้ไอคอนเหล่านั้น คุณสามารถคลิกขวาบนส่วนหัวของแถวใด ๆ และดูรายละเอียดแนวลึกโดยเลือกจากเมนูที่ปรากฏขึ้น

![](media/desktop-matrix-visual/matrix-visual_7.png)

โปรดสังเกตว่า มีหลายตัวเลือกบนเมนูที่ปรากฏ ซึ่งสร้างผลลัพธ์ที่แตกต่างกัน:

เลือก**ดูรายละเอียดแนวลึก** ขยายเมทริกซ์สำหรับแถวระดับ*นั้น* *ยกเว้น*หัวแถวอื่น ๆ ทั้งหมดที่ไม่ใช้หัวแถวที่ถูกคลิกขวา ในรูปต่อไปนี้ *คอมพิวเตอร์*ถูกคลิกขวา และเลือก**ดูรายละเอียดแนวลึก** โปรดสังเกตว่า แถวอื่น ๆ ในระดับบนสุดจะไม่ปรากฏในเมทริกซ์ นี่เป็นคุณลักษณะที่มีประโยชน์ และจะน่าสนใจโดยเฉพาะเมื่อเราไปถึงส่วน**ไฮไลต์เชื่อมโยง**

![](media/desktop-matrix-visual/matrix-visual_8.png)

เราสามารถคลิกที่ไอคอน**ดูรายละเอียดเลื่อนขึ้น** เพื่อกลับไปยังมุมมองระดับบนสุดก่อนหน้าได้ ถ้าเราแล้วเลือก**แสดงระดับถัดไป**จากเมนูคลิกขวา เราจะได้รายการตามลำดับตัวอักษร ของรายการในระดับถัดไปทั้งหมด (ในกรณีนี้ คือเขตข้อมูล*ประเภทย่อย*) โดยไม่มีลำดับชั้นสูงกว่าของการจัดประเภท

![](media/desktop-matrix-visual/matrix-visual_8a.png)

เมื่อเราคลิกที่ไอคอน**ดูรายละเอียดเลื่อนขึ้น**ในมุมบนซ้าย เพื่อให้เมทริกซ์แสดงประเภทระดับบนสุดทั้งหมด แล้วคลิกขวาอีกครั้ง และเลือก**ขยายไปยังระดับถัดไป** จะเราเห็นต่อไปนี้:

![](media/desktop-matrix-visual/matrix-visual_9.png)

คุณยังสามารถใช้รายการเมนู**รวม**และ**ไม่รวม** เพื่อเก็บ (หรือเอาออก ตามลำดับ) แถวที่ถูกคลิกขวา (และประเภทย่อยใด ๆ) จากเมทริกซ์

### <a name="drill-down-on-column-headers"></a>ดูรายละเอียดบนส่วนหัวของคอลัมน์
คล้ายกับความสามารถในการเจาะรายละเอียดบนแถว คุณสามารถดูรายละเอียดบน**คอลัมน์**ได้ ในรูปต่อไปนี้ คุณเห็นว่า มีสองเขตข้อมูลใน**คอลัมน์** ที่สร้างเป็นลำดับชั้นแบบเดียวกับที่เราใช้กับแถว ก่อนหน้านี้ในบทความ ในเขตข้อมูล**คอลัมน์** เรามี*ชั้น*และ*สี*

![](media/desktop-matrix-visual/matrix-visual_10.png)

ในวิชวล**เมทริกซ์** เมื่อเราคลิกขวาที่คอลัมน์ เราเห็นตัวเลือกที่จะดูรายละเอียด ในรูปต่อไปนี้ เราคลิกขวาบน *Deluxe* และเลือก**ดูรายละเอียดแนวลึก**

![](media/desktop-matrix-visual/matrix-visual_11.png)

เมื่อ**ดูรายละเอียดแนวลึก**ถูกเลือก ลำดับชั้นคอลัมน์ถัดไปของ *Deluxe* จะแสดง ซึ่งในกรณีนี้คือ*สี*

![](media/desktop-matrix-visual/matrix-visual_12.png)

ส่วนเหลือของรายการเมนูคลิกขวา ทำงานกับคอลัมน์แบบเดียวกับที่ทำให้แถว (ดูส่วนก่อนหน้า**ดูรายละเอียดบนส่วนหัวของแถว**) คุณสามารถ**แสดงระดับถัดไป**, **ขยายไประดับถัดไป** และ**รวม**หรือ**ไม่รวม**คอลัมน์ของคุณ เหมือนกับที่คุณสามารถทำได้กับแถวได้

> [!NOTE]
> ไอคอนดูรายละเอียดแนวลึก และดูข้อมูลสรุป ที่มุมบนซ้ายของวิชวลเมทริกซ์ ใช้กับแถวเท่านั้น เมื่อต้องการเจาะลึกบนคอลัมน์ คุณต้องใช้เมนูคลิกขวา
> 
> 

## <a name="stepped-layout-with-matrix-visuals"></a>รูปแบบขั้น กับวิชวลเมทริกซ์
วิชวล**เมทริกซ์** ทำการเยื้องประเภทย่อยในลำดับชั้น ใต้แต่ละประเภทใหญ่ ซึ่งเรียกว่า**รูปแบบขั้น**

ในวิชวลเมทริกซ์ เวอร์ชัน*เดิม* ประเภทย่อยจะถูกแสดงในคอลัมน์ต่างหาก และใช้พื้นที่วิชวลมากขึ้น รูปต่อไปนี้แสดงตารางในวิชวล**เมทริกซ์**เวอร์ชันเดิม โปรดสังเกตว่า ประเภทย่อยอยู่ในคอลัมน์ต่างหาก

![](media/desktop-matrix-visual/matrix-visual_14.png)

ในรูปต่อไปนี้ คุณเห็นวิชวล**เมทริกซ์** ที่แสดงใน**รูปแบบขั้น** โปรดสังเกตว่า ประเภท*คอมพิวเตอร์* มีประเภทย่อย (อุปกรณ์คอมพิวเตอร์ เดสก์ท็อป แล็ปท็อป จอ ฯลฯ) แสดงเยื้องเล็กน้อย ให้วิชวลดูสะอาดตา และดูแน่นขึ้น

![](media/desktop-matrix-visual/matrix-visual_13.png)

คุณสามารถปรับเปลี่ยนการตั้งค่า**รูปแบบขั้น**ได้อย่างง่ายดาย เมื่อเลือกวิชวล**เมทริกซ์** ในส่วน**รูปแบบ** (ไอคอนลูกกลิ้งสี) ของบานหน้าต่าง**การจัดรูปแบบการแสดงข้อมูล** ขยายส่วน**ส่วนหัวของแถว** ในนั้นมีสองตัวเลือก: การสลับ**รูปแบบขั้น** (ให้เปิดหรือปิด) และ**การเยื้องเค้าโครงแบบขั้น** (ระบุระยะของการเยื้อง เป็นพิกเซล)

![](media/desktop-matrix-visual/matrix-visual_15.png)

ถ้าคุณปิด**รูปแบบขั้น** ประเภทย่อยจะแสดงในอีกคอลัมน์ แทนที่จะเยื้องภายใต้ประเภทหลัก

## <a name="subtotals-with-matrix-visuals"></a>ผลรวมย่อย กับวิชวลเมทริกซ์
คุณสามารถเปิดปิดผลรวมย่อย ในวิชวลเมทริกซ์ สำหรับทั้งแถวและคอลัมน์ ในรูปต่อไปนี้ คุณเห็นการตั้งค่าผลรวมย่อยของแถว เป็น**เปิด**

![](media/desktop-matrix-visual/matrix-visual_20.png)

ในส่วน**รูปแบบ**ของบานหน้าต่าง**การจัดรูปแบบการแสดงข้อมูล** ขยายการ์ด**ผลรวมย่อย** และเลื่อน**ผลรวมย่อยแถว**เพื่อ**ปิด** เมื่อคุณทำเช่นนั้น จะไม่มีแสดงผลรวมย่อย

![](media/desktop-matrix-visual/matrix-visual_21.png)

กระบวนการเดียวกัน ใช้ได้กับผลรวมย่อยของคอลัมน์

## <a name="cross-highlighting-with-matrix-visuals"></a>การไฮไลต์เชื่อมโยง ด้วยวิชวลเมทริกซ์
ด้วยวิชวล**เมทริกซ์** องค์ประกอบใด ๆ ในเมทริกซ์สามารถเลือกเป็นพื้นฐานสำหรับการไฮไลต์เชื่อมโยงได้ เลือกคอลัมน์ใน**เมทริกซ์** และคอลัมน์นั้นจะถูกไฮไลต์ เช่นเดียวกับวิชวลอื่น ๆ บนหน้ารายงาน นี่เป็นคุณลักษณะของวิชวลและการเลือกจุดข้อมูล ที่หลาย ๆ วิชวลมี และตอนนี้วิชวล**เมทริกซ์**สามารถทำได้แล้ว

นอกจากนี้ การใช้ CTRL+คลิก ยังใช้ได้กับการไฮไลต์เชื่อมโยง ตัวอย่างเช่น ในรูปต่อไปนี้ คอลเลกชันของประเภทย่อย ถูกเลือกในวิชวล**เมทริกซ์** สังเกตว่า รายการที่ไม่ได้เลือกในวิชวลจะเป็นสีเทา และวิชวลอื่น ๆ บนหน้าสะท้อนการเลือกในวิชวล**เมทริกซ์**

![](media/desktop-matrix-visual/matrix-visual_16.png)

## <a name="shading-and-font-colors-with-matrix-visuals"></a>การแรเงาและสีแบบอักษร กับวิชวลเมทริกซ์
ด้วยวิชวล**เมทริกซ์** คุณสามารถใช้**การจัดรูปแบบตามเงื่อนไข** (สีและแรเงา) ในพื้นหลังของเซลล์ภายในเมทริกซ์ และคุณสามารถใช้การจัดรูปแบบตามเงื่อนไข กับข้อความและค่า

เพื่อใช้การจัดรูปแบบตามเงื่อนไข คุณสามารถทำอย่างใดอย่างหนึ่งต่อไปนี้เมื่อเลือกวิชวลเมทริกซ์แล้ว:

* ในบานหน้าต่าง**เขตข้อมูล** คลิกขวาที่เขตข้อมูล และเลือก**การจัดรูปแบบตามเงื่อนไข**จากเมนู
  
  ![](media/desktop-matrix-visual/matrix-visual_17.png)
* หรือ ในบานหน้าต่าง**รูปแบบ** ขยายการ์ด**การจัดรูปแบบตามเงื่อนไข** และสำหรับ**สเกลสีพื้นหลัง**หรือ**สเกลสีฟอนต์** เลื่อนแถบเลื่อนเพื่อ**เปิด** เปิดใช้งานอย่างใดอย่างหนึ่ง จะแสดงลิงก์สำหรับ*การควบคุมขั้นสูง* ซึ่งให้คุณสามารถกำหนดสีและค่าสำหรับการจัดรูปแบบสี
  
  ![](media/desktop-matrix-visual/matrix-visual_18.png)

วิธีอย่างใดอย่างหนึ่งข้างบน จะให้ผลลัพธ์เดียวกัน การเลือก*การควบคุมขั้นสูง* จะแสดงกล่องโต้ตอบต่อไปนี้ ให้คุณทำการปรับปรุง:

![](media/desktop-matrix-visual/matrix-visual_19.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป

คุณอาจสนใจบทความต่อไปนี้:

* [ใช้เส้นตาราง และจัดชิดเส้นตาราง ในรายงาน Power BI Desktop](desktop-gridlines-snap-to-grid.md)
* [แหล่งข้อมูลใน Power BI Desktop](desktop-data-sources.md)
* [ชนิดข้อมูลใน Power BI Desktop](desktop-data-types.md)

 