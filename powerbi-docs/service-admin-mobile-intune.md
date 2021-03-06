---
title: กำหนดค่าแอปฯมือถือโดยใช้ Microsoft Intune
description: วิธีการกำหนดค่าแอปฯมือถือ Power BI ด้วย Microsoft Intune ซึ่งรวมถึงวิธีการเพิ่มและการปรับใช้แอปพลิเคชัน และวิธีการสร้างนโยบายแอปพลิเคชันสำหรับอุปกรณ์เคลื่อนที่เมื่อต้องควบคุมการรักษาความปลอดภัย
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 565c43be3489c23f26a98f99ce2d70022be965d2
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2018
ms.locfileid: "44728007"
---
# <a name="configure-mobile-apps-with-microsoft-intune"></a>กำหนดค่าแอปฯมือถือโดยใช้ Microsoft Intune
Microsoft Intune ช่วยให้องค์กรต่าง ๆ สามารถจัดการอุปกรณ์ต่าง ๆ และแอปพลิเคชันได้ ในแอปพลิเคชันมือถือ Power BI สำหรับ iOS และ Android รวมกับ Intune เพื่อให้คุณจัดการแอปพลิเคชันนี้บนอุปกรณ์ของคุณได้ และเพื่อควบคุมการรักษาความปลอดภัย ด้วยนโยบายการกำหนดค่า คุณสามารถควบคุมรายการ เช่น การบังคับใช้ PIN เพื่อเข้าใช้งาน การควบคุมวิธีจัดการกับข้อมูลโดยแอปพลิเคชัน หรือแม้แต่การเข้ารหัสลับข้อมูลแอปพลิเคชันเมื่อไม่ได้ใช้งาน

