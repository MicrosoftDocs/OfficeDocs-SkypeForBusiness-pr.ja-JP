---
title: Lync Phone Edition 構成設定のコレクションの作成または変更
TOCTitle: Lync Phone Edition 構成設定のコレクションの作成または変更
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49886992
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Phone Edition 構成設定のコレクションの作成または変更

 

_**トピックの最終更新日:** 2013-02-23_

Lync Server をインストールすると、Lync Phone Edition の設定のグローバル コレクションが作成されます。これらの設定は、展開内の Lync Phone Edition を実行しているすべてのデバイスに適用されます。これらの設定はいつでも変更できます。また、特定のサイト内のデバイスに適用される新しい設定のコレクションを設定することもできます。サイト設定はグローバル設定よりも優先されます。

構成設定は、コレクション名、スコープ (グローバルまたはサイト)、SIP セキュリティ設定、ログ レベル、音声のサービス品質 (QoS) レベル、電話のロックの設定、および電話のロックの詳細 (暗証番号 (PIN) を解除する必要がある期間と、電話が自動的にロックされる前に電話がアイドル状態になる期間) で構成されます。

## Lync Phone Edition 構成設定のコレクションの作成または既存のコレクションの設定の編集を行うには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**デバイス構成**\] ナビゲーション ボタンをクリックします。

4.  \[**デバイス構成**\] ページで、次のいずれかを実行します。
    
      - Lync Phone Edition 構成設定の新しいコレクションを作成するには、\[**新規作成**\] をクリックし、サイトを選択して \[**OK**\] をクリックします。既定の設定を確認し、必要な場合は変更を加えます。
    
      - 既存のコレクションの設定を変更するには、コレクションをクリックし、\[**編集**\] メニューをクリックします。\[**詳細の表示**\] をクリックし、変更を行います。
        

        > [!TIP]
        > グローバル コレクションの既定の設定に戻すには、[<STRONG>編集</STRONG>] メニューをクリックして [<STRONG>削除</STRONG>] をクリックし、[<STRONG>OK</STRONG>] をクリックします。この操作では、グローバル コレクションが削除されるのではなく、設定が既定にリセットされるだけです。



5.  \[**コミット**\] をクリックします。

## Lync Server 管理シェル コマンドレットを使用して新しい Lync Phone Edition 構成設定を作成するには

Lync Server 管理シェルと **New-CsUCPhoneConfiguration** コマンドレットを使用して、Lync Phone Edition 構成設定を作成することもできます (サイト スコープの場合のみ)。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell. リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。 のリモート セッションから実行できます。

## 既定値を使用する新しい Lync Phone Edition 構成設定を作成するには

  - 次のコマンドでは、Redmond サイト用に UC 電話構成設定の新しいセットを作成します。
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    このコマンドでは (必須の Identity パラメーター以外の) パラメーターが指定されていないため、新しい構成設定のコレクションでは、すべてのプロパティに既定値が使用されます。

## 新しい Lync Phone Edition 構成設定の作成時に 1 つのプロパティ値を変更するには

  - 別のプロパティ値を使用する設定を作成するには、該当するパラメーターとパラメータ値を追加します。たとえば、既定で電話のロックを必要とする UC 電話構成設定のコレクションを作成するには、次のようなコマンドを使用します。
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

## 新しい Lync Phone Edition 構成設定の作成時に複数のプロパティ値を変更するには

  - 複数のパラメーターを含めることにより、複数のプロパティ値を変更できます。たとえば次のコマンドでは、電話のロックを適用し、さらに PIN の最小桁数を 8 桁に設定します。
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

詳細については、「[New-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsUCPhoneConfiguration)」を参照してください。

## 関連項目

#### タスク

[Lync Phone Edition 構成設定の既存コレクションの削除](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Lync Phone Edition のセキュリティ設定の構成](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[電話のロックの適用](lync-server-2013-enforce-phone-locking.md)

