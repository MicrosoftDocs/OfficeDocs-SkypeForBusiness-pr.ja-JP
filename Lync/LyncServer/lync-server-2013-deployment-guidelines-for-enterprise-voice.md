---
title: 'Lync Server 2013: エンタープライズ Voip の展開ガイドライン'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 770dfe3ce43af7dc2e6984698c095430b5c34f69
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 でのエンタープライズ Voip の展開ガイドライン

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

このトピックでは、Lync Server 2013 およびエンタープライズ Voip ワークロードの展開を計画する際に考慮すべき前提条件およびその他のガイドラインについて説明します。

<div>

## <a name="deployment-prerequisites"></a>展開に関する前提条件

エンタープライズ Voip を展開する場合の最適な環境については、IT インフラストラクチャ、ネットワーク、およびシステムが次の前提条件を満たしていることを確認してください。

  - Lync Server 2013 Standard Edition または Enterprise Edition がインストールされており、ネットワーク上で運用できます。

  - エッジサーバーはすべて、エッジサーバー (アクセスエッジサービス、音声ビデオエッジサービス、Web 会議エッジサービス、リバースプロキシ) を含む境界ネットワークに展開され、動作します。

  - 1人以上のユーザーが作成され、Lync Server に対して有効になっています。

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) または最新のサービスパック、または Microsoft Exchange Server 2010 がインストールされている。 これらのうちの1つは、Exchange ユニファイドメッセージング (UM) と Lync Server を統合し、豊富な通知を提供したり、クライアントエンドポイントにログ情報を呼び出したりするために必要です。

  - エンタープライズ Voip が有効になっている各ユーザーの**msRTCSIP**属性に、一意のプライマリ電話番号が指定および正規化されています。
    
    <div>
    

    > [!NOTE]  
    > Lync Server は、e.164 番号と直接内向きではない (DID) 番号をサポートしています。 非 DID 番号は、プライベート内線番号がエンタープライズ全体で一意であることを要件として、 <STRONG> &lt;&gt;&lt;内線&gt; </STRONG>番号または内線番号の形式、または数字の文字列として表すことができます。 たとえば、1001のプライベート番号は、 <STRONG>+ 1425550100、ext = 1001</STRONG>、または<STRONG>1001</STRONG>として表すことができます。 <STRONG>1001</STRONG>として表される場合、このプライベート番号は企業全体で一意であることが期待されます。

    
    </div>

  - エンタープライズ Voip を展開する管理者は、RTCUniversalServerAdmins グループのメンバーである必要があります。

  - 少なくとも、Office Communicator 2007 は正常に展開されています。 このリリースの新機能を使用するには、Lync 2013 が展開されています。

  - マイクロソフトまたはサードパーティの CA (証明機関) インフラストラクチャのいずれかを使用して、MKI (Managed key infrastructure) が展開され、構成されていること。

  - 仲介サーバーをインストールする各コンピューターの要件は次のとおりです。
    
      - ドメインのメンバーサーバーで、Active Directory ドメインサービス用に準備されています。 Active Directory ドメインサービスの準備手順については、「展開」のドキュメントの「 [Active Directory ドメインサービスの Lync Server 2013 の準備](lync-server-2013-preparing-active-directory-domain-services.md)」を参照してください。
    
      - 次のいずれかのオペレーティング システムを実行していること。
        
          - <span></span>  
            64 ビット版の Windows Server 2008 Standard オペレーティング システム
        
          - <span></span>  
            64 ビット版の Windows Server 2008 Enterprise オペレーティング システム

  - 公衆交換電話網 (PSTN) または構内交換機 (PBX) への接続に時分割多重 (TDM) 接続を使用する場合は、1 つ以上の PSTN ゲートウェイを展開できること (接続に SIP トランクを使用する場合、PSTN ゲートウェイは不要です)。

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>電力、ネットワーク、または電話サービスの停止

お客様の場所で、停止、中断、その他の電源、ネットワーク、または電話サービスの低下が発生した場合、Lync Server の音声、インスタントメッセージング、プレゼンス、およびその他の機能が正しく動作しないことがあります。

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>エンタープライズ VoIP が、サーバーの可用性と VoIP クライアントおよびハードウェアの正常動作に依存する

Lync Server との音声通信は、サーバーソフトウェアの可用性と、サーバーソフトウェアに接続する音声クライアントまたはハードウェア電話デバイスの適切な機能に依存しています。

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>緊急サービスへの代替アクセス手段

音声クライアント (Lync クライアントまたは Lync Phone Edition デバイスを実行している PC など) をインストールする場所については、電源障害が発生した場合に、ユーザーが緊急サービス (たとえば、911または 999) を呼び出すためのバックアップオプションを維持することをお勧めします。、Lync Server、Lync、Lync Phone Edition デバイスの動作を妨げる可能性がある、ネットワーク接続の低下、電話サービスの停止、その他の問題が発生します。 このような代替オプションには、標準公衆交換電話網回線に接続された電話、携帯電話などが含まれます。

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>緊急呼び出しと複数回線電話システム

複数行の電話システム (MLTS) の使用は、U の対象となる場合があります。発信者が緊急サービスに発信されたときに、発信者の電話番号、内線、または物理的な場所を該当する緊急サービスに提供するために MLTS が必要とするその他の国/地域の法律または連邦法 (911 や999などのエマージェンシー・アクセス番号をダイヤルする場合など)。 このリリースでは、lync server [2013 での緊急サービス (E9-1-1) の計画](lync-server-2013-planning-for-emergency-services-e9-1-1.md)」に記載されているように、緊急サービスプロバイダーに発信者の物理的な場所を提供するように lync Server を構成できます。 MLTS の法令に準拠するには、Lync Server、Lync クライアント、Lync Phone Edition デバイスの購入者の責任を負う必要があります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

