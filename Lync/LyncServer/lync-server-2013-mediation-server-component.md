---
title: 'Lync Server 2013: 仲介サーバーコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1f3476f8b4e99b2abccb67f1d75446a126df03d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a>Lync Server 2013 の仲介サーバーコンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

エンタープライズボイスのワークロードを展開する場合は、Lync Server 2013 の仲介サーバーを展開する必要があります。 このセクションでは、基本的な機能、依存関係、基本的なトポロジ、計画ガイドラインについて説明します。

仲介サーバーは、内部の Lync Server 2013、エンタープライズ Voip インフラストラクチャ、公衆交換電話網 (PSTN) ゲートウェイ、またはセッション開始プロトコル (SIP) トランク間のメディアの変換を行います。 Lync Server 2013 側では、仲介サーバーが単一の相互 TLS (MTLS) トランスポートアドレスでリッスンします。 ゲートウェイ側では、仲介サーバーは、トポロジドキュメントで定義された trunks に関連付けられているすべての関連するリッスンポートをリッスンします。 すべての認定ゲートウェイが TLS をサポートしている必要がありますが、TCP を有効にすることもできます。 TLS をサポートしないゲートウェイのために TCP がサポートされています。

環境に既存のパブリックブランチ Exchange (PBX) がインストールされている場合は、仲介サーバーがエンタープライズボイスユーザーと PBX 間の通話を処理します。 PBX が ip-pbx の場合は、PBX と仲介サーバーの間の直接 SIP 接続を作成できます。 お使いの PBX が Time ディビジョンマルチプレクシング (TDM) PBX である場合は、仲介サーバーと PBX 間の PSTN ゲートウェイも展開する必要があります。

仲介サーバーは、既定でフロントエンドサーバーと連携しています。 また、仲介サーバーは、パフォーマンス上の理由から単体プールに展開することもできます。 SIP トランクを展開する場合は、スタンドアロンプールを強くお勧めします。

メディアバイパスと DNS の負荷分散をサポートする限定 PSTN ゲートウェイに直接 SIP 接続を展開する場合、スタンドアロンの仲介サーバープールは必要ありません。 認定ゲートウェイは、仲介サーバーのプールに対する DNS 負荷分散をサポートし、プール内の任意の仲介サーバーからトラフィックを受信できるため、スタンドアロンの仲介サーバープールは必要ありません。

また、次の条件のいずれかが満たされている限り、IP Pbx を展開した場合、またはインターネットテレフォニーサーバープロバイダーのセッションボーダーコントローラー (SBC) に接続している場合は、仲介サーバーをフロントエンドプールで検索することをお勧めします。

  - IP PBX または SBC は、プール内の任意の仲介サーバーからトラフィックを受信し、プール内のすべての仲介サーバーに一律にトラフィックをルーティングできるように構成されています。

  - IP-PBX ではメディアのバイパスはサポートされていませんが、仲介サーバーをホストしているフロントエンドプールは、どのメディアのバイパスが適用されないかを呼び出します。

Microsoft Lync Server 2013 の計画ツールを使用すると、仲介サーバーを配置するフロントエンドプールが負荷を処理できるかどうかを評価することができます。 環境がこれらの要件を満たしていない場合は、スタンドアロンの仲介サーバープールを展開する必要があります。

仲介サーバーの主な機能は次のとおりです。

  - Lync Server 側での SRTP の暗号化と暗号化解除

  - TCP 経由の SIP (TLS をサポートしていないゲートウェイ用) を相互 TLS 経由の SIP に変換する

  - Lync Server と仲介サーバーのゲートウェイピアの間でのメディアストリームの翻訳

  - ネットワーク外のクライアントを内部の ICE コンポーネントに接続して、NAT およびファイアウォールのメディアトラバーサルを有効にする

  - エンタープライズボイスクライアントでのリモートワーカーからの通話など、ゲートウェイでサポートされていないコールフローの中継として機能する

  - SIP トランクを含む展開では、pstn のサポートを提供するために SIP トランクサービスプロバイダを使用して、PSTN ゲートウェイの必要性を排除します。

次の図は、基本的な PSTN ゲートウェイとエンタープライズ Voip インフラストラクチャと通信するときに、仲介サーバーによって使用されるシグナリングとメディアプロトコルを示しています。

**仲介サーバーで使用される信号およびメディアのプロトコル**

![仲介サーバーのプロトコルの図](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "仲介サーバーのプロトコルの図")

<div>


> [!NOTE]  
> PSTN ゲートウェイと仲介サーバー間のネットワークで TCP または RTP/RTCP (SRTP または SRTP の代わりに) を使用している場合は、ネットワークのセキュリティとプライバシーの確保に役立つ対策を講じることをお勧めします。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 の M:N トランク](lync-server-2013-m-n-trunk.md)

  - [Lync Server 2013 の通話受付管理と仲介サーバー](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [Lync Server 2013 の Enhanced 9-1-1 (E9-1-1) と仲介サーバー](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [Lync Server 2013 のメディア バイパスと仲介サーバー](lync-server-2013-media-bypass-and-mediation-server.md)

  - [Lync Server 2013 の仲介サーバーのコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [Lync Server 2013 での仲介サーバーの展開ガイドライン](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

