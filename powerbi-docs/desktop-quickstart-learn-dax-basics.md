---
title: พื้นฐาน DAX ใน Power BI Desktop
description: พื้นฐาน DAX ใน Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: ca2f9e3393df2fd205474983ab9868aa9401ed9d
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/27/2018
ms.locfileid: "39329212"
---
# <a name="dax-basics-in-power-bi-desktop"></a>พื้นฐาน DAX ใน Power BI Desktop
บทความนี้มีไว้สำหรับผู้ใช้ที่ยังใหม่กับ Power BI Desktop โดยมีไว้เพื่อให้คำแนะนำที่ง่ายและรวดเร็วแก่คุณเกี่ยวกับวิธีการที่คุณสามารถใช้นิพจน์การวิเคราะห์ข้อมูล (DAX) เพื่อแก้ปัญหาการคำนวณพื้นฐานและการวิเคราะห์ข้อมูลต่างๆ เราจะไปดูกันที่ข้อมูลแนวคิดบางอย่าง ชุดงานที่คุณสามารถทำให้เสร็จสมบูรณ์ และแบบทดสอบเพื่อทดสอบสิ่งที่คุณได้เรียนรู้ไปสักเล็กน้อย หลังจากจบบทความนี้ คุณควรมีความเข้าใจที่ดีเกี่ยวกับแนวคิดพื้นฐานสำคัญที่สุดของ DAX

## <a name="what-is-dax"></a>DAX คืออะไร
DAX คือ คอลเลกชันของฟังก์ชัน ตัวดำเนินการ และค่าคงที่ที่สามารถใช้ในสูตรหรือนิพจน์เพื่อคำนวณและส่งคืนค่าอย่างน้อยหนึ่งค่า กล่าวให้ง่ายขึ้นก็คือ DAX จะช่วยให้คุณสร้างข้อมูลใหม่จากข้อมูลที่มีอยู่แล้วในแบบจำลองของคุณ

## <a name="why-is-dax-so-important"></a>ทำไม DAX จึงสำคัญมาก
การสร้างไฟล์ Power BI Desktop ใหม่และนำเข้าข้อมูลบางอย่างเข้าไปในนั้นทำได้ค่อนข้างง่าย คุณยังสามารถสร้างรายงานที่แสดงข้อมูลเชิงลึกอันมีค่าได้โดยไม่ต้องใช้สูตร DAX ใด ๆ เลย แต่จะเกิดอะไรขึ้นถ้าคุณจำเป็นต้องวิเคราะห์เปอร์เซ็นต์การเติบโตในแต่ละประเภทผลิตภัณฑ์และสำหรับช่วงวันที่ที่แตกต่างกัน หรือคุณจำเป็นต้องคำนวณการเติบโตแบบปีต่อปีเมื่อเปรียบเทียบกับแนวโน้มของตลาด สูตร DAX ทำให้มีความสามารถนี้รวมถึงความสามารถอื่นๆ อีกหลายอย่างที่สำคัญด้วย การเรียนรู้วิธีการสร้างสูตร DAX อย่างมีประสิทธิภาพจะช่วยให้คุณได้รับประโยชน์สูงสุดจากข้อมูลของคุณ เมื่อได้ข้อมูลที่ต้องการ คุณก็สามารถเริ่มแก้ปัญหาทางธุรกิจที่แท้จริงซึ่งส่งผลกระทบต่อผลลัพธ์ทางธุรกิจของคุณ นี่คือประสิทธิภาพของ Power BI และ DAX จะช่วยให้คุณบรรลุสิ่งนั้น

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
คุณอาจคุ้นเคยกับการสร้างสูตรใน Microsoft Excel อยู่แล้ว ความรู้นั้นจะเป็นประโยชน์ในการทำความเข้าใจ DAX แต่ถึงแม้ว่าคุณจะไม่มีประสบการณ์เกี่ยวกับสูตร Excel มาก่อน แนวคิดที่อธิบายไว้ที่นี้สามารถช่วยให้คุณเริ่มต้นการสร้างสูตร DAX และแก้ไขปัญหา BI ในความเป็นจริงได้ทันที

เราจะมุ่งเน้นไปที่การทำความเข้าใจสูตร DAX ที่ใช้ในการคำนวณต่างๆ โดยเฉพาะอย่างยิ่ง ในหน่วยวัดและคอลัมน์จากการคำนวณ คุณควรจะมีความคุ้นเคยอยู่แล้วกับ Power BI Desktop การนำเข้าข้อมูล การเพิ่มเขตข้อมูลในรายงาน และควรมีความคุ้นเคยกับแนวคิดพื้นฐานเรื่อง [หน่วยวัด](desktop-measures.md)และ[คอลัมน์จากคำนวณ](desktop-calculated-columns.md)ด้วย