## <a name="general-mobile-device-management-configuration"></a>การกำหนดค่าการจัดการอุปกรณ์เคลื่อนที่ทั่วไป
บทความนี้ไม่ใช่แนวทางแบบเต็มสำหรับการกำหนดค่า Microsoft Intune หากคุณเพิ่งเริ่มใช้งาน Intune มีบางสิ่งที่คุณต้องตรวจสอบให้แน่ใจว่าคุณได้มีการตั้งค่าแล้ว [เรียนรู้เพิ่มเติม](https://technet.microsoft.com/library/jj676587.aspx)

Microsoft Intune สามารถมีร่วมกับการจัดการอุปกรณ์เคลื่อน (Mobile Device Management: MDM) ภายใน Office 365 ได้ [เรียนรู้เพิ่มเติม](https://blogs.technet.microsoft.com/configmgrdogs/2016/01/04/microsoft-intune-co-existence-with-mdm-for-office-365/)

บทความนี้ถือว่ามีการกำหนดค่า Intune อย่างถูกต้อง และคุณมีอุปกรณ์ที่ลงทะเบียนกับ Intune เรีบบร้อยแล้ว ถ้าคุณใช้งานร่วมอยู่กับ MDM อุปกรณ์ดังกล่าวจะแสดงหากคุณลงทะเบียนภายใน MDM แต่จะพร้อมใช้งานการจัดการภายใน Intune

> [!NOTE]
> หลังจากที่องค์กรของคุณได้กำหนดค่า Microsoft Intune MAM ถ้าคุณใช้แอปฯมือถือ Power BI บนอุปกรณ์ Android หรือ iOS รีเฟรชข้อมูลที่เบื้องหลังจะถูกปิดใช้งาน ครั้งถัดไปที่คุณเข้าใช้งานแอปฯ Power BI จะรีเฟรชข้อมูลจากบริการของ Power BI บนเว็บ
> 
> 

## <a name="step-1-get-the-url-for-the-application"></a>ขั้นตอนที่ 1: รับ URL สำหรับแอปพลิเคชัน
ก่อนที่เราจะสร้างแอปพลิเคชันภายใน Intune เราต้องใช้ URL สำหรับแอปฯ สำหรับ iOS เราจะดาวน์โหลดแอปฯนี้จาก iTunes สำหรับ Android คุณสามารถดาวน์โหลดได้จากหน้าของ Power BI สำหรับมือถือ

บันทึก URL เนื่องจากคุณต้องใช้ข้อมูลนี้เมื่อเราสร้างแอปพลิเคชัน

### <a name="ios"></a>iOS
เมื่อต้องการ URL ของแอปฯสำหรับ iOS เราสามารถดาวน์โหลดได้จาก iTunes

1. เปิด iTunes
2. ค้นหา*Power BI*
3. คุณจะเห็น**Microsoft Power BI**ในรายการใต้**แอปฯ iPhone**และ**แอปฯ iPad** คุณสามารถใช้ได้ทั้งสองแบบเนื่องจากคุณจะได้ URL เดียวกัน
4. เลือก**รับ** เมนูเบบเลื่อนลง และเลือก**คัดลอกลิงก์**
   
    ![](media/service-admin-mobile-intune/itunes-url.png)

ซึ่งควรมีลักษณะคล้ายต่อไปนี้

    https://itunes.apple.com/us/app/microsoft-power-bi/id929738808?mt=8

### <a name="android"></a>Android
คุณสามารถรับ URL สำหรับ Google Play ได้จาก[หน้ามือ Power BI](https://powerbi.microsoft.com/mobile/) คลิกที่ไอคอน**ดาวน์โหลดจาก Google Play** ระบบจะนำคุณไปยังหน้าแอปฯ คุณสามารถคัดลอก URL จากแถบที่อยู่เบราว์เซอร์ ซึ่งควรมีลักษณะคล้ายต่อไปนี้

    https://play.google.com/store/apps/details?id=com.microsoft.powerbim

## <a name="step-2-create-a-mobile-application-management-policy"></a>ขั้นตอนที่ 2: สร้างนโยบายการจัดการแอปพลิเคชันสำหรับอุปกรณ์เคลื่อนที่
นโยบายการจัดการแอปพลิเคชันมือถือช่วยให้คุณสามารถบังคับใช้รายการต่าง ๆ เช่น PIN การเข้าถึงได้ ซึ่งคุณสามารถสร้างได้ภายในพอร์ทัล Intune 

คุณสามารถสร้างแอปพลิเคชันดังกล่าว หรือนโยบายก่อนได้ ลำดับของรายการที่เพิ่มเข้ามาเหล่านี้ไม่มีความสำคัญ เนื่องจากเพียงแค่จำเป็นให้มีอยู่สำหรับขั้นตอนการปรับใช้

1. เลือก**นโยบาย** > **กำหนดค่านโยบาย**
   
    ![](media/service-admin-mobile-intune/intune-policy.png)
2. เลือก**เพิ่ม...**
3. ใต้**ซอฟต์แวร์** คุณสามารถเลือกการจัดการแอปพลิเคชันมือถือ (Mobile Application Management) สำหรับ Android หรือ iOS ได้ เมื่อต้องการเริ่มต้นใช้งานได้อย่างรวดเร็ว คุณสามารถเลือก**สร้างนโยบายด้วยการตั้งค่าที่แนะนำ** หรือคุณสามารถสร้างนโยบายกำหนดเองได้
4. แก้ไขนโยบายเพื่อกำหนดค่าข้อจำกัดที่คุณต้องการบนแอปพลิเคชัน

## <a name="step-3-create-the-application"></a>ขั้นตอนที่ 3: สร้างแอปพลิเคชัน
แอปพลิเคชันเป็นอ้างอิงหรือแพคเกจที่ถูกบันทึกลงใน Intune เพื่อการใช้งาน เราจะต้องสร้างแอปพลิเคชัน และอ้างอิง URL แอปฯที่เราได้รับมาจาก Google Play หรือ iTunes

คุณสามารถสร้างแอปพลิเคชันดังกล่าว หรือนโยบายก่อนได้ ลำดับของรายการที่เพิ่มเข้ามาเหล่านี้ไม่มีความสำคัญ เนื่องจากเพียงแค่จำเป็นให้มีอยู่สำหรับขั้นตอนการปรับใช้

1. ไปยังพอร์ทัล Intune และเลือก**แอปฯ**จากเมนูทางด้านซ้าย
2. เลือก**เพิ่มแอปฯ** ซึ่งจะเปิดขึ้นในแอปพลิเคชัน**เพิ่มซอฟต์แวร์**

### <a name="ios"></a>iOS
1. เลือก**จัดการแอปฯ iOS จาก App Store**จากรายการแบบเลื่อนลง
2. ใส่ URL ของแอปฯที่เราได้จาก[ขั้นตอนที่ 1](#step-1-get-the-url-for-the-application)และเลือก**ถัดไป**
   
    ![](media/service-admin-mobile-intune/intune-add-software-ios1.png)
3. ใส่**ผู้ตีพิมพ์** **ชื่อ** และ**คำอธิบาย** นอกจากนี้ คุณยังสามารถเลือกใส่**ไอคอน**ได้ **ประเภท**มีไว้สำหรับแอปฯ Company Portal เมื่อคุณทำเสร็จแล้ว เลือก**ถัดไป**
4. คุณสามารถตัดสินใจว่าคุณต้องการเผยแพร่ในแอปฯเป็น**ใด ๆ** (ค่าเริ่มต้น) **iPad** หรือ**iPhone**ได้ การตั้งเป็นค่าเริ่มต้น ส่วนนี้จะแสดงเป็น**ใด ๆ**และจะสามารถใช้งานได้กับอุปกรณ์ทั้งสองชนิด แอปฯ Power BI มี URL เดียวกันสำหรับทั้ง iPhone และ iPad เลือก**ถัดไป**
5. เลือก**อัปโหลด**

> [!NOTE]
> คุณอาจไม่เห็นรายการดังกล่าวปรากฏในรายการแอปฯจนกว่าจะรีเฟรชหน้า คุณสามารถคลิก**ภาพรวม**และกลับไปยัง**แอปฯ**เพื่อให้ได้หน้าที่ต้องการโหลดอีกครั้ง
> 
> 

![](media/service-admin-mobile-intune/intune-add-software-ios2.png)

### <a name="android"></a>Android
1. เลือก**เชื่อมโยงภายนอก**จากรายการแบบเลื่อนลง
2. ใส่ URL ของแอปฯที่เราได้จาก[ขั้นตอนที่ 1](#step-1-get-the-url-for-the-application)และเลือก**ถัดไป**
   
    ![](media/service-admin-mobile-intune/intune-add-software-android1.png)
3. ใส่**ผู้ตีพิมพ์** **ชื่อ** และ**คำอธิบาย** นอกจากนี้ คุณยังสามารถเลือกใส่**ไอคอน**ได้ **ประเภท**มีไว้สำหรับแอปฯ Company Portal เมื่อคุณทำเสร็จแล้ว เลือก**ถัดไป**
4. เลือก**อัปโหลด**

> [!NOTE]
> คุณอาจไม่เห็นรายการดังกล่าวปรากฏในรายการแอปฯจนกว่าจะรีเฟรชหน้า คุณสามารถคลิก**ภาพรวม**และกลับไปยัง**แอปฯ**เพื่อให้ได้หน้าที่ต้องการโหลดอีกครั้ง
> 
> 

![](media/service-admin-mobile-intune/intune-add-software-android2.png)

## <a name="step-4-deploy-the-application"></a>ขั้นตอนที่ 4: ใช้งานแอปพลิเคชัน
หลังจากที่คุณเพิ่มแอปพลิเคชันแล้ว คุณจะต้องนำแอปฯดังกล่าวมาใช้เพื่อให้พร้อมใช้งานสำหรับผู้ใช้ของคุณ นี่คือขั้นตอนที่คุณจะผสานรวมนโยบายที่คุณสร้างขึ้นด้วยแอปฯเข้าด้วยกัน

### <a name="ios"></a>iOS
1. บนหน้าจอแอปฯ เลือกแอปฯที่คุณสร้างขึ้น จากนั้นเลือกลิงก์**จัดการการปรับใช้...** 
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios1.png)
2. ที่หน้าจอ**เลือกกลุ่ม** คุณสามารถเลือกกลุ่มที่คุณต้องการปรับใช้แอปฯนี้ เลือก**ถัดไป**
3. ที่หน้าจอ**การดำเนินการปรับใช้** คุณสามารถเลือกวิธีที่คุณต้องการปรับใช้แอปฯนี้ได้ การเลือก**ติดตั้งพร้อมใช้งาน**หรือ**จำเป็นต้องติดตั้ง** จะทำให้แอปฯพร้อมใช้งานใน Company Portal สำหรับผู้ใช้เพื่อทำการติดตั้งตามความต้องการ หลังจากที่คุณได้ทำการเลือกแล้ว เลือก**ถัดไป**
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios2.png)
4. ที่หน้าจอ**การจัดการแอปฯอุปกรณ์เคลื่อนที่** คุณสามารถเลือกนโยบายการจัดการแอปฯอุปกรณ์เคลื่อนที่ที่เราสร้างขึ้นใน[ขั้นตอนที่ 2](#step-2-create-a-mobile-application-management-policy)ได้ ซึ่งจะเป็นค่าเริ่มต้นสำหรับนโยบายที่คุณได้ทำไว้ ถ้านั่นคือนโยบาย iOS เดียวที่พร้อมใช้งาน เลือก**ถัดไป**
   
    ![](media/service-admin-mobile-intune/intune-deploy-ios3.png)
5. ในหน้าจอ**โพรไฟล์ VPN** คุณสามารถเลือกนโยบายได้ถ้าคุณมีสำหรับองค์กรของคุณ ซึ่งค่าเริ่มต้นเป็น**ไม่มี** เลือก**ถัดไป**
6. ที่หน้าจอ**กำหนดค่าแอปฯอุปกรณ์เคลื่อนที่** คุณสามารถเลือกข้อ**นโยบายการกำหนดค่าแอปฯ**ได้ถ้าคุณได้สร้างไว้ ซึ่งค่าเริ่มต้นเป็น**ไม่มี** ข้อมูลนี้ไม่จำเป็น เลือก**เสร็จสิ้น**

หลังจากที่คุณมีการปรับใช้แอปฯดังกล่าวแล้ว แอปฯควรแสดง**ใช่**สำหรับการปรับใช้บนหน้าแอปฯ

### <a name="android"></a>Android
1. บนหน้าจอแอปฯ เลือกแอปฯที่คุณสร้างขึ้น จากนั้นเลือกลิงก์**จัดการการปรับใช้...** 
   
    ![](media/service-admin-mobile-intune/intune-deploy-android1.png)
2. ที่หน้าจอ**เลือกกลุ่ม** คุณสามารถเลือกกลุ่มที่คุณต้องการปรับใช้แอปฯนี้ เลือก**ถัดไป**
3. ที่หน้าจอ**การดำเนินการปรับใช้** คุณสามารถเลือกวิธีที่คุณต้องการปรับใช้แอปฯนี้ได้ การเลือก**ติดตั้งพร้อมใช้งาน**หรือ**จำเป็นต้องติดตั้ง** จะทำให้แอปฯพร้อมใช้งานใน Company Portal สำหรับผู้ใช้เพื่อทำการติดตั้งตามความต้องการ หลังจากที่คุณได้ทำการเลือกแล้ว เลือก**ถัดไป**
   
    ![](media/service-admin-mobile-intune/intune-deploy-android2.png)
4. ที่หน้าจอ**การจัดการแอปฯอุปกรณ์เคลื่อนที่** คุณสามารถเลือกนโยบายการจัดการแอปฯอุปกรณ์เคลื่อนที่ที่เราสร้างขึ้นใน[ขั้นตอนที่ 2](#step-2-create-a-mobile-application-management-policy)ได้ ซึ่งจะเป็นค่าเริ่มต้นสำหรับนโยบายที่คุณได้ทำไว้ ถ้านั่นคือนโยบาย Android เดียวที่พร้อมใช้งาน เลือก**เสร็จสิ้น**
   
    ![](media/service-admin-mobile-intune/intune-deploy-android3.png)

หลังจากที่คุณมีการปรับใช้แอปฯดังกล่าวแล้ว แอปฯควรแสดง**ใช่**สำหรับการปรับใช้บนหน้าแอปฯ

## <a name="step-5-install-the-application-on-a-device"></a>ขั้นตอนที่ 5: ติดตั้งแอปพลิเคชันบนอุปกรณ์
คุณจะติดตั้งแอปพลิเคชันผ่านแอปฯ Company Portal ถ้าคุณยังไม่ได้ติดตั้ง Company Portal คุณสามารถรับได้ผ่าน App Store บนแพลตฟอร์ม Android หรือ iOS คุณจะลงชื่อเข้าใช้ Company Portal ด้วยการเข้าสู่ระบบขององค์กรของคุณ

1. เปิดแอปฯ Company Portal
2. ถ้าคุณไม่เห็นแอปฯ Power BI แสดงเป็นแอปฯแนะนำ ให้เลือก**แอปฯบริษัท**
   
    ![](media/service-admin-mobile-intune/intune-companyportal1.png)
3. เลือกแอปฯ Power BI ที่คุณนำไปใช้
   
    ![](media/service-admin-mobile-intune/intune-companyportal2.png)
4. เลือก **ติดตั้ง**
   
    ![](media/service-admin-mobile-intune/intune-companyportal3.png)
5. ถ้าคุณอยู่ใช้ iOS นั่นจะช่วยส่งแอปฯให้คุณ เลือก**ติดตั้ง**ที่กล่องโต้ตอบพุช
   
    ![](media/service-admin-mobile-intune/intune-companyportal5.png)

หลังจากติดตั้ง คุณจะเห็นว่า**แอปฯนี้จัดการโดยบริษัทของคุณ** ถ้าคุณเปิดใช้งานการเข้าถึงด้วย PIN คุณจะเห็นรายการต่อไปนี้ในนโยบาย

![](media/service-admin-mobile-intune/intune-powerbi-pin.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[กำหนดค่าและปรับใช้นโยบายการจัดการแอปพลิเคชันมือถือในคอนโซล Microsoft Intune](https://technet.microsoft.com/library/dn878026.aspx)  
[แอปฯ Power BI สำหรับอุปกรณ์เคลื่อนที่](consumer/mobile/mobile-apps-for-mobile-devices.md)  

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](http://community.powerbi.com/)

