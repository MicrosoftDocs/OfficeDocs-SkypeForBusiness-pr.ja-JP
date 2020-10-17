---
title: 'Lync Server 2013: 仲介サーバーコンポーネント'
description: 'Lync Server 2013: 仲介サーバーコンポーネント。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08c11bff3ee7077d991204cda5a9885787c50ec2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568643"
---
# <a name="mediation-server-component-in-lync-server-2013"></a>Lync Server 2013 の仲介サーバーコンポーネント

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

エンタープライズ Voip ワークロードを展開する場合は、Lync Server 2013、仲介サーバーを展開する必要があります。 ここでは、基本機能、依存関係、基本的なトポロジ、および計画ガイドラインについて説明します。

仲介サーバーは、内部の Lync Server 2013、エンタープライズ Voip インフラストラクチャ、公衆交換電話網 (PSTN) ゲートウェイ、またはセッション開始プロトコル (SIP) トランク間のメディアの信号と、一部の構成におけるメディアを変換します。 Lync Server 2013 側では、仲介サーバーは単一の相互 TLS (MTLS) トランスポートアドレスでリッスンします。 ゲートウェイ側では、トポロジ ドキュメントで定義されたトランクに関連付けられているすべてのリッスン ポートをリッスンします。 すべての認定ゲートウェイが TLS をサポートしている必要がありますが、TCP を有効にすることもできます。 TLS をサポートしないゲートウェイのために TCP がサポートされています。

環境内に既存の構内交換業者 (PBX) がある場合、仲介サーバーはエンタープライズ Voip ユーザーと PBX 間の通話を処理します。 PBX が ip-pbx の場合は、PBX と仲介サーバーの間に直接 SIP 接続を作成できます。 PBX が Time ディビジョン多重 (TDM) PBX である場合は、仲介サーバーと PBX の間に PSTN ゲートウェイを展開する必要もあります。

既定では、仲介サーバーはフロントエンドサーバーと併置されています。 パフォーマンス上の理由で、仲介サーバーをスタンドアロンプールに展開したり、SIP トランキングを展開したりすることもできます。この場合、スタンドアロンプールを使用することを強くお勧めします。

メディア バイパスと DNS 負荷分散をサポートする認定 PSTN ゲートウェイに直接 SIP 接続を展開する場合、スタンドアロンのfea-mediation-poolは必要ありません。 スタンドアロンの仲介サーバー プールが必要でないのは、認定ゲートウェイが仲介サーバーのプールへの DNS 負荷分散に対応しており、プール内のすべての仲介サーバーからトラフィックを受信できるからです。

また、IP-PBX を展開している場合またはインターネット テレフォニー サーバー プロバイダーのセッション ボーダー コントローラー (SBC) に接続する場合に、以下のどちらかの条件に一致するときは、フロントエンド プールに仲介サーバーを併置することをお勧めします。

  - IP-PBX または SBC は、プール内の任意の仲介サーバーからのトラフィックを受信するように構成されており、プール内のすべての仲介サーバーにトラフィックを均等にルーティングできる。

  - Ip-pbx はメディアバイパスをサポートしていませんが、仲介サーバーをホストしているフロントエンドプールは、メディアバイパスが適用されない通話の音声トランスコーディングを処理できます。

Microsoft Lync Server 2013、計画ツールを使用して、仲介サーバーを併置するフロントエンドプールが負荷を処理できるかどうかを評価できます。 これらの要件に適合しない環境では、スタンドアロン仲介サーバー プールを展開する必要があります。

仲介サーバーの主な機能は次のとおりです。

  - Lync Server 側での SRTP の暗号化と復号化

  - TCP 上の SIP (TLS がサポートされないゲートウェイ用) の相互 TLS 上の SIP への変換。

  - Lync Server と仲介サーバーのゲートウェイピアとの間のメディアストリームの変換

  - ネットワーク外部のクライアントから内部 ICE コンポーネントへの接続。これにより、メディアは NAT およびファイアウォールを通過できます。

  - ゲートウェイがサポートしていない通話フロー (エンタープライズ Voip クライアントでのリモートワーカーからの呼び出しなど) の仲介者としての役割を果たす

  - SIP トランキングを含む展開での SIP トランキング サービス プロバイダーとの連携による PSTN のサポートの提供。これにより、PSTN ゲートウェイを使用する必要がなくなります。

次の図は、基本的な PSTN ゲートウェイおよびエンタープライズ Voip インフラストラクチャと通信するときに仲介サーバーによって使用される信号およびメディアプロトコルを示しています。

**仲介サーバーで使用される信号およびメディアのプロトコル**

![仲介サーバーのプロトコルの図](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "仲介サーバーのプロトコルの図")

<div>


> [!NOTE]  
> PSTN ゲートウェイと仲介サーバーの間のネットワークで TCP または RTP/RTCP (SRTP または SRTP ではなく) を使用している場合は、ネットワークのセキュリティとプライバシーを確保するために対策を講じることをお勧めします。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 の M:N トランク](lync-server-2013-m-n-trunk.md)

  - [Lync Server 2013 での通話受付管理と仲介サーバー](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [Lync Server 2013 の拡張 9-1-1 (E9-1-1) および仲介サーバー](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Lync Server 2013 のメディアバイパスと仲介サーバー](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Lync Server 2013 の仲介サーバーのコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Lync Server 2013 の仲介サーバーの展開ガイドライン](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

