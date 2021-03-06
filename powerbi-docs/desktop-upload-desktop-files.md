---
title: เผยแพร่จาก Power BI Desktop
description: เผยแพร่จาก Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: d513c68dba27bb6e37a158eaad4059b24bc8db6a
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34482003"
---
# <a name="publish-from-power-bi-desktop"></a>เผยแพร่จาก Power BI Desktop
เมื่อคุณเผยแพร่เป็นไฟล์**Power BI Desktop**ไปยัง**Power BI service** ข้อมูลอยู่ในรูปแบบและใด ๆ ที่คุณสร้างขึ้นในมุมมอง**รายงาน**ซึ่งเผยแพร่ไปยังพื้นที่ทำงาน Power BI ของคุณ คุณจะเห็นชุดข้อมูลใหม่ที่มีชื่อเดียวกัน และรายงานต่างๆในตัวนำทางของพื้นที่ทำงานของคุณ

โดยการเผยแพร่จาก**Power BI Desktop**มีผลเช่นเดียวกับการใช้การ**รับข้อมูล**ใน Power BI เพื่อเชื่อมต่อ และอัปโหลดไฟล์**Power BI Desktop**

> [!NOTE]
> การเปลี่ยนแปลงใดๆ ที่คุณทำกับรายงาน Power BI ตัวอย่างเช่น เพิ่ม, ลบ หรือเปลี่ยนแปลงการแสดงภาพในรายงาน จะไม่ถูกบันทึกลงในไฟล์ **Power BI Desktop** ต้นฉบับ
> 
> 

## <a name="to-publish-a-power-bi-desktop-dataset-and-reports"></a>เมื่อต้องการเผยแพร่ชุดข้อมูลและรายงาน Power BI Desktop
1. ใน Power BI Desktop \> **ไฟล์** \>**เผยแพร่** \> **เผยแพร่ไปยัง Power BI** หรือคลิกเผยแพร่**บนริบ**บอน  

   ![ปุ่มเผยแพร่](media/desktop-upload-desktop-files/pbid_publish_publishbutton.png)

2. ลงชื่อเข้าใช้ไปยัง Power BI
3. เลือกปลายทาง

   ![เลือกปลายทางของการเผยแพร่](media/desktop-upload-desktop-files/pbid_publish_select_destination.png)

เมื่อเสร็จแล้ว คุณจะได้รับลิงก์ไปยังรายงานของคุณ คลิกที่ลิงก์เพื่อเปิดรายงานในไซต์ Power BI ของคุณ

![กล่องโต้ตอบเผยแพร่สำเร็จ](media/desktop-upload-desktop-files/pbid_publish_success.png)

## <a name="re-publish-or-replace-a-dataset-published-from-power-bi-desktop"></a>เผยแพร่อีกครั้งหรือแทนที่ชุดข้อมูลที่เผยแพร่จาก Power BI Desktop
เมื่อคุณเผยแพร่ไฟล์**Power BI Desktop** ชุดข้อมูลและรายงานใด ๆ ที่คุณสร้างขึ้นใน**Power BI Desktop**ถูกอัปโหลดไปยังเไซต์ Power BI ของคุณ เมื่อคุณเผยแพร่แฟ้ม**Power BI Desktop**ของคุณอีกครั้ง ชุดข้อมูลในไซต์ Power BI ของคุณจะถูกแทนที่ด้วยชุดข้อมูลที่ถูกอัปเดจากไฟล์**Power BI Desktop**

เรื่องนี้ค่อนข้างตรงไปตรงมา แต่ก็มีบางสิ่งที่คุณควรทราบ

* ถ้าคุณมีชุดข้อมูลสองรายการ หรือมากกว่าใน Power BI โดยใช้ชื่อเดียวกันกับไฟล์**Power BI Desktop** การเผยแพร่อาจล้มเหลวได้ ตรวจสอบให้แน่ใจว่า คุณมีชุดข้อมูลเดียวเท่านั้นใน Power BI ที่มีชื่อเดียวกัน นอกจากนี้คุณยังสามารถเปลี่ยนชื่อไฟล์และเผยแพร่ โดยสร้างชุดข้อมูลใหม่ชื่อเดียวกันกับไฟล์
* ถ้าคุณเปลี่ยนชื่อหรือลบคอลัมน์หรือหน่วยวัด การแสดงภาพใดๆที่คุณมีใน Power BI ที่มีเขตข้อมูลนั้นอาจจะไม่สามารถใช้งาน 
* Power BI ละเว้นการเปลี่ยนแปลงการจัดรูปแบบบางอย่างของคอลัมน์ที่มีอยู่ ตัวอย่างเช่น ถ้าคุณเปลี่ยนรูปแบบของคอลัมน์จาก 0.25 เป็น 25%
* ถ้าคุณมีการกำหนดเวลาการรีเฟรชสำหรับชุดข้อมูลของคุณใน Power BI และคุณได้เพิ่มแหล่งข้อมูลใหม่ลงในไฟล์ของคุณ แล้วเผยแพร่อีกครั้ง คุณจะต้องลงชื่อเข้าใช้*จัดการแหล่งข้อมูล*ก่อนที่จะมีการรีเฟรชตามกำหนดเวลาครั้งถัดไป

