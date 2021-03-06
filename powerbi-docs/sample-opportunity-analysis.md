---
title: 'ตัวอย่างการวิเคราะห์โอกาสทางการขายสำหรับ Power BI: ชมการแนะนำ'
description: 'ตัวอย่างการวิเคราะห์โอกาสทางการขายสำหรับ Power BI: ชมการแนะนำ'
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/20/2018
ms.author: mihart
LocalizationGroup: Samples
ms.openlocfilehash: 2a7bc3ae08d46ccc9340295a1a6bc9f8303382f8
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/26/2018
ms.locfileid: "36945100"
---
# <a name="opportunity-analysis-sample-for-power-bi-take-a-tour"></a>ตัวอย่างการวิเคราะห์โอกาสทางการขายสำหรับ Power BI: ชมการแนะนำ

## <a name="overview-of-the-opportunity-analysis-sample"></a>ภาพรวมของตัวอย่างการวิเคราะห์โอกาสทางการขาย
**ตัวอย่างการวิเคราะห์โอกาสทางการขาย**ประกอบไปด้วยแดชบอร์ด (และรายงานที่เกี่ยวข้อง) สำหรับบริษัทซอฟต์แวร์ที่มีช่องทางขาย 2 ช่องทาง: *โดยตรง*และ*ผ่านคู่ค้า* ผู้จัดการฝ่ายขายสร้างแดชบอร์ดนี้เพื่อติดตามโอกาสและรายได้ตามภูมิภาค ขนาดโอกาส และช่องทาง

ผู้จัดการฝ่ายขายอาศัยตัววัดรายได้สองตัว:

* **รายได้** – นี่คือการประมาณของพนักงานขายว่า เขาคิดว่ายอดขายเป็นเท่าไร
* **รายได้ที่แยกแยะแล้ว** – นี่คำนวณจาก รายได้ X % ความน่าจะเป็น และเป็นที่ยอมรับโดยทั่วไปว่า ค่านี้เป็นค่าที่ใช้คาดการณ์ยอดขายจริงได้แม่นยำกว่า ความน่าเป็น กำหนดจาก ***ขั้นตอนการขาย***ปัจจุบันของข้อตกลง
  * ลูกค้าเป้าหมาย – 10%  
  * ตรวจสอบคุณสมบัติ – 20%  
  * โซลูชัน – 40%  
  * ข้อเสนอ – 60%  
  * เสร็จสิ้น – 80%

  ![](media/sample-opportunity-analysis/opportunity1.png)

