---
title: 'Lync Server 2013: ABC プールフェールオーバーのバックアップ前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bd6bd22b29cd5031e83f0e8e8a09755c730be64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Lync Server 2013 での ABC プールフェールオーバーのバックアップ前提条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-26_

ABC プールのフェールオーバー手順を使用することで最大のメリットを得るには、障害とフェールオーバーが発生する前に、特定のバックアップを実行する必要があります。

  - **Export-cslisconfiguration**コマンドレットを使用して、プール A から場所情報サービス (LIS) 構成データを定期的にバックアップする必要があります。
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - **Export-CsRgsConfiguration**コマンドレットを使用して、プール A の応答グループ構成データを定期的にバックアップする必要があります。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    一般に、毎日バックアップを行うことをお勧めしますが、変更が多い場合は、より頻度の高いバックアップのスケジュールが必要になることもあります。 障害が発生した場合に失われる可能性のある情報は、バックアップの頻度、および変更の頻度と量によって異なります。
    
    応答グループアプリケーションに保存できるアプリケーションレベルの設定は、プールごとに1つだけです。 これらの設定には、 **Get-CsRgsConfiguration**コマンドレットを使用してアクセスできます。 設定には、既定の保留音の設定、既定の保留音のオーディオファイル、エージェントの呼び出し元の猶予期間、呼び出しコンテキストの構成が含まれます。 これらの設定**は、** **replaceexistingsettings**パラメーターを使用して、別のプールから別のプールに移動できます。ただし、この操作は、移動先のプール内のアプリケーションレベルの設定より優先されます。
    
    <div>
    

    > [!TIP]  
    > 別の場所に、応答グループアプリケーションの構成に使用したすべての元のオーディオファイル (つまり、レコーディングまたは音楽の保留中のファイル) のバックアップコピーを保存します。

    
    </div>
    
    コールパーク用にアップロードされた保留中のカスタマイズされた保留中のファイルがプールにある場合は、それらのコピーを別の場所に保持する必要があります。 これらのファイルは、Lync Server 2013 の障害復旧プロセスの一環としてバックアップされません。プールにアップロードされたファイルが破損、破損、または消去されると、それらのファイルは失われます。
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > コールパークアプリケーションは、1つのプールに対して1セットの設定と1つのカスタマイズされた音楽保留オーディオファイルのみを保存できます。 これらの設定には、 <STRONG>new-cscpsconfiguration</STRONG>コマンドレットを使用してアクセスできます。 コールパークの障害復旧メカニズムは、バックアッププールのコールパークアプリケーションに依存しているため、障害が発生した場合、プライマリプールの設定はバックアップまたは保持されません。 プライマリプールが失われた場合、これらの設定を回復することはできません。また、プライマリプールを置き換えるために新しいプールを展開する場合は、コールパーク設定とカスタマイズされた音楽オンホールドオーディオファイルを再構成する必要があります。

    
    </div>

  - 割り当てられていない電話機能の一部としてアナウンスを構成する場合は、最初の構成時に使用した元のオーディオファイルのコピーを別の場所に保存することをお勧めします。 この操作を行わなかった場合は、オーディオファイルのインポート先のサーバーまたはプールのファイルストアに構成されたオーディオファイルのコピーを取得できます。 これらのファイルは、Lync Server 2013 の障害復旧プロセスの一環としてバックアップされません。プールにアップロードされたファイルが破損、破損、または消去されると、それらのファイルは失われます。 未使用の番号の音声機能を構成するために使用されているすべてのオーディオファイルを、サーバーまたはプールのファイルストアからコピーするには、次の値を使用します。
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - プール内にデータベースの監視とアーカイブを行っている場合は、SQL Server 管理ツールを使用してバックアップする必要があります。 このようなデータベースは Lync Server バックアップサービスを使用してバックアップされないため、ABC フェールオーバーの手順では、データベースがプール A に併置されている場合、監視およびアーカイブデータベースは保持されません。

</div>

<span> </span>

</div>

</div>

</div>

