---
title: 'Lync Server 2013: 外部ユーザー アクセスの計画'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76d4853e7e748128214fc93b721a59e979af03e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 の外部ユーザー アクセスの計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-19_

ほとんどの組織の通信には、内部ネットワーク内にないサービスやユーザーが関係しています。 これらのサービスとユーザーには、一時的または完全にオフサイトになっている従業員、顧客またはパートナーの組織の従業員、パブリックインスタントメッセージング (IM) サービスを使用しているユーザー、招待する可能性のある顧客、パートナー、匿名ユーザーが含まれます。会議やプレゼンテーションを行うことができます。 このドキュメントでは、これらのユーザーを、"*外部ユーザー*" と総称して示します。

Microsoft Lync Server 2013 では、組織内のユーザーは IM とプレゼンスを使って外部ユーザーと通信できます。また、オフサイトの従業員や他の種類の外部ユーザーとの音声/ビデオ (A/V) 会議や web 会議に参加することができます。 また、モバイルデバイスやエンタープライズ Voip からの外部アクセスをサポートすることもできます。 組織のメンバーではない外部ユーザーは、Lync Server 2013 会議に参加して、匿名の出席者を許可することができます。

組織のファイアウォール間の通信をサポートするには、境界ネットワーク (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます) に Lync Server 2013 エッジサーバーを展開します。 エッジサーバーは、ファイアウォール外のユーザーが内部の Lync Server 2013 展開に接続する方法を制御します。 また、ファイアウォール内で発生する外部ユーザーとの通信も制御します。

必要に応じて、1つ以上の場所に1つ以上のエッジサーバーを展開することができます。 このセクションでは、Lync Server 2013 での外部ユーザーアクセスのシナリオについて説明し、エッジとリバースプロキシトポロジを計画する方法について説明します。

<div>


> [!NOTE]  
> エンタープライズボイスと外部ユーザーのアクセスをサポートするにはエッジサーバーが必要ですが、このセクションでは IM、プレゼンス、A/V 会議、フェデレーション、web 会議、Lync Mobile のサポートについて重点的に説明します。 エンタープライズ Voip のサポートの詳細については、計画ドキュメントの「 <A href="lync-server-2013-planning-for-enterprise-voice.md">Lync Server 2013 でのエンタープライズ voip の計画</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [エッジ サーバーの計画に影響する Lync Server 2013 での変更点](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Lync Server 2013 の外部ユーザー アクセス コンポーネントのシステム要件](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Lync Server 2013 における外部ユーザー アクセスの概要](lync-server-2013-overview-of-external-user-access.md)

  - [Lync Server 2013 での自動検出について](lync-server-2013-understanding-autodiscover.md)

  - [Lync Server 2013 でのトポロジの選択](lync-server-2013-choosing-a-topology.md)

  - [Lync Server 2013 のデータの収集](lync-server-2013-data-collection.md)

  - [Lync Server 2013 の DNS の要件を確認する](lync-server-2013-determine-dns-requirements.md)

  - [Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Lync Server 2013 でエッジ サーバー証明書を計画する](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

