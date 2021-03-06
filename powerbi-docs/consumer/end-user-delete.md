---
title: ลบแดชบอร์ด รายงาน เวิร์กบุ๊ก ชุดข้อมูล หรือพื้นที่ทำงาน
description: เรียนรู้วิธีการลบเกือบทุกสิ่งจาก Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 04/11/2018
ms.author: mihart
LocalizationGroup: Common tasks
ms.openlocfilehash: c47575c06a4d9bd29571d4fd548b6afbcdaeb608
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/22/2018
ms.locfileid: "46564658"
---
# <a name="delete-almost-anything-in-power-bi-service"></a>ลบเกือบทุกสิ่งในบริการ Power BI
บทความนี้สอนวิธีการลบแดชบอร์ด รายงาน เวิร์กบุ๊ก ชุดข้อมูล แอปฯ การแสดงภาพ และพื้นที่ทำงานในบริการ Power BI

## <a name="delete-a-dashboard"></a>ลบแดชบอร์ด
สามารถลบแดชบอร์ดได้ การลบแดชบอร์ดไม่ได้ลบชุดข้อมูลพื้นฐานหรือรายงานใด ๆ ที่เชื่อมโยงกับแดชบอร์ดนั้น

* ถ้าคุณเป็นเจ้าของแดชบอร์ด คุณสามารถลบออกได้ ถ้าคุณแชร์แดชบอร์ดกับเพื่อนร่วมงาน การลบแดชบอร์ดจากพื้นที่ทำงานของ Power BI จะลบแดชบอร์ดจากพื้นที่ทำงาน Power BI ของเพื่อนร่วมงานของคุณด้วย
* ถ้ามีการแชร์แดชบอร์ดกับคุณและคุณไม่ต้องการเห็นอีกต่อไป คุณสามารถลบออกได้  การลบแดชบอร์ดจะไม่เป็นการลบออกจากพื้นที่ทำงาน Power BI ของใคร
* หากแดชบอร์ดเป็นส่วนหนึ่งของการ[แพ็คเนื้อหาขององค์กร](../service-organizational-content-pack-disconnect.md) วิธีเดียวที่จะลบออกได้คือการลบชุดข้อมูลที่เกี่ยวข้อง

### <a name="to-delete-a-dashboard"></a>การลบแดชบอร์ด
1. ในพื้นที่ทำงานของคุณ เลือกแถบ**แดชบอร์ด**
2. ค้นหาแดชบอร์ดที่ต้องการลบแล้วเลือกไอคอนลบ ![ไอคอนลบ](./media/end-user-delete/power-bi-delete-icon.png).

    ![วิดีโอ](./media/end-user-delete/power-bi-delete-dash.gif)

## <a name="delete-a-report"></a>ลบรายงาน
ไม่ต้องกังวล การลบรายงานไม่ลบชุดข้อมูลที่มีรายงานอยู่  และการแสดงภาพใด ๆ ที่คุณปักหมุดจากรายงานจะปลอดภัย--การแสดงภาพเหล่านี้จะยังคงอยู่บนแดชบอร์ดจนกว่าคุณลบทีละอัน

### <a name="to-delete-a-report"></a>การลบรายงาน
1. ในพื้นที่ทำงานของคุณ เลือกแถบ**รายงาน**
2. ค้นหารายงานที่ต้องการลบแล้วเลือกไอคอนลบ   ![ไอคอนลบ](./media/end-user-delete/power-bi-delete-icon.png).   

    ![แถบการรายงานของพื้นที่ทำงาน](./media/end-user-delete/power-bi-delete-reportnew.png)
3. ยืนยันการลบ

   ![ลบกล่องโต้ตอบรายงาน](./media/end-user-delete/power-bi-delete-report.png)

   > [!NOTE]
   > ถ้ารายงานดังกล่าวเป็นส่วนหนึ่งของการ[ชุดเนื้อหา](../service-organizational-content-pack-introduction.md) คุณจะไม่สามารถลบออกโดยใช้วิธีการนี้  ดู[การลบการเชื่อมต่อไปยังชุดเนื้อหาขององค์กร](../service-organizational-content-pack-disconnect.md)
   >
   >

## <a name="delete-a-workbook"></a>ลบสมุดงาน
สามารถลบสมุดงานได้ อย่างไรก็ตาม การลบสมุดงานจะลบรายงานและแผ่นแดชบอร์ดที่ประกอบด้วยข้อมูลจากสมุดงานทั้งหมดี้ด้วย

