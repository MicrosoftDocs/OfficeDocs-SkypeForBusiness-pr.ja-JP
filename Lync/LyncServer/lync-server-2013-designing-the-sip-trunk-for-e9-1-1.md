---
title: 'Lync Server 2013: E9 の SIP トランクの設計-1-1'
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
ms.openlocfilehash: b0ca42092b33632dbc7aed84808499b13ab0843c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762515"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a>Lync Server 2013 での E9 の SIP トランクの設計

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-03_

Lync Server では、SIP trunks を使用して、緊急通話を E9 サービスプロバイダーに接続します。 E9-1-1 用の緊急サービス SIP トランクは、1 つの中央サイト、複数の中央サイト、または各ブランチ サイトにセットアップできます。 ただし、発信者のサイトと緊急サービス SIP トランクをホストするサイト間の WAN リンクが使用できない場合、切断されたサイトのユーザーが発信した通話では、ローカル公衆交換電話網 (PSTN) ゲートウェイ経由で ECRC に通話をルーティングする特別な電話使用法レコードがユーザーの音声ポリシーに必要です。 通話受付管理で同時通話数制限が有効な場合も同様です。

<div>


> [!NOTE]  
> Lync Server 環境で SIP トランクを実装するには、次の2つの方法があります。 
> <UL>
> <LI>
> <P>外部向けのパブリックルーティングインターフェイスを使用して、SIP トランクプロバイダーと通信するマルチホーム仲介サーバーを使います。</P>
> <LI>
> <P>オンプレミスセッションボーダーコントローラー (SBC) を使って、仲介サーバーと SIP トランクプロバイダーのサービス間に安全な境界点を指定します。</P></LI></UL>後者の方法を選択した場合は、選択する SBC の型とモデルが認定済みであり、SIP INVITE の一部としてプレゼンス情報データ フォーマット位置オブジェクト (PIDF-LO) 場所データの通過がサポートされていることを確認します。 サポートされてない場合、緊急サービスのサービス プロバイダーに到着した通話から場所情報が除去されます。 認定 SBCs の詳細については、at で<A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>「Microsoft Lync 用のインフラストラクチャ認定」を参照してください。<BR>E9-1-1 サービス プロバイダーは、冗長性を確保するために SBC のペアへのアクセスを提供します。 仲介サーバートポロジと通話ルーティング構成について、いくつかの決定を行う必要があります。 たとえば、2 つの SBC を同等のピアとして扱い、SBC 間の通話にラウンドロビン ルーティングを使用するのか、または一方の SBC をプライマリ、もう一方をセカンダリとして指定するのかを決定します。



</div>

Lync Server での SIP トランクの展開の詳細については、「 [Lync server 2013 で sip トランクを実装する方法](lync-server-2013-how-do-i-implement-sip-trunking.md)」を参照してください。 E9-1-1 用 SIP トランクの展開方法を決定する際に次の質問が役立ちます。

  - **SIP トランクの展開に、専用接続を使用するか、それとも共有のインターネット接続を使用するか。**  
    緊急電話は常につながることが重要です。専用線で接続すれば、ネットワーク上の他のトラフィックによって回線が専有されることがなくなり、サービス品質 (QoS) も実装できます。パブリック インターネット経由で緊急サービスのサービス プロバイダーに接続し、緊急電話の機密性を保証する必要がある場合は、IPsec 暗号化が必要です。

<!-- end list -->

  - **E9 展開は、耐障害性のために設計されていますか?**  
    これは緊急時向けのソリューションなので、回復性が重要です。 プライマリおよびセカンダリの仲介サーバーと SIP trunks を、ディザスタートレラントな場所に展開します。 サポート対象のユーザーに最も近いプライマリ仲介サーバーを展開し、セカンダリ仲介サーバー (別の地理的な場所にある) 経由でフェールオーバー通話をルーティングすることをお勧めします。

<!-- end list -->

  - **ブランチ オフィスごとに個別に SIP トランクを展開するかどうか。**  
    Lync Server には、回復可能なデータネットワークがあり、各ブランチに SIP トランクを展開する、または停止中にローカルゲートウェイへの呼び出しをプッシュするなど、支店での音声回復性を処理するためのいくつかの戦略が用意されています。 詳細については、「 [Lync Server 2013 のブランチサイト SIP トランク](lync-server-2013-branch-site-sip-trunking.md)」を参照してください。

<!-- end list -->

  - **通話受付管理 (CAC) を有効にするかどうか。**  
    Lync Server では、通常の通話とは異なる方法で緊急通話を処理することはできません。 そのため、帯域幅管理や通話受付管理 (CAC) が E9-1-1 の構成に悪影響を与える場合があります。 CAC が有効になっており、緊急電話がルーティングされているリンク上に構成された制限数を超過した場合は、緊急電話がブロックされたり、ローカル PSTN ゲートウェイにルーティングされたりします。 前述のように、このような通話には場所データが含まれていないので、ECRC に手動でルーティングする必要があります。

</div>

<span> </span>

</div>

</div>

</div>