ตัวอย่างนี้เป็นส่วนหนึ่งของชุดตัวอย่าง ที่แสดงให้เห็นวิธีการที่คุณสามารถใช้ Power BI กับข้อมูล รายงาน และแดชบอร์ดที่เกี่ยวข้องกับธุรกิจ นี่เป็นข้อมูลจริงจาก obviEnce ([www.obvience.com)](http://www.obvience.com/) ที่ตัวตนต่าง ๆ ได้ถูกลบออกไป

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

 ก่อนที่คุณสามารถใช้ตัวอย่าง คุณต้องดาวน์โหลดในรูปแบบ[ชุดเนื้อหา](https://docs.microsoft.com/power-bi/sample-opportunity-analysis#get-the-content-pack-for-this-sample) [ไฟล์ .pbix](http://download.microsoft.com/download/9/1/5/915ABCFA-7125-4D85-A7BD-05645BD95BD8/Opportunity%20Analysis%20Sample%20PBIX.pbix) หรือ[เวิร์กบุ๊ก Excel](http://go.microsoft.com/fwlink/?LinkId=529782)

### <a name="get-the-content-pack-for-this-sample"></a>รับชุดเนื้อหาสำหรับตัวอย่างนี้

1. เปิดบริการ Power BI (app.powerbi.com) และเข้าสู่ระบบ
2. ที่มุมด้านล่างซ้าย เลือก**รับข้อมูล**
   
    ![](media/sample-datasets/power-bi-get-data.png)
3. บนหน้า รับข้อมูล ที่ปรากฏขึ้น เลือกไอคอน**ตัวอย่าง**
   
   ![](media/sample-datasets/power-bi-samples-icon.png)
4. เลือก**ตัวอย่างการวิเคราะห์โอกาสทางการขาย** แล้วเลือก**เชื่อมต่อ**  
  
   ![รับข้อมูล](media/sample-opportunity-analysis/opportunity-connect.png)
   
5. Power BI นำเข้าชุดเนื้อหา และเพิ่มแดชบอร์ด รายงาน และชุดข้อมูลใหม่ไปยังพื้นที่ทำงานปัจจุบันของคุณ เนื้อหาใหม่จะถูกทำเครื่องหมายด้วยเครื่องหมายดอกจันสีเหลือง 
   
   ![เครื่องหมายดอกจัน](media/sample-opportunity-analysis/opportunity-asterisk.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>รับไฟล์ .pbix สำหรับตัวอย่างนี้

อีกทางเลือกหนึ่งคือ คุณสามารถดาวน์โหลดตัวอย่างเป็นไฟล์ .pbix ซึ่งถูกออกแบบมาสำหรับใช้กับ Power BI Desktop 

 * [ตัวอย่างการวิเคราะห์โอกาสทางการขาย](http://download.microsoft.com/download/9/1/5/915ABCFA-7125-4D85-A7BD-05645BD95BD8/Opportunity%20Analysis%20Sample%20PBIX.pbix)

### <a name="get-the-excel-workbook-for-this-sample"></a>รับเวิร์กบุ๊ก Excel สำหรับตัวอย่างนี้
คุณยังสามารถ[ดาวน์โหลดเพียงชุดข้อมูล (เวิร์กบุ๊ก Excel)](http://go.microsoft.com/fwlink/?LinkId=529782) สำหรับตัวอย่างนี้ได้ เวิร์กบุ๊กประกอบด้วยแผ่นงาน Power View ที่คุณสามารถดู และปรับเปลี่ยน เมื่อต้องการดูข้อมูลดิบ เลือก **Power Pivot > จัดการ**


## <a name="what-is-our-dashboard-telling-us"></a>แดชบอร์ดกำลังบอกอะไรแก่เรา
ผู้จัดการฝ่ายขายของเรา ได้สร้างแดชบอร์ดเพื่อติดตามเมตริกที่สำคัญที่สุดของเธอ เมื่อเธอเห็นสิ่งที่น่าสนใจ เธอสามารถเลือกไทล์เพื่อเจาะลึกลงในข้อมูล

1. รายได้ของบริษัทคือ 2 พันล้านเหรียญ และรายได้ที่แยกแยะแล้ว คือ 461 ล้านเหรียญ
2. จำนวนโอกาสทางการขายและรายได้ เป็นไปตามรูปแบบกรวยที่คุ้นเคย โดยค่าผลรวมมีค่าที่ทยอยลดลงเมื่อผ่านไปยังขั้นตอนถัด ๆ ไป
3. โอกาสทางการขายของเรา ส่วนใหญ่อยู่ในภูมิภาคตะวันออก
4. โอกาสที่มีขนาดใหญ่กว่า สร้างรายได้ให้มากกว่า โอกาสขนาดกลางหรือโอกาสขนาดเล็ก
5. ข้อตกลงซื้อขายของคู่ค้า สร้างรายได้ให้มากกว่า: เฉลี่ยแล้วที่ $8M เทียบกับ $6M สำหรับการขายโดยตรง

เนื่องจากความพยายามเพื่อให้ได้ข้อตกลงมีเท่ากัน ไม่ว่าข้อตกลงนั้นจะจัดเป็นขนาดใหญ่ กลาง หรือเล็ก บริษัทของเราควรเจาะลึกลงไปในข้อมูลเพื่อศึกษาเพิ่มเติมเกี่ยวกับโอกาสขนาดใหญ่

เลือกไทล์**จำนวนโอกาสทางการขาย ตามการขับเคลื่อนโดยคู่ค้าและขั้นตอนการขาย** เพื่อเปิดไปยังหน้า 1 ของรายงาน  
![](media/sample-opportunity-analysis/opportunity2.png)

## <a name="explore-the-pages-in-the-report"></a>สำรวจหน้าต่าง ๆ ในรายงาน
### <a name="page-1-of-our-report-is-titled-opportunity-count-overview"></a>หน้า 1 ของรายงานของเรามีชื่อว่า "ภาพรวมจำนวนโอกาสทางการขาย"
![](media/sample-opportunity-analysis/opportunity3.png)

* ตะวันออก คือภูมิภาคที่ใหญ่ที่สุดของเราในแง่จำนวนโอกาสทางการขาย  
* บนแผนภูมิวงกลม เลือกทีละภูมิภาค เพื่อกรองหน้า สำหรับแต่ละภูมิภาค คู่ค้าจะพยายามคว้าหาโอกาสขนาดใหญ่มากกว่า   
* แผนภูมิคอลัมน์ จำนวนโอกาส ตามการขับเคลื่อนโดยคู่ค้าและขนาดของโอกาส แสดงให้เห็นอย่างชัดเจนว่า ส่วนใหญ่ของโอกาสขนาดใหญ่ถูกขับเคลื่อนโดยคู่ค้า และอีกมากของโอกาสขนาดเล็กและขนาดกลางไม่ได้ถูกขับเคลื่อนโดยคู่ค้า
* เลือกแต่ละขั้นตอนการขายในแผนภูมิแท่งในด้านล่างซ้าย เพื่อดูความแตกต่างของจำนวนตามภูมิภาค และสังเกตว่า ถึงแม้ภูมิภาคตะวันออกเป็นภูมิภาคที่ใหญ่ที่สุดของเราในแง่การนับจำนวน แต่จำนวนการขายที่อยู่ในขั้นโซลูชัน ข้อเสนอ และขั้นสุดท้าย ของทั้ง 3 ภูมิภาคมีจำนวนไล่ ๆ กัน ซึ่งหมายความว่า เราสามารถปิดการขายในภูมิภาคกลางและตะวันตก ด้วยเปอร์เซ็นต์ที่สูงกว่า

### <a name="page-2-of-our-report-is-titled-revenue-overview"></a>หน้า 2 ของรายงานของเรามีชื่อว่า "ภาพรวมรายได้"
หน้านี้จะดูที่ข้อมูลคล้ายกัน แต่ใช้มุมมองของรายได้แทนที่จะเป็นการนับจำนวน  
![](media/sample-opportunity-analysis/opportunity4.png)

* ภูมิภาคตะวันออก เป็นภูมิภาคที่ใหญ่ที่สุดของเรา ไม่เพียงแค่จำนวนโอกาสแต่ยังรวมถึงรายได้ด้วย  
* การกรอง ตามการขับเคลื่อนโดยคู่ค้า (เลือก**ใช่**ในคำอธิบายแผนภูมิด้านขวาบน) เปิดเผยรายได้ที่ $1.5B และ $294M เปรียบเทียบตัวเลขนี้กับ $644B และ $166M สำหรับรายได้ที่ไม่ได้ขับเคลื่อนโดยคู่ค้า  
* รายได้เฉลี่ยสำหรับบัญชีขนาดใหญ่มีขนาดมากกว่า (8M) ถ้าโอกาสทางการขายมาจากการขับเคลื่อนของคู่ค้า เทียบกับตัวเลข 6M สำหรับธุรกิจที่ไม่ได้มาจากการขับเคลื่อนของคู่ค้า  
* สำหรับธุรกิจที่ขับเคลื่อนโดยคู่ค้า รายได้เฉลี่ยต่อโอกาสทางการขายขนาดใหญ่ เกือบจะเป็นสองเท่าของโอกาสทางการขายขนาดกลาง (4M)  
* รายได้เฉลี่ยสำหรับธุรกิจขนาดเล็กและขนาดกลาง มีค่าใกล้เคียงกันทั้งที่ขับเคลื่อนโดยคู่ค้า และไม่ได้ขับเคลื่อนโดยคู่ค้า   

ชัดเจนแล้วว่า คู่ค้าของเราขายให้กับลูกค้าได้ดีกว่า  จึงสมเหตุสมผลที่จะส่งต่อข้อเสนอไปทางคู่ค้าให้มากขึ้น

### <a name="page-3-of-our-report-is-titled-region-stage-counts"></a>หน้า 3 ของรายงานเรามีชื่อว่า "จำนวนระดับภูมิภาค"
หน้านี้ดูข้อมูลที่คล้ายกัน แต่แยกตามภูมิภาคและขั้นตอน  
![](media/sample-opportunity-analysis/opportunity5.png)

* กรองตามภูมิภาคตะวันออก (เลือก**ตะวันออก**ในแผนภูมิวงกลม) แสดงให้เห็นว่า โอกาสทางการขายในตะวันออกแบ่งระหว่าง ขับเคลื่อนและไม่ขับเคลื่อนผ่านคู่ค้า เกือบเท่ากัน
* โอกาสขนาดใหญ่ พบได้มากสุดในภูมิภาคส่วนกลาง โอกาสขนาดเล็กพบมากในภูมิภาคตะวันออก และโอกาสขนาดกลางพบมากสุดในภูมิภาคตะวันตก

### <a name="page-4-of-our-report-is-titled-upcoming-opportunities"></a>หน้า 4 ของรายงานเรามีชื่อว่า "โอกาสที่กำลังจะมาถึง"
อีกครั้งที่ เรากำลังดูปัจจัยที่คล้ายกัน แต่ครั้งนี้จากมุมมองของ วันที่/เวลา  
![](media/sample-opportunity-analysis/opportunity6.png)

CFO ของเราใช้หน้านี้เพื่อจัดสรรปริมาณงาน โดยดูที่โอกาสของรายได้ ตามขั้นตอนการขายและเดือน เธอสามารถวางแผนอย่างเหมาะสม

* รายได้เฉลี่ยสำหรับขั้นตอนสุดท้าย มีค่าสูงสุด การปิดข้อเสนอเหล่านี้ คือสิ่งสำคัญที่สุด
* การกรองตามเดือน (โดยการเลือกชื่อเดือน ในตัวแบ่งส่วนข้อมูลด้านซ้าย) แสดงว่า เดือนมกราคมมีข้อเสนอขนาดใหญ่ในขั้นตอนสุดท้ายเป็นสัดส่วนที่สูง ด้วยรายได้ที่แยกแยะแล้วที่ $75M เดือนกุมภาพันธ์ ทางกลับกัน มีข้อเสนอปานกลางในขั้นตอนโซลูชันและข้อเสนอเป็นส่วนใหญ่
* โดยทั่วไป ตัวเลขรายได้ที่แยกแยะแล้ว ผันผวนตาม ขั้นตอนการขาย จำนวนโอกาส และขนาดของข้อเสนอ เพิ่มตัวกรอง (โดยใช้บานหน้าต่างตัวกรองบนด้านขวา) สำหรับปัจจัยเหล่านี้เพื่อค้นหาข้อมูลเชิงลึกเพิ่มเติม

นี่เป็นสภาพแวดล้อมที่ปลอดภัยที่จะทดลองสิ่งต่าง ๆ﻿ คุณสามารถเลือกที่จะไม่บันทึกการเปลี่ยนแปลงของคุณ ถ้าคุณบันทึก คุณสามารถ**รับข้อมูล**สำหรับสำเนาชุดใหม่ของตัวอย่างนี้ได้เสมอ

## <a name="next-steps-connect-to-your-data"></a>ขั้นตอนถัดไป: เชื่อมต่อกับข้อมูลของคุณ
เราหวังว่าการแนะนำนี้ ได้แสดงให้เห็นว่าแดชบอร์ด, Q&A และรายงาน Power BI สามารถให้ข้อมูลเชิงลึกในข้อมูลการติดตามโอกาสในการขาย ตอนนี้ถึงตาคุณแล้ว — ลองเชื่อมต่อกับข้อมูลของคุณเอง ด้วย Power BI คุณสามารถเชื่อมต่อกับแหล่งข้อมูลที่หลากหลาย เรียนรู้เพิ่มเติมเกี่ยวกับ[เริ่มต้นใช้งาน Power BI](service-get-started.md)

[ดาวน์โหลดตัวอย่าง](sample-datasets.md)  
