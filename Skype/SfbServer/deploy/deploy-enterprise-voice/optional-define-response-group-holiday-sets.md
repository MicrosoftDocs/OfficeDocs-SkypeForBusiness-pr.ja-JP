---
title: (オプション) Skype for Business 2015 での応答グループ休日セットの定義
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: 作成またはビジネス サーバーのエンタープライズ VoIP の Skype での応答グループ休日セットを変更します。
ms.openlocfilehash: b176a90b11957128fe485cd608608798d6ff6365
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business-2015"></a>(オプション) Skype for Business 2015 での応答グループ休日セットの定義
 
作成またはビジネス サーバーのエンタープライズ VoIP の Skype での応答グループ休日セットを変更します。
  
休日設定では、応答グループが営業しない日を定義し、その日に実行するアクションを指定します。休日セットは、応答グループに適用する休日のコレクションです。
  
> [!NOTE]
> ワークフローが管理ワークフローとして定義されている場合、CsResponseGroupManager の役割に割り当てられたユーザーは、管理するワークフローの休日を設定および変更できます。 
  
### <a name="to-create-a-holiday-set"></a>休日セットを作成するには

1. RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. 定義する休日ごとに、次のコマンドを実行します。
    
   ```
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    定義した休日を含める休日セットを作成するには、次のコマンドを実行します。
    
   ```
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    次の例では、2 つの休日を含む休日セットを示します。
    
   ```
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>関連項目

#### 

[設計とビジネス 2015年の Skype で応答グループ ワークフローを作成します。](designing-and-creating-response-group-workflows.md)
#### 

[新しい-CsRgsHoliday](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)
  
[新しい-CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)

