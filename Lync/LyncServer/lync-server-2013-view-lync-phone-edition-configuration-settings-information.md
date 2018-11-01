---
title: Lync Phone Edition 構成設定情報の表示
TOCTitle: Lync Phone Edition 構成設定情報の表示
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49886853
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Phone Edition 構成設定情報の表示

 

_**トピックの最終更新日:** 2013-02-23_

Lync Phone Edition を実行しているデバイスに関する構成情報を表示できます。情報はコレクションにまとめられています。Lync Server をインストールすると、展開内で Lync Phone Edition を実行しているすべてのデバイスに適用される、Lync Phone Edition 設定のコレクションが得られます。特定のサイトに対して、設定の新しいコレクションを作成することもできます。サイト設定は、グローバル設定より優先されます。設定の各コレクションは、名前、スコープ (グローバルまたはサイト)、SIP セキュリティ設定、ログ レベル、音声のサービス品質 (QoS) レベル、電話ロック設定、および電話ロックの詳細 (ロック解除の暗証番号 (PIN) の最小桁数および電話が自動ロックされるまでの時間) で構成されています。

## Lync Phone Edition を実行しているデバイスに関する構成情報を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**デバイスの構成**\] 移動ボタンをクリックします。

4.  \[**デバイスの構成**\] ページで、情報を表示する設定のコレクションをクリックします。名前、スコープ、SIP セキュリティ設定、音声の品質レベル、および電話ロック設定がメイン ページに表示されます。ログ レベルと電話ロックの詳細を表示するには、\[**編集**\] メニューをクリックし、\[**詳細の表示**\] をクリックします。

## Lync Server 管理シェル コマンドレットを使用して Lync Phone Edition の構成情報を表示するには

Lync Server 管理シェルと **Get-CsUCPhoneConfiguration** コマンドレットを使用して、Lync Phone Edition の構成情報を表示することもできます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## Lync Phone Edition の構成情報を表示するには

  - Lync Phone Edition のすべての構成設定について情報を表示するには、Lync Server 管理シェルで次のコマンドを入力して、Enter キーを押します。
    
        Get-CsUCPhoneConfiguration
    
    コマンドを実行すると、次のような情報が返されます。
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

詳細については、「[Get-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUCPhoneConfiguration)」を参照してください。

## 関連項目

#### タスク

[Lync Phone Edition 構成設定のコレクションの作成または変更](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Lync Phone Edition 構成設定の既存コレクションの削除](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Lync Phone Edition のセキュリティ設定の構成](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[電話のロックの適用](lync-server-2013-enforce-phone-locking.md)

