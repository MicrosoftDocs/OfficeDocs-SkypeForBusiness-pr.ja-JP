---
title: 'Lync Server 2013: エンタープライズ VoIP の展開ガイドライン'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0f4f6198f8fb82720834d112bcf363554aaf84d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 のエンタープライズ VoIP の展開ガイドライン

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

このトピックでは、Lync Server 2013 およびエンタープライズボイスワークロードの展開を計画する際に考慮する必要のある前提条件およびその他のガイドラインについて説明します。

<div>

## <a name="deployment-prerequisites"></a>展開の前提条件

エンタープライズ Voip を展開するときに最適なエクスペリエンスを実現するには、IT インフラストラクチャ、ネットワーク、システムが次の前提条件を満たしていることを確認します。

  - Lync Server 2013 Standard Edition または Enterprise Edition がネットワークにインストールされ、動作する。

  - すべてのエッジサーバーは、アクセスエッジサービス、A/V Edge サービス、Web 会議エッジサービス、リバースプロキシなどのエッジサーバーを含む境界ネットワークに展開され、動作します。

  - Lync Server の1人以上のユーザーが作成され、有効になっている。

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) または最新の Service pack、または Microsoft Exchange Server 2010 がインストールされています。 これらのいずれかを使用するには、Exchange ユニファイドメッセージング (UM) を Lync Server と統合し、クライアントエンドポイントに対して豊富な通知と通話ログ情報を提供する必要があります。

  - エンタープライズ Voip が有効になっている各ユーザーの**msrtcsip-userenabled true**属性に、固有のプライマリ電話番号が指定、正規化、コピーされました。
    
    <div>
    

    > [!NOTE]  
    > Lync Server は、電子番号をサポートしていません。 非表示の数値は、" <STRONG> &lt;e.i&gt;&lt;&gt; </STRONG> " または "内線" の形式で表すことができます。また、秘密の内線番号は企業全体で一意である必要があります。 たとえば、1001の秘密番号は、 <STRONG>+ 1425550100; ext = 1001</STRONG>、または<STRONG>1001</STRONG>として表すことができます。 <STRONG>1001</STRONG>として表現された場合、このプライベート番号は企業全体で一意であるという期待があります。

    
    </div>

  - エンタープライズボイスを展開する管理者は、RTCUniversalServerAdmins グループのメンバーである必要があります。

  - 少なくとも、Office Communicator 2007 が正常に展開されました。 このリリースの新機能を使用するには、Lync 2013 が展開されています。

  - 管理キー基盤 (MKI) は、Microsoft またはサードパーティの証明機関 (CA) インフラストラクチャを使用して展開および構成されます。

  - 仲介サーバーをインストールするコンピューターごとに、次のことを行う必要があります。
    
      - ドメインのメンバーサーバーで、Active Directory ドメインサービスの準備ができていること。 Active Directory ドメインサービスの準備手順については、展開ドキュメントで「 [Lync Server 2013 用 Active Directory ドメインサービスの準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。
    
      - 次のいずれかのオペレーティングシステムを実行している。
        
          - <span></span>  
            64ビット版の Windows Server 2008 標準オペレーティングシステム
        
          - <span></span>  
            Windows Server 2008 Enterprise オペレーティングシステムの64ビット版

  - 公衆交換電話網 (PSTN) または構内交換機 (PBX) への接続が、Time 除算多重 (TDM) 接続によって使用されている場合は、1つ以上の PSTN ゲートウェイを展開することができます。 (接続が SIP トランクを使っている場合、PSTN ゲートウェイは必要ありません)。

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>電源、ネットワーク、または電話サービスの停止

お客様の所在地での電源、ネットワーク、または電話サービスの停止、中断、またはその他のパフォーマンス低下が発生した場合は、Lync Server および Lync Server に接続されたデバイスの音声、インスタントメッセージ、プレゼンス、その他の機能が正常に動作しないことがあります。

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>エンタープライズ Voip は、サーバーの可用性と音声クライアントとハードウェアの運用性に依存

Lync Server との音声通信は、サーバーソフトウェアの可用性と、サーバーソフトウェアに接続する音声クライアントまたはハードウェア電話デバイスの適切な機能によって異なります。

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>緊急サービスへのアクセスの代替手段

音声クライアント (たとえば、Lync クライアントまたは Lync Phone Edition のデバイスを実行している PC) をインストールする場合は、電源障害が発生した場合に緊急サービス (911 や999など) を呼び出すためのバックアップオプションを維持することをお勧めします。または、ネットワーク接続の低下、電話サービスの停止、lync Server、Lync、Lync Phone Edition のデバイスの操作を妨げる可能性があるその他の問題が発生します。 このような代替オプションには、標準の公衆交換電話網回線または携帯電話に接続された電話が含まれている場合があります。

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>緊急通話と複数回線電話システム

複数行の電話システム (MLTS) を使用する場合は、米国の州または連邦法が必要となる場合があります。これには、発信者の電話番号、内線番号、またはその他の国/地域の法律が必要であり、発信者は、緊急サービス (911 や999などのエマージェンシーアクセス番号をダイヤルするときなど) に設定されます。 このリリースでは、 [lync server 2013 の緊急サービス (E9) の計画](lync-server-2013-planning-for-emergency-services-e9-1-1.md)に記載されているように、発信者の物理的な場所を緊急サービスプロバイダーに提供するように構成することができます。 MLTS 法へのコンプライアンスは、Lync Server、Lync クライアント、Lync Phone Edition デバイスの購入者に対する唯一の責任となります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

