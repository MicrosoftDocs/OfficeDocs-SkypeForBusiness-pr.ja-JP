---
title: 'Lync Server 2013: バックアップと復元のプロセスの概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94cebbc9a11e1857bed419c97f52f065326b1772
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504874"
---
# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Lync Server 2013 のバックアップと復元のプロセスの概要

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-26_

このセクションでは、Lync Server 2013 のバックアップと復元のプロセスがどのように機能するかの概要について説明します。 すべての Standard Edition サーバーおよび Enterprise Edition サーバーでは、その場所に関係なく同じプロセスを使用します。

一般に、バックアッププロセスは次のように動作します。

  - バックアップ先は、どのプールにも属さないスタンドアロンコンピューター上の共有フォルダーとして作成します。 バックアップの場所は **$Backup**で参照されます。

  - 通常、スケジュールに従って、lync server データベースおよび [バックアップと復元の2013要件](lync-server-2013-backup-and-restoration-requirements-data.md) で説明されているすべてのファイルストアをバックアップします。この手順については、「lync server [2013](lync-server-2013-backing-up-lync-server.md) をバックアップする」で説明している手順に従います。中央管理ストアには、すべてのサーバー設定と構成が含まれています。

  - その後のバックアップを実行するたびに、新しい共有フォルダーを作成し、 **$Backup** 参照するパスを変更します。

一般的に、復元プロセスは次のように動作します。

  - 障害または停止が発生した場合は、 **$Backup** によって参照されている場所のデータを新しいコンピューターまたはクリーンなコンピューターに復元します。
    
    <div>
    

    > [!IMPORTANT]  
    > この復元プロセスでは、データは既存のサーバーの状態に復元されません。 つまり、このプロセスでは、サーバーがクリーンまたは新規である必要があります。

    
    </div>

  - 障害点までユーザーおよび会議情報を回復できるようにするには、「 [Lync Server 2013 での高可用性と障害復旧の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」で説明されているように、フロントエンドプールをペアとする障害復旧トポロジを実装できます。

  - すべてのドメインネームシステム (DNS) 構成、動的ホスト構成プロトコル (DHCP) の構成、ドメイン名、コンピューターの完全修飾ドメイン名 (Fqdn)、ファイルストアのパスなどは、バックアップ時の復元時と同じである必要があります。

Lync Server を実行しているサーバーに障害が発生した場合、復旧には次の手順が含まれます。

  - エラーが発生したコンピューターと同じ FQDN を使用して、新しいまたはクリーンなコンピューターにオペレーティングシステムをインストールします。

  - 証明書を再インストールします。

  - サーバーがデータベースをホストしている場合は、Microsoft SQL Server 2012 または Microsoft SQL Server 2008 R2 をインストールします。

  - 一般的に、サーバーがデータベースをホストしていた場合は、トポロジビルダーを実行して、データベースを作成およびインストールし、アクセス制御リスト (Acl) を設定します。

  - 通常、サーバーがサーバーの役割をホストしている場合は、Lync Server 展開ウィザードの手順 1 ~ 4 を実行して、ローカル構成ファイルをインストールし、サーバーの役割コンポーネントをインストールし、証明書を割り当て、サービスを開始します。
    
    <div>
    

    > [!NOTE]  
    > サーバーがサーバーの役割と併置されているデータベースをホストしていた場合は、Lync Server Deployment ウィザードの手順2を実行すると、データベースが再作成されます。

    
    </div>

  - サーバーがデータベースをホストしていた場合は、バックアップしたデータを復元します。

</div>

<span> </span>

</div>

</div>

</div>

