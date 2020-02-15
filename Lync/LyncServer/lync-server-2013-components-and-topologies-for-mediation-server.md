---
title: 'Lync Server 2013: 仲介サーバーのコンポーネントとトポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9369c7ab74f19b8ccc53ff0c071e0458b21e6e0f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013 の仲介サーバーのコンポーネントとトポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

このトピックでは、仲介サーバーが依存するコンポーネントと、仲介サーバーを展開するためのトポロジについて説明します。

<div>

## <a name="dependencies"></a>依存関係

仲介サーバーには、次のような依存関係があります。

  - **レジストラー.** 必須です。 レジストラーは、仲介サーバーと Lync Server 2013 ネットワークとの通信における通知の次ホップです。 仲介サーバーは、仲介サーバーのみで構成されるスタンドアロンプールにインストールされるだけでなく、レジストラーと共にフロントエンドサーバーに併置することができます。 レジストラーは、仲介サーバーと、存続可能ブランチアプライアンス上の PSTN ゲートウェイと併置されます。

  - **監視サーバー。** 推奨オプションです。 監視サーバーは、仲介サーバーがメディアセッションに関連付けられている品質指標を記録することを可能にします。

  - **エッジ サーバー。** 外部ユーザー サポートで必要です。 エッジサーバーを使用すると、仲介サーバーは、NAT またはファイアウォールの内側に配置されたユーザーと対話できます。

</div>

<div>

## <a name="topologies"></a>テクノロジ

Lync Server 2013、仲介サーバーは、既定では、Standard Edition サーバー、フロントエンドプール、または存続可能ブランチアプライアンス上のレジストラーのインスタンスに併置されます。 フロントエンドプール内のすべての仲介サーバーは、同じように構成する必要があります。

パフォーマンスが問題になる場合は、専用のスタンドアロンプールに1つ以上の仲介サーバーを展開することをお勧めします。 または、SIP トランキングを展開している場合は、スタンドアロンの仲介サーバープールを展開することをお勧めします。

メディア バイパスと DNS 負荷分散をサポートする認定 PSTN ゲートウェイに直接 SIP 接続を展開する場合、スタンドアロンのfea-mediation-poolは必要ありません。 スタンドアロンの仲介サーバー プールが必要でないのは、認定ゲートウェイが仲介サーバーのプールへの DNS 負荷分散に対応しており、プール内のすべての仲介サーバーからトラフィックを受信できるからです。

また、IP-PBX を展開している場合またはインターネット テレフォニー サーバー プロバイダーのセッション ボーダー コントローラー (SBC) に接続する場合に、以下のどちらかの条件に一致するときは、フロントエンド プールに仲介サーバーを併置することをお勧めします。

  - IP-PBX または SBC は、プール内の任意の仲介サーバーからのトラフィックを受信するように構成されており、プール内のすべての仲介サーバーにトラフィックを均等にルーティングできる。

  - Ip-pbx はメディアバイパスをサポートしていませんが、仲介サーバーをホストしているフロントエンドプールは、メディアバイパスが適用されない通話の音声トランスコーディングを処理できます。

Microsoft Lync Server 2013、計画ツールを使用して、仲介サーバーを併置するフロントエンドプールが負荷を処理できるかどうかを評価できます。 これらの要件に適合しない環境では、スタンドアロン仲介サーバー プールを展開する必要があります。

展開するトポロジの詳細については、「 [Lync server 2013 の仲介サーバーの展開ガイドライン](lync-server-2013-deployment-guidelines-for-mediation-server.md)」を参照してください。

次の図は、WAN リンクで接続された 2 つのサイトからなる簡単なトポロジを示しています。 サイト1のフロントエンドプールのレジストラーと仲介サーバーが併置されます。 サイト1の仲介サーバーは、サイト1の PSTN ゲートウェイとサイト2のゲートウェイの両方を制御します。 このトポロジでは、サイトおよび地域情報を使用できるようにメディア バイパスがグローバルに有効になっていて、各 PSTN ゲートウェイ (GW1 と GW2) へのトランクはバイパスが有効になっています。

**仲介サーバーがサイト 1 にあり、PSTN ゲートウェイがサイト 2 にある、WAN リンクで接続されたサイトの例**

![仲介サーバーの WAN ゲートウェイを使用した音声トポロジ](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "仲介サーバーの WAN ゲートウェイを使用した音声トポロジ")

次の図は、サイト1のフロントエンドプールのレジストラーに仲介サーバーが併置され、サイト1の IP-PBX への直接 SIP 接続がある単純なトポロジを示しています。 この図では、仲介サーバーはサイト2の PSTN ゲートウェイも制御します。 サイト1と2の両方に Lync ユーザーが存在するとします。 また、ip-pbx によって制御されるメディアエンドポイントに送信される前に、Lync エンドポイントから送信されるすべてのメディアでスキャンする必要がある、関連付けられたメディアプロセッサが ip-pbx にあると仮定します。 このトポロジでは、サイトおよび地域情報を使用できるようにメディア バイパスがグローバルに有効になっていて、PBX と PSTN ゲートウェイへのトランクはバイパスが有効になっています。

**仲介サーバーがサイト 1 にあり、PBX がサイト 2 にある、WAN リンクで接続されたサイトの例**

![音声トポロジ仲介サーバーの WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "音声トポロジ仲介サーバーの WAN PBX")

PBX トポロジの計画の詳細については、「lync server [2013 の仲介サーバーの展開ガイドライン](lync-server-2013-deployment-guidelines-for-mediation-server.md)」と「 [Direct SIP Deployment Options in lync server 2013](lync-server-2013-direct-sip-deployment-options.md)」を参照してください。

このトピックの最後の図は、仲介サーバーがインターネットテレフォニーサービスプロバイダーの SBC に接続されているトポロジを示しています。 SIP トランクトポロジの詳細については、「 [Lync Server 2013 の sip トランキング](lync-server-2013-sip-trunking.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

