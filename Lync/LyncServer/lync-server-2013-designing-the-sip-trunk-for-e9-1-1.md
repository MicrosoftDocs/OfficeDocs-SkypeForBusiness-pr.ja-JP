---
title: 'Lync Server 2013: E9-1-1 の SIP トランクの設計'
description: 'Lync Server 2013: E9-1-1 の SIP トランクの設計。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ced3c92cb14739367c4e54da933a536cb66deb08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542603"
---
# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a>Lync Server 2013 での E9-1-1 の SIP トランクの設計

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-03_

Lync Server は、SIP トランクを使用して、緊急電話を E9-1-1 サービスプロバイダーに接続します。 E9-1-1 用の緊急サービス SIP トランクは、1 つのセントラル サイト、複数のセントラル サイト、または各ブランチ サイトにセットアップできます。 ただし、発信者のサイトと緊急サービス SIP トランクをホストするサイト間の WAN リンクが使用できない場合、切断されたサイトのユーザーが発信した通話では、ローカル公衆交換電話網 (PSTN) ゲートウェイ経由で ECRC に通話をルーティングする特別な電話使用法レコードがユーザーの音声ポリシーに必要です。 通話受付管理で同時通話数制限が有効な場合も同様です。

<div>


> [!NOTE]  
> Lync Server 環境で SIP トランクを実装するには、次の2つの方法があります。 
> <UL>
> <LI>
> <P>SIP トランクプロバイダーと通信するために、外向きのパブリックにルーティングされたインターフェイスを使用する、マルチホームの仲介サーバーを使用します。</P>
> <LI>
> <P>仲介サーバーと SIP トランクプロバイダーのサービスとの間には、オンプレミスのセッションボーダーコントローラー (SBC) を使用して、安全な境界点を指定します。</P></LI></UL>後者の方法を選択した場合は、選択する SBC の型とモデルが認定済みであり、SIP INVITE の一部としてプレゼンス情報データ フォーマット位置オブジェクト (PIDF-LO) 場所データの通過がサポートされていることを確認します。 サポートされてない場合、緊急サービスのサービス プロバイダーに到着した通話から場所情報が除去されます。 認定された SBCs の詳細については、「」の「Microsoft Lync 向けのインフラストラクチャ認定」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=248425">https://go.microsoft.com/fwlink/p/?LinkId=248425</A> 。<BR>E9-1-1 サービス プロバイダーは、冗長性を確保するために SBC のペアへのアクセスを提供します。 仲介サーバートポロジと通話ルーティング構成に関していくつかの決定を行う必要があります。 たとえば、2 つの SBC を同等のピアとして扱い、SBC 間の通話にラウンドロビン ルーティングを使用するのか、または一方の SBC をプライマリ、もう一方をセカンダリとして指定するのかを決定します。



</div>

Lync Server での SIP トランクの展開の詳細については、「 [Lync server 2013 で sip トランキングを実装する方法](lync-server-2013-how-do-i-implement-sip-trunking.md)」を参照してください。 E9-1-1 用 SIP トランクの展開方法を決定する際に次の質問が役立ちます。

  - **SIP トランクの展開に、専用接続を使用するか、それとも共有のインターネット接続を使用するか。**  
    緊急電話は常につながることが重要です。専用線で接続すれば、ネットワーク上の他のトラフィックによって回線が専有されることがなくなり、サービス品質 (QoS) も実装できます。パブリック インターネット経由で緊急サービスのサービス プロバイダーに接続し、緊急電話の機密性を保証する必要がある場合は、IPsec 暗号化が必要です。

<!-- end list -->

  - **E9-1-1 展開は、障害許容を目的として設計されていますか?**  
    これは緊急時向けのソリューションなので、回復性が重要です。 プライマリおよびセカンダリの仲介サーバーと SIP トランクを、障害に対する耐性のある場所に展開します。 サポートしているユーザーに最も近いプライマリ仲介サーバーを展開し、セカンダリ仲介サーバー (別の地理的な場所にある) を経由してフェールオーバー呼び出しをルーティングすることをお勧めします。

<!-- end list -->

  - **ブランチ オフィスごとに個別に SIP トランクを展開するかどうか。**  
    Lync Server には、回復可能なデータネットワークがある場合、各ブランチに SIP トランクを展開する場合、停止中にローカルゲートウェイに呼び出しをプッシュする場合など、ブランチオフィスの音声の復元を処理するためのいくつかの戦略が用意されています。 詳細については、「 [Lync Server 2013 のブランチサイト SIP トランキング](lync-server-2013-branch-site-sip-trunking.md)」を参照してください。

<!-- end list -->

  - **通話受付管理 (CAC) を有効にするかどうか。**  
    Lync Server は、通常の通話とは異なる方法で緊急通話を処理しません。 そのため、帯域幅管理や通話受付管理 (CAC) が E9-1-1 の構成に悪影響を与える場合があります。 CAC が有効になっており、緊急電話がルーティングされているリンク上に構成された制限数を超過した場合は、緊急電話がブロックされたり、ローカル PSTN ゲートウェイにルーティングされたりします。 前述のように、このような通話には場所データが含まれていないので、ECRC に手動でルーティングする必要があります。

</div>

<span> </span>

</div>

</div>

</div>

