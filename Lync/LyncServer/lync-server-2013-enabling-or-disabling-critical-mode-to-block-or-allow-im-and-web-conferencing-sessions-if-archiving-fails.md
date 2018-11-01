---
title: アーカイブが失敗した場合に IM および Web 会議セッションを禁止または許可するための重要モードの有効化または無効化
TOCTitle: アーカイブが失敗した場合に IM および Web 会議セッションを禁止または許可するための重要モードの有効化または無効化
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182609(v=OCS.15)
ms:contentKeyID: 48274189
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アーカイブが失敗した場合に IM および Web 会議セッションを禁止または許可するための重要モードの有効化または無効化

 

_**トピックの最終更新日:** 2013-02-23_

Lync Server 2013 コントロール パネルでは、アーカイブ構成を使ってクリティカル モードを有効および無効にします。これには、次のアーカイブ構成が含まれます。

  - Lync Server 2013 を展開すると既定で作成されるグローバル構成。

  - 特定のサイトまたはプールについてアーカイブを実装する方法を指定するために作成して使用できるオプションのサイトレベル構成およびプール レベル構成。

アーカイブ構成は、最初はアーカイブの展開時にセットアップしますが、展開後に構成を変更、追加、および削除できます。指定できるオプションやアーカイブ構成の階層など、アーカイブ構成の実装の詳細については、「計画」、「展開」、または「操作」のドキュメントの「[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)」を参照してください。

> [!NOTE]
> アーカイブを使用するには、内部通信、外部通信、または Lync Server 2013 に所属するユーザーのためにその両方のアーカイブを有効にするかどうかを指定するためのアーカイブ ポリシーを構成する必要があります。既定では、アーカイブは内部通信および外部通信のどちらに対しても有効になっていません。ポリシーでアーカイブを有効にする前に、このセクションの説明に従って、展開および必要に応じて特定のサイトやプールに対して適切なアーカイブ構成を指定する必要があります。アーカイブの有効化の詳細については、「展開」のドキュメントの「<a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">アーカイブ ポリシーの構成と割り当て</a>」を参照してください。<br />
> アーカイブを展開した後に、Exchange Server の統合を使用してアーカイブ データおよびアーカイブ ファイルを Exchange 2013 サーバーに保存し、すべてのユーザーが Exchange 2013 サーバーに所属することを決定した場合は、トポロジから SQL Server データベース構成を削除する必要があります。このためには、トポロジ ビルダーを使用する必要があります。詳細については、「操作」のドキュメントの「<a href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013 でのアーカイブ データベース オプションの変更</a>」を参照してください。


## アーカイブで障害が発生した場合に IM セッションと Web 会議セッションのブロックを有効または無効にするには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**監視とアーカイブ**\] をクリックし、\[**アーカイブ構成**\] をクリックします。

4.  アーカイブ構成の一覧から、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、\[**編集**\]、\[**詳細の表示**\] の順にクリックして次の操作を実行します。

5.  障害が発生したときのアーカイブの動作を設定するには、\[**アーカイブ失敗時はインスタント メッセージング (IM) または Web 会議セッションを禁止する**\] チェック ボックスをオンまたはオフにします。

6.  \[**確定**\] をクリックします。

## Lync ServerWindows PowerShell コマンドレットを使用してクリティカル モードを有効および無効にする

**Set-CsArchivingConfiguration** コマンドレットを使用してクリティカル モードを有効または無効にできます。このコマンドレットは、Lync Server 2013 管理シェル または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## クリティカル モードを有効にする

  - クリティカル モードを有効にするには、BlockOnArchiveFailure プロパティの値を True ($True) に設定します。次に例を示します。
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

## クリティカル モードを無効にする

  - クリティカル モードを無効にするには、BlockOnArchiveFailure プロパティの値を False ($False) に設定します。次に例を示します。
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

詳細については、[Set-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingConfiguration) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### タスク

[Lync Server 2013 でのアーカイブ データベース オプションの変更](lync-server-2013-changing-archiving-database-options.md)  

#### 概念

[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)  

#### その他のリソース

[Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

