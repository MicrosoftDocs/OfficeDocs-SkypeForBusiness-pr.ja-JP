---
title: PIN ポリシーの削除
TOCTitle: PIN ポリシーの削除
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48272634
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# PIN ポリシーの削除

 

_**トピックの最終更新日:** 2013-02-23_

暗証番号 (PIN) ポリシーを削除するには、次の手順を実行します。

> [!NOTE]
> グローバル PIN ポリシーを削除することはできません。


## Lync Server 2013 コントロール パネルで PIN ポリシーを削除するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**セキュリティ**\] をクリックし、\[**PIN ポリシー**\] をクリックします。

4.  \[**PIN ポリシー**\] ページの検索フィールドにで、削除するポリシーの名前または名前の一部を入力します。

5.  ポリシーのリストで対象のポリシーをクリックし、\[**編集**\] をクリックして、\[**削除**\] をクリックします。

6.  \[**OK**\] をクリックします。

## Lync Server 管理シェルとコマンドレットを使用した PIN ポリシーの削除

Windows PowerShell と Remove-CsPinPolicy コマンドレットを使用して、PIN ポリシーを削除できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 特定の PIN ポリシーの削除

  - 次のコマンドは、Identity が RedmondPinPolicy の PIN ポリシーを削除します。
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

## サイト スコープに適用されるすべての PIN ポリシーの削除

  - 次のコマンドは、サイト スコープで構成されたすべての PIN ポリシーを削除します。
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

## 共通パターンの使用を許可するすべての PIN ポリシーの削除

  - 次のコマンドは、共通パターン G の使用を許可するすべての PIN ポリシーを削除します。
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

詳細については、[Remove-CsPinPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsPinPolicy) コマンドレットのヘルプ トピックを参照してください。

