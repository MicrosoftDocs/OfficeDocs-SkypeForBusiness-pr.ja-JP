---
title: ダイヤルイン会議アクセス番号の削除
TOCTitle: ダイヤルイン会議アクセス番号の削除
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48271412
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ダイヤルイン会議アクセス番号の削除

 

_**トピックの最終更新日:** 2013-02-23_

ダイヤルイン会議アクセス番号を削除するには、次の手順を実行します。

## ダイヤルイン会議アクセス番号を削除するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**会議**\] をクリックし、\[**ダイヤルイン アクセス番号**\] をクリックします。

4.  \[ダイヤルイン アクセス番号\] ページの一覧で、削除するダイヤルイン番号をクリックし、\[**編集**\] をクリックして、\[**削除**\] をクリックします。

5.  \[**OK**\] をクリックします。

## Windows PowerShell コマンドレットを使用したダイヤルイン会議アクセス番号の削除

ダイヤルイン会議アクセス番号は、Windows PowerShell と **Remove-CsDialInConferencingAccessNumber** コマンドレットを使用して削除することもできます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 特定のダイヤルイン会議アクセス番号の削除

  - 次のコマンドは、ID が sip:RedmondDialInAccess@litwareinc.com であるダイヤルイン会議アクセス番号を削除します。
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

## 特定の地域に関連するすべてのダイヤルイン会議アクセス番号の削除

  - 次のコマンドは、Northwest 地域に関連するすべてのダイヤルイン会議アクセス番号を削除します。
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

## 第 1 言語に基づくダイヤルイン会議アクセス番号の削除

  - 次のコマンドは、第 1 言語がイタリア語であるすべてのダイヤルイン会議アクセス番号を削除します。
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

詳細については、[Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) コマンドレットのヘルプ トピックを参照してください。

