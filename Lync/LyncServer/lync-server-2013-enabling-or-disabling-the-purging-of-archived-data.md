---
title: 'Lync Server 2013: アーカイブデータの削除を有効または無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28eba32895ca928b40e42a04d8d701c7257f1e43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>Lync Server 2013 でアーカイブデータの削除を有効または無効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

Lync Server 2013 コントロールパネルで、[アーカイブ構成] を使って、パージを有効または無効にし、パージの実装方法を構成します。 これには、次のアーカイブ構成が含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバル構成。

  - 作成および使用して、特定のサイトまたはプールに対するアーカイブの実装方法を指定することができる、オプションのサイトレベルとプールレベルの構成。

アーカイブの展開時にアーカイブ構成を最初に設定しましたが、展開後に構成の変更、追加、削除を行うことができます。 アーカイブ構成の実装方法について詳しくは、「指定できるオプションやアーカイブ構成の階層」を参照してください。「 [Lync Server 2013 でのアーカイブの動作](lync-server-2013-how-archiving-works.md)(計画ドキュメント、展開)」を参照してください。ドキュメント、または操作のドキュメント。

<div>


> [!NOTE]  
> Lync Server 2013 を使っているユーザーのためにアーカイブを使用するには、内部通信のアーカイブを有効にするか、外部通信を有効にするかを指定するようにアーカイブポリシーを構成する必要があります。 既定では、内部または外部の通信でアーカイブは有効になっていません。 すべてのポリシーでアーカイブを有効にする前に、このセクションで説明するように、展開用に適切なアーカイブ構成を指定し、必要に応じて特定のサイトとプールを指定する必要があります。 アーカイブを有効にする方法の詳細については、展開ドキュメントの「 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013 でアーカイブポリシーを構成して割り当てる</A>」を参照してください。<BR>Microsoft Exchange 統合を使用して Exchange 2013 サーバー上のアーカイブデータとファイルを保存し、すべてのユーザーが Exchange 2013 サーバー上にある場合は、アーカイブを展開した後に、SQL Server データベースの構成を削除する必要があります。を選びます。 この操作を行うには、トポロジビルダーを使用する必要があります。 詳細については、「運用ドキュメントの「 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013 でアーカイブデータベースのオプションを変更する</A>」を参照してください。



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>アーカイブの消去を有効または無効にするには

1.  CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ構成**] をクリックします。

4.  アーカイブ構成の一覧から、適切なグローバル構成、サイト構成、またはプール構成の名前をクリックし、[**編集**]、[**詳細の表示**] の順にクリックし、次の操作を実行します。
    
      - 削除を有効にする場合は、[**アーカイブ データの削除を有効にする**] チェック ボックスをオンにし、次のいずれかの操作を行います。
        
          - すべてのレコードを削除する場合は、[**最大日数が経過したエクスポートおよび保存済みアーカイブ データを削除する**] をクリックし、日数を指定します。
        
          - エクスポートされたデータのみを削除する場合は、[**エクスポート済みのアーカイブ データのみを削除する**] をクリックします。
    
      - 削除を無効にするには、[**アーカイブ データの削除を有効にする**] チェック ボックスをオフにします。

5.  [**確定**] をクリックします。

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用してアーカイブデータの削除を有効または無効にする

アーカイブデータの自動削除を有効または無効にするには、Windows PowerShell と**CsArchivingConfiguration**コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>すべてのアーカイブデータの削除を有効にするには

  - すべてのアーカイブデータの削除を有効にするには、 **Enablepurging 消去**プロパティを true ($True) に設定します。 次に例を示します。
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    このコマンドを実行すると、Lync Server では、 **KeepArchivingDataForDays**プロパティに指定した値よりも古いすべてのアーカイブレコードが削除されます。

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>エクスポートされたアーカイブデータのみを削除できるようにするには

  - データファイルにエクスポートされたレコード ( [CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)コマンドレットを使用して) をアーカイブするようにパージを制限するには、PurgeExportedArchivesOnly プロパティも True ($True) に設定する必要があります。 次に例を示します。
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    このコマンドを実行すると、Lync Server は、2つの条件を満たすアーカイブレコードのみを消去します。 1) は、 **KeepArchivingDataForDays**プロパティに指定された値よりも古いものです。and、2) **CsArchivingData**コマンドレットを使用してエクスポートされている。

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>すべてのアーカイブデータの削除を無効にするには

  - アーカイブレコードの自動削除を無効にするには、 **Enablepurging 削除**プロパティを False ($False) に設定します。 次に例を示します。
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

アーカイブデータの削除に関するその他のオプションなど、詳細については、 [CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのアーカイブのしくみ](lync-server-2013-how-archiving-works.md)  


[Lync Server 2013 でアーカイブポリシーを構成して割り当てる](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[組織、サイト、およびプールの Lync Server 2013 でアーカイブ構成オプションを管理する](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

