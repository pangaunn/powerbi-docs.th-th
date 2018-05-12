---
title: ส่งข้อมูลลงในชุดข้อมูล
description: ส่งข้อมูลลงในชุดข้อมูล Power BI
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
ms.date: 01/05/2017
ms.author: maghan
ms.openlocfilehash: 8cebd6d7020a997fa9f49cd1f5618232a299bb4f
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/30/2018
---
# <a name="push-data-into-a-power-bi-dataset"></a>ส่งข้อมูลลงในชุดข้อมูล Power BI
โดยใช้ Power BI API คุณสามารถส่งข้อมูลลงในชุดข้อมูล Power BI ตัวอย่างเช่น คุณต้องการขยายลำดับงานทางธุรกิจที่มีอยู่ในการส่งข้อมูลที่สำคัญลงในชุดข้อมูลของคุณ ในกรณีนี้ คุณต้องการส่งชุดข้อมูลการตลาดและการขายซึ่งมีตารางผลิตภัณฑ์อยู่ลงในชุดข้อมูล

ก่อนที่คุณเริ่มต้นใช้งานส่งข้อมูลลงในชุดข้อมูล คุณจำเป็นต้องมี Azure Active Directory (Azure AD) และ[บัญชี Power BI](create-an-azure-active-directory-tenant.md)

## <a name="steps-to-push-data-into-a-dataset"></a>ขั้นตอนการส่งข้อมูลลงในชุดข้อมูล
* ขั้นตอนที่ 1: [ลงทะเบียนแอปกับ Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)
* ขั้นตอนที่ 2: [รับโทเค็นการเข้าถึงการรับรองความถูกต้อง ](walkthrough-push-data-get-token.md)
* ขั้นตอนที่ 3:[สร้างชุดข้อมูลใน Power BI](walkthrough-push-data-create-dataset.md)
* ขั้นตอนที่ 4:[รับชุดข้อมูลเพื่อเพิ่มแถวลงในตาราง Power BI](walkthrough-push-data-get-datasets.md)
* ขั้นตอนที่ 5:[เพิ่มแถวลงในตาราง Power BI](walkthrough-push-data-add-rows.md)

ในส่วนถัดไปคือการสนทนาทั่วไปของการดำเนินการ Power BI API ที่ส่งข้อมูล

