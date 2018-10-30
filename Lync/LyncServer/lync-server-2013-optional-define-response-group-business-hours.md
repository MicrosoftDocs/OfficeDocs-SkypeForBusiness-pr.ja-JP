---
title: 'Lync Server 2013: (オプション) 応答グループの営業時間の定義'
TOCTitle: (オプション) 応答グループの営業時間の定義
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205291(v=OCS.15)
ms:contentKeyID: 48273704
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (オプション) Lync Server 2013 での応答グループの営業時間の定義

 

_**トピックの最終更新日:** 2012-11-01_

## 営業時間の定義

営業時間設定では、ワークフローが通話に応答できる時間を定義し、営業時間外の通話に対するアクションを指定します。応答グループ管理者は、 **New-CsRgsHoursOfBusiness** コマンドレットを使用して、使用できる応答グループの数に制限がない事前設定スケジュールを作成できます。


> [!TIP]
> ワークフローを作成または変更するときに、そのワークフローのみに適用されるカスタム スケジュールを指定できます。詳細については、「<A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Lync Server 2013 でのハント グループ ワークフローの作成または変更</A>」および「<A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">Lync Server 2013 での対話ワークフローの作成または変更</A>」を参照してください。


> [!NOTE]
> ワークフローが管理ワークフローとして定義されている場合、CsResponseGroupManager の役割を割り当てられているすべてのユーザーは、管理するワークフローのカスタム営業時間を設定および変更できます。



> [!IMPORTANT]
> 次のコマンドレットのパラメーターの時刻表記は、24 時間形式で入力する必要があります (例: 20:00 は午後 8:00 を表します)。



## 事前設定された営業時間コレクションを作成するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  定義する一意の時間の範囲ごとに、以下を実行します。
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    定義した範囲を使用する営業時間コレクションを作成するには、以下を実行します。
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    次の例では、平日の営業時間を午前 9:00 から午後 5:00 に、土曜日の営業時間を午前 8:00 から午前 10:00 と午後 2:00 から午後 6:00 に、日曜日は営業時間なしに指定します。
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

## 関連項目

#### 概念

[Lync Server 2013 でのハント グループ ワークフローの作成または変更](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Lync Server 2013 での対話ワークフローの作成または変更](lync-server-2013-create-or-modify-an-interactive-workflow.md)  

#### その他のリソース

[New-CsRgsTimeRange](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsTimeRange)  
[New-CsRgsHoursOfBusiness](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsHoursOfBusiness)

