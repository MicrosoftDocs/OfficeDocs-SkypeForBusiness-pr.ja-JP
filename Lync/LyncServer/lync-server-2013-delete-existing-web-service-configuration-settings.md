---
title: 既存の Web サービス構成設定の削除
TOCTitle: 既存の Web サービス構成設定の削除
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48273509
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 既存の Web サービス構成設定の削除

 

_**トピックの最終更新日:** 2013-02-23_

Web サービス ポリシーを削除するには、次の手順を実行します。

## Web サービス ポリシーを削除するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**セキュリティ**\] をクリックし、\[**Web サービス**\] をクリックします。

4.  \[**Web サービス**\] ページの検索フィールドに、削除するポリシーの名前または名前の一部を入力します。

5.  ポリシーのリストで対象のポリシーをクリックし、\[**編集**\] をクリックして、\[**削除**\] をクリックします。

6.  \[**OK**\] をクリックします。

## Lync Server 管理シェル コマンドレットを使用して新しい Web サービス構成設定を削除する

Lync Server 管理シェル と **Remove-CsWebServiceConfiguration** コマンドレットを使用して、Web サービス構成設定を削除することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## Web サービス構成設定の特定のコレクションを削除するには

  - 次のコマンドを実行すると、レドモンド サイトに適用されている Web サービス セキュリティ設定が削除されます。
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

## サイト スコープに適用されているすべての Web サービス構成設定を削除するには

  - 次のコマンドを実行すると、サービス スコープに適用されているすべての Web サービス セキュリティ設定が削除されます。
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

## 証明書認証を許可しているすべての Web サービス構成設定を削除するには

  - 次のコマンドを実行すると、証明書認証の使用を許可しているすべての Web サービス セキュリティ設定が削除されます。
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

詳細については、「[Remove-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsWebServiceConfiguration)」を参照してください。

## 関連項目

#### その他のリソース

[セキュリティの構成](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)

