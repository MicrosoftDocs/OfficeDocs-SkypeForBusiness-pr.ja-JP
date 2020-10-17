---
title: 'Lync Server 2013: 仲介サーバーの展開とピアの定義'
description: 'Lync Server 2013: 仲介サーバーの展開とピアの定義を行います。'
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
ms.openlocfilehash: fc3afce038371920beea1cc52549d8d027429e08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545233"
---
# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>Lync Server 2013 での仲介サーバーの展開とピアの定義

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

エンタープライズ Voip ワークロード、ダイヤルイン会議、および高度なエンタープライズ Voip アプリケーション (応答グループアプリケーション、コールパークアプリケーション、通話受付管理 (CAC) など) は、フロントエンドプールで利用できます。 Lync Server 2013 では、仲介サーバーの機能はフロントエンドサーバーに組み込まれています。 独立したスタンドアロンの仲介サーバーは不要になりました。 フロントエンドプールは、サポートされているゲートウェイ (公衆交換電話網 (PSTN) ゲートウェイまたは ip-pbx) と直接通信することができ、仲介サーバーが仲介者として機能する必要性を排除します。

唯一の例外は、インターネット テレフォニー サービス プロバイダーのセッション ボーダー コントローラーに接続する SIP トランクを構成する場合です。 エンタープライズ Voip インフラストラクチャを SIP トランクプロバイダーに接続するには、個別の仲介サーバーを展開する必要があります。

Lync Server (フロントエンドプールまたはスタンドアロン仲介サーバー上の仲介サーバーコンポーネント) とゲートウェイとの間の接続は、 *トランク*と呼ばれる論理的な関連付けとして定義されます。 このセクションのトピックでは、トランクを定義する方法と、SIP トランクに接続する場合にスタンドアロンの仲介サーバーを展開する方法について説明します。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 のトポロジビルダーでの仲介サーバーの定義](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Lync Server 2013 のトポロジビルダーでゲートウェイを定義する](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Lync Server 2013 での仲介サーバーのファイルのインストール](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Lync Server 2013 のトポロジビルダーでの追加トランクの定義](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>関連情報

[Lync Server 2013 でのダイヤルイン会議の構成](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

