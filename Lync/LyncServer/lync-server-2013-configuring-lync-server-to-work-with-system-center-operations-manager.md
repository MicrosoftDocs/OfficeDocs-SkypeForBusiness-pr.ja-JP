---
title: System Center Operations Manager と連携するように Lync Server を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 150b240fe0c2be769e407cacecd8440bd4596ae5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506234"
---
# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>Lync Server 2013 を System Center Operations Manager と連携するように構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

System Center Operations Manager と連携するように Microsoft Lync Server 2013 インフラストラクチャを構成するには、次の3つのことを行う必要があります。

  - プライマリ System Center Operations Manager 管理サーバーを識別して構成します。 管理サーバーの構成には、System Center Operations Manager 2012 または System Center Operations manager 2007 R2 のインストール、および SQL Server を使用したバックエンドデータベースの設定が含まれます。 使用する必要がある SQL Server の実際のバージョンは、使用している System Center Operations Manager のバージョンによって異なります。 詳細については、「 [Lync server 2013 でプライマリ管理サーバーを構成する](lync-server-2013-configuring-the-primary-management-server.md)」を参照してください。

  - 監視する Lync Server コンピューターを特定し、構成します。 System Center Operations manager を使用して Lync Server コンピューターを監視するには、System Center Operations Manager エージェントファイルをインストールし、プロキシとして動作するように各サーバーを構成する必要があります。

  - Lync Server *監視ノード*として動作するコンピューターを識別して構成します。 監視ノードは、定期的に Lync Server 代理トランザクションを実行するコンピューターです。これは、Windows PowerShell コマンドレットで、システムへのログオン、またはインスタントメッセージの交換機能などの主要な Lync Server コンポーネントが期待どおりに動作していることを確認します。

このセクションのトピックでは、これらの各タスクを実行するための手順について説明しています。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 でのプライマリ管理サーバーの構成](lync-server-2013-configuring-the-primary-management-server.md)

  - [Lync Server 2013 管理パックのインストール](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Lync Server 2013 で監視される Lync Server コンピューターの構成](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Lync Server 2013 での監視ノードのインストールと構成](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

