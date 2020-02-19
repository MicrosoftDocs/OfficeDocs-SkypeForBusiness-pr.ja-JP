---
title: 'Lync Server 2013: 仲介サーバーの展開ガイドライン'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Mediation Server
ms:assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398622(v=OCS.15)
ms:contentKeyID: 48184606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f55ec3444348b2717721dcad890a4712cd8b9a3b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138198"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013 の仲介サーバーの展開ガイドライン

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-12_

このトピックでは、仲介サーバーの展開の計画ガイドラインについて説明します。 これらのガイドラインを確認した後、計画ツールを使用して、展開することを決定した最終的な調整トポロジのモデルとして利用できる代替トポロジを作成および表示することをお勧めします。

<div>

## <a name="collocated-or-stand-alone-mediation-server"></a>併置またはスタンドアロンの仲介サーバー

仲介サーバーは、既定では、Standard Edition サーバーまたは中央サイトのフロント エンド プール内のフロント エンド サーバーに併置されます。 処理できる公衆交換電話網 (PSTN) 通話の数と、プールで必要なコンピューターの数は、以下によって決まります。

  - 仲介サーバープールが制御するゲートウェイピアの数

  - これらのゲートウェイを通過する、ボリュームの大きいトラフィック期間

  - 仲介サーバーをバイパスしているメディアを持つ通話の割合

計画時には、メディアバイパスを使用するように構成されていない PSTN 通話と音声ビデオ会議のためのメディア処理要件と、サポートする必要のある時間外呼び出しの数に対するシグナリング通信を処理するために必要な処理を考慮してください。 CPU が十分でない場合は、仲介サーバーのスタンドアロンプールを展開する必要があります。および PSTN ゲートウェイ、IP-PBX、および sbc は、1つのプール内の併置された仲介サーバーによって制御されるサブセット、または1つまたは複数のスタンドアロンプールにあるスタンドアロン仲介サーバーによって制御されるサブセットに分割する必要があります。

PSTN ゲートウェイ、IP-PBX、またはセッションボーダーコントローラー (sbc) を展開した場合は、次に示すように、仲介サーバーのプールを操作するための適切な機能がサポートされていない場合は、次のものを含むスタンドアロンプールに関連付けられている必要があります。単一の仲介サーバーの場合:

  - プール内の仲介サーバーでネットワーク層のドメインネームシステム (DNS) 負荷分散を実行する (または、プール内のすべての仲介サーバーにトラフィックを均等にルーティングする)

  - プール内のすべての仲介サーバーからのトラフィックを受け付ける

Microsoft Lync Server 2013、計画ツールを使用して、仲介サーバーをフロントエンドプールと併置することで負荷を処理できるかどうかを評価できます。 これらの要件に適合しない環境では、スタンドアロン仲介サーバー プールを展開する必要があります。

</div>

<div>

## <a name="central-site-and-branch-site-considerations"></a>中央サイトとブランチ サイトに関する考慮事項

中央サイトの仲介サーバーを使用して、ブランチ サイトの IP-PBX ゲートウェイまたは PSTN ゲートウェイの通話をルーティングできます。 ただし、SIP トランクを展開する場合は、各トランクが終了するサイトに仲介サーバーを展開する必要があります。 中央サイトの仲介サーバーでブランチ サイトの IP-PBX ゲートウェイまたは PSTN ゲートウェイの通話をルーティングする場合は、メディア バイパスを使用する必要はありません。 ただし、メディア バイパスを有効にできる場合は、有効にすると、メディア パスが信号パスを通過する必要がなくなるため、メディア パスの遅延を低減して、メディアの品質を高めることができます。 メディア バイパスにより、プールの処理負荷も軽減することができます。

<div>


> [!NOTE]  
> メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。 Microsoft は、認定パートナーで PSTN ゲートウェイと sbc のセットをテストしており、Cisco IP-PBX でいくつかのテストを行いました。 メディアバイパスがサポートされるのは、統合コミュニケーションのオープン相互運用性プログラム– Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=268730">https://go.microsoft.com/fwlink/p/?LinkId=268730</A>の製品およびバージョンのみです。



</div>

ブランチサイトの復元が必要な場合は、ブランチサイトに存続可能ブランチアプライアンスまたはフロントエンドサーバー、仲介サーバー、ゲートウェイの組み合わせを展開する必要があります。 (ブランチサイトの復元には、サイトでのプレゼンスと会議の弾力性がありません)。音声のブランチサイトの計画のガイダンスについては、「 [Lync Server 2013 でのブランチサイトの音声の復元の計画](lync-server-2013-planning-for-branch-site-voice-resiliency.md)」を参照してください。

Ip-pbx との対話の場合、ip-pbx が、複数の初期ダイアログと RFC 3960 の相互作用との早いメディア操作を適切にサポートしていない場合は、ip-pbx から Lync エンドポイントへの着信呼び出しについて、応答メッセージの最初の数文字をクリッピングすることができます。 中央サイトの仲介サーバーがブランチ サイトでルートが終了する IP-PBX の通話をルーティングしている場合、信号が完了するのにより長い時間が必要になるため、この動作はさらに深刻になります。 この現象が見られる場合は、最初の少数の単語のクリッピングを減らす唯一の方法は、ブランチサイトに仲介サーバーを展開することだけです。

また、中央サイトに TDM PBX がある場合や、IP-PBX によって PSTN ゲートウェイの必要性がなくならない場合は、仲介サーバーおよび PBX に接続する通話ルートにゲートウェイを展開する必要があります。

<div>


> [!NOTE]  
> スタンドアロンの仲介サーバーのメディアパフォーマンスを向上させるには、これらのサーバーのネットワークアダプターで受信側スケーリング (RSS) を有効にする必要があります。 RSS は、着信パケットがサーバーの複数のプロセッサによって平行して処理されるのを可能にします。 詳細については、「」の「Windows Server の受信側<A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?LinkId=268731</A>スケーリングの拡張機能」を参照してください。 RSS を有効にする方法の詳細については、ネットワークアダプターのドキュメントを参照してください。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