## <a name="power-bi-api-operations-to-push-data"></a>การดำเนินการของ BI API power เพื่อส่งข้อมูล
คุณสามารถส่งแหล่งข้อมูลไปยัง Power BI ได้โดยใช้ Power BI REST API เมื่อแอปเพิ่มแถวไปยังชุดข้อมูล ไทล์บนแดชบอร์ดจะได้รับการอัปเดตโดยอัตโนมัติด้วยข้อมูลที่อัปเดตแล้ว เมื่อต้องส่งข้อมูล ให้คุณใช้การดำเนินการ[สร้างชุดข้อมูล](https://msdn.microsoft.com/library/mt203562.aspx)พร้อมกับการ[ดำเนินการ](https://msdn.microsoft.com/library/mt203561.aspx)เพิ่มแถว เมื่อต้องการค้นหาชุดข้อมูล ให้คุณใช้การ[ดำเนินการ](https://msdn.microsoft.com/library/mt203567.aspx)รับชุดข้อมูล คุณสามารถส่งรหัสของกลุ่มเพื่อทำงานกับกลุ่มได้จากการดำเนินการเหล่านี้ ใช้การ[ดำเนินการ](https://msdn.microsoft.com/library/mt243842.aspx)รับกลุ่มเพื่อรับรายการของรหัสกลุ่ม

ต่อไปนี้เป็นการดำเนินการเพื่อส่งข้อมูลลงในชุดข้อมูล:

* [สร้างชุดข้อมูล](https://msdn.microsoft.com/library/mt203562.aspx)
* [รับชุดข้อมูล](https://msdn.microsoft.com/library/mt203567.aspx)
* [เพิ่มแถว](https://msdn.microsoft.com/library/mt203561.aspx)
* [รับกลุ่ม](https://msdn.microsoft.com/library/mt243842.aspx)

คุณสามารถสร้างชุดข้อมูลใน Power BI ได้โดยการส่งสตริง JavaScript Object Notation (JSON) ไปยังบริการ Power BI เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับ JSON ดู[การแนะนำ JSON](http://json.org/)

สตริง JSON สำหรับชุดข้อมูลที่มีรูปแบบต่อไปนี้:

**Power BI ชุดข้อมูล JSON วัตถุ**

    {"name": "dataset_name", "tables":
        [{"name": "", "columns":
            [{ "name": "column_name1", "dataType": "data_type"},
             { "name": "column_name2", "dataType": "data_type"},
             { ... }
            ]
          }
        ]
    }

สำหรับตัวอย่างชุดข้อมูลการขายและการตลาดของเรา คุณจะผ่านสตริง JSON เช่นตัวอย่างด้านล่าง ในตัวอย่างนี้**การขายและการตลาด**คือชื่อของชุดข้อมูล และ**ผลิตภัณฑ์**คือชื่อของตาราง หลังจากที่คุณกำหนดตาราง จากนั้นกำหนดสคีของตาราง สำหรับ**ชุดข้อมูลการขายและการตลาด**และสคีของตารางมีคอลัมน์เหล่านี้: รหัสผลิตภัณฑ์ ผู้ผลิต ประเภท ส่วน ผลิตภัณฑ์ และ เสร็จสมบูรณ์

**ตัวอย่างชุดข้อมูลวัตถุ JSON**

    {
        "name": "SalesMarketing",
        "tables": [
            {
                "name": "Product",
                "columns": [
                {
                    "name": "ProductID",
                    "dataType": "int"
                },
                {
                    "name": "Manufacturer",
                    "dataType": "string"
                },
                {
                    "name": "Category",
                    "dataType": "string"
                },
                {
                    "name": "Segment",
                    "dataType": "string"
                },
                {
                    "name": "Product",
                    "dataType": "string"
                },
                {
                    "name": "IsCompete",
                    "dataType": "bool"
                }
                ]
            }
        ]
    }

คุณสามารถใช้ชนิดข้อมูลต่อไปนี้สำหรับสคีของตาราง Power BI

## <a name="power-bi-table-data-types"></a>ชนิดข้อมูลตาราง Power BI
| **ชนิดข้อมูล** | **ข้อจำกัด** |
| --- | --- |
| Int64 |Int64.MaxValue และ Int64.MinValue ไม่ได้รับอนุญาต |
| สองครั้ง |Double.MaxValue และค่า Double.MinValue ไม่ได้รับอนุญาต NaN ที่ไม่ได้รับการสนับสนุน + ค่าอนันต์และ - ค่าอนันต์ที่ไม่ได้รับการสนับสนุนในบางฟังก์ชัน (เช่น Min, Max) |
| บูลีน |ไม่มี |
| วันที่เวลา |ในระหว่างการโหลดข้อมูล เราแบ่งนับค่าด้วยเศษส่วนวันให้กับตัวคูณทั้งหมดของ 1/300 วินาที (3.33ms) |
| สตริง |อนุญาตให้มีอักขระได้ถึง 128K อักขระในขณะนี้ |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>เรียนรู้เพิ่มเติมเกี่ยวกับการส่งข้อมูลลงใน Power BI
เมื่อต้องการเริ่มต้นใช้งานการส่งข้อมูลลงในชุดข้อมูล ดู[ขั้นตอนที่ 1: ลงทะเบียนแอปกับ Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)ในบานหน้าต่างนำทางด้านซ้าย

[ขั้นตอนถัดไป >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[ลงทะเบียนใช้งาน Power BI](create-an-azure-active-directory-tenant.md)  
[สร้างชุดข้อมูล](https://msdn.microsoft.com/library/mt203562.aspx)  
[รับชุดข้อมูล](https://msdn.microsoft.com/library/mt203567.aspx)  
[เพิ่มแถว](https://msdn.microsoft.com/library/mt203561.aspx)  
[รับกลุ่ม](https://msdn.microsoft.com/library/mt243842.aspx)  
[การแนะนำ JSON](http://json.org/)  
[ภาพรวมของ Power BI REST API](overview-of-power-bi-rest-api.md)  
คุณมีคำถามเพิ่มเติมหรือไม่ [ ลองเข้าร่วมกับชุมชน Power BI ](http://community.powerbi.com/)