**สมุดงานตัวอย่าง**

วิธีที่ีดีที่สุดในการเรียนรู้ DAX ก็คือ การสร้างสูตรพื้นฐานบางสูตร ใชสูตรนั้นๆ กับข้อมูลจริงบางอย่าง และดูผลลัพธ์ด้วยตัวคุณเอง ตัวอย่างและงานในที่นี้ี่ใช้ตัวอย่างการขาย Contoso สำหรับไฟล์แสดงตัวอย่าง Power BI Desktop นี่คือตัวอย่างไฟล์เดียวกันที่ใช้ในบทความ [บทช่วยสอน: สร้างหน่วยวัดของคุณเองใน Power BI Desktop](desktop-tutorial-create-measures.md) ต่อไปนี้เป็น [ไฟล์ตัวอย่าง](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20for%20Power%20BI%20Designer.zip) ให้ดาวน์โหลด

## <a name="lets-begin"></a>มาเริ่มกันเลย!
เราจะกำหนดกรอบความเข้าใจเรื่อง DAX โดยเกี่ยวข้องกับแนวคิดพื้นฐานสามข้อ: *ไวยากรณ์* *ฟังก์ชัน* และ*บริบท* แน่นอนว่า ยังมีแนวคิดที่สำคัญอื่น ๆ เกี่ยวกับ DAX อีก แต่การทำความเข้าใจแนวคิดสามข้อเหล่านี้จะช่วยให้คุณมีข้อมูลพื้นฐานที่ดีที่สุดเกี่ยวกับสร้างทักษะ DAX

### <a name="syntax"></a>ไวยากรณ์
ก่อนที่คุณจะสร้างสูตรของคุณเอง ลองมาดูที่ไวยากรณ์ของสูตร DAX กันก่อน ไวยากรณ์ประกอบด้วยองค์ประกอบต่าง ๆ ที่ทำให้เกิดสูตรหรือกล่าวให้ง่ายยิ่งขึ้นก็คือ วิธีเขียนสูตร ตัวอย่างเช่น มาดูสูตร DAX อย่างง่ายสำหรับหน่วยวัด

![](media/desktop-quickstart-learn-dax-basics/qsdax_1_syntax.png)

สูตรนี้ประกอบด้วยองค์ประกอบไวยากรณ์ดังต่อไปนี้:

**A.** ชื่อหน่วยวัด **ยอดขายรวม**

**B.** ตัวดำเนินการเครื่องหมายเท่ากับ (**=**) ระบุจุดเริ่มต้นของสูตร เมื่อคำนวณแล้ว ก็จะส่งคืนผลลัพธ์

**C.** ฟังก์ชัน DAX **SUM** จะรวมยอดทั้งหมดของตัวเลขในคอลัมน์ **ยอดขาย [SalesAmount]** คุณจะได้เรียนรู้เพิ่มเติมเกี่ยวกับฟังก์ชันต่างๆ ในภายหลัง

**D.** วงเล็บ **()** จะล้อมรอบนิพจน์ที่ประกอบด้วยอย่างน้อยหนึ่งอาร์กิวเมนต์ ฟังก์ชันทั้งหมดจำเป็นต้องมีอย่างน้อยหนึ่งอาร์กิวเมนต์ อาร์กิวเมนต์จะส่งผ่านค่าไปยังฟังก์ชัน

**E.** ตารางอ้างอิง **ยอดขาย**

**F.** คอลัมน์อ้างอิง **[SalesAmount]** ในตารางยอดขาย ด้วยอาร์กิวเมนต์นี้ ฟังก์ชัน SUM จะทราบได้ว่าจะรวมผล SUM ในคอลัมน์ใดบ้าง

เมื่อคุณพยายามทำความเข้าใจสูตร DAX การแบ่งย่อยแต่ละองค์ประกอบให้เป็นภาษาที่คุณคิดและพูดทุกวันมักจะเป็นประโยชน์ ตัวอย่างเช่น คุณสามารถอ่านสูตรนี้ได้เป็น:

> *สำหรับหน่วยวัดชื่อ ยอดขายรวม ให้คำนวณ (=) SUM ของค่าในคอลัมน์ [SalesAmount] ในตารางยอดขาย*
> 
> 

