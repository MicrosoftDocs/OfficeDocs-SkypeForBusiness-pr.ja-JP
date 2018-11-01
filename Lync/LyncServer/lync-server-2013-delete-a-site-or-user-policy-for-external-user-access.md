---
title: 'Lync Server 2013: 外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除'
TOCTitle: 外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48272457
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での外部ユーザー アクセスに関するサイト ポリシーまたはユーザー ポリシーの削除

 

_**トピックの最終更新日:** 2013-02-22_

Lync Server コントロール パネルの一覧のサイト ポリシーやユーザー ポリシーは、\[**外部アクセス ポリシー**\] ページで削除できます。グローバル ポリシーを削除すると、実際には削除されず、外部ユーザー アクセス オプションのサポートが含まれていない既定の設定にリセットされるだけです。グローバル ポリシーのリセットの詳細については、「[Lync Server 2013 での外部ユーザー アクセスに関するグローバル ポリシーのリセット](lync-server-2013-reset-the-global-policy-for-external-user-access.md)」を参照してください。

## 外部ユーザー アクセスのサイト ポリシーまたはユーザー ポリシーを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  \[**外部ユーザー アクセス**\] をクリックし、\[**外部アクセス ポリシー**\] をクリックします。

4.  \[**外部アクセス ポリシー**\] タブで、削除するサイト ポリシーまたはユーザー ポリシーをクリックして \[**編集**\] をクリックし、\[**削除**\] をクリックします。

5.  削除について確認するメッセージが表示されたら、\[**OK**\] をクリックします。

## Windows PowerShell コマンドレットを使用した PIN ポリシーの削除

外部アクセスポリシーは、Windows PowerShell と Remove-CsExternalAccessPolicy コマンドレットを使用して削除できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 特定の外部アクセス ポリシーを削除するには

  - 次のコマンドでは、Redmond サイトに適用されている外部アクセス ポリシーを削除します。
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

## ユーザーごとのスコープに適用されているすべての外部アクセス ポリシーを削除するには

  - 次のコマンドでは、ユーザーごとのスコープで構成されているすべての外部アクセス ポリシーを削除します。
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

## 外部ユーザー アクセスが無効になっているすべての外部アクセス ポリシーを削除するには

  - 次のコマンドでは、外部ユーザー アクセス ポリシーが無効になっているすべての外部アクセス ポリシーを削除します。
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

詳細は、[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) コマンドレットのヘルプ トピックを参照してください。

