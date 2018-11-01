---
title: (オプション) 応答グループ休日セットの定義
TOCTitle: (オプション) 応答グループ休日セットの定義
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49886961
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (オプション) 応答グループ休日セットの定義

 

_**トピックの最終更新日:** 2014-02-07_

休日設定では、応答グループが営業しない日を定義し、その日に実行するアクションを指定します。休日セットは、応答グループに適用する休日のコレクションです。

> [!NOTE]
> ワークフローが管理ワークフローとして定義されている場合、CsResponseGroupManager の役割に割り当てられたユーザーは、管理するワークフローの休日を設定および変更できます。


## 休日セットを作成するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  定義する休日ごとに、次のコマンドを実行します。
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    定義した休日を含める休日セットを作成するには、次のコマンドを実行します。
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    次の例では、2 つの休日を含む休日セットを示します。
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

## 関連項目

#### 概念

[Lync Server 2013 でのハント グループ ワークフローの作成または変更](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Lync Server 2013 での対話ワークフローの作成または変更](lync-server-2013-create-or-modify-an-interactive-workflow.md)  

#### その他のリソース

[New-CsRgsHoliday](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsHoliday)  
[New-CsRgsHolidaySet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsHolidaySet)