เมื่อเพิ่มเข้าไปในรายงานแล้ว หน่วยวัดนี้จะคำนวณและส่งคืนค่าโดยการหาผลรวมยอดขายสำหรับแต่ละเขตข้อมูลอื่น ๆ ที่รวมอยู่ด้วย เช่น โทรศัพท์มือถือในสหรัฐอเมริกา

คุณอาจกำลังคิดว่า 'หน่วยวัดนี้ก็ทำอย่างเดียวกันกับการที่ฉันเพียงแค่เพิ่มเขตข้อมูล SalesAmount ลงในรายงานของฉันไม่ใช่หรือ' ก็ใช่ แต่มีเหตุผลที่ดีในการสร้างหน่วยวัดของเราเองขึ้นมาซึ่งจะหาผลรวมของค่าจากเขตข้อมูล SalesAmount: เราสามารถใช้สิ่งนี้เป็นอาร์กิวเมนต์ในสูตรอื่น ๆ ได้ ซึ่งอาจดูเหมือนว่าสับสนเล็กน้อยในตอนนี้ แต่เมื่อคุณเพิ่มพูนทักษะเกี่ยวกับสูตร DAX การที่คุณทราบในข้อนี้จะทำให้สูตรของคุณและแบบจำลองของคุณมีประสิทธิภาพมากยิ่งขึ้น อันที่จริงแล้ว คุณจะเห็นหน่วยวัดยอดขายรวมปรากฏขึ้นเป็นอาร์กิวเมนต์ในสูตรอื่นในภายหลัง

