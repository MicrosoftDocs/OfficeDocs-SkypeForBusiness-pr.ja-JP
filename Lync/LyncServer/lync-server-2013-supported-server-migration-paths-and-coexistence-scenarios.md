---
title: 'Lync Server 2013: サポートされるサーバー移行パスと共存のシナリオ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33b2ce878fef53f444e3834e8b1cd40286c24b0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Lync Server 2013 でサポートされるサーバー移行パスと共存のシナリオ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-16_

Lync Server 2013 は、次のいずれかの移行をサポートしています。

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

これらの以前のバージョンの両方を実行している環境からの移行はサポートされていません。 Microsoft Office Communications Server 2007 や Live Communications Server 2005 などの以前のバージョンからの移行はサポートされていません。 以前の展開にグループチャットが含まれていた場合は、個別に移行する必要があります。

<div>

## <a name="migration-methods"></a>移行方法

すべての Lync Server トポロジとサーバーロールの移行がサポートされます。 Standard Edition server から Enterprise Edition server に移行することで、1つのトポロジから別のトポロジに移行することができます。

Lync Server 2013 は、次の移行方法のみをサポートしています。

  - <span></span>  
    **サイドバイサイド移行。** サイドバイサイドの移行では、Lync Server 2013 は既存の Microsoft Lync Server 2010 または Office Communications Server 2007 R2 の展開と共に展開され、その後、操作を新しいサーバーに移してユーザーを Lync Server 2013 に移行します。 この方法を使うには、移行時にハードウェアやソフトウェアを含めた追加のサーバープラットフォーム、およびシステム名とプール名が新しい構成で異なる必要があります。 以前のバージョンに戻す必要がある場合は、操作を前のサーバーに戻すことができます。

Active Directory ドメインサービスフォレスト間の移行はサポートされていません。

推奨される移行パスは、段階的なアプローチです。 以前のリリースから移行する方法について詳しくは、「段階的なコンポーネントの展開」をご覧ください。移行ドキュメントの次のトピックを参照してください。

  - [Lync Server 2010 から Lync Server 2013 への移行](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Office Communications Server 2007 R2 から Lync Server 2013 への移行](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Lync Server 2010、グループ チャットまたは Office Communicatins Server 2007 R2 グループ チャットから Lync Server 2013、常設チャット サーバーへの移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>共存シナリオ

Lync Server 2013 は、Lync Server 2010 の展開または Office Communications Server 2007 R2 の展開のコンポーネントと共存させることができます。 Lync Server 2010 と Office Communications Server 2007 R2 の両方 (3 つのバージョンの同時展開) での Lync Server 2013 の同時展開はサポートされていません。

以前の Lync Server 2010 または Office Communications Server 2007 R2 の展開が、新しい Lync Server 2013 の展開で一時的に coexists される段階的な移行では、混合バージョンルーティングのサポートは制限されています。 詳細については、移行に関するドキュメントを参照してください。

Lync Server 2013 データベースインスタンスには、Microsoft SQL Server 2008 R2 または Microsoft SQL Server 2012 を実行している個別のコンピューターと個別のコンピューターを使用する必要があります。 Lync Server 2010 または Office Communications Server 2007 R2 フロントエンドプールに使用している Lync Server 2013 フロントエンドプールに対して、同じインスタンスの SQL Server を使用することはできません。 Lync server 2010 または Office Communications Server 2007 R2 を既に展開している展開のために、トポロジビルダーで Lync Server 2013 を定義して構成した場合、トポロジビルダーでは、既に使用されている Lync Server 2013 のインスタンスを定義することはできません。トポロジ。

次のメッセージが表示され、この問題が発生したことを通知する\[メッセージが表示さ\]れます。 "サーバーの sql Server FQDN には、既に sql インスタンスホスティングロール ' ユーザーストア ' が含まれています。"

<div>


> [!NOTE]  
> Lync Server 2013 の展開に初めて導入されたサーバーの役割を展開する場合は、移行ドキュメントと展開ドキュメントの説明に従って既存の展開をアップグレードし、次に示すように新しいサーバーの役割を展開する必要があります。計画ドキュメントと展開ドキュメント。 グループチャットの以前のバージョンを移行する場合は、Lync Server 2010 または Office Communications Server 2007 R2 から他のすべてのコンポーネントを移行するプロセスを完了した後で、最後に移行します。



</div>

特定の共存要件、および Lync Server 2010 または Office Communications Server 2007 R2 および Lync Server 2013 コンポーネントの共存と移行の詳細については、「 [Lync server 2010 から Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) [に移行する」を参照してください。Office Communications Server 2007 R2 から Lync Server 2013 へ](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)の移行に関するドキュメントを参照してください。 クライアントの混在バージョンサポートの詳細については、「 [Lync Server 2013 での以前の展開でサポートされているクライアント](lync-server-2013-supported-clients-from-previous-deployments.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

