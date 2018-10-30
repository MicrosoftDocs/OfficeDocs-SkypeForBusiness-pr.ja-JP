---
title: 電話のロックの適用
TOCTitle: 電話のロックの適用
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48271539
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 電話のロックの適用

 

_**トピックの最終更新日:** 2013-02-23_

セキュリティ上の理由から、Lync Phone Edition デバイスをロックすることができます。電話ロックを適用した場合、構成した期間が経過した後に、Lync Phone Edition を実行するデバイスがロックされます。電話がロックされると、ユーザーは電話をかけることはできますが、予定表と連絡先情報、ボイス メール、または通話ログにアクセスしたり、検索を使用したりできません。電話ロックを解除するには、ユーザーは PIN を入力する必要があります。

電話ロックを適用するには、Lync Server コントロール パネルまたは Lync Server PowerShell コマンドレットを使用して電話ロックの有効化と構成を行う必要があります。電話ロックはグローバルに適用するか、電話ロックの対象として構成されたサイト内でのみ適用できます。

## 電話ロックを構成して適用するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  \[**クライアント**\] をクリックして、\[**デバイス構成**\] をクリックします。

4.  \[**デバイス構成**\] タブのデバイス構成のリストで、電話ロックの設定値を変更する構成をダブルクリックします。

5.  \[**デバイス構成の編集**\] ダイアログ ボックスで、\[**デバイス ロックを適用する**\] チェック ボックスがオンになっていることを確認します。

6.  \[**最小 PIN サイズ**\] で、ロック解除 PIN に含める必要がある最小桁数の既定値を受け入れるか、新しい値を指定します。PIN の桁数の範囲は、4 ～ 15 桁であり、既定は 6 です。

7.  \[**電話ロック タイムアウト**\] で、電話が自動ロックされるまでの最短時間の既定値を受け入れるか、新しい値を指定します。タイムアウト値の範囲は 0 ～ 60 分であり、既定は 10 です。値は、HH:MM:SS の形式で入力します。

8.  \[**確定**\] をクリックします。

## Windows PowerShell コマンドレットによる電話ロックの適用

Set-CsUCPhoneConfiguration コマンドレットを使用して、電話ロックを適用できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 電話ロックを有効にするには

  - 次のコマンドは、Redmond サイトの電話ロックを有効にします。電話ロックを無効にするには、EnforcePhoneLock プロパティを False ($False) に設定します。
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

## 電話ロックを有効にして、電話ロックのタイムアウトを変更するには

  - 次のコマンドは、電話ロックを有効にして、電話ロックのタイムアウトを 30 分に設定します。
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

## 組織全体で電話ロックを有効にするには

  - 次の例では、組織で使用されているすべての UC 電話構成設定で、電話ロックが有効になります。
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

詳細については、[Set-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUCPhoneConfiguration) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### 概念

[Lync Server 2013 認証の管理](lync-server-2013-managing-lync-server-authentication.md)  

#### その他のリソース

[Lync Server 2013 でのデバイス、電話、クライアント アプリケーションの管理](lync-server-2013-managing-devices-phones-and-client-applications.md)

