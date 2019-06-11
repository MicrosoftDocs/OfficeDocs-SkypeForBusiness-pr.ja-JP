---
title: System Center Operations Manager を使用するように Lync Server を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server to work with System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205188(v=OCS.15)
ms:contentKeyID: 48185179
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a6f26d4701cf1ed48f0069bcf7994e20ef0b2af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-system-center-operations-manager"></a>System Center Operations Manager と連携するように Lync Server 2013 を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

System Center Operations Manager と連携するように Microsoft Lync Server 2013 インフラストラクチャを構成するには、次の3つの手順を実行する必要があります。

  - プライマリ System Center Operations Manager management server を特定して構成します。 管理サーバーの構成には、System Center Operations Manager 2012 または System Center Operations Manager 2007 R2 のインストール、SQL Server を使用したバックエンドデータベースのセットアップが含まれます。 使用する必要がある実際の SQL Server バージョンは、使用している System Center Operations Manager のバージョンによって異なります。 詳細については、「 [Lync server 2013 でプライマリ管理サーバーを構成する](lync-server-2013-configuring-the-primary-management-server.md)」を参照してください。

  - 監視する Lync Server コンピューターを特定して構成します。 System Center Operations manager を使用して Lync Server コンピューターを監視するには、System Center Operations Manager エージェントファイルをインストールし、各サーバーがプロキシとして動作するように構成する必要があります。

  - Lync Server *watcher ノード*として機能するコンピューターを特定して構成します。 ウォッチャーノードは、Lync Server の代理トランザクションを定期的に実行するコンピューターであり、システムへのログオン機能やインスタントメッセージの交換機能などの主要な Lync Server コンポーネントを確認する Windows PowerShell コマンドレットです。期待どおりに動作します。

このセクションのトピックでは、これらの各タスクを実行するための手順について説明します。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でのプライマリ管理サーバーの構成](lync-server-2013-configuring-the-primary-management-server.md)

  - [Lync Server 2013 管理パックのインストール](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Lync Server 2013 で監視される Lync Server コンピューターを構成する](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Lync Server 2013 でのウォッチャーノードのインストールと構成](lync-server-2013-installing-and-configuring-watcher-nodes.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

