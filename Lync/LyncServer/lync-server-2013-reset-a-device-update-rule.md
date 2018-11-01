---
title: デバイス更新ルールのリセット
TOCTitle: デバイス更新ルールのリセット
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994069(v=OCS.15)
ms:contentKeyID: 52056710
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# デバイス更新ルールのリセット

 

_**トピックの最終更新日:** 2013-02-23_

テスト デバイス上で更新プログラムが動作する仕組みを使用しない場合は、デバイス更新ルールをリセットすることができます。これにより、ルールの保留状態が削除され、テスト デバイスから更新プログラムがアンインストールされます。

Lync Server コントロール パネルまたは Windows PowerShell を使用して、デバイス更新ルールを削除できます。

> [!NOTE]
> 承認した (つまりロールアウトした) ルールをアンインストールするには、そのルールを復元します。詳細については、「<a href="lync-server-2013-restore-a-device-update-rule.md">デバイス更新ルールの復元</a>」を参照してください。


## Lync Server コントロール パネルを使用してデバイス更新ルールをリセットするには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**デバイスの更新**\] ナビゲーション ボタンをクリックします。

4.  \[**デバイスの更新**\] ページで、次のいずれかの操作を行います。
    
      - 1 つのルールをリセットするには、リセットするルールを選択します。
    
      - すべてのルールをリセットするには、\[**編集**\] メニュー、\[**すべて選択**\] の順にクリックします。
    
      - 1 つのブランドのルールをすべてリセットするには、\[**ブランド**\] 列メニューを使用します。

5.  \[**操作**\] をクリックし、\[**保留中の更新の取り消し**\] をクリックします。
    

    > [!TIP]
    > 取り消したデバイス更新ルールを今後ロールアウトしないことが確実である場合は、それらを削除することもできます。詳細については、「<A href="lync-server-2013-remove-a-device-update-rule.md">デバイス更新ルールの削除</A>」を参照してください。



## Windows PowerShell コマンドレットを使用してデバイス更新ルールをリセットする

デバイス更新ルールは、Windows PowerShell と **Reset-CsDeviceUpdateRule** コマンドレットを使用してリセットすることもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。

> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 (<a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>) を参照してください。


## サーバー上の特定のデバイス更新ルールをリセットするには

  - 以下のコマンドは、Web サーバー atl-cs-001.litwareinc.com 上のデバイス更新ルール d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 をリセットします。
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

## サーバー上のすべてのデバイス更新ルールをリセットするには

  - 以下のコマンドは、Web サーバー atl-cs-001.litwareinc.com 上のすべてのデバイス更新ルールをリセットします。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

## 特定のブランドを持つデバイス更新ルールをすべてリセットするには

  - この例では、Microsoft と同等のブランドを持つ組織全体のデバイス更新ルールがすべてリセットされます。
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

詳細については、[Reset-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Reset-CsDeviceUpdateRule) コマンドレットに関するヘルプ トピックを参照してください。

## 関連項目

#### タスク

[デバイス更新プログラム ルールを承認する](lync-server-2013-approve-a-device-update-rule.md)

