---
title: 既存のレジストラー構成設定の削除
TOCTitle: 既存のレジストラー構成設定の削除
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48273263
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 既存のレジストラー構成設定の削除

 

_**トピックの最終更新日:** 2013-02-23_

レジストラーを削除するには、次の手順に従います。

## レジストラーを削除するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**セキュリティ**\] をクリックし、\[**レジストラー**\] をクリックします。

4.  \[**レジストラー**\] ページの検索フィールドに、削除するレジストラーの名前または名前の一部を入力します。

5.  一覧で、対象のレジストラーをクリックし、\[**編集**\] をクリックして、\[**削除**\] をクリックします。

6.  \[**OK**\] をクリックします。

## Lync Server 管理シェル コマンドレットを使用したレジストラー構成設定の削除

Lync Server 管理シェル と **Remove-CsProxyConfiguration** コマンドレットを使用してレジストラー構成設定を削除できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## レジストラーのセキュリティ設定の特定のセットを削除するには

  - 次のコマンドは、エッジ サーバー atl-edge-011.litwareinc.com に適用されるレジストラーのセキュリティ設定を削除します。
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

## サイト スコープに適用されるレジストラーのセキュリティ設定をすべて削除するには

  - 次のコマンドは、レジストラー サービスに適用されるすべてのレジストラーのセキュリティ設定を削除します。
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

## NTLM 認証を許可するレジストラーのセキュリティ設定をすべて削除するには

  - 次のコマンドは、クライアント認証に NTLM の使用を許可するレジストラーのセキュリティ設定をすべて削除します。
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

詳細については、「[Remove-CsProxyConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsProxyConfiguration)」を参照してください。

