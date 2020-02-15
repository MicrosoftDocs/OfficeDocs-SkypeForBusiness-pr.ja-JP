---
title: 'Lync Server 2013: 応答グループを新しいプールに移動する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41d739ae79998fe3dbf3acadba2b2f480a960a30
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>Lync Server 2013 の新しいプールへの応答グループの移動

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

Lync Server 2013 は、完全修飾ドメイン名 (FQDN) が異なる場合でも、あるプールから別のプールに応答グループを移動するための新しいコマンドレットのサポートを導入しました。

次の手順を使用して、応答グループを1つのフロントエンドプールから別の FQDN の別のフロントエンドプールに移動します。

<div>


> [!NOTE]  
> 共存環境では、Lync Server 2013&nbsp;フロントエンドプール間でのみ応答グループを移動できます。



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>応答グループを異なる FQDN を持つプールに移動するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  移動元のプール内の応答グループをエクスポートします。コマンドラインで、次のように入力します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    例:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    エクスポート中に移動元のプールから応答グループを削除するには、–RemoveExportedConfiguration パラメーターを含めます。たとえば、次のように入力します。
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  応答グループを移動先のプールにインポートし、移動先のプールを新しい所有者として割り当てます。コマンドラインで、次のように入力します。
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    応答グループのアプリケーションレベルの設定をソースプールから移行先のプールにコピーする場合は、-ReplaceExistingRgsSettings パラメーターを含めます。 プールごとにアプリケーションレベルの設定のセットを 1 つだけ定義できます。 アプリケーションレベルの設定をソース プールから転送先プールにコピーする場合は、転送先プールの設定がソース プールの設定に置き換えられます。 アプリケーションレベルの設定をソース プールからコピーしない場合は、転送先プールの既存の設定が、インポートされた応答グループに適用されます。
    
    例:
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > アプリケーションレベルの設定には、既定の保留音の構成、既定の保留音の音声ファイル、エージェント リングバックの猶予期間、および通話コンテキストの構成が含まれます。 これらの構成を表示するには、<STRONG>Get-CsRgsConfiguration</STRONG> コマンドレットを実行します。 このコマンドレットの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">get-help</A>」を参照してください。

    
    </div>

4.  次の操作を実行してインポートされた応答グループの構成を表示することにより、インポートが成功したことを確認します。
    
      - すべてのワークフローがインポートされたことを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - すべてのキューがインポートされたことを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - すべてのエージェント グループがインポートされたことを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - すべての営業時間がインポートされたことを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - すべての休日セットがインポートされたことを確認します。コマンドラインで、次のように入力します。
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  応答グループの 1 つに電話をかけ、通話が正しく処理されることを確認して、インポートが正常に完了したことを確認します。

6.  公式エージェント グループのメンバーであるエージェントに、移動先のプール内のエージェント グループにサインインするように要求します。

7.  前の手順で移動元のプールから応答グループを削除しなかった場合は、移動元のプールから応答グループを削除します。コマンドラインで、次のように入力します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    次に例を示します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

