---
title: การสนับสนุนเบราว์เซอร์สำหรับเซิร์ฟเวอร์รายงาน Power BI
description: เรียนรู้เกี่ยวกับรุ่นเบราว์เซอร์ที่ได้รับการสนับสนุนสำหรับการจัดการและดูแลเซิร์ฟเวอร์รายงาน Power BI และการควบคุม Report Viewer
services: powerbi
documentationcenter: ''
author: markingmyname
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
ms.date: 01/25/2018
ms.author: maghan
ms.openlocfilehash: 273a336280a371f694fb08a43d75e24535942e9a
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/30/2018
---
# <a name="browser-support-for-power-bi-report-server"></a>การสนับสนุนเบราว์เซอร์สำหรับเซิร์ฟเวอร์รายงาน Power BI
เรียนรู้เกี่ยวกับรุ่นเบราว์เซอร์ที่ได้รับการสนับสนุนสำหรับการจัดการและดูแลเซิร์ฟเวอร์รายงาน Power BI และการควบคุม Report Viewer

## <a name="browser-requirements-for-the-web-portal"></a>ข้อกำหนดของเบราว์เซอร์สำหรับพอร์ทัลเว็บ
ต่อไปนี้คือรายการปัจจุบันของเบราว์เซอร์ที่ได้รับการสนับสนุนสำหรับพอร์ทัลเว็บ

**Microsoft Windows**  
*Windows 7, 8.1, 10 Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple OS X**  
*OS X 10.9-10.11*

* Apple Safari (+)
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple iOS**  
*iPhone และ iPad ที่เป็น iOS 10*

* Apple Safari (+)

**Google Android**  
*โทรศัพท์และแท็บเล็ตระบบ Android 4.4 (KitKat) หรือรุ่นล่าสุด*

* Google Chrome (+)
  
  **(+)** รุ่นล่าสุดที่เผยแพร่สาธารณะ

## <a name="browser-requirements-for-the-report-viewer-web-control-2015"></a>ข้อกำหนดของเบราว์เซอร์สำหรับการควบคุมเว็บตัวแสดงรายงาน (2015)
ต่อไปนี้คือรายการปัจจุบันของเบราว์เซอร์ที่ได้รับการสนับสนุนด้วยการควบคุมเว็บตัวแสดงรายงาน ตัวแสดงรายงานสนับสนุนการดูรายงานจากพอร์ทัลเว็บ

**Microsoft Windows**  
*Windows 7, 8.1, 10 Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple OS X**  
*OS X 10.9-10.11*

* Apple Safari (+)
  
  **(+)** รุ่นล่าสุดที่เผยแพร่สาธารณะ

### <a name="authentication-requirements"></a>ข้อกำหนดการรับรองความถูกต้อง
เบราว์เซอร์ที่สนับสนุนแผนงานการรับรองความถูกต้องเฉพาะที่ต้องดำเนินการโดยเซิร์ฟเวอร์รายงานตามลำดับเพื่อให้คำขอของไคลเอ็นต์เสร็จสมบูรณ์ ตารางต่อไปนี้ระบุชนิดการรับรองความถูกต้องเริ่มต้นที่ได้รับการสนับสนุนโดยแต่ละเบราว์เซอร์ที่ใช้งานบนระบบปฏิบัติการ Windows

| **ชนิดของเบราว์เซอร์** | **การสนับสนุน** | **ค่าเริ่มต้นของเบราว์เซอร์** | **ค่าเริ่มต้นของเซิร์ฟเวอร์** |
| --- | --- | --- | --- |
| **Microsoft Edge** (+) |Negotiate, Kerberos, NTLM, Basic |Negotiate |ใช่ การตั้งค่าการรับรองความถูกต้องเริ่มต้นทำงานกับ Edge |
| **Microsoft Internet Explorer** |Negotiate, Kerberos, NTLM, Basic |Negotiate |ใช่ การตั้งค่าการรับรองความถูกต้องเริ่มต้นทำงานกับ Internet Explorer |
| **Google Chrome**(+) |Negotiate, NTLM, Basic |Negotiate |ใช่ การตั้งค่าการรับรองความถูกต้องเริ่มต้นทำงานกับ Chrome |
| **Mozilla Firefox**(+) |NTLM, Basic |NTLM |ใช่ การตั้งค่าการรับรองความถูกต้องเริ่มต้นทำงานกับ Firefox |
| **Apple Safari**(+) |NTLM, Basic |Basic |ใช่ การตั้งค่าการรับรองความถูกต้องเริ่มต้นทำงานกับ Safari |

 **(+)** รุ่นล่าสุดที่เผยแพร่สาธารณะ

