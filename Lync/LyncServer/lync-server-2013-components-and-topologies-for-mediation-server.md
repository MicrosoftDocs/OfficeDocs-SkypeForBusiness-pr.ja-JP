---
title: 'Lync Server 2013: 仲介サーバーのコンポーネントとトポロジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f9c353dc65f5e943e082df9321a934ea8f14be1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013 の仲介サーバーのコンポーネントとトポロジ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

このトピックでは、仲介サーバーが依存しているコンポーネントと、仲介サーバーを展開できるトポロジについて説明します。

<div>

## <a name="dependencies"></a>依存関係

仲介サーバーには、次の依存関係があります。

  - **登録.** 必須。 レジストラーは、Lync Server 2013 ネットワークとの仲介サーバー操作での通知の next-hop です。 仲介サーバーはレジストラーと共にフロントエンドサーバーに、また、仲介サーバーのみで構成されている単体プールにインストールすることに注意してください。 レジストラーは、Survivable Branch Appliance で仲介サーバーと PSTN ゲートウェイと連携しています。

  - **サーバーを監視します。** 省略可能ですが、強くお勧めします。 監視サーバーによって、仲介サーバーはそのメディアセッションに関連付けられた品質指標を記録できます。

  - **エッジサーバー。** 外部ユーザーのサポートに必要。 エッジサーバーによって、仲介サーバーが NAT またはファイアウォールの背後にあるユーザーとやり取りできるようになります。

</div>

<div>

## <a name="topologies"></a>トポロジー

既定では、Lync Server 2013 の仲介サーバーは、標準エディションサーバー、フロントエンドプール、または Survivable Branch Appliance 上のレジストラーのインスタンスと連携しています。 フロントエンドプール内のすべての仲介サーバーは、同じように構成する必要があります。

パフォーマンスが問題になる場合は、専用のスタンドアロンプールに1つ以上の仲介サーバーを展開することをお勧めします。 または、SIP トランクを展開している場合は、スタンドアロンの仲介サーバープールを展開することをお勧めします。

メディアバイパスと DNS の負荷分散をサポートする限定 PSTN ゲートウェイに直接 SIP 接続を展開する場合、スタンドアロンの仲介サーバープールは必要ありません。 認定ゲートウェイは、仲介サーバーのプールに対する DNS 負荷分散をサポートし、プール内の任意の仲介サーバーからトラフィックを受信できるため、スタンドアロンの仲介サーバープールは必要ありません。

また、次の条件のいずれかが満たされている限り、IP Pbx を展開した場合、またはインターネットテレフォニーサーバープロバイダーのセッションボーダーコントローラー (SBC) に接続している場合は、仲介サーバーをフロントエンドプールで検索することをお勧めします。

  - IP PBX または SBC は、プール内の任意の仲介サーバーからトラフィックを受信し、プール内のすべての仲介サーバーに一律にトラフィックをルーティングできるように構成されています。

  - IP-PBX ではメディアのバイパスはサポートされていませんが、仲介サーバーをホストしているフロントエンドプールは、どのメディアのバイパスが適用されないかを呼び出します。

Microsoft Lync Server 2013 の計画ツールを使用すると、仲介サーバーを配置するフロントエンドプールが負荷を処理できるかどうかを評価することができます。 環境がこれらの要件を満たしていない場合は、スタンドアロンの仲介サーバープールを展開する必要があります。

展開するトポロジの詳細については、「 [Lync server 2013 での仲介サーバーの展開ガイドライン](lync-server-2013-deployment-guidelines-for-mediation-server.md)」を参照してください。

次の図は、WAN リンクで接続された 2 つのサイトから成る簡単なトポロジを示しています。 仲介サーバーは、サイト1のフロントエンドプールのレジストラーと連携しています。 サイト1の仲介サーバーは、サイト1の PSTN ゲートウェイとサイト2のゲートウェイの両方を制御します。 このトポロジでは、サイトおよび地域情報を使用できるようにメディア バイパスがグローバルに有効になっていて、各 PSTN ゲートウェイ (GW1 と GW2) へのトランクはバイパスが有効になっています。

**仲介サーバーがサイト 1 にあり、PSTN ゲートウェイがサイト 2 にある、WAN リンクで接続されたサイトの例**

![仲介サーバー WAN ゲートウェイを使用した音声トポロジ](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "仲介サーバー WAN ゲートウェイを使用した音声トポロジ")

次の図は、仲介サーバーがサイト1のフロントエンドプールのレジストラーと関連付けられており、サイト1で IP PBX との直接 SIP 接続がある簡単なトポロジを示しています。 この図では、仲介サーバーはサイト2でも PSTN ゲートウェイを制御します。 Lync ユーザーがサイト1と2の両方に存在することを前提とします。 また、IP PBX では、IP PBX によって制御されるメディアエンドポイントに送信する前に、Lync エンドポイントから送信されたすべてのメディアによってスキャンする必要がある関連メディアプロセッサがあることを前提とします。 このトポロジでは、サイトおよび地域情報を使用できるようにメディア バイパスがグローバルに有効になっていて、PBX と PSTN ゲートウェイへのトランクはバイパスが有効になっています。

**仲介サーバーがサイト 1 にあり、PBX がサイト 2 にある、WAN リンクで接続されたサイトの例**

![ボイストポロジ仲介サーバーの WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "ボイストポロジ仲介サーバーの WAN PBX")

PBX トポロジの計画の詳細については、「 [Lync server 2013 の仲介サーバーの展開ガイドライン](lync-server-2013-deployment-guidelines-for-mediation-server.md)」および「 [lync SERVER 2013 の SIP 展開オプション](lync-server-2013-direct-sip-deployment-options.md)」を参照してください。

このトピックの最後の図は、仲介サーバーがインターネットテレフォニーサービスプロバイダーの SBC に接続されているトポロジを示しています。 SIP トランクのトポロジの詳細については、「 [Lync Server 2013 の sip トランク](lync-server-2013-sip-trunking.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

