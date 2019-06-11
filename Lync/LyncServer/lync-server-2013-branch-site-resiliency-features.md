---
title: 'Lync Server 2013: ブランチ サイトの復元機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e452dc297a79525b587d13aa58ed1e1270d41aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Lync Server 2013 のブランチ サイトの復元機能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-10_

ブランチ サイトに復元性を提供する場合、ブランチ サイトで中央サイトへの WAN 接続に障害が発生したり、中央サイトが到達不能であったりする場合に、次の音声機能を引き続き使用できる必要があります。

<div>


  - 着信と発信の公衆交換電話網 (PSTN) 通話

  - 同じサイトおよび 2 つの異なるサイト間でのユーザー同士のエンタープライズ通話

  - 通話の保留、取得、転送などの基本的な通話処理

  - 2 者間のインスタント メッセージング

  - 着信の転送、エンドポイントの同時呼び出し、通話委任、およびチーム呼び出しサービス。ただし、委任者と代理人 (管理者と管理スタッフなど) またはすべてのチーム メンバーが同じサイトに構成されている場合のみ

  - 詳細な通話の記録 (CDR)

  - 自動応答アテンダントを使用した PSTN ダイヤルイン会議

  - ボイス メール機能 (ボイス メール ルーティング設定を構成している場合) (詳しくは、「 [Lync Server 2013 のブランチサイトの回復性の要件](lync-server-2013-branch-site-resiliency-requirements.md)」をご覧ください)。

  - ユーザーの認証と権限の付与

以下の機能は、回復可能なソリューションがブランチサイトでのフルスケールの Lync Server 展開である場合にのみ使用できます。

  - IM、Web、音声ビデオ会議

  - プレゼンスおよび応答不可 (DND) ベースのルーティング (通話は DND がアクティブになっている内線番号で呼び出し音が鳴らない)

  - 着信の転送設定の更新

  - 応答グループアプリケーションとコールパークアプリケーション

  - 新しい固定電話とクライアントのプロビジョニング。ただし、ブランチサイトに Active Directory ドメインサービスが存在する場合に限ります。

  - 拡張 9-1-1 (E9-1-1)
    
    E9 が展開され、中央サイトの SIP トランクが WAN リンクがダウンしているために使用できない場合、Survivable Branch Appliance は、ローカルブランチゲートウェイに E9 1-1 の通話をルーティングします。 この機能を有効にするには、WAN に障害が発生した場合、ブランチ サイトのユーザーの音声ポリシーにより、ローカルのゲートウェイに通話をルーティングする必要があります。

<div>


> [!NOTE]  
> SBA (存続可能ブランチ オフィス) は、XMPP ではサポートされません。 SBA 構成をホームにしているユーザーは、Im を送信したり、XMPP の連絡先とプレゼンスを表示したりすることはできません。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