ลองมาดูบางอย่างเพิ่มเติมเกี่ยวกับสูตรนี้กัน โดยเฉพาะอย่างยิ่ง เราได้แนะนำฟังก์ชัน [SUM](https://msdn.microsoft.com/library/ee634387.aspx) ไปแล้ว ฟังก์ชันเป็นสูตรที่เขียนไว้ล่วงหน้าซึ่งทำให้สามารถทำการคำนวณที่ซับซ้อนและจัดการกับตัวเลข วันที่ เวลา ข้อความและอื่น ๆ ได้ง่ายยิ่งขึ้น คุณจะได้เรียนรู้เพิ่มเติมเกี่ยวกับฟังก์ชันต่างๆ ในภายหลัง

คุณยังเห็นคอลัมน์ [SalesAmount] ถูกนำหน้าด้วยตารางยอดขายซึ่งมีคอลัมน์ดังกล่าวอยู่ในนั้น ซึ่งเรียกว่า ชื่อคอลัมน์แบบเต็มที่มีชื่อคอลัมน์ที่นำหน้าด้วยชื่อตาราง คอลัมน์ที่อ้างอิงไว้ในตารางเดียวกันไม่จำเป็นต้องมีชื่อตารางรวมอยู่ในสูตร ซึ่งสามารถทำให้สูตรที่ยาวซึ่งอ้างอิงคอลัมน์จำนวนมากสั้นลงและอ่านได้ง่ายขึ้น อย่างไรก็ตาม เป็นการดีที่จะรวมชื่อตารางไว้ในสูตรหน่วยวัดของคุณด้วยแม้จะอยู่ในตารางเดียวกัน

> [!NOTE]
> ถ้าชื่อตารางประกอบด้วยช่องว่าง คำสำคัญที่สงวนไว้ หรืออักขระที่ไม่ได้รับอนุญาต คุณจะต้องใส่ชื่อตารางไว้ในเครื่องหมายอัญประกาศเดี่ยว นอกจากนี้ คุณยังจำเป็นต้องใส่ชื่อตารางในเครื่องหมายอัญประกาศถ้าชื่อประกอบด้วยอักขระใด ๆ ที่อยู่นอกช่วงอักขระพยัญชนะผสมตัวเลข ANSI โดยไม่ต้องคำนึงถึงว่าตำแหน่งที่ตั้งของคุณสนับสนุนชุดอักขระหรือไม่
> 
> 

เป็นเรื่องสำคัญที่ว่า สูตรของคุณมีไวยากรณ์ที่ถูกต้อง ในกรณีส่วนใหญ่ ถ้าไวยากรณ์ไม่ถูกต้อง ข้อผิดพลาดทางไวยากรณ์จะถูกส่งคืน ในกรณีอื่น ๆ ไวยากรณ์อาจถูกต้อง แต่ค่าที่ส่งคืนอาจไม่ใช่สิ่งที่คุณคาดคิด ตัวแก้ไข DAX ใน Power BI Desktop มีคุณลักษณะคำแนะนำซึ่งใช้เพื่อสร้างสูตรที่ถูกต้องทางไวยากรณ์โดยช่วยให้คุณสามารถเลือกองค์ประกอบที่ถูกต้องได้

มาสร้างสูตรอย่างง่ายกัน งานนี้จะช่วยให้คุณเข้าใจมากยิ่งขึ้นเกี่ยวกับไวยากรณ์ของสูตรและวิธีที่คุณลักษณะคำแนะนำในแถบสูตรสามารถช่วยคุณได้

### <a name="task-create-a-measure-formula"></a>งาน: สร้างสูตรหน่วยวัด
เพื่อทำงานนี้ให้เสร็จสมบูรณ์ คุณจะต้องเปิดไฟล์ Power BI Desktop ตัวอย่างยอดขาย Contoso
    
1. ในมุมมองรายงาน ในรายการเขตข้อมูล คลิกขวาบนตาราง **ยอดขาย**และจากนั้น คลิก **หน่วยวัดใหม่**
    
2. ในแถบสูตร แทนที่ **หน่วยวัด**ด้วยการพิมพ์ชื่อหน่วยวัดใหม่ **ยอดขายไตรมาสก่อนหน้า**
    
3. หลังเครื่องหมายเท่ากับ พิมพ์ **SUM** ตามด้วยวงเล็บเปิด
    
   แทนที่จะพิมพ์ชื่อคอลัมน์เพื่อหาผลรวมค่าในทันที เรากำลังจะใส่ฟังก์ชันอื่น เพื่อ*กรอง*ข้อมูลที่เราต้องการหาผลรวม
    
4. ระหว่างวงเล็บ พิมพ์ **CALCULATE** ตามด้วยวงเล็บเปิด
    
   คุณจะใช้ฟังก์ชัน CALCULATE เพื่อกรองจำนวนที่เราต้องการหาผลรวมโดยอาร์กิวเมนต์ที่ส่งผ่านไปยังฟังก์ชัน CALCULATE นี่คือสิ่งเรียกว่าฟังก์ชันซ้อนกัน ฟังก์ชัน CALCULATE มีอย่างน้อยสองอาร์กิวเมนต์ อาร์กิวเมนต์แรกเป็นนิพจน์ที่จะประเมิน และอาร์กิวเมนต์ที่สองเป็นตัวกรอง
   
5. ระหว่างวงเล็บ **()** สำหรับฟังก์ชัน **CALCULATE** พิมพ์ **Sales[SalesAmount]** นี่เป็นอาร์กิวเมนต์นิพจน์แรกสำหรับฟังก์ชัน CALCULATE ของเรา
    
6. พิมพ์เครื่องหมายจุลภาค (**,**) เพื่อระบุตัวกรองแรก แล้วพิมพ์ **PREVIOUSQUARTER** ตามด้วยวงเล็บเปิด
    
   คุณจะใช้ฟังก์ชันตัวแสดงเวลา PREVIOUSQUARTER เพื่อกรองผลลัพธ์ SUM ของเราตามไตรมาสก่อนหน้า
    
7. ระหว่างวงเล็บ **()** สำหรับฟังก์ชัน PREVIOUSQUARTER พิมพ์**Calendar[DateKey]**
    
   ฟังก์ชัน PREVIOUSQUARTER มีหนึ่งอาร์กิวเมนต์ซึ่งเป็นคอลัมน์ที่ประกอบด้วยช่วงวันต่อเนื่องกัน
    
8. ตรวจสอบให้แน่ใจว่า ทั้งสองอาร์กิวเมนต์ถูกส่งผ่านไปยังฟังก์ชัน PREVIOUSQUARTER และฟังก์ชัน CALCULATE ถูกปิดด้วยวงเล็บปิดสองอัน **))**
    
   ในตอนนี้สูตรของคุณควรมีลักษณะดังนี้:
    
   **ยอดขายไตรมาสก่อนหน้า = CALCULATE(SUM(Sales[SalesAmount]), PREVIOUSQUARTER(Calendar[DateKey]))**
    
9. คลิกที่เครื่องหมายถูก ![](media/desktop-quickstart-learn-dax-basics/qsdax_syntax_taskcheckmark.png)ในแถบสูตรหรือกด Enter เพื่อตรวจสอบสูตร และเพิ่มไปยังแบบจำลอง

คุณทำสำเร็จแล้ว! คุณเพิ่งสร้างหน่วยวัดโดยใช้ DAX และไม่ใช่เรื่องง่ายๆ เลย สูตรนี้จะทำงานเพื่อคำนวณยอดขายรวมสำหรับไตรมาสก่อนหน้าโดยขึ้นอยู่กับตัวกรองที่ใช้ในรายงาน ตัวอย่างเช่น ถ้าเราใส่ SalesAmount และหน่วยวัด Previous Quarter Sales ใหม่ของเราในแผนภูมิ แล้วเพิ่ม Year และ QuarterOfYear เป็นตัวแบ่งส่วนข้อมูล เราจะได้บางอย่างดังนี้:

