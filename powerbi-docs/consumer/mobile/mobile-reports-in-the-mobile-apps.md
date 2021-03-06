---
title: สำรวจรายงานในแอปอุปกรณ์เคลื่อนที่ Power BI
description: เรียนรู้เกี่ยวกับการดูและโต้ตอบกับรายงานในแอปอุปกรณ์เคลื่อนที่ Power BI บนโทรศัพท์หรือแท็บเล็ตของคุณ คุณสร้างรายงานในบริการ Power BI หรือ Power BI Desktop จาก นั้น ก็สามารถโต้ตอบกับรายงานเหล่านั้นได้ในแอปอุปกรณ์เคลื่อนที่
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 08/17/2018
ms.author: maggies
ms.openlocfilehash: 7a5c60eea81eeb3a1f4e8a7f5b807fd8c7bfb6b5
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/21/2018
ms.locfileid: "46547257"
---
# <a name="explore-reports-in-the-power-bi-mobile-apps"></a>สำรวจรายงานในแอปอุปกรณ์เคลื่อนที่ Power BI
นำไปใช้กับ:

| ![iPhone](././media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![iPad](././media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![โทรศัพท์ Android](././media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![แท็บเล็ต Android](././media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![อุปกรณ์ Windows 10](./media/mobile-reports-in-the-mobile-apps/win-10-logo-40-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone |iPad |โทรศัพท์ Android |แท็บเล็ต Android |อุปกรณ์ Windows 10 |

รายงาน Power BI คือ มุมมองแบบโต้ตอบของข้อมูลของคุณที่มีการแสดงผลด้วยภาพที่แสดงการค้นพบและข้อมูลเชิงลึกแตกต่างจากข้อมูลนั้น การดูรายงานในแอปอุปกรณ์เคลื่อนที่ Power BI เป็นขั้นตอนที่สามในกระบวนการแบบสามขั้นตอน

1. [สร้างรายงานใน Power BI Desktop](../../desktop-report-view.md) คุณยังสามารถ [ปรับรายงานให้เหมาะสมสำหรับโทรศัพท์](mobile-apps-view-phone-report.md) ใน Power BI Desktop ได้ 
2. เผยแพร่รายงานเหล่านั้นไปยังบริการ Power BI [(https://powerbi.com)](https://powerbi.com)หรือ[เซิร์ฟเวอร์รายงาน Power BI](../../report-server/get-started.md)  
3. จากนั้น โต้ตอบกับรายงานเหล่านั้นในแอปอุปกรณ์เคลื่อนที่ Power BI

## <a name="open-a-power-bi-report-in-the-mobile-app"></a>เปิดรายงาน Power BI ในแอปอุปกรณ์เคลื่อนที่
รายงาน Power BI ถูกเก็บไว้ในตำแหน่งที่ต่างกันในแอปอุปกรณ์เคลื่อนที่ตามตำแหน่งที่คุณได้รับรายงานเหล่านั้น รายงานเหล่านั้นอาจอยู่ในแอป แชร์กับฉัน พื้นที่ทำงาน (รวมถึงพื้นที่ทำงานขงฉัน) หรือบนเซิร์ฟเวอร์รายงานได้ ในบางครั้ง คุณเข้าถึงแดชบอร์ดที่เกี่ยวข้องเพื่อเข้าถึงรายงาน และในบางครั้ง ก็มีแสดงรายการไว้

* ในแดชบอร์ด แตะจุดไข่ปลา (...) ตรงมุมขวาบนของไทล์ > **เปิดรายงาน**
  
  ![เปิดรายงาน](./media/mobile-reports-in-the-mobile-apps/power-bi-android-open-report-tile.png)
  
  ไม่ใช่ไทล์ทั้งหมดที่มีตัวเลือกเปิดในรายงาน ตัวอย่างเช่น ไทล์ที่สร้างขึ้นโดยการถามคำถามในกล่องการถามตอบจะไม่เปิดรายงานเมื่อคุณแตะ 
  
  บนโทรศัพท์ รายงานจะเปิดขึ้นในโหมดแนวนอน เว้นแต่ว่าจะมี [การปรับให้เหมาะสมสำหรับดูบนโทรศัพท์](mobile-reports-in-the-mobile-apps.md#view-reports-optimized-for-phones)
  
  ![รายงานบนโทรศัพท์ในโหมดแนวนอน](./media/mobile-reports-in-the-mobile-apps/power-bi-iphone-report-landscape.png)

## <a name="view-reports-optimized-for-phones"></a>ดูรายงานที่ปรับให้เหมาะสมสำหรับโทรศัพท์
ผู้เขียนรายงาน Power BI สามารถสร้างเค้าโครงรายงานที่ปรับให้เหมาะสมสำหรับโทรศัพท์โดยเฉพาะ หน้ารายงานที่ปรับให้เหมาะสมสำหรับโทรศัพท์ได้เพิ่มฟังก์ชันการทำงาน: เช่น คุณสามารถเจาะลึกและเรียงลำดับการแสดงผลด้วยภาพ และสามารถเข้าถึง [ตัวกรองผู้สร้างรายงานที่ถูกเพิ่มไปยังหน้ารายงาน](mobile-apps-view-phone-report.md#filter-the-report-page-on-a-phone) รายงานเปิดขึ้นบนมือถือของคุณ จะถูกกรองข้อมูลด้วยค่าการกรองในรายงานบนเว็บ และมีข้อความแจ้งว่ามีตัวกรองกำลังใช้งานอยู่บนหน้า คุณสามารถเปลี่ยนตัวกรองบนโทรศัพท์ของคุณได้

ในรายการรายงาน รายงานที่ปรับให้เหมาะสมแล้วจะมีไอคอนพิเศษ ![ไอคอนรายงานบนโทรศัพท์](./media/mobile-reports-in-the-mobile-apps/power-bi-phone-report-icon.png):

![เปิดรายงานบนโทรศัพท์](./media/mobile-reports-in-the-mobile-apps/power-bi-android-phone-report.png)

เมื่อคุณดูรายงานนั้นบนโทรศัพท์ จะเปิดขึ้นในมุมมองแนวตั้ง

![รายงานในมุมมองแนวตั้ง](./media/mobile-reports-in-the-mobile-apps/07-power-bi-phone-report-portrait.png)

 รายงานอาจมีหน้าที่ปรับและไม่ได้ปรับให้เหมาะสมสำหรับโทรศัพท์ผสมกัน ถ้าเป็นเช่นนั้น เมื่อคุณพลิกดูรายงาน มุมมองก็จะสลับจากแนวตั้งเป็นแนวนอนสำหรับแต่ละหน้า

อ่านเพิ่มเติมเกี่ยวกับ [รายงานที่ปรับให้เหมาะสมสำหรับมุมมองโทรศัพท์](mobile-apps-view-phone-report.md)

## <a name="use-slicers-to-filter-a-report"></a>ใช้ตัวแบ่งส่วนข้อมูลเพื่อกรองข้อมูลในรายงาน
เมื่อคุณออกแบบรายงานใน Power BI Desktop หรือบริการ Power BI ให้พิจารณา [เพิ่มตัวแบ่งส่วนข้อมูลในหน้ารายงาน](../../visuals/power-bi-visualization-slicers.md) คุณและเพื่อนร่วมงานสามารถใช้ตัวแบ่งส่วนข้อมูลเพื่อกรองหน้านั้นในเบราว์เซอร์และในแอปอุปกรณ์เคลื่อนที่ได้ เมื่อคุณดูรายงานบนโทรศัพท์ของคุณ คุณสามารถดูและโต้ตอบกับตัวแบ่งส่วนข้อมูลในโหมดแนวนอนและในหน้าที่ปรับให้เหมาะสมสำหรับโหมดแนวตั้งของโทรศัพท์ ถ้าคุณเลือกค่าในตัวแบ่งส่วนข้อมูลหรือตัวกรองในเบราว์เซอร์ ค่านั้นก็จะถูกเลือกเมื่อคุณดูหน้านั้นในแอปอุปกรณ์เคลื่อนที่ด้วย คุณจะเห็นข้อความที่บอกว่า มีตัวกรองที่ใช้งานอยู่บนหน้านั้น  

* เมื่อคุณเลือกค่าในตัวแบ่งส่วนข้อมูลบนหน้ารายงาน ก็จะมีการกรองการแสดงผลด้วยภาพอื่น ๆ บนหน้านั้น
  
  ![ตัวแบ่งส่วนข้อมูลรายงาน](./media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-slicer.png)
  
  ในภาพประกอบนี้ ตัวแบ่งส่วนข้อมูลจะกรองแผนภูมิคอลัมน์เพื่อแสดงค่าเฉพาะเดือนกรกฎาคมเท่านั้น

## <a name="cross-filter-and-highlight-a-report"></a>กรองแบบไขว้และเน้นรายงาน Power BI
เมื่อคุณเลือกค่าในการแสดงผลด้วยภาพหนึ่งๆ แล้ว ก็จะไม่มีการกรองการแสดงผลด้วยภาพอื่น ๆ ซึ่งเป็นการเน้นค่าที่เกี่ยวข้องในการแสดงผลด้วยภาพอื่น ๆ

* แตะค่าในการแสดงผลด้วยภาพ
  
  ![กรองหน้าแบบไขว้](./media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-highlight.png)
  
  การแตะคอลัมน์ Large ในการเน้นการแสดงผลด้วยภาพหนึ่งๆ ที่เกี่ยวข้องกับค่าในการแสดงผลด้วยภาพอื่น ๆ 

## <a name="sort-a-visual-on-an-ipad-or-a-tablet"></a>เรียงลำดับการแสดงผลด้วยภาพบน iPad หรือแท็บเล็ต
* แตะแผนภูมิ แตะจุดไข่ปลา (**...** ) แล้วแตะชื่อเขตข้อมูล
  
   ![เรียงลำดับการแสดงผลด้วยภาพ](./media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-sort.png)
* เมื่อต้องการย้อนกลับลำดับการจัดเรียง ให้แตะจุดไข่ปลา (**...** ) อีกครั้ง จากนั้นแตะชื่อเขตข้อมูลเดียวกันอีกครั้ง

## <a name="drill-down-and-up-in-a-visual"></a>ดูรายละเอียดแนวลึก และดูข้อมูลสรุปในวิชวล
ถ้าผู้สร้างรายงานได้เพิ่มความสามารถการดูรายละเอียดแนวลึกในวิชวล คุณสามารถดูรายละเอียดแนวลึกในวิชวล เพื่อดูค่าที่ประกอบขึ้นมาเป็นวิชวล คุณ [เพิ่มการเจาะดูข้อมูลลึกลงในการแสดงผลด้วยภาพ](../end-user-drill.md) ใน Power BI Desktop หรือบริการ Power BI 

* แตะค้างที่แถบหนึ่ง หรือชี้ในภาพเพื่อแสดงเคล็ดลับเครื่องมือ ถ้าวิชวลมีรายละเอียดแนวลึก ด้านล่างของคำแนะนำมีลูกศรที่คุณสามารถแตะได้ 
  
  ![การดูรายละเอียดแนวลึกในวิชวล](./media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-down-tooltip.png)

* เพื่อกลับไปดูข้อมูลสรุป แตะที่ลูกศรขึ้นในคำแนะนำ
  
  ![เจาะดูข้อมูลลึกขึ้น](./media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up-tooltip.png)

* นอกจากนี้คุณยังสามารถดูรายละเอียดแนวลึกในจุดข้อมูลทั้งหมดในวิชวล เปิดในโหมดโฟกัส แตะที่ไอคอนสำรวจ จากนั้นเลือกแสดงระดับถัดไป หรือขยายเพื่อแสดงทั้งระดับปัจจุบันและระดับถัดไป

   ![Power BI ดูรายละเอียดแนวลึกทั้งหมด](./media/mobile-reports-in-the-mobile-apps/power-bi-drill-down-all.png)

## <a name="drill-through-from-one-page-to-another"></a>การเข้าถึงรายละเอียดข้อมูลจากหน้าหนึ่งไปอีกหน้าหนึ่ง

ด้วย *drillthrough* (การเข้าถึงรายละเอียด) เมื่อคุณแตะส่วนของวิชวล Power BI จะนำคุณไปยังหน้าอื่นในรายงาน ที่กรองด้วยค่าที่คุณแตะ ผู้สร้างรายงานสามารถกำหนดหนึ่งหรือหลายตัวเลือกสำหรับการ drillthrough ซึ่งแต่ละตัวเลือกจะพาคุณไปยังรายงานคนละหน้า ในกรณีดังกล่าว คุณสามารถเลือกว่าคุณต้องการเข้าถึงรายละเอียดตัวไหน ในตัวอย่างต่อไปนี้ เมื่อคุณแตะที่ค่าในมาตรวัด คุณสามารถเลือกระหว่างการเข้าถึงรายละเอียด **spent by business area** (การใช้จ่ายตามด้านธุรกิจ) หรือ **planning by business area** (การวางแผนตามด้านธุรกิจ) ได้

![การเข้าถึงรายละเอียดใน Power BI สำหรับอุปกรณ์เคลื่อนที่](./media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-through-it-spent-report.png)

เมื่อคุณดูที่รายละเอียด ปุ่มย้อนกลับจะนำคุณกลับไปยังรายงานหน้าก่อนหน้า

อ่านเกี่ยวกับวิธีการ[เพิ่ม drill-through ใน Power BI Desktop](../../desktop-drillthrough.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [ดูและโต้ตอบกับรายงาน Power BI ที่ปรับให้เหมาะสมกับโทรศัพท์ของคุณ](mobile-apps-view-phone-report.md)
* [สร้างเวอร์ชันของรายงานที่ปรับให้เหมาะสมสำหรับโทรศัพท์](../../desktop-create-phone-report.md)
* มีคำถามหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)

