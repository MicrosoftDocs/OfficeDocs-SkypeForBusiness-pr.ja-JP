---
title: 'Lync Server 2013: 通話受付制御の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86961c9f282e1a486bf7cf94eda494d37c415cf6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a>Lync Server 2013 での通話受付制御の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

通話受付制御 (CAC) は、使用可能な帯域幅に基づいてリアルタイムのセッションを確立して、混雑したネットワークのユーザーに対して低品質のオーディオ/ビデオ品質を防ぐことができるかどうかを決定するソリューションです。 CAC は、オーディオとビデオについてのみリアルタイムのトラフィックを制御し、データトラフィックには影響しません。 既定の WAN パスに必要な帯域幅がない場合、CAC はインターネットパス経由で通話をルーティングすることがあります。 詳細については、計画ドキュメントの「 [Lync Server 2013 での通話受付制御の計画](lync-server-2013-planning-for-call-admission-control.md)」を参照してください。

このセクションでは、ネットワークで CAC を展開して管理する方法を説明する一連の手順を示します。

<div>


> [!IMPORTANT]  
> CAC を展開する前に、計画ドキュメントの「 <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Lync Server 2013 での通話受付制御の要件の収集</A>」で説明されているように、エンタープライズネットワークトポロジに必要なすべての情報を収集する必要があります。 また、展開ドキュメントの「 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 でフロントエンドプールまたは Standard Edition サーバーを定義して構成</A>する」で説明されているように、CAC コンポーネントがインストールされ、有効になっていることを確認します。



</div>

<div>


> [!NOTE]  
> このセクションのすべての CAC の展開と管理の例は、Lync Server 管理シェルを使用して実行されます。 代わりに、Lync Server コントロールパネルの [<STRONG>ネットワーク構成</STRONG>] セクションを使用して、CAC を管理することもできます。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 での CAC のネットワーク領域の構成](lync-server-2013-configure-network-regions-for-cac.md)

  - [Lync Server 2013 で帯域幅ポリシープロファイルを作成する](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Lync Server 2013 での CAC 用のネットワークサイトの構成](lync-server-2013-configure-network-sites-for-cac.md)

  - [Lync Server 2013 で、サブネットとネットワークサイトを CAC に関連付ける](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Lync Server 2013 でネットワークの地域リンクを作成する](lync-server-2013-create-network-region-links.md)

  - [Lync Server 2013 でのネットワーク間通信領域ルートの作成](lync-server-2013;-create-network-interregion-routes.md)

  - [Lync Server 2013 でネットワークのサイト間ポリシーを作成する](lync-server-2013-create-network-intersite-policies.md)

  - [Lync Server 2013 で通話受付制御を有効にする](lync-server-2013-enable-call-admission-control.md)

  - [Lync Server 2013 の通話受付制御の展開チェックリスト](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