หากมีการจัดเก็บสมุดงานใน OneDrive for Business การลบสมุดงานจาก Power BI จะไม่ลบออกจาก OneDrive

### <a name="to-delete-a-workbook"></a>การลบสมุดงาน
1. ในพื้นที่ทำงานของคุณ เลือกแถบ**สมุดงาน**
2. ค้นหาสมุดงานที่ต้องการลบแล้วเลือก ลบ ![ไอคอนลบ](./media/end-user-delete/power-bi-delete-report2.png) ไอคอน

    ![แถบสมุดงาน](./media/end-user-delete/power-bi-delete-workbooknew.png)
3. ยืนยันการลบ

   ![ลบกล่องโต้ตอบสมุดงาน](./media/end-user-delete/power-bi-delete-confirm.png)

## <a name="delete-a-dataset"></a>ลบชุดข้อมูล
สามารถลบชุดข้อมูลได้ อย่างไรก็ตาม การลบชุดข้อมูลจะลบรายงานและแผ่นแดชบอร์ดที่มีข้อมูลจากชุดข้อมูลนั้นทั้งหมดด้วย

หากชุดข้อมูลเป็นส่วนหนึ่งของ[ชุดเนื้อหาระดับองค์กร](../service-organizational-content-pack-disconnect.md)อย่างน้อยหนึ่งชุด วิธีเดียวที่จะลบชุดข้อมูลจากชุดเนื้อหาที่กำลังมีการใช้งานอยู่คือ รอให้มีการประมวลผลเสร็จเรียบร้อย จากนั้นนั้นลองลบอีกครั้ง

### <a name="to-delete-a-dataset"></a>การลบชุดข้อมูล
1. ในพื้นที่ทำงานของคุณ เลือกแถบ**ชุดข้อมูล**
2. ค้นหาชุดข้อมูลที่ต้องการลบแล้วเลือกจุดไข่ปลา (...)  

    ![แถบชุดข้อมูล](./media/end-user-delete/power-bi-delete-datasetnew.png)
3. จากรายการแบบเลื่อนลง เลือก**ลบ**

   ![เมนูจุดไข่ปลา](./media/end-user-delete/power-bi-delete-datasetnew2.png)
4. ยืนยันการลบ

   ![ลบกล่องโต้ตอบแดชบอร์ด](./media/end-user-delete/power-bi-delete-dataset-confirm.png)

## <a name="delete-an-app-workspace"></a>ลบพื้นที่ทำงานสำหรับแอปฯ
> [!WARNING]
> เมื่อคุณสร้างพื้นที่ทำงานแอปฯ คุณสร้างกลุ่ม Office 365 และเมื่อคุณลบพื้นที่ทำงานแอปฯ คุณลบกลุ่ม Office365 นั้นด้วย นั่นหมายความว่า กลุ่มจะถูกลบออกจากผลิตภัณฑ์ O365 อื่น ๆ เช่น SharePoint และทีม Microsoft
>
>

ในฐานะเป็นผู้เขียนพื้นที่ทำงานแอปฯ คุณสามารถลบพื้นที่ทำงานแอปฯได้ เมื่อคุณลบพื้นที่ทำงานแอปฯ แอปฯที่เชื่อมโยงสำหรับสมาชิกของกลุ่มทั้งหมดจะถูกลบไปด้วย และจะลบออกจาก AppSource ของคุณหากคุณได้เผยแพร่แอปฯไปยังทั้งองค์กรของคุณ การลบพื้นที่ทำงานแอปฯจะแตกต่างจากการออกจากพื้นที่ทำงานแอปฯ

### <a name="to-delete-an-app-workspace---if-you-are-an-admin"></a>การลบพื้นที่ทำงานแอปฯ ในกรณีที่คุณเป็นผู้ดูแลระบบ
1. จากการนำทางด้านซ้าย เลือก**พื้นที่ทำงาน**

    ![พื้นที่ทำงานแอปฯ](./media/end-user-delete/power-bi-delete-workspace.png)
2. เลือกจุดไข่ปลา (...) ทางด้านขวาของพื้นที่ทำงานเพื่อลบ และเลือก**แก้ไขพื้นที่ทำงาน**

   ![เมนูจุดไข่ปลา > แก้ไขพื้นที่ทำงาน](./media/end-user-delete/power-bi-edit-workspace.png)