![](media/desktop-quickstart-learn-dax-basics/qsdax_3_chart.png)

คุณเพิ่งได้รับคำแนะนำเกี่ยวกับแง่มุมที่สำคัญต่าง ๆ ของสูตร DAX ก่อนอื่น สูตรนี้ประกอบด้วยสองฟังก์ชัน ข้อสังเกต [PREVIOUSQUARTER](https://msdn.microsoft.com/library/ee634385.aspx) ซึ่งเป็นฟังก์ชันตัวแสดงเวลาจะซ้อนกันเป็นอาร์กิวเมนต์ที่ส่งผ่านไปยังฟังก์ชันตัวกรอง [CALCULATE](https://msdn.microsoft.com/library/ee634825.aspx) สูตร DAX สามารถมีได้จนถึง 64 ฟังก์ชันซ้อนกัน ไม่น่าเคยมีสูตรที่ประกอบด้วยฟังก์ชันที่ซ้อนกันมากเช่นนี้มาก่อน อันที่จริงแล้ว สูตรดังกล่าวสร้างและแก้ไขจุดบกพร่องได้ยากมาก และไม่อาจทำได้อย่างรวดเร็วด้วย

ในสูตรนี้ คุณยังใช้ตัวกรองด้วย ตัวกรองจะช่วยทำให้สิ่งที่จะคำนวณแคบลง ในกรณีนี้ คุณเลือกตัวกรองหนึ่งตัวเป็นอาร์กิวเมนต์ซึ่งแท้จริงแล้วเป็นผลลัพธ์ของฟังก์ชันอื่น คุณจะได้เรียนรู้เพิ่มเติมเกี่ยวกับตัวกรองต่างๆ ในภายหลัง

ในตอนท้าย คุณสามารถใช้ฟังก์ชัน CALCULATE ได้ ฟังก์ชันนี้เป็นหนึ่งในฟังก์ชันที่มีประสิทธิภาพที่สุดใน DAX เมื่อคุณเขียนแบบจำลองและสร้างสูตรที่ซับซ้อนมากยิ่งขึ้น ก็มีแนวโน้มว่า คุณจะต้องใช้ฟังก์ชันนี้บ่อยครั้ง ถึงแม้ว่าการกล่างถึงฟังก์ชัน CALCULATE จะอยู่นอกขอบเขตของบทความนี้ แต่เมื่อใดที่คุณเพิ่มพูนความรูเกี่ยวกับ DAX ควรสนใจฟังก์ชันนี้เป็นพิเศษ

### <a name="syntax-quickquiz"></a>แบบทดสอบอย่างเร็วเรื่องไวยากรณ์
1. ปุ่มนี้บนแถบสูตรทำอะไรได้บ้าง
   
   > ![](media/desktop-quickstart-learn-dax-basics/qsdax_2_syntaxquiz.png)
   > 
   > 
2. อะไรที่ต้องล้อมรอบชื่อคอลัมน์ในสูตร DAX อยู่เสมอ

คำตอบมีให้ไว้ในตอนท้ายของบทความนี้

### <a name="functions"></a>ฟังก์ชัน
ฟังก์ชัน คือ สูตรที่กำหนดไว้ล่วงหน้าซึ่งดำเนินการคำนวณโดยใช้ค่าที่ระบุซึ่งเรียกว่าอาร์กิวเมนต์ตามลำดับหรือโครงสร้างเฉพาะ อาร์กิวเมนตอาจจะเป็นฟังก์ชันอื่น ๆ สูตร นิพจน์ ส่วนอ้างอิงคอลัมน์ ตัวเลข ข้อความ ค่าตรรกะ เช่น TRUE หรือ FALSE หรือค่าคงที่อื่นก็ได้

DAX มีประเภทของฟังก์ชันดังต่อไปนี้: [วันที่และเวลา](https://msdn.microsoft.com/library/ee634786.aspx) [ตัวแสดงเวลา](https://msdn.microsoft.com/library/ee634763.aspx) [ข้อมูล](https://msdn.microsoft.com/library/ee634552.aspx) ฟังก์ชัน[เชิงตรรกะ](https://msdn.microsoft.com/library/ee634365.aspx) [ คณิตศาสตร์](https://msdn.microsoft.com/library/ee634241.aspx) [สถิติ](https://msdn.microsoft.com/library/ee634822.aspx) [ข้อความ](https://msdn.microsoft.com/library/ee634938.aspx) [หลัก/รอง](https://msdn.microsoft.com/library/mt150102.aspx) และ[อื่น ๆ](https://msdn.microsoft.com/library/mt150101.aspx) ถ้าคุณคุ้นเคยกับฟังก์ชันในสูตร Excel ฟังก์ชันหลายฟังก์ชันใน DAX อาจจะดูคล้ายคลึงกัน อย่างไรก็ตาม ฟังก์ชัน DAX จะไม่ซ้ำกันในลักษณะดังต่อไปนี้:

* ฟังก์ชัน DAX จะอ้างอิงถึงคอลัมน์หรือตารางทั้งหมดเสมอ ถ้าคุณต้องการใช้ค่าเฉพาะจากตารางหรือคอลัมน์เท่านั้น คุณสามารถเพิ่มตัวกรองลงในสูตรได้
* ถ้าคุณต้องการกำหนดการคำนวณเองแบบทีละแถว DAX มีฟังก์ชันที่ช่วยให้คุณใช้ค่าแถวปัจจุบันหรือค่าเกี่ยวข้อง เช่น ชนิดของอาร์กิวเมนต์เพื่อทำการคำนวณที่แตกต่างกันไปตามบริบท คุณจะได้เรียนรู้เพิ่มเติมเกี่ยวกับบริบทในภายหลัง
* DAX มีฟังก์ชันต่าง ๆ ที่ส่งคืนตารางแทนที่จะเป็นค่า ตารางจะไม่แสดงไว้ แต่จะใช้เพื่อให้ข้อมูลป้อนเข้าไปยังฟังก์ชันอื่น ๆ ตัวอย่างเช่น คุณสามารถเรียกใช้ตารางแล้วนับค่าที่แยกชัดในนั้นหรือคำนวณผลรวมแบบไดนามิกผ่านตารางหรือคอลัมน์ที่กรองแล้ว
* DAX มีฟังก์ชันตัวแสดงเวลาต่าง ๆ ฟังก์ชันเหล่านี้ช่วยให้คุณสามารถกำหนดหรือเลือกช่วงวันที่ และดำเนินการคำนวณแบบไดนามิกตามสิ่งเหล่านั้นได้ ตัวอย่างเช่น คุณสามารถเปรียบเทียบผลรวมตลอดระยะเวลาแบบขนาน
* Excel มีฟังก์ชันที่ได้รับความนิยมมาก ได้แก่ VLOOKUP ฟังก์ชัน DAX ไม่ได้ใช้เซลล์หรือช่วงเซลล์ในการอ้างอิงเหมือนกับ VLOOKUP ใน Excel ฟังก์ชัน DAX จะใช้คอลัมน์หรือตารางในการอ้างอิง โปรดทราบว่า ใน Power BI Desktop คุณกำลังทำงานโดยใช้แบบจำลองข้อมูลเชิงสัมพันธ์ การค้นหาค่าในตารางอื่นทำได้ค่อนข้างง่ายมาก และในกรณีส่วนใหญ่ คุณไม่จำเป็นต้องสร้างสูตรใด ๆ เลย
  
  ตามที่คุณเห็น ฟังก์ชันใน DAX สามารถช่วยให้คุณสามารถสร้างสูตรที่มีประสิทธิภาพมาก เราเพียงแค่กล่าวถึงพื้นฐานของฟังก์ชันคร่าวๆ เท่านั้น เมื่อคุณเพิ่มพูนทักษะเกี่ยวกับ DAX คุณก็จะสร้างสูตรโดยใช้ฟังก์ชันที่แตกต่างกันได้มากมาย หนึ่งในแหล่งที่ดีที่สุดสำหรับเรียนรู้รายละเอียดเกี่ยวกับฟังก์ชัน DAX แต่ละฟังก์ชันจะอยู่ใน [การอ้างอิงฟังก์ชัน DAX](https://msdn.microsoft.com/library/ee634396.aspx)

### <a name="functions-quickquiz"></a>แบบทดสอบอย่างเร็วเรื่องฟังก์ชัน
1. ฟังก์ชันอ้างอิงถึงสิ่งใดเสมอ
2. สูตรสูตรหนึ่งสามารถประกอบด้วยฟังก์ชันมากกว่าหนึ่งได้หรือไม่
3. คุณจะใช้ฟังก์ชันประเภทใดเพื่อเชื่อมสองสตริงข้อความเข้าด้วยกันเป็นสตริงเดียว

คำตอบมีให้ไว้ในตอนท้ายของบทความนี้

### <a name="context"></a>บริบท
บริบทเป็นแนวคิดเกี่ยวกับ DAX ที่สำคัญที่สุดข้อหนึ่งที่ต้องทำความเข้าใจ มีบริบทอยู่สองชนิดใน DAX ได้แก่ บริบทแถวและบริบทตัวกรอง ก่อนอื่น เราจะมาดูที่บริบทแถว

**บริบทแถว**

บริบทแถวที่นึกถึงได้ง่ายที่สุดก็คือ แถวปัจจุบัน ซึ่งสามารถนำไปใช้ได้เมื่อใดก็ตามที่สูตรมีฟังก์ชันซึ่งใช้ตัวกรองเพื่อระบุแถวเดี่ยวในตาราง ฟังก์ชันดังกล่าวจะใช้บริบทแถวสำหรับแต่ละแถวของตารางซึ่งทำการกรองทั่วทั้งหมดอยู่แล้ว บริบทแถวชนิดนี้ใช้บ่อยที่สุดกับหน่วยวัด

**บริบทตัวกรอง**

บริบทตัวกรองจะเข้าใจได้ยากกว่าบริบทแถวเล็กน้อย คุณสามารถนึกภาพบริบทตัวกรองได้ง่ายมากที่สุดเป็น: ตัวกรองอย่างน้อยหนึ่งตัวที่ใช้ในการคำนวณที่กำหนดผลลัพธ์หรือค่าได้

บริบทตัวกรองจะไม่ได้มีอยู่แทนที่ีบริบทแถว แต่จะใช้เพิ่มเติมจากบริบทแถวแทน ตัวอย่างเช่น เพื่อทำให้ค่าแคบลงเพื่อรวมอยู่ในการคำนวณ คุณสามารถใช้บริบทตัวกรองซึ่งไม่เพียงจะระบุบริบทแถวเท่านั้น แต่ว่ายังระบุเพียงค่า (ตัวกรอง) เฉพาะในบริบทแถวด้วย

บริบทตัวกรองจะพบเห็นได้ง่ายในรายงานของคุณ ตัวอย่างเช่น เมื่อคุณเพิ่ม TotalCost ในการจัดรูปแบบแสดงข้อมูล แล้วเพิ่ม Year และ Region คุณกำลังกำหนดบริบทตัวกรองที่เลือกเซตย่อยของข้อมูลที่ยึดตามปีและภูมิภาคที่ระบุ

ทำไมบริบทตัวกรองจึงมีความสำคัญต่อ DAX อย่างมาก เนื่องจากในขณะที่บริบทตัวกรองจะสามารถใช้ได้ง่ายที่สุดโดยการเพิ่มเขตข้อมูลในการจัดรูปแบบแสดงข้อมูล บริบทตัวกรองก็ยังสามารถใช้ในสูตร DAX โดยการกำหนดตัวกรองโดยใช้ฟังก์ชัน เช่น ALL, RELATED, FILTER, CALCULATE ได้โดยความสัมพันธ์ต่างๆ และหน่วยวัดและคอลัมน์อื่น ๆ ตัวอย่างเช่น มาดูสูตรดังต่อไปนี้ในหน่วยวัดที่ชื่อ Store Sales:

![](media/desktop-quickstart-learn-dax-basics/qsdax_4_context.png)

เพื่อให้เข้าใจสูตรนี้ได้ดียิ่งขึ้น เราสามารถแยกย่อยลงมาได้เช่นเดียวกับสูตรอื่นๆ

สูตรนี้ประกอบด้วยองค์ประกอบไวยากรณ์ดังต่อไปนี้:

**A.** ชื่อหน่วยวัด **Store Sales**

**B.** ตัวดำเนินการเครื่องหมายเท่ากับ (**=**) ระบุจุดเริ่มต้นของสูตร

**C.** ฟังก์ชัน **CALCULATE** จะประเมินนิพจน์เป็นอาร์กิวเมนต์ในบริบทที่ปรับเปลี่ยนตามตัวกรองที่ระบุ

**D.** วงเล็บ **()** จะล้อมรอบนิพจน์ที่ประกอบด้วยอย่างน้อยหนึ่งอาร์กิวเมนต์

**E.** หน่วยวัด **[Total Sales]** ในตารางเดียวกันเป็นนิพจน์ หน่วยวัด Total Sales มีสูตรดังนี้: = SUM(Sales[SalesAmount])

**F.** เครื่องหมายจุลภาค (**,**) แยกอาร์กิวเมนต์นิพจน์แรกจากอาร์กิวเมนต์ตัวกรอง

**G.** คอลัมน์อ้างอิงแบบเต็ม **Channel[ChannelName]** นี่คือบริบทแถวของเรา แต่ละแถวในคอลัมน์นี้จะระบุแชนเนล: Store, Online เป็นต้น

**H.** ค่าเฉพาะ **Store** เป็นตัวกรอง นี่คือบริบทตัวกรองของเรา

สูตรนี้ช่วยให้มั่นใจเฉพาะค่ายอดขายที่กำหนดโดยหน่วยวัด Total Sales ซึ่งจะถูกคำนวณสำหรับแถวในคอลัมน์ Channel[ChannelName] โดยใช้ค่า "Store" เป็นตัวกรองเท่านั้น

ตามที่คุณสามารถลองนึกภาพได้ การที่เราสามารถกำหนดบริบทตัวกรองภายในสูตรได้นั้นเป็นขีดความสามารถที่ดีเยี่ยมและมีประสิทธิภาพมาก การที่เราสามารถอ้างอิงเฉพาะค่าใดค่าหนึ่งในตารางที่เกี่ยวข้องได้นั้นเป็นเพียงแค่ตัวอย่างเดียว ไม่ต้องกังวลถ้าคุณยังไม่เข้าใจบริบทได้ทั้งหมดในทันที เมื่อคุณสร้างสูตรของคุณเอง คุณจะเข้าใจบริบทและเหตุผลที่บริบทมีความสำคัญมากต่อ DAX ได้ดียิ่งขึ้นเอง

### <a name="context-quickquiz"></a>แบบทดสอบอย่างเร็วเรื่องบริบท
1. บริบทสองชนิดมีอะไรบ้าง
2. บริบทตัวกรองคืออะไร
3. บริบทแถวคืออะไร

คำตอบมีให้ไว้ในตอนท้ายของบทความนี้

## <a name="summary"></a>สรุป
หลังจากที่คุณมีความเข้าใจพื้นฐานเกี่ยวกับแนวคิดที่สำคัญที่สุดเรื่อง DAX คุณจะสามารถเริ่มสร้างสูตร DAX สำหรับหน่วยวัดได้ด้วยตนเอง จริงอยู่ที่ว่า DAX อาจจะเรียนรู้ได้ยากสักหน่อย แต่ก็ยังมีทรัพยากรมากมายพร้อมให้คุณใช้งาน หลังจากอ่านบทความนี้และได้ลองใช้สูตรบางสูตรของคุณเอง คุณก็จะสามารถเรียนรู้เพิ่มเติมเกี่ยวกับแนวคิด DAX อื่น ๆ และสูตรที่สามารถช่วยให้คุณแก้ปัญหาทางธุรกิจของคุณเองได้ มีทรัพยากร DAX หลายแหล่งพร้อมให้คุณใช้งาน ที่สำคัญที่สุดก็คือ [การอ้างอิงนิพจน์การวิเคราะห์ข้อมูล (DAX)](https://msdn.microsoft.com/library/gg413422.aspx)

DAX มี่มานานหลายปีแล้วในเครื่องมือ Microsoft BI อื่น ๆ เช่น ตัวแบบ Power Pivot และตัวแบบ Analysis Services Tabular จึงมีข้อมูลที่ยอดเยี่ยมมากมาย คุณสามารถค้นหาข้อมูลเพิ่มเติมได้ในหนังสือ เอกสารทางเทคนิค และบล็อกจากทั้ง Microsoft และผู้เชี่ยวชาญด้าน BI ชั้นนำ [Wiki ศูนย์ทรัพยากร DAX บน TechNet](http://social.technet.microsoft.com/wiki/contents/articles/dax-resource-center.aspx) เป็นแหล่งที่ยอดเยี่ยมในการเริ่มต้นเช่นกัน

### <a name="quickquiz-answers"></a>คำตอบของแบบทดสอบอย่างเร็ว
ไวยากรณ์:

1. ตรวจสอบและใส่หน่วยวัดลงในแบบจำลอง
2. วงเล็บเหลี่ยม []

ฟังก์ชัน:

1. ตารางและคอลัมน์
2. ใช่ สูตรสูตรหนึ่งสามารถมีได้จนถึง 64 ฟังก์ชันซ้อนกัน
3. [ฟังก์ชันข้อความ](https://msdn.microsoft.com/library/ee634938.aspx)

บริบท:

1. บริบทแถวและบริบทตัวกรอง
2. ตัวกรองอย่างน้อยหนึ่งตัวในการคำนวณที่กำหนดเป็นค่าเดียว
3. แถวปัจจุบัน

