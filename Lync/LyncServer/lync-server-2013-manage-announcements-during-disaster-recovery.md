---
title: 'Lync Server 2013: 障害復旧時のアナウンスの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6058974b8473bc2c6db91abaaeb1550647ba592d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 での障害復旧時のアナウンスの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

Lync Server 2013 は、停止中に割り当てられていない番号への通話のアナウンスをサポートしています。 停止中のアナウンス機能の復元は任意です。 停止中にアナウンスを復元する場合は、バックアップ プールでアナウンス構成を再作成する必要があります。 このセクションでは、障害復旧中にアナウンスを復元する場合に、何を行う必要があるかについて説明します。

このセクションは、アナウンスアプリケーションを使用する割り当てられていない番号範囲に適用されます。 Exchange ユニファイド メッセージング (UM) 自動応答を使用する割り当てなしの番号範囲には適用されません。

<div>

## <a name="before-an-outage"></a>停止前

システム停止時にアナウンスを使用するかどうかにかかわらず、アナウンスアプリケーション用に構成したカスタマイズされたオーディオファイルのバックアップを個別に作成する必要があります。 カスタマイズしたアナウンスは、Lync Server の障害復旧プロセスの一環としてバックアップされません。 ファイルのバックアップを別途作成しておらず、サーバーにアップロードしたファイルが破損したり消去されたりした場合、ファイルは失われます。

カスタマイズされたオーディオファイルのバックアップコピーがなく、元のオーディオファイルが使用できなくなった場合は、元のサーバーまたはプールのファイルストアを調べて、アナウンスアプリケーション用に構成したオーディオファイルを見つけることができます。ファイルをインポートしました。 アナウンスメントアプリケーションに対して構成したすべてのオーディオファイルを、ファイルストアからコピーすることができます。

**ファイルストアからオーディオファイルをコピーするには**

1.  コマンド ラインで、次のコマンドを実行します。
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    次に例を示します。
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    X-ApplicationServer-X は、プールのアプリケーション サーバーのサービス ID です (例: 1-ApplicationServer-1")


</div>

<div>

## <a name="during-an-outage"></a>停止中

停止中にアナウンスメントアプリケーションを使用するには、このセクションで説明されているタスクを実行して、バックアッププールでアナウンス構成を再作成する必要があります。

<div>


> [!NOTE]  
> 手順 2 を実行するとすぐに割り当てなしの番号範囲の所有権をバックアップ プールが取得するので、これらのタスクは、バックアップ プールへのフェールオーバー後に実行することをお勧めします。



</div>

<div>


> [!NOTE]  
> この手順は、Exchange UM 自動応答の電話番号を使用する番号範囲については必要ありません。



</div>

**バックアッププールでアナウンス構成を再作成するには**

1.  次の手順を実行して、プライマリ プールに展開したアナウンスをバックアップ プールに再作成します。
    
    1.  プライマリ プールで使用していたオーディオ ファイルがある場合は、**Import-CsAnnouncementFile** コマンドレットを使用し、Parent パラメーターにバックアップ プールを指定して、そのオーディオ ファイルをバックアップ プールにインポートします。
    
    2.  **New-CsAnnouncement** コマンドレットを使用し、Parent パラメーターにバックアップ プールを指定して、個々のアナウンスを再作成します。
    
    <div>
    

    > [!NOTE]  
    > これらのパラメーターを使用してバックアッププールにアナウンスを作成する方法の詳細については、「 <A href="lync-server-2013-create-an-announcement.md">create a アナウンスメント In Lync Server 2013</A>」を参照してください。

    
    </div>

2.  すべてのアナウンスがバックアップ プールに再作成されたら、プライマリ プールでアナウンスを使用している割り当てなしの番号範囲をすべて、バックアップ プールに再作成したアナウンスに転送します。
    
    プライマリ プールでアナウンスを使用している割り当てなしの番号範囲ごとに、次のコマンドを実行します。
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>停止後

プライマリ プールが利用可能になったら、停止中に変更した割り当てなしの番号範囲を、再びプライマリ プールに転送する必要があります。

<div>


> [!NOTE]  
> この手順は、Exchange UM 自動応答の電話番号を使用する番号範囲については必要ありません。



</div>

**プライマリプールでアナウンスを復元するには**

1.  復旧中にプライマリ プールを再構築した場合は、バックアップ プールで実行したのと同様にオーディオ ファイルをインポートし、アナウンスを作成することによって、プライマリ プールにアナウンスを再作成する必要があります。ただし、この場合は Parent パラメーターにプライマリ プールを指定しません。詳細については、このトピックで前述した「停止中」のトピックを参照してください。

2.  停止中に変更した割り当てなしの番号範囲ごとに、次のコマンドを実行します。
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  必要に応じて、バックアッププールで再作成したアナウンスを削除します。 バックアッププールアナウンスアプリケーションのアナウンスの一覧を取得します。 コマンド ラインで、次のコマンドを実行します。
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    例:
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    結果の一覧で、削除するアナウンスを特定し、その GUID をコピーします。削除するアナウンスごとに、次のコマンドを実行します。
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    次に例を示します。
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

