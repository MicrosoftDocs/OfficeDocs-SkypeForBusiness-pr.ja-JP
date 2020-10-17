---
title: 'Lync Server 2013: サポートされているサーバー移行パスと共存のシナリオ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ed7689931cf917c77527266918832ead8bd0a27
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523974"
---
# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Lync Server 2013 でサポートされているサーバー移行パスと共存のシナリオ

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-16_

Lync Server 2013 は、以下のいずれかの移行をサポートしています。

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

これらの以前のバージョンの両方を実行している環境からの移行はサポートされていません。 Microsoft Office Communications Server 2007 または Live Communications Server 2005 などの以前のバージョンからの移行はサポートされていません。 以前の展開にグループチャットが含まれていた場合は、個別に移行する必要があります。

<div>

## <a name="migration-methods"></a>移行方法

すべての Lync Server トポロジおよびサーバーの役割の移行がサポートされています。 Standard Edition サーバーから Enterprise Edition サーバーへのトポロジを含め、あるトポロジから別のトポロジに移行できます。

Lync Server 2013 でサポートされるのは、次の移行方法のみです。

  - <span></span>  
    **並行した移行。** Side-by-side 移行では、Lync Server 2013 が既存の Microsoft Lync Server 2010 または Office Communications Server 2007 R2 展開と共に展開され、その後、運用を新しいサーバーに移行して、ユーザーを Lync Server 2013 に移行します。 この方法では、移行中にハードウェアとソフトウェアを含む追加のサーバープラットフォームが必要です。また、新しい構成ではシステム名とプール名が異なります。 以前のバージョンにロールバックする必要が生じた場合は、操作を以前のサーバーに戻すことができます。

Active Directory ドメインサービスフォレスト間での移行はサポートされていません。

推奨される移行パスは、段階的なアプローチです。 以前のリリースからの移行の詳細については、「移行」のドキュメントの次のトピックを参照してください。

  - [Lync Server 2010 から Lync Server 2013 への移行](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Office Communications Server 2007 R2 から Lync Server 2013 への移行](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Lync Server 2010、グループ チャットまたは Office Communicatins Server 2007 R2 グループ チャットから Lync Server 2013、常設チャット サーバーへの移行](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>共存シナリオ

Lync Server 2013 は、Lync Server 2010 展開または Office Communications Server 2007 R2 展開のコンポーネントと共存できます。 Lync server 2010 と Office Communications Server 2007 R2 (すべてのバージョンの同時展開) の両方で Lync Server 2013 を同時に展開することはサポートされていません。

以前の Lync Server 2010 または Office Communications Server 2007 R2 展開が新しい Lync Server 2013 展開を一時的に coexists する段階的な移行では、混在バージョンルーティングのサポートは制限されています。 詳細については、移行に関するドキュメントを参照してください。

Lync Server 2013 データベースインスタンスでは、Microsoft SQL Server 2008 R2 または Microsoft SQL Server 2012 を実行している独立した別個のコンピューターを使用する必要があります。 Lync Server 2010 または Office Communications Server 2007 R2 フロントエンドプールに使用する Lync Server 2013 フロントエンドプールに対して、同じ SQL Server のインスタンスを使用することはできません。 既に Lync 2010 Server または Office Communications Server 2007 R2 が展開されている展開のために、トポロジビルダーで Lync Server 2013 を定義して構成した場合、トポロジビルダーでは、トポロジで既に使用されている Lync Server 2013 のインスタンスを定義することはできません。

トポロジビルダーでは、次のメッセージが表示されます。この問題については、「 \[ サーバーの sql server の FQDN \] に、sql インスタンスのホストされている役割 ' ユーザーストア ' が既に含まれています。」というメッセージが表示されます。

<div>


> [!NOTE]  
> Lync Server 2013 の展開に新しく追加されたサーバーの役割を展開する場合は、まず、「移行」のドキュメントおよび「展開」のドキュメントで説明されているように既存の展開をアップグレードしてから、「計画」のドキュメントと「展開」のドキュメントで説明されているように、新しいサーバーの役割を展開します。 以前のバージョンのグループチャットを移行する場合は、Lync Server 2010 または Office Communications Server 2007 R2 から他のすべてのコンポーネントを移行するプロセスを完了した後、最後に移行します。



</div>

特定の共存要件および Lync Server 2010 または Office Communications Server 2007 R2 および Lync Server 2013 コンポーネントの共存および移行の詳細については、「移行」のドキュメントの「 [migration From Lync server 2010 To Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) 」および「 [Migration From Office Communications server 2007 R2 to lync server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) 」を参照してください。 クライアントの混合バージョンサポートの詳細については、「 [Lync Server 2013 での以前の展開でサポートされているクライアント](lync-server-2013-supported-clients-from-previous-deployments.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

