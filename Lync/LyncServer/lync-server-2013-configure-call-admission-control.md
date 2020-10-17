---
title: 'Lync Server 2013: 通話受付管理の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1edac7fe7b3b56cdaa5324f1c6e976bfb0b746fe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517664"
---
# <a name="configure-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 で通話受付管理を構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

通話受付管理 (CAC) は、使用可能な帯域幅に基づいてリアルタイムセッションを確立して、混雑したネットワーク上のユーザーの音声/ビデオの品質が低下しないようにするかどうかを決定するソリューションです。 CAC は、音声とビデオのリアルタイムトラフィックのみを制御し、データトラフィックには影響を与えません。 既定の WAN パスに必要な帯域幅がない場合、CAC はインターネットパス経由で通話をルーティングすることがあります。 詳細については、「計画」のドキュメントの「 [Lync Server 2013 での通話受付管理の計画](lync-server-2013-planning-for-call-admission-control.md) 」を参照してください。

ここでは、ネットワークに CAC を展開して管理する方法を例示する一連の手順例を示します。

<div>


> [!IMPORTANT]  
> CAC を展開する前に、「計画」のドキュメントの「 <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Lync Server 2013 での通話受付管理の要件の収集</A> 」の説明に従って、エンタープライズネットワークトポロジに必要なすべての情報を収集する必要があります。 また、「展開」のドキュメントの「 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 でのフロントエンドプールまたは Standard Edition サーバーの定義と構成</A> 」の説明に従って、CAC コンポーネントがインストールされ、アクティブ化されていることを確認してください。



</div>

<div>


> [!NOTE]  
> このセクションのすべての CAC の展開と管理の例は、Lync Server 管理シェルを使用して実行されます。 別の方法として、Lync Server コントロールパネルの [ <STRONG>ネットワーク構成</STRONG> ] セクションを使用して CAC を管理することもできます。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 で CAC のネットワーク地域を構成する](lync-server-2013-configure-network-regions-for-cac.md)

  - [Lync Server 2013 での帯域幅ポリシープロファイルの作成](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Lync Server 2013 で CAC のネットワークサイトを構成する](lync-server-2013-configure-network-sites-for-cac.md)

  - [Lync Server 2013 での CAC のネットワークサイトへのサブネットの関連付け](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Lync Server 2013 でのネットワーク地域リンクの作成](lync-server-2013-create-network-region-links.md)

  - [Lync Server 2013 でのネットワーク地域間ルートの作成](lync-server-2013;-create-network-interregion-routes.md)

  - [Lync Server 2013 でのネットワークサイト間ポリシーの作成](lync-server-2013-create-network-intersite-policies.md)

  - [Lync Server 2013 で通話受付管理を有効にする](lync-server-2013-enable-call-admission-control.md)

  - [Lync Server 2013 の通話受付管理の展開チェックリスト](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

