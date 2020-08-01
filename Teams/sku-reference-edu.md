---
title: エデュケーション SKU リファレンス
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: karsmith
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 教育教員および Student のライセンスプランと SKU Id を一覧表示します。
f1keywords: ''
ms.openlocfilehash: 921ea3313709fc16b415915b444e416527076251
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533894"
---
# <a name="education-sku-reference"></a>エデュケーション SKU リファレンス

この記事では、組織内のユーザーをライセンスの種類別に識別するために PowerShell を使用する場合に参照として使用できる、教育教職員と学生向けのライセンス計画 (Sku) と SKU Id の一覧を示します。

## <a name="faculty-licenses"></a>教職員向けライセンス

|プラン名 |SkuPartNumber   |SkuID |
|---------|---------|---------|
|Office 365 教育 E3 (教職員向け)     |ENTERPRISEPACK_FACULTY         |e4fa3838-3d01-42df-aa28-5e0a4c68604b         |
|Office 365 エデュケーション (教職員向け)       |STANDARDWOFFPACK_FACULTY        |94763226-9b3c-4e75-a931-5c89701abe66         |
|Office 365 エデュケーション (教職員向け)       |STANDARDWOFFPACK_IW_FACULTY     |78e66a63-337a6a9a4-89594-1c6654dfb56         |
|Office 365 エデュケーション E5 for Faculty    |ENTERPRISEPREMIUM_FACULTY       |a4585165-0533-458a-97e3-c400570268c4         |
|教職員用の PSTN 会議がない Office 365 エデュケーション E5      |ENTERPRISEPREMIUM_NOPSTNCONF_FACULTY         |9a320620-ca3d-4705-a79d-27c135c96e05         |
|Office 365 教育機関 (教職員向け)     |STANDARDPACK_FACULTY         |a19037fc-48b4-4d57-b079-ce44b7832473         |
|Office 365 教育 E3 (教職員向け)     |ENTERPRISEPACK_EDULRG         |f5a9147f-b4f8-4924-a9f0-8fadaac4982f         |
|Office 365 エデュケーション E4 for Faculty      |ENTERPRISEWITHSCAL_FACULTY         |16732e85-c0e3-438e-a82f-71f39cbe2acb         |
|Microsoft 365 エデュケーション A3 for Faculty      |M365EDU_A3_FACULTY         |4b590615-0888-425a-a965-b3bf7789848d         |
|Microsoft 365 エデュケーション A5 for Faculty       |M365EDU_A5_FACULTY         |e97c048c-37a4-45fb-ab50-922fbf07a370         |
|Microsoft 365 A5 (教員用電話会議なし)     |M365EDU_A5_NOPSTNCONF_FACULTY         |e578b273-6db4-4691-bba0-8d691f4da603         |
|Office 365 エデュケーション for Homeschool for Faculty     |STANDARDWOFFPACK_HOMESCHOOL_FAC         |43e691ad-1491-4e8c-8dc9-da6b8262c03b         |
|Office 365 A1 for Faculty (デバイス用)     |STANDARDWOFFPACK_FACULTY_DEVICE         |af4e28de-6b52-4fd3-a5f4-6bf708a304d3         |

## <a name="student-licenses"></a>学生ライセンス

|製品名 |SkuPartNumber   |SkuID |
|---------|---------|---------|
|Office 365 教育 E3 (学生向け)       |ENTERPRISEPACK_STUDENT         |8fc2205d49 e51-4401-97f0-5 c89ef1aafbb         |
|Office 365 エデュケーション (学生向け)     |STANDARDWOFFPACK_IW_STUDENT         |314c4481-f395-4525-be8b-2ec4bb1e9d91         |
|学生向け Office 365 教育 E5      |ENTERPRISEPREMIUM_STUDENT         |ee656612-49fa-43e5-b67e-cb1fdf7699df         |
|学生用の PSTN 会議がない Office 365 エデュケーション E5     |ENTERPRISEPREMIUM_NOPSTNCONF_STUDENT         |1164451b-e2e5-4c9e-8fa6-e5122d90dbdc         |
|Office 365 教育機関 (学生向け)       |STANDARDPACK_STUDENT         |d37ba356-38c5-4c82-90da-3d714f72a382         |
|Office 365 エデュケーション E4 (学生向け)      |ENTERPRISEWITHSCAL_STUDENT         |05e8cabf-68b5-480f-a930-2143d472d959         |
|Microsoft 365 エデュケーション A3 for Students      |M365EDU_A3_STUDENT         |7cfd9a2b7b e11047 c39a3f20-c6a3f36a3121         |
|Microsoft 365 エデュケーション A3 学生向け特典       |M365EDU_A3_STUUSEBNFT         |18250162-5d87 4-43607 a834-d195c15c80f3         |
|学生用 Microsoft 365 教育用 A5        |M365EDU_A5_STUDENT       |46c119d4-0379 44 a9d3f9066d3f909e        |
|Microsoft 365 A5 Student use 特典     |M365EDU_A5_STUUSEBNFT         |31d57bc7-3a05-4867-ab53-97a17835a411         |
|Microsoft 365 A5 (学生の電話会議なし)      |M365EDU_A5_NOPSTNCONF_STUDENT         |a25c01ce-bab1-47e9-a6d0-ebe939b99ff9         |
|学生用の電話会議がない Microsoft 365 A5 の利点    |M365EDU_A5_NOPSTNCONF_STUUSEBNFT         |81441ae1-0b31-4185-a6c0-32b6b84d419f         |
|Office 365 A3 for Students     |ENTERPRISEPACKPLUS_STUDENT         |98b6e77 3-24d44-c・・・・8-6e787a1f8204         |
|Office 365 A3 Student use 特典     |ENTERPRISEPACKPLUS_STUUSEBNFT         |476aad1e-7a7f-473c-9d20-35665a5cbd4f         |
|Office 365 A5 Student の使用に関する利点    |ENTERPRISEPREMIUM_STUUSEBNFT         |f6e603f1-1a6d-4d32-a730-34b809cb9731         |
|学生用電話会議なしの Office 365 A5 には特典が利用できる  |ENTERPRISEPREMIUM_NOPSTNCONF_STUUSEBNFT         |bc86c9cd-3058-43ba-9972-141678675ac1         |
|学生向けの Office 365 エデュケーション Homeschool     |STANDARDWOFFPACK_HOMESCHOOL_STU         |afbb89a7-db5f-45fb-8af0-1bc5c5015709         |
|Office 365 A1 for Students (デバイス用)     |STANDARDWOFFPACK_STUDENT_DEVICE         |160d609e-ab08-4fce-bc1c-ea13321942ac         |
|学生用の Office 365 A1 Plus     |STANDARDWOFFPACK_IW_STUDENT         |e82ae690-a2d5-4d76-8d30-7c6e01e6022e         |

## <a name="related-topics"></a>関連項目

- [学校の大規模なユーザーセットにポリシーを割り当てる](batch-group-policy-assignment-edu.md)
