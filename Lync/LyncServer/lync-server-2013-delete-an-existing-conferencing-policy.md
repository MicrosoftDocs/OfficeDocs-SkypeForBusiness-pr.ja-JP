---
title: 既存の会議ポリシーの削除
TOCTitle: 既存の会議ポリシーの削除
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49886996
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 既存の会議ポリシーの削除

 

_**トピックの最終更新日:** 2013-02-23_

ユーザーレベルまたはサイトレベルの電話会議ポリシーを削除するには、次の手順を実行します。

> [!NOTE]
> グローバル電話会議ポリシーを削除することはできません。


## サイトまたはユーザーの電話会議ポリシーを削除するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**会議**\] をクリックし、\[**電話会議ポリシー**\] をクリックします。

4.  電話会議ポリシーのリストで、削除するサイト ポリシーまたはユーザー ポリシーをクリックし、\[編集\] をクリックして、\[削除\] をクリックします。

## Lync Server 管理シェル コマンドレットを使用した電話会議ポリシーの削除

Lync Server 管理シェルおよび **Remove-CsConferencingPolicy** コマンドレットを使用して、トランク構成設定を削除することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 指定した電話会議ポリシーを削除するには

  - 次のコマンドは、ID RedmondConferencingPolicy を持つ電話会議ポリシーを削除します。
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

## ユーザーごとのスコープに適用されているすべての電話会議ポリシーを削除するには

  - 次のコマンドは、ユーザーごとのスコープで構成されているすべての電話会議ポリシーを削除します。
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

## 外部ユーザーによる記録を許可するすべての電話会議ポリシーを削除するには

  - 次のコマンドは、外部ユーザーに会議の記録を許可するすべての電話会議ポリシーを削除します。
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

詳細については、「[Remove-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsConferencingPolicy)」を参照してください。

