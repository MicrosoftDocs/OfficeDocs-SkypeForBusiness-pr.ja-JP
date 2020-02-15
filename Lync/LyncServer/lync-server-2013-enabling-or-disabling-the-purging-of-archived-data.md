---
title: 'Lync Server 2013: アーカイブされたデータの削除を有効または無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e62ff615b4e2fcf5ec10f470993f985db0363a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>Lync Server 2013 でのアーカイブされたデータの削除を有効または無効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

Lync Server 2013 コントロールパネルでは、アーカイブ構成を使用して、削除を有効または無効にし、削除の実装方法を構成します。 これには、次のアーカイブ構成が含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバル構成。

  - 特定のサイトまたはプールに対するアーカイブの実装方法を指定するために作成して使用できる、オプションのサイトレベルおよびプールレベルのポリシー。

アーカイブ構成は、最初はアーカイブの展開時に設定しますが、展開後に変更、追加、および削除できます。 指定できるオプションやアーカイブ構成の階層など、アーカイブ構成の実装方法の詳細については、「計画」のドキュメント、「展開」、または「操作」のドキュメントの「 [Lync Server 2013 でのアーカイブの仕組み](lync-server-2013-how-archiving-works.md)」を参照してください。

<div>


> [!NOTE]  
> Lync Server 2013 に所属するユーザーのアーカイブを使用するには、アーカイブポリシーを構成して、内部通信、外部通信、またはその両方のアーカイブを有効にするかどうかを指定する必要があります。 既定では、アーカイブは内部通信および外部通信のどちらに対しても有効になっていません。 ポリシーでアーカイブを有効にする前に、このセクションの説明に従って、展開および必要に応じて特定のサイトやプールに対して適切なアーカイブ構成を指定する必要があります。 アーカイブを有効にする方法の詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でのアーカイブポリシーの構成と割り当て</A>」を参照してください。<BR>Microsoft Exchange 統合を使用してアーカイブデータおよびファイルを Exchange 2013 サーバーに保存し、すべてのユーザーが Exchange 2013 サーバーに所属している場合は、アーカイブを展開した後に、SQL Server データベース構成を削除する必要があります。トポロジから。 これを行うには、トポロジビルダーを使用する必要があります。 詳細については、「操作」のドキュメントの「 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013 でのアーカイブデータベースオプションの変更</A>」を参照してください。



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>アーカイブの削除を有効または無効にするには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

4.  アーカイブ構成の一覧で、適切なグローバル、サイト、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。その後、次の操作を行います。
    
      - 削除を有効にする場合は、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにして、次のいずれかの操作を行います。
        
          - すべてのレコードを削除する場合は、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックして、日数を指定します。
        
          - エクスポートされたデータのみを削除する場合は、[**エクスポート済みのアーカイブ データのみを削除する**] をクリックします。
    
      - 削除を無効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオフにします。

5.  [**確定**] をクリックします。

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してアーカイブデータの削除を有効または無効にする

アーカイブデータの自動削除を有効または無効にするには、Windows PowerShell と**set-csarchivingconfiguration**コマンドレットを使用して管理できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>すべてのアーカイブデータの削除を有効にするには

  - すべてのアーカイブ データの削除を有効化するには、**EnablePurging** プロパティを True ($True) に設定します。 例:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    このコマンドを実行すると、 **KeepArchivingDataForDays**プロパティに指定された値よりも古いすべてのアーカイブレコードが Lync Server によって削除されます。

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>エクスポートされたアーカイブデータのみを削除できるようにするには

  - [Export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)コマンドレットを使用して、データファイルにエクスポートされたレコードをアーカイブするように削除を制限するには、PurgeExportedArchivesOnly プロパティを True ($True) に設定する必要もあります。 例:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    このコマンドを実行すると、Lync Server は、2つの条件を満たすレコードのアーカイブのみを削除します。 1) は、 **KeepArchivingDataForDays**プロパティに指定された値よりも古いものです。および 2) は、 **export-csarchivingdata**コマンドレットを使用してエクスポートされています。

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>すべてのアーカイブデータの削除を無効にするには

  - アーカイブ レコードの自動削除を無効化するには、**EnablePurging** プロパティを False ($False) に設定します。 次に例を示します。
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

アーカイブデータを削除するためのその他のオプションを含む詳細については、 [set-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)  


[Lync Server 2013 でのアーカイブポリシーの構成と割り当て](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[組織、サイト、およびプールの Lync Server 2013 でのアーカイブ構成オプションの管理](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

