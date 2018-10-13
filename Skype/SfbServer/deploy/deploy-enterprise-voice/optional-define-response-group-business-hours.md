---
title: (省略可能)ビジネス用の Skype を定義する応答グループの営業時間
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: 作成または応答グループのビジネス サーバーのエンタープライズ VoIP の Skype での営業時間を変更します。
ms.openlocfilehash: a5f24d218ab15cb1307f042363147c9e915a351e
ms.sourcegitcommit: 28e0e8043f418505039cd12407c927f454c141f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "25546807"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a>(省略可能)ビジネス用の Skype を定義する応答グループの営業時間 
 
作成または応答グループのビジネス サーバーのエンタープライズ VoIP の Skype での営業時間を変更します。
  
## <a name="defining-business-hours"></a>営業時間の定義

営業時間設定では、ワークフローが通話に応答できる時間を定義し、営業時間外の通話に対するアクションを指定します。 応答グループの管理者は、応答グループの任意の数に使用できる定義済みのスケジュールを作成するのに**新規 CsRgsHoursOfBusiness**コマンドレットを使用することができます。
  
> [!TIP]
> ワークフローを作成または変更するときに、そのワークフローのみに適用されるカスタム スケジュールを指定できます。 詳細については、[設計と応答のビジネス用の Skype でのグループのワークフローを作成する](designing-and-creating-response-group-workflows.md)を参照してください。 
  
> [!NOTE]
> ワークフローが管理ワークフローとして定義されている場合、CsResponseGroupManager の役割を割り当てられているすべてのユーザーは、管理するワークフローのカスタム営業時間を設定および変更できます。 
  
> [!IMPORTANT]
> 次のコマンドレットのパラメーターの時刻表記は、24 時間形式で入力する必要があります (例: 20:00 は午後 8:00 を表します)。 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>事前設定された営業時間コレクションを作成するには

1. RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. 定義する一意の時間の範囲ごとに、以下を実行します。
    
   ```
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    定義した範囲を使用する営業時間コレクションを作成するには、以下を実行します。
    
   ```
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    次の例では、平日の営業時間を午前 9:00 から午後 5:00 に、土曜日の営業時間を午前 8:00 から午前 10:00 と午後 2:00 から午後 6:00 に、日曜日は営業時間なしに指定します。
    
   ```
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>関連項目

[新しい-CsRgsTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[新しい-CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
