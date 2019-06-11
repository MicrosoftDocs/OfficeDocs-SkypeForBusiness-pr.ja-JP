---
title: 'Lync Server 2013: 応答グループを新しいプールに移動する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving response groups to a new pool
ms:assetid: da0db765-41e5-430b-b5a7-5418ec5ff2a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205298(v=OCS.15)
ms:contentKeyID: 48185538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e682ce99826cd5b9f2812c358e1028bfb491ddef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-response-groups-to-a-new-pool-in-lync-server-2013"></a>Lync Server 2013 の新しいプールへの応答グループの移動

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

Lync Server 2013 では、完全修飾ドメイン名 (FQDN) が異なる場合でも、1つのプールから別のプールに応答グループを移動するための新しいコマンドレットのサポートが導入されています。

次の手順を使用して、1つのフロントエンドプールから別の FQDN で応答グループを別のフロントエンドプールに移動します。

<div>


> [!NOTE]  
> 共存環境では、Lync Server 2013&nbsp;フロントエンドプール間でのみ応答グループを移動できます。



</div>

<div>

## <a name="to-move-response-groups-to-a-pool-with-a-different-fqdn"></a>応答グループを別の FQDN のプールに移動するには

1.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

2.  ソースプールの応答グループをエクスポートします。 コマンドラインで、次のように入力します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source FQDN>" -FileName "<export file name>"
    
    例:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -FileName "C:\RgsExportSource.zip"
    
    エクスポート中にソースプールから応答グループを削除するには、– RemoveExportedConfiguration パラメーターを含めます。 次に例を示します。
    
        Export-CsRgsConfiguration -Source ApplicationServer:source.contoso.com -FileName "C:\RgsExportSource.zip" -RemoveExportedConfiguration

3.  宛先プールに応答グループをインポートして、新しい所有者として宛先プールを割り当てます。 コマンド ラインで次を入力します。
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<destination pool>" -FileName "<export file name>" -OverwriteOwner
    
    応答グループのアプリケーションレベルの設定をソースプールから移行先のプールにコピーする必要がある場合は、– ReplaceExistingRgsSettings パラメーターを含めます。 プールごとに1つのアプリケーションレベルの設定のみを定義できます。 ソースプールからターゲットプールにアプリケーションレベルの設定をコピーすると、ソースプールの設定が移行先のプールの設定と置き換わります。 ソースプールからアプリケーションレベルの設定をコピーしない場合、移行先プールの既存の設定はインポートされた応答グループに適用されます。
    
    次に例を示します。
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:destination.contoso.com" -FileName "C:\RgsExportSource.zip" -OverwriteOwner -ReplaceExistingRgsSettings
    
    <div>
    

    > [!NOTE]  
    > アプリケーションレベルの設定には、既定の音楽保留の構成、既定の音楽の保留中のオーディオファイル、エージェントの ringback の猶予期間、通話コンテキストの構成が含まれます。 これらの構成設定を表示するには、 <STRONG>Get-CsRgsConfiguration</STRONG>コマンドレットを実行します。 このコマンドレットの詳細については、「 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration">Get-CsRgsConfiguration</A>」を参照してください。

    
    </div>

4.  インポートされた応答グループの構成を表示してインポートが正常に完了したことを確認するには、次の操作を行います。
    
      - すべてのワークフローがインポートされたことを確認します。 コマンドラインで、次のように入力します。
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - すべてのキューがインポートされたことを確認します。 コマンドラインで、次のように入力します。
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - すべてのエージェントグループがインポートされたことを確認します。 コマンドラインで、次のように入力します。
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<destination pool FQDN>"
    
      - すべての勤務時間がインポートされたことを確認します。 コマンドラインで、次のように入力します。
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<destination pool FQDN>" 
    
      - すべての休日セットがインポートされたことを確認します。 コマンドラインで、次のように入力します。
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<destination pool FQDN>" 

5.  応答グループの1つに通話を発信し、通話が正しく処理されていることを確認して、インポートが成功したことを確認します。

6.  送信先のプールのエージェントグループにサインインするために、正式なエージェントグループのメンバーであるエージェントを要求します。

7.  ソースプールから応答グループを削除していない場合は、ソースプールから応答グループを削除します。 コマンドラインで、次のように入力します。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<source pool FQDN> -RemoveExportedConfiguration -FileName "<temporary export file name>"
    
    例:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:source.contoso.com" -RemoveExportedConfiguration -FileName "C:\TempRGsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

