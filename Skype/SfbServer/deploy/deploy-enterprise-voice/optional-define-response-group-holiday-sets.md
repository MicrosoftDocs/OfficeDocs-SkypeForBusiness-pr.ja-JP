---
title: (省略可能)Skype for Business での応答グループ休日セットの定義
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Skype for Business Server エンタープライズ VoIP で応答グループ休日セットを作成または変更します。
ms.openlocfilehash: dd3144c687329f82542d5b658c47212dd390c9fb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830987"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a>(省略可能)Skype for Business での応答グループ休日セットの定義
 
Skype for Business Server エンタープライズ VoIP で応答グループ休日セットを作成または変更します。
  
休日設定では、応答グループが営業しない日を定義し、その日に実行するアクションを指定します。休日セットは、応答グループに適用する休日のコレクションです。
  
> [!NOTE]
> ワークフローが管理ワークフローとして定義されている場合、CsResponseGroupManager の役割に割り当てられたユーザーは、管理するワークフローの休日を設定および変更できます。 
  
### <a name="to-create-a-holiday-set"></a>休日セットを作成するには

1. RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。
    
2. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
    
3. 定義する休日ごとに、以下を実行します。
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    定義した休日を含める休日セットを作成するには、以下を実行します。
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    次の例では、2 つの休日を含む休日セットを示します。
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>関連項目

[Skype for Business での応答グループ ワークフローの設計と作成](designing-and-creating-response-group-workflows.md)

[New-CsRgsHoliday](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[New-CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
