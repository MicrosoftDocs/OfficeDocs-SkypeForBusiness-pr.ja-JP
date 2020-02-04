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
ms.openlocfilehash: 559ebb5a5d5ba91b5a4952037c18ad509ed5cec7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Lync Server 2013 のバックアップと復元プロセスの概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-26_

このセクションでは、Lync Server 2013 のバックアップと復元プロセスのしくみの概要について説明します。 すべての Standard Edition server および Enterprise Edition server では、場所に関係なく同じプロセスを使用します。

一般的に、バックアッププロセスは次のように動作します。

  - 任意のプールに含まれていないスタンドアロンコンピューター上の共有フォルダーとして、バックアップの場所を作成します。 バックアップの場所は **$Backup**で参照されます。

  - 定期的にスケジュールが設定されている場合は、「lync server 2013 のバックアップと復元の要件」 [2013](lync-server-2013-backing-up-lync-server.md)で説明した手順に従って、lync server データベースと[バックアップと復元の要件](lync-server-2013-backup-and-restoration-requirements-data.md)について説明している、すべてのサーバーの設定と構成が含まれます。

  - それ以降のバックアップを実行するたびに、新しい共有フォルダーを作成し、参照を **$Backup**パスを変更します。

通常、復元プロセスは次のように動作します。

  - 障害または障害が発生した場合は、 **$Backup**によって参照されている場所のデータを新しいコンピューターまたはクリーンコンピューターに復元します。
    
    <div>
    

    > [!IMPORTANT]  
    > この復元プロセスでは、既存のサーバーの状態にデータが復元されることはありません。 つまり、このプロセスではサーバーがクリーンまたは新規である必要があります。

    
    </div>

  - ユーザーと会議の情報をエラーの発生時に回復できるようにするために、「 [Lync Server 2013 での高可用性と障害回復の計画](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)」で説明されているように、フロントエンドプールがペアになった障害回復トポロジを実装できます。

  - すべてのドメインネームシステム (DNS) 構成、動的ホスト構成プロトコル (DHCP) 構成、ドメイン名、コンピューターの完全修飾ドメイン名 (Fqdn)、ファイルストアパスなどは、復元時に同じである必要があります。バックアップ。

Lync Server が実行されているサーバーで障害が発生した場合、次の手順に従います。

  - 故障したコンピューターと同じ FQDN を使用して、新しいまたはクリーンなコンピューターにオペレーティングシステムをインストールします。

  - 証明書を再インストールします。

  - サーバーがデータベースをホストしている場合は、Microsoft SQL Server 2012 または Microsoft SQL Server 2008 R2 をインストールします。

  - 一般的に、サーバーがデータベースをホストしている場合は、トポロジビルダーを実行してデータベースを作成してインストールし、アクセス制御リスト (Acl) を設定します。

  - 通常、サーバーの役割をホストしているサーバーの場合は、Lync Server 展開ウィザードの手順1から4を実行して、ローカル構成ファイルをインストールし、サーバーの役割コンポーネントをインストールして、証明書を割り当て、サービスを開始します。
    
    <div>
    

    > [!NOTE]  
    > サーバーがサーバーの役割と連携しているデータベースをホストしている場合は、Lync Server 展開ウィザードの手順2を実行するとデータベースが再作成されます。

    
    </div>

  - サーバーがデータベースをホストしている場合は、バックアップしたデータを復元します。

</div>

<span> </span>

</div>

</div>

</div>

