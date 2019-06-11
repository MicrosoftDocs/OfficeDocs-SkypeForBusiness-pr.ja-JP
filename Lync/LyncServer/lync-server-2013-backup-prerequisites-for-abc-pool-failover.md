---
title: 'Lync Server 2013: ABC プールフェールオーバーのバックアップ前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7cdb228b0a748c830aa488e7b058bf8664360d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Lync Server 2013 での ABC プールフェールオーバーのバックアップの前提条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-26_

ABC プールフェールオーバーの手順を最大限に活用するには、障害が発生してフェールオーバーが発生する前に、特定のバックアップを実行する必要があります。

  - **CsLISConfiguration**コマンドレットを使用して、場所情報サービス (LIS) 構成データをプール A から定期的にバックアップする必要があります。
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - **Export-CsRgsConfiguration**コマンドレットを使用して、プール A の応答グループの構成データを定期的にバックアップする必要があります。
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    一般的に、毎日のバックアップを実行することをお勧めしますが、変更の量が多い場合は、より頻繁にバックアップをスケジュールすることをお勧めします。 障害が発生した場合に失われる可能性のある情報の量は、バックアップの頻度、および変更の頻度と量によって異なります。
    
    応答グループのアプリケーションは、1つのプールにつき1つのアプリケーションレベルの設定のみを格納できます。 これらの設定にアクセスするには、 **Get-CsRgsConfiguration**コマンドレットを使用します。 設定には、既定の音楽保留の構成、既定の音楽保留中のオーディオファイル、エージェントの呼び出し元の猶予期間、通話コンテキストの構成が含まれます。 これらの設定は、" **Replaceexistingsettings** " パラメーターを使用して、 **Import-CsRgsConfiguration**コマンドレットによってプール間で転送できますが、この操作によって、宛先のアプリケーションレベルの設定が上書きされます。生産.
    
    <div>
    

    > [!TIP]  
    > 別の場所で、応答グループアプリケーションの構成に使用されているすべての元のオーディオファイル (つまり、レコーディングまたは音楽の保留ファイル) のバックアップコピーを保持します。

    
    </div>
    
    プール内のコールパークにアップロードされたカスタマイズ済みの音楽の保存ファイルがある場合は、そのファイルのコピーを別の場所に保存しておく必要があります。 これらのファイルは、Lync Server 2013 の障害回復プロセスの一部としてはバックアップされません。プールにアップロードされたファイルが破損、破損、または消去された場合、これらのファイルは失われます。
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > コールパークアプリケーションには、1つのセットの設定と、1つのプールにつき1つのカスタマイズされた音楽オンホールドオーディオファイルしか保存できません。 これらの設定にアクセスするには、 <STRONG>CsCpsConfiguration</STRONG>コマンドレットを使用します。 コールパークの障害回復メカニズムはバックアッププールのコールパークアプリケーションに依存するため、障害が発生した場合、プライマリプールの設定はバックアップされないか、維持されません。 プライマリプールが失われた場合は、これらの設定を復元することはできません。また、新しいプールがプライマリプールの代わりとして展開されている場合は、コールパークの設定と、カスタマイズされた音楽の保留中のオーディオファイルを再構成する必要があります。

    
    </div>

  - 未割り当ての電話機能の一部としてアナウンスを構成する場合は、最初の設定で使用した元のオーディオファイルのコピーを別の場所に残しておくことをお勧めします。 この操作を行わなかった場合は、オーディオファイルがインポートされたサーバーまたはプールのファイルストアに、構成されたオーディオファイルのコピーを取得できます。 これらのファイルは、Lync Server 2013 の障害回復プロセスの一部としてはバックアップされません。プールにアップロードされたファイルが破損、破損、または消去された場合、これらのファイルは失われます。 割り当てられていない番号の音声機能を構成するために使用されるすべてのオーディオファイルをサーバーまたはプールのファイルストアからコピーするには、次のように使用します。
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - プールにデータベースの監視とアーカイブを行っている場合は、SQL Server 管理ツールを使用してバックアップを作成する必要があります。 "データベースは Lync Server Backup Service でバックアップされていないため、データベースがプール A に併置されている場合、" データベースの監視 "および" アーカイブ "プロシージャでは、データベースは保持されません。

</div>

<span> </span>

</div>

</div>

</div>

