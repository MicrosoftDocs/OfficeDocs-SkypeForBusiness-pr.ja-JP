---
title: 'Lync Server 2013: E9-1-1 の概要'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 144f189c119653ddb02316193e78b9156fad2278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a>Lync Server 2013 の E9-1-1 の概要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-29_

Microsoft Lync Server 2013 は、Lync クライアントおよび Lync Phone Edition デバイスからの拡張 9-1-1 (E9) 通話をサポートしています。 Lync Server for E9-1-1 を構成すると、Lync 2013 または Lync Phone Edition から発信された緊急通報の情報が、場所情報サービスデータベースから発信されます。 ERLs は、事務所の建物やその他のマルチテナント機能のより正確な場所を特定するのに役立つ、市民 (つまり、番地) とその他の情報で構成されています。 ユーザーが緊急通話を発信すると、Lync Server は、仲介サーバー経由で E9 1-1 サービスプロバイダーに通話の音声を転送します。 E9 サービスプロバイダーは、呼び出し元の都市のアドレスを使って、発信者の位置情報を提供している公共の安全性応答ポイント (PSAP) に呼び出しをルーティングし、さらに、PSAP が呼び出し元の ERL を検索するために使用する緊急サービスクエリキー (ESQK) を送信します。

Lync Server では、E9 サービスプロバイダーへの緊急通話のルーティング方法として、次の2つの方法がサポートされています。

  - 対象となる E9-1-1 サービス プロバイダーへのセッション開始プロトコル (SIP) トランク接続

  - 公衆交換電話網 (PSTN) ベースの E9-1-1 サービス プロバイダーへの緊急位置識別番号 (ELIN) ゲートウェイ

SIP トランク E9 サービスプロバイダを使用する場合は、Location Information service データベースに ERLs を追加してから、E9 サービスプロバイダーによって管理されているマスターの住所ガイド (MSAG) に対して場所を検証します。 ロケーション情報を含まない通話、またはロケーションが MSAG で確認されていない通話を受けた場合、E9-1-1 サービス プロバイダーは、可能であれば、発信者のロケーションを口頭で確認する特別な訓練を受けたスタッフがいる、国または地域の緊急通話応答センター (ECRC) に通話をルーティングしてから、適切な PSAP に手動でルーティングします (PSTN への Direct-Inward-Diaing (DID) 番号を顧客に提供している E9-1-1 サービス プロバイダーもあります。 この番号は、SIP トランクが何らかの理由で失敗した場合に 9-1-1 通話をルーティングするための代替手段となります)。

Time ディビジョン多重 (TDM) と IP ベースの構内交換 (PBX) 電話とは異なり、Lync のエンドポイントは、非常にモバイルです。 E9 機能を展開すると、発信者がどこにいるかに関係なく、Lync Server によって、発信者の位置情報を提供している PSAP に緊急通話をルーティングすることができます。 たとえば、本社がワシントン州レドモンドにあるユーザーがカンザス州ウィチタの支社のコンピューターから緊急電話をかけると、SIP トランクまたは PSTN ベースの E9-1-1 サービス プロバイダーは、その通話をレドモンドではなくウィチタの PSAP にルーティングします。

ELIN ゲートウェイを使用している場合は、場所情報サービスデータベースに ERLs も追加しますが、それぞれの場所には ELIN 番号も含めます。 ELIN 番号は、緊急通話中の緊急通話番号になります。 その後で、使用する PSTN 事業者が ELIN を自動ロケーション識別 (ALI) データベースにアップロードすることを確認する必要があります。

<div>


> [!NOTE]  
> Lync に接続されたアナログデバイスでは、位置情報サービスから、または E9 のサービスプロバイダーへの送信場所に関する情報を受信できません。 SIP トランク E9-1-1 サービス プロバイダー オプションを使用し、アナログ電話からの E9-1-1 をサポートする必要がある場合、次の 2 つの方法があります。 
> <UL>
> <LI>
> <P><STRONG>従来の PS-ALI オプション</STRONG>&nbsp;&nbsp;&nbsp;アナログ電話が配備され、それぞれのアナログ電話があれば、各サイトにローカルの PSTN ゲートウェイがある場合は、プライベートスイッチを使って直接アナログデバイスの場所をプロビジョニングできます。位置情報の識別 (PS-ALI) サービスプロバイダー。 この場合は、特別な細工をした Lync voice のポリシーを構成して、それらをアナログデバイスの連絡先オブジェクトに割り当てて、ローカルゲートウェイからサイトをサービスする PSTN プロバイダー (ルーティングされるのではなく、ローカルゲートウェイから) に直接通話を発信します。E9-1-1 サービスプロバイダ SIP トランクへの通話。 緊急電話がかかってくると、PSTN トランクに関連付けられている PS-ALI プロバイダーのデータベースが各アナログ電話の DID を物理ロケーションにマッピングし、その場所を PSAP に提供します。 これらのレコードは、電話が異なる ERL に移動するたびに、PS-ALI サービス プロバイダーが更新する必要があります。</P>
> <LI>
> <P><STRONG>E9 サービスプロバイダオプション</STRONG>&nbsp;&nbsp;&nbsp;: E9 サービスプロバイダでサポートされている場合は、アナログ電話の dids と、対応する erls を E9 サービスプロバイダに登録することができます。 プロバイダーが、PIDF データが含まれていない Lync Server からの通話を受信した場合、プロバイダーは、通話相手の DID 番号に一致するデータベースがあるかどうかを確認できます。 データベースから取得した ERL を使うことで、プロバイダーは緊急通話を適切な PSAP に自動的にルーティングすることができます。また、PSAP は、ディスパッチャーが呼び出し元の場所を参照できるようにする、アナログデバイスと ESQK レコードを受け取ります。</P></LI></UL>ELIN ゲートウェイ オプションを使用し、アナログ電話からの E9-1-1 をサポートする必要がある場合、前述の 1 つ目のオプションで説明したように、アナログ機器のロケーションを直接 PS-ALI サービス プロバイダーに対してプロビジョニングすることができます。</div>

Lync Server の観点から、E9 プロセスは次の2つのステージに分けることができます。

  - ステージ 1: 場所の取得

  - ステージ 2: E9-1-1 サービス プロバイダーへの緊急電話のルーティング

このセクションでは、これらのステージがどのように動作するのかを説明します。

クライアントの場所を自動検出するようにインフラストラクチャを構成しようと計画している場合は、まず発信者を場所にマッピングするために使用するネットワーク構成要素を決定する必要があります。 使用可能なオプションの詳細については、「 [Lync Server 2013 で場所を決定するために使用されるネットワーク要素を定義する](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)」を参照してください。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 での場所の取得](lync-server-2013-acquiring-a-location.md)

  - [Lync Server 2013 での SIP トランクを使用した E9-1-1 通話のルーティング](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [Lync Server 2013 での ELIN ゲートウェイを使用した E9-1-1 通話のルーティング](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

