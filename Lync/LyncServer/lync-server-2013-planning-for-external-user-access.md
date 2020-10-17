---
title: 'Lync Server 2013: 外部ユーザーアクセスの計画'
description: 'Lync Server 2013: 外部ユーザーアクセスの計画。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8f1854791ed837b963d4c80f3467e4e89555592
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562783"
---
# <a name="planning-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013 での外部ユーザーアクセスの計画

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-19_

ほとんどの組織の通信には、内部ネットワーク外のサービスやユーザーが関与しています。 これらのサービスやユーザーには、一時的または恒久的にオフサイトにいる従業員、顧客組織やパートナー組織の従業員、パブリック インスタント メッセージング (IM) サービスの利用者、会議やプレゼンテーションに招待した見込み顧客やパートナー、匿名ユーザーなどが含まれます。 このドキュメントでは、これらの人々を総称して外部ユーザー** と呼びます。

Microsoft Lync Server 2013 を使用すると、組織内のユーザーは IM とプレゼンスを使用して外部ユーザーと通信することができ、オフサイトの従業員やその他の種類の外部ユーザーとの音声ビデオ (A/V) 会議や web 会議に参加できます。 モバイル デバイスからの外部アクセスや、エンタープライズ VoIP を利用した外部アクセスもサポートできます。 組織のメンバーではない外部ユーザーは、Lync Server 2013 の会議に参加して、匿名の出席者を許可することができます。

組織のファイアウォール間での通信をサポートするには、wan Server 2013 エッジサーバーを境界ネットワーク (DMZ、非武装地帯、スクリーンサブネットとも呼ばれます) に展開します。 エッジサーバーは、ファイアウォールの外側にあるユーザーが内部の Lync Server 2013 展開に接続する方法を制御します。 ファイアウォールの内側から発信された外部ユーザーへの通信も制御します。

要件に応じて、1 つまたは複数の場所に、1 つまたは複数のエッジ サーバーを展開できます。 このセクションでは、Lync Server 2013 の外部ユーザーアクセスのシナリオと、エッジおよびリバースプロキシトポロジを計画する方法について説明します。

<div>


> [!NOTE]  
> エンタープライズ Voip と外部ユーザーアクセスをサポートするエッジサーバーが必要ですが、このセクションでは IM、プレゼンス、音声ビデオ会議、フェデレーション、web 会議、Lync Mobile のサポートに焦点を当てます。 エンタープライズ Voip のサポートの詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-enterprise-voice.md">planning For Enterprise voice In Lync Server 2013</A> 」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [エッジサーバーの計画に影響する Lync Server 2013 の変更点](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Lync Server 2013 の外部ユーザーアクセスコンポーネントのシステム要件](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Lync Server 2013 の外部ユーザーアクセスの概要](lync-server-2013-overview-of-external-user-access.md)

  - [Lync Server 2013 の自動検出について](lync-server-2013-understanding-autodiscover.md)

  - [Lync Server 2013 でのトポロジの選択](lync-server-2013-choosing-a-topology.md)

  - [Lync Server 2013 のデータ収集](lync-server-2013-data-collection.md)

  - [Lync Server 2013 の DNS 要件を決定する](lync-server-2013-determine-dns-requirements.md)

  - [Lync Server 2013 の外部の音声ビデオファイアウォールおよびポートの要件を決定する](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Lync Server 2013 でエッジサーバー証明書を計画する](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Lync Server 2013 での外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

