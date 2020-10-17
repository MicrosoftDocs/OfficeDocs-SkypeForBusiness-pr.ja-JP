---
title: 'Lync Server 2013: E9-1-1 の概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce1c97914abf8e5db393cd932c0a453885e86a5c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530624"
---
# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Lync Server 2013 の E9-1-1 の概要

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-29_

Microsoft Lync Server 2013 は、Lync クライアントおよび Lync Phone Edition デバイスからの、Enhanced 9-1-1 (E9-1-1) 通話をサポートしています。 E9-1-1 用に Lync Server を構成すると、Lync 2013 または Lync Phone Edition からの緊急電話が、場所情報サービスデータベースからの緊急対応の場所 (ERL) 情報が含まれるようになります。 ERLs は、事務所の建物やその他のマルチテナント施設でより正確な場所を特定するのに役立つ、市民 (つまり、ストリート) アドレスとその他の情報で構成されています。 ユーザーが緊急電話をかけると、Lync Server は、仲介サーバー経由で E9-1-1 サービスプロバイダーに通話オーディオと場所およびコールバック情報をルーティングします。 E9-1-1 サービスプロバイダーは、発信者の都市アドレスを使用して、発信者の場所を提供する公衆安全応答ポイント (PSAP) に通話をルーティングし、PSAP が発信者の ERL を検索するために使用する緊急サービスクエリキー (ESQK) に沿って送信します。

Lync Server は、E9-1-1 サービスプロバイダーへの緊急通話をルーティングするための2つの方法をサポートしています。

  - 対象となる E9-1-1 サービス プロバイダーへのセッション開始プロトコル (SIP) トランク接続

  - 公衆交換電話網 (PSTN) ベースの E9-1-1 サービス プロバイダーへの緊急位置識別番号 (ELIN) ゲートウェイ

SIP トランク E9-1-1 サービスプロバイダーを使用する場合は、ERLs を場所情報サービスデータベースに追加し、E9-1-1 サービスプロバイダーによって保持されているマスターストリートアドレスガイド (MSAG) に対して場所を検証します。 ロケーション情報を含まない通話、またはロケーションが MSAG で確認されていない通話を受けた場合、E9-1-1 サービス プロバイダーは、可能であれば、発信者のロケーションを口頭で確認する特別な訓練を受けたスタッフがいる、国または地域の緊急通話応答センター (ECRC) に通話をルーティングしてから、適切な PSAP に手動でルーティングします (ECRC への Direct-Inward-Diaing (DID) 番号を顧客に提供している E9-1-1 サービス プロバイダーもあります。 この番号は、SIP トランクが何らかの理由で失敗した場合に 9-1-1 通話をルーティングするための代替手段となります) 。

Time ディビジョン多重 (TDM) および IP ベースの構内交換機 (PBX) 電話 (固定の場所が存在する) とは異なり、Lync エンドポイントは非常に多くのモバイルにすることができます。 E9-1-1 機能を展開するときに、Lync Server は発信者の所在地に関係なく、緊急電話を発信者に提供する PSAP にルーティングします。 たとえば、本社がワシントン州レドモンドにあるユーザーがカンザス州ウィチタの支社のコンピューターから緊急電話をかけると、SIP トランクまたは PSTN ベースの E9-1-1 サービス プロバイダーは、その通話をレドモンドではなくウィチタの PSAP にルーティングします。

ELIN ゲートウェイを使用する場合は、場所情報サービスデータベースに ERLs も追加しますが、各場所には ELIN 番号も含めます。 ELIN 番号は、緊急通話中の緊急通話番号になります。 その後で、使用する PSTN 事業者が ELIN を自動ロケーション識別 (ALI) データベースにアップロードすることを確認する必要があります。

<div>


> [!NOTE]  
> Lync に接続されたアナログデバイスでは、場所情報サービスまたは E9-1-1 サービスプロバイダーへの送信場所から場所情報を受信できません。 SIP トランク E9-1-1 サービス プロバイダー オプションを使用し、アナログ電話からの E9-1-1 をサポートする必要がある場合、次の 2 つの方法があります。 
> <UL>
> <LI>
> <P><STRONG>従来の ALI オプション</STRONG> &nbsp; &nbsp; &nbsp;アナログ電話が展開されている各サイトにローカルの PSTN ゲートウェイがあり、それぞれのアナログ電話機に DID がある場合は、プライベートスイッチ/自動場所識別 (ALI) サービスプロバイダーを使用して、アナログデバイスの場所を直接プロビジョニングできます。 この場合は、特別に作成された Lync 音声ポリシーを構成し、アナログ デバイスの連絡先オブジェクトに割り当てることで、その電話からの E9-1-1 通話をローカル ゲートウェイを通じて (E9-1-1 サービス プロバイダーの SIP トランクに通話をルーティングするのではなく) その場所を担当する PSTN プロバイダーに直接ルーティングできます。 緊急電話がかかってくると、PSTN トランクに関連付けられている PS-ALI プロバイダーのデータベースが各アナログ電話の DID を物理ロケーションにマッピングし、その場所を PSAP に提供します。 これらのレコードは、電話が異なる ERL に移動するたびに、PS-ALI サービス プロバイダーが更新する必要があります。</P>
> <LI>
> <P><STRONG>E9-1-1 サービスプロバイダーオプション</STRONG> &nbsp; &nbsp; &nbsp;E9-1-1 サービスプロバイダーによってサポートされている場合は、E9-1-1 サービスプロバイダーを使用して、アナログ電話 DIDs とそれに対応する ERLs を登録することができます。 プロバイダーが PIDF-LO データを含まない Lync Server からの呼び出しを受信した場合、プロバイダーは、呼び出し元の DID 番号に一致するデータベースがあるかどうかを確認できます。 プロバイダーは、データベースから取得された ERL を使用して、自動的に緊急通話を適切な PSAP にルーティングします。また、PSAP は、発信者の場所を参照できるようにするために、ディスパッチャーがアナログデバイスと ESQK レコードを受け取ります。</P></LI></UL>ELIN ゲートウェイ オプションを使用し、アナログ電話からの E9-1-1 をサポートする必要がある場合、前述の 1 つ目のオプションで説明したように、アナログ機器のロケーションを直接 PS-ALI サービス プロバイダーに対してプロビジョニングすることができます。</div>

Lync Server の観点から、E9-1-1 プロセスは次の2つのステージに分けることができます。

  - ステージ 1: 場所の取得

  - ステージ 2: E9-1-1 サービス プロバイダーへの緊急電話のルーティング

このセクションでは、これらのステージがどのように動作するのかを説明します。

クライアントの場所を自動検出するようにインフラストラクチャを構成しようと計画している場合は、まず発信者を場所にマッピングするために使用するネットワーク構成要素を決定する必要があります。 使用可能なオプションの詳細については、「 [Lync Server 2013 で場所を特定するために使用するネットワーク要素の定義](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)」を参照してください。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での場所の取得](lync-server-2013-acquiring-a-location.md)

  - [Lync Server 2013 での SIP トランクを使用した E9-1-1 通話のルーティング](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Lync Server 2013 の ELIN ゲートウェイを使用した E9-1-1 通話のルーティング](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

