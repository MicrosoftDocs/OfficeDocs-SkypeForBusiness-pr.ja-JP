---
title: 'Lync Server 2013: 外部ユーザー アクセスに関するグローバル ポリシーのリセット'
TOCTitle: 外部ユーザー アクセスに関するグローバル ポリシーのリセット
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48272723
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での外部ユーザー アクセスに関するグローバル ポリシーのリセット

 

_**トピックの最終更新日:** 2013-02-22_

グローバル ポリシーを完全に削除することはできません。グローバル ポリシーに対して \[**削除**\] オプションを使用すると、外部ユーザー アクセス オプションのサポートが含まれていない既定の設定に、グローバル ポリシーがリセットされるだけです。

## グローバル ポリシーを既定の設定にリセットするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**外部ユーザー アクセス**\] をクリックし、\[**外部アクセス ポリシー**\] をクリックします。

4.  \[**外部アクセス ポリシー**\] タブでグローバル ポリシーをクリックし、\[**編集**\] をクリックして、\[**削除**\] をクリックします。

5.  削除について確認するメッセージが表示されたら、\[**OK**\] をクリックします。ページの先頭に、グローバル ポリシーがリセットされたことを知らせるメッセージが表示されます。

## Windows PowerShell コマンドレットを使用したグローバル外部アクセス ポリシーのリセット

グローバル外部アクセス ポリシーは、Windows PowerShell および Remove-CsExternalAccessPolicy コマンドレットを使用してリセットできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## グローバル外部アクセス ポリシーをリセットするには

  - 次のコマンドは、グローバル外部アクセス ポリシーをリセットします。
    
        Remove-CsExternalAccessPolicy -Identity "global"

詳細については、[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) コマンドレットのヘルプ トピックを参照してください。