### <a name="script-requirements-for-viewing-reports"></a>ข้อกำหนดของสคริปต์สำหรับการดูรายงาน
หากต้องการใช้ตัวแสดงรายงาน กำหนดค่าเบราว์เซอร์ของคุณเพื่อเรียกใช้สคริปต์

ถ้าไม่สามารถเปิดใช้งานสคริปต์ คุณจะเห็นข้อความแสดงข้อผิดพลาดที่คล้ายกับข้อความต่อไปนี้เมื่อคุณเปิดรายงาน:

```
Your browser does not support scripts or has been configured to not allow scripts to run. Click here to view this report without scripts
```

 ถ้าคุณเลือกที่จะดูรายงานโดยไม่มีการสนับสนุนสคริปต์ รายงานจะแสดงในรูปแบบ HTML ที่ไม่สามารถแสดงรายงานได้ เช่น แถบเครื่องมือรายงานและแผนผังเอกสาร

> [!NOTE]
> แถบเครื่องมือรายงานเป็นส่วนหนึ่งของส่วนประกอบตัวแสดง HTML ตามค่าเริ่มต้น แถบเครื่องมือจะปรากฏที่ด้านบนของทุกรายงานที่แสดงในหน้าต่างเบราว์เซอร์ ตัวแสดงรายงานมีคุณลักษณะต่างๆที่รวมไปถึงความสามารถในการค้นหารายงานสำหรับข้อมูล เลื่อนไปที่หน้าที่ระบุ และปรับขนาดหน้ากระดาษเพื่อดูวัตถุประสงค์ สำหรับข้อมูลเพิ่มเติมเกี่ยวกับแถบเครื่องมือรายงานหรือตัวแสดง HTML ดูที่[ตัวแสดง HTML และแถบเครื่องมือรายงาน](https://docs.microsoft.com/sql/reporting-services/html-viewer-and-the-report-toolbar)
> 
> 

## <a name="browser-support-for-report-viewer-web-server-controls-in-visual-studio"></a>การสนับสนุนเบราว์เซอร์สำหรับการควบคุมเซิร์ฟเวอร์เว็บตัวแสดงรายงานใน Visual Studio
การควบคุมเซิร์ฟเวอร์เว็บตัวแสดงรายงานถูกใช้เพื่อฝังฟังก์ชันการทำงานของรายงานในเว็บแอปพลิเคชัน ASP.NET สำหรับข้อมูลเพิ่มเติมเกี่ยวกับวิธีการรับตัวควบคุมตัวแสดงรายงาน ดูที่[บริการการรวมรายงานโดยใช้การควบคุมตัวแสดงรายการ - เริ่มต้นใช้งาน](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started)

ใช้เบราว์เซอร์ที่มีสคริปต์ที่สนับสนุนการเปิดใช้งาน ถ้าเบราว์เซอร์ไม่สามารถเรียกใช้สคริปต์ คุณจะไม่สามารถดูรายงานได้

**Microsoft Windows**  
*Windows 7, 8.1, 10 Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)
  
  **(+)** รุ่นล่าสุดที่เผยแพร่สาธารณะ

## <a name="next-steps"></a>ขั้นตอนถัดไป
[คู่มือผู้ดูแลระบบ](admin-handbook-overview.md)  
[เริ่มต้นใช้งานด่วน: ติดตั้งเซิร์ฟเวอร์รายงาน Power BI](quickstart-install-report-server.md)  
[ติดตั้งตัวสร้างรายงาน](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[ดาวน์โหลดเครื่องมือข้อมูลเซิร์ฟเวอร์ SQL (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

คุณมีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
