---
title: Lync Phone Edition のセキュリティ設定の構成
TOCTitle: Lync Phone Edition のセキュリティ設定の構成
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48272416
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Phone Edition のセキュリティ設定の構成

 

_**トピックの最終更新日:** 2013-02-23_

SIP セキュリティ設定と電話のロック設定により、Lync Phone Edition を実行しているデバイスのセキュリティを向上させることができます。

## Lync Phone Edition のセキュリティ設定を構成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**デバイス構成**\] をクリックします。

4.  \[**デバイス構成**\] ページのデバイス構成の一覧で、セキュリティ設定を変更する構成をダブルクリックします。

5.  \[**デバイス構成の編集**\] の \[**SIP セキュリティ**\] で、SIP セキュリティ レベルを指定します。既定のレベルは \[**高**\] (推奨される設定) です。

6.  \[**デバイス構成の編集**\] の \[**電話のロック**\] で、\[**デバイス ロックの適用**\] チェック ボックス (既定ではオン) をオンまたはオフにして、PIN の最小桁数 (既定では 6 桁) とタイムアウト期間 (既定では 10 分) を指定します。これらの既定値を使用するか、または PIN の桁数を大きくするかタイムアウト期間を小さくする (あるいはその両方を行う) ことをお勧めします。
    
    > [!NOTE]
    > 詳細については、「<a href="lync-server-2013-enforce-phone-locking.md">電話のロックの適用</a>」を参照してください。


## Lync Server 管理シェル コマンドレットを使用した Lync Phone Edition 電話のセキュリティ設定の構成

Lync Server 管理シェルと **Get-CsUCPhoneConfiguration** コマンドレットを使用してセキュリティ設定を管理することもできます。このコマンドレットは、Lync Server 2013 管理シェル から、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## SIP セキュリティ モードを変更するには

  - 次のコマンドでは、UC 電話設定のグローバル コレクションの SIPSecurityMode を Medium に設定します。SIP セキュリティは、Low または High (既定値) に設定することもできます。
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

## PIN の最小桁数を変更するには

  - 次の例では、すべての UC 電話設定で必要とされる PIN の最小桁数を 7 桁に変更します。
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

詳細については、「[Get-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUCPhoneConfiguration)」を参照してください。

## 関連項目

#### 概念

[Lync Server 2013 認証の管理](lync-server-2013-managing-lync-server-authentication.md)  

#### その他のリソース

[Lync Server 2013 でのデバイス、電話、クライアント アプリケーションの管理](lync-server-2013-managing-devices-phones-and-client-applications.md)

