---
title: 'Lync Server 2013: ブランチサイトの復元機能'
description: 'Lync Server 2013: ブランチサイトの復元機能。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a498751ce99d0e8e85d6cbe53915c864e64440bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552203"
---
# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Lync Server 2013 のブランチサイトの復元機能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-10_

ブランチ サイトに復元性を提供する場合、ブランチ サイトで中央サイトへの WAN 接続に障害が発生したり、中央サイトが到達不能なときに、次の音声機能を引き続き使用できる必要があります。

<div>


  - 着信と発信の公衆交換電話網 (PSTN) 通話

  - 同じサイトおよび 2 つの異なるサイト間でのユーザー同士のエンタプライズ通話

  - 通話の保留、取得、転送などの基本的な通話処理

  - 2 者間のインスタント メッセージング

  - 着信の転送、エンドポイントの同時呼び出し、通話委任、およびチーム呼び出しサービス。ただし、委任者と代理人 (管理者と管理スタッフなど) またはすべてのチーム メンバーが同じサイトに構成されている場合のみ

  - 詳細な通話の記録 (CDR)

  - 自動応答アテンダントを使用した PSTN ダイヤルイン会議

  - ボイスメールの再ルーティング設定を構成する場合は、ボイスメール機能。 (詳細については、「 [Lync Server 2013 のブランチサイトの復元要件](lync-server-2013-branch-site-resiliency-requirements.md)」を参照してください)。

  - ユーザーの認証と権限の付与

次の機能は、復元ソリューションがブランチサイトの Lync Server のフルスケール展開である場合にのみ使用できます。

  - IM、Web、音声ビデオ会議

  - プレゼンスおよび応答不可 (DND) ベースのルーティング (通話は DND がアクティブになっている内線番号で呼び出し音が鳴らない)

  - 着信の転送設定の更新

  - 応答グループアプリケーションとコールパークアプリケーション

  - 新しい電話とクライアントのプロビジョニングは、ブランチサイトに Active Directory ドメインサービスが存在する場合にのみ行います。

  - Enhanced 9-1-1 (E9-1-1)
    
    E9-1-1 が展開されており、WAN リンクがダウンしているために中央サイトの SIP トランクが使用できない場合、存続可能ブランチアプライアンスは E9-1-1 呼び出しをローカルブランチゲートウェイにルーティングします。 この機能を有効にするには、WAN に障害が発生した場合、ブランチ サイトのユーザーの音声ポリシーにより、ローカルのゲートウェイに通話をルーティングする必要があります。

<div>


> [!NOTE]  
> SBA (存続可能 branch office) は XMPP ではサポートされていません。 SBA 構成に所属するユーザーは、Im を送信したり、XMPP の連絡先でプレゼンスを表示したりすることはできません。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

