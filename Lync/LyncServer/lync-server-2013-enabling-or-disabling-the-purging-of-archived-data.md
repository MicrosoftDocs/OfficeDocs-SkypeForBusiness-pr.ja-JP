---
title: アーカイブ データの削除の有効と無効の切り替え
TOCTitle: アーカイブ データの削除の有効と無効の切り替え
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48271524
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アーカイブ データの削除の有効と無効の切り替え

 

_**トピックの最終更新日:** 2013-02-23_

Lync Server 2013 コントロール パネルで、アーカイブ構成を使用して削除の有効と無効を切り替え、削除の実装方法を構成します。次のようなアーカイブ構成があります。

  - Lync Server 2013 の展開時に既定で作成されるグローバル構成

  - 特定のサイトまたはプールでのアーカイブの実装方法を指定するために作成および使用できる、サイトレベルまたはプールレベルのオプションの構成

アーカイブ構成は、最初はアーカイブの展開時に設定しますが、展開後に変更、追加、および削除できます。指定できるオプションやアーカイブ構成の階層など、アーカイブ構成の実装の詳細については、「計画」、「展開」、または「操作」のドキュメントの「[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)」を参照してください。

> [!NOTE]
> Lync Server 2013 に所属するユーザーに対してアーカイブを使用するには、内部通信、外部通信、またはその両方のアーカイブを有効にするかどうかを指定するためのアーカイブ ポリシーを構成する必要があります。既定では、アーカイブは内部通信および外部通信のどちらに対しても有効になっていません。ポリシーでアーカイブを有効にする前に、このセクションの説明に従って、展開および必要に応じて特定のサイトやプールに対して適切なアーカイブ構成を指定する必要があります。アーカイブの有効化の詳細については、「展開」のドキュメントの「<a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">アーカイブ ポリシーの構成と割り当て</a>」を参照してください。<br />
> アーカイブを展開した後に、Microsoft Exchange 統合を使用してアーカイブ データおよびアーカイブ ファイルを Exchange 2013 サーバーに保存し、すべてのユーザーが Exchange 2013 サーバーに所属することを決定した場合は、トポロジから SQL Server データベース構成を削除する必要があります。このためには、トポロジ ビルダーを使用する必要があります。詳細については、「操作」のドキュメントの「<a href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013 でのアーカイブ データベース オプションの変更</a>」を参照してください。


## アーカイブの削除を有効または無効にするには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**監視とアーカイブ**\] をクリックし、\[**アーカイブ構成**\] をクリックします。

4.  アーカイブ構成の一覧で、適切なグローバル、サイト、またはプール構成の名前をクリックし、\[**編集**\]、\[**詳細の表示**\] の順にクリックします。その後、次の操作を行います。
    
      - 削除を有効にする場合は、\[**アーカイブ データの削除を有効にする**\] チェック ボックスをオンにして、次のいずれかの操作を行います。
        
          - すべてのレコードを削除する場合は、\[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**\] をクリックして、日数を指定します。
        
          - エクスポートされたデータのみを削除する場合は、\[**エクスポート済みのアーカイブ データのみを削除する**\] をクリックします。
    
      - 削除を無効にするには、\[**アーカイブ データの削除を有効にする**\] チェック ボックスをオフにします。

5.  \[**確定**\] をクリックします。

## Lync Server 管理シェル コマンドレットを使用してアーカイブ データの削除を有効化および無効化する

Windows PowerShell および **Set-CsArchivingConfiguration** コマンドレットを使用して、アーカイブ データの自動削除の有効化および無効化を管理することもできます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## すべてのアーカイブ データの削除の有効化

  - すべてのアーカイブ データの削除を有効化するには、**EnablePurging** プロパティを True ($True) に設定します。次に例を示します。
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    このコマンドを実行した後、**KeepArchivingDataForDays** プロパティに指定した日数よりも古いすべてのアーカイブ レコードが Lync Server によって毎日削除されます。

## エクスポートされたアーカイブ データのみの削除の有効化

  - ([Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData) コマンドレットを使用して) データ ファイルにエクスポートされたアーカイブ レコードのみを削除するには、PurgeExportedArchivesOnly プロパティも True ($True) に設定する必要があります。次に例を示します。
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    このコマンドの実行後、Lync Server では、1) **KeepArchivingDataForDays** プロパティに指定された日数よりも古いアーカイブ レコード、2) **Export-CsArchivingData** コマンドレットを使用してエクスポートされたアーカイブ レコードという 2 つの条件を満たすアーカイブ レコードのみが削除されます。

## すべてのアーカイブ データの削除の無効化

  - アーカイブ レコードの自動削除を無効化するには、**EnablePurging** プロパティを False ($False) に設定します。次に例を示します。
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

アーカイブ データを削除する場合の追加のオプションを含む詳細については、[Set-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingConfiguration) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### 概念

[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)  

#### その他のリソース

[アーカイブ ポリシーの構成と割り当て](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[Lync Server 2013 での組織、サイト、およびプールのアーカイブ構成オプションの管理](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

