---
title: 'Lync Server 2013: 障害復旧時のアナウンスの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65627e68b31e23908e9fd5258a69862f7ea15b79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 での障害復旧時のアナウンスの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

Lync Server 2013 は、停止中に、未割り当ての電話番号への通話に対するお知らせをサポートします。 停止中のアナウンスメント機能の復元は任意です。 停止中にお知らせを復元する場合は、バックアッププールでアナウンスメントの構成を再作成する必要があります。 このセクションでは、障害回復中にお知らせを復元する場合に必要な操作について説明します。

このセクションは、アナウンスメントアプリケーションを使用する未割り当ての番号範囲に適用されます。 このセクションは、Exchange ユニファイドメッセージング (UM) 自動応答を使用する未使用の番号範囲には適用されません。

<div>

## <a name="before-an-outage"></a>停止前

システム停止中にお知らせを使用するかどうかに関係なく、アナウンスメントアプリケーション用に構成したカスタマイズされたオーディオファイルのバックアップを個別に作成する必要があります。 カスタマイズされたお知らせは、Lync Server の障害回復プロセスの一部としてはバックアップされません。 ファイルのバックアップを個別に行わず、サーバーやプールにアップロードしたファイルが破損している、破損している、または消去された場合、ファイルは失われます。

カスタマイズしたオーディオファイルのバックアップコピーを持っておらず、元のオーディオファイルを使用できない場合は、最初にサーバーまたはプールのファイルストアを参照して、アナウンスメントアプリケーション用に構成したオーディオファイルを見つけることができます。ファイルをインポートしました。 アナウンスメントアプリケーション用に設定したすべてのオーディオファイルを、ファイルストアからコピーできます。

**ファイルストアからオーディオファイルをコピーするには**

1.  コマンド ラインで、次のコマンドを実行します。
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    例:
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    ここで、ApplicationServer-X はプールのアプリケーションサーバーのサービス ID を示します (たとえば、1-ApplicationServer-1)。


</div>

<div>

## <a name="during-an-outage"></a>停止中

このセクションで説明されているタスクを実行することにより、アプリの停止中にお知らせの設定を再作成する必要があります。

<div>


> [!NOTE]  
> バックアッププールにフェールオーバーした後、これらのタスクを実行することをお勧めします。これは、手順2を実行するとすぐに、割り当てられていない番号範囲の所有権を取得するためです。



</div>

<div>


> [!NOTE]  
> Exchange UM 自動応答の電話番号を使用する番号の範囲については、以下の手順は必要ありません。



</div>

**バックアッププールでお知らせの構成を再作成するには**

1.  バックアッププールのプライマリプールに展開したお知らせを再作成するには、次の操作を行います。
    
    1.  **インポート-CsAnnouncementFile**コマンドレットを使用して、プライマリプールで使用されているすべてのオーディオファイルをバックアッププールにインポートし、親パラメーターのバックアッププールを指定します。
    
    2.  **新しい-csannouncement**コマンドレットを使用し、親パラメーターのバックアッププールを指定して、各アナウンスを再作成します。
    
    <div>
    

    > [!NOTE]  
    > これらのパラメーターを使用してバックアッププールでお知らせを作成する方法の詳細については、「 <A href="lync-server-2013-create-an-announcement.md">Lync Server 2013 でお知らせを作成</A>する」を参照してください。

    
    </div>

2.  すべてのアナウンスをバックアッププールに再作成したら、プライマリプールのお知らせを使用する、割り当てられていないすべての番号範囲をバックアッププール内の再作成したアナウンスにリダイレクトします。
    
    割り当てられていない番号の範囲ごとに、プライマリプールでお知らせを使用するには、次の操作を実行します。
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>停止後

プライマリプールが利用可能になったら、停止するために変更した未使用の番号範囲をプライマリプールに戻す必要があります。

<div>


> [!NOTE]  
> Exchange UM 自動応答の電話番号を使用する番号の範囲については、以下の手順は必要ありません。



</div>

**プライマリプールのアナウンスを復元するには**

1.  回復中にプライマリプールを再構築する必要がある場合は、親のプライマリプールを指定することを除いて、オーディオファイルをインポートしてお知らせを作成し、その場合と同様に、プライマリプールでお知らせを再作成する必要があります。引き. 詳細については、このトピックの前の「停止中」を参照してください。

2.  停止のために変更した未使用の番号の範囲ごとに、次を実行します。
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  必要に応じて、バックアッププールで再作成したお知らせを削除します。 バックアッププールのアナウンスメントアプリケーションのお知らせリストを取得します。 コマンド ラインで、次のコマンドを実行します。
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    例:
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    結果の一覧で、削除するお知らせを見つけて、Guid をコピーします。 削除するお知らせごとに、次を実行します。
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    例:
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