3. ในหน้าต่าง**การแก้ไขพื้นที่ทำงาน** เลือก**ลบพื้นที่ทำงาน** > **ลบ**

    ![ลบพื้นที่ทำงาน](./media/end-user-delete/power-bi-delete-workspace2.png)

### <a name="to-remove-an-app-workspace-from-your-list"></a>การลบพื้นที่ทำงานแอปฯจากรายการของคุณ
หากคุณไม่ต้องการเป็นสมาชิกของพื้นที่ทำงานแอปฯ คุณสามารถ***ออก***จากพื้นที่ทำงานแอปฯนั้น และระบบจะลบพื้นที่ทำงานแอปฯจากรายการของคุณ การออกจากพื้นที่ทำงานจะมีอยู่แล้วสำหรับสมาชิกในพื้นที่ทำงานอื่น ๆ ทั้งหมด  

> [!IMPORTANT]
> หากคุณเป็นผู้ดูแลระบบเพียงคนเดียวในพื้นที่ทำงานของแอปฯ Power BI จะไม่อนุญาตให้คุณออกจากพื้นที่ทำงาน
>
>

1. เริ่มในพื้นที่ทำงานแอปฯที่คุณต้องการลบออก
2. ที่มุมบนขวา เลือกจุดไข่ปลา (...) แล้วเลือก**ออกจากพื้นที่ทำงาน** > **ออก**

      ![ออกจากพื้นที่ทำงาน](./media/end-user-delete/power-bi-leave-workspace.png)

   > [!NOTE]
   > ตัวเลือกที่คุณเห็นในรายการแบบเลื่อนลงขึ้นอยู่กับว่า คุณเป็นผู้ดูแลระบบหรือเป็นสมาชิกของพื้นที่ทำงานแอปฯนั้น
   >
   >

## <a name="delete-or-remove-an-app"></a>ลบหรือนำแอปฯออกไป
เราสามารถลบแอปฯออกจากหน้ารายการแอปฯของคุณได้ง่าย ๆ แต่เฉพาะผู้ดูแลระบบสำหรับแอปฯเท่านั้นที่สามารถลบแอปฯได้อย่างถาวร

### <a name="remove-an-app-from-your-app-list-page"></a>การลบแอปฯออกจากหน้ารายการแอปฯของคุณ
การลบแอปฯจากหน้ารายการแอปฯของคุณจะไม่ลบแอฯปสำหรับสมาชิกคนอื่น ๆ

1. ในการนำทางด้านซ้าย เลือก**Apps**เมื่อต้องเปิดหน้ารายการแอปฯ
2. เลื่อนไปยังแอปฯที่ต้องการลบ แล้วเลือกไอคอน![](./media/end-user-delete/power-bi-delete-report2.png)ลบ

   ![เลือกแอปฯ](./media/end-user-delete/power-bi-delete-app.png)

   หากคุณเอาแอปฯออกโดยไม่ได้ตั้งใจ คุณมีหลายตัวเลือกสำหรับการเรียกคือแอปฯดังกล่าว  คุณสามารถขอให้ผู้สร้างแอปฯส่งแอปฯกลับมาใหม่ คุณสามารถค้นหาอีเมลต้นฉบับที่มีลิงค์ไปยังแอปฯ คุณสามารถตรวจสอบ[ศูนย์การแจ้งเตือน](end-user-notification-center.md)ของคุณเพื่อดูว่าแอปฯดังกล่าวยังคงอยู่ในรายการแจ้งเตือนหรือไม่ หรือคุณสามารถตรวจสอบ [ AppSource](end-user-apps.md) ขององค์กรของคุณ

## <a name="considerations-and-troubleshooting"></a>ข้อควรพิจารณาและการแก้ไขปัญหา
บทความนี้ครอบคลุมวิธีการลบบล็อคก่อสร้างหลักของบริการ Power BI แต่ยังมีสิ่งอื่นอีกที่คุณสามารถลบได้ใน Power BI  

* [ลบแดชบอร์ดที่แนะนำของคุณ](end-user-featured.md#change-the-featured-dashboard)
* [ลบแดชบอร์ด (ที่ไม่ใช่รายการโปรด)](end-user-favorite.md)
* [ลบหน้ารายงาน](end-user-delete.md)
* [ลบแผ่นแดชบอร์ดหนึ่ง](../service-dashboard-edit-tile.md)
* [ลบภาพการแสดงภาพรายงาน](end-user-delete.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)
