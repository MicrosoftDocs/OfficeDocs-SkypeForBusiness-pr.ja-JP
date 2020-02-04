---
title: 'Lync Server 2013: 仲介サーバーの展開とピアの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b20f5e733dddd34971ca3a5070e99364785e147a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>Lync Server 2013 での仲介サーバーの展開とピアの定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

エンタープライズボイスワークロード、ダイヤルイン会議、高度なエンタープライズボイスアプリケーション (応答グループアプリケーション、コールパークアプリケーション、通話受付制御 (CAC) など) は、フロントエンドプールで利用できます。 Lync Server 2013 では、仲介サーバーの機能がフロントエンドサーバーに組み込まれています。 独立したスタンドアロンの仲介サーバーは必要なくなりました。 フロントエンドプールは、サポートされているゲートウェイ (公衆交換電話網 (PSTN) ゲートウェイまたは IP PBX) と直接通信することができ、仲介サーバーが介在して機能する必要がなくなります。

唯一の例外は、インターネット テレフォニー サービス プロバイダーのセッション ボーダー コントローラーに接続する SIP トランクを構成する場合です。 エンタープライズ Voip インフラストラクチャを SIP トランクプロバイダに接続するには、個別の仲介サーバーを展開する必要があります。

Lync Server (フロントエンドプールまたはスタンドアロンの仲介サーバー上の仲介サーバーコンポーネント) とゲートウェイの間の接続は、*トランク*と呼ばれる論理的な関連付けとして定義されます。 このセクションのトピックでは、SIP トランクに接続している場合に、トランクを定義し、スタンドアロンの仲介サーバーを展開する方法について説明します。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 でのトポロジビルダーでの仲介サーバーの定義](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Lync Server 2013 でのトポロジビルダーでのゲートウェイの定義](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Lync Server 2013 で仲介サーバー用のファイルをインストールする](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Lync Server 2013 のトポロジビルダーで追加の trunks を定義する](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>関連項目

[Lync Server 2013 でのダイヤルイン会議の構成](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

