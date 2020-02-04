---
title: Lync Server 2013 サイト
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398076(v=OCS.15)
ms:contentKeyID: 48183233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2e5dc3323ad14f02a5b24258878512707f66f19
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a>Lync Server 2013 の Lync Server サイト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-16_

Lync server では、Lync Server コンポーネントが含まれているネットワーク上の*サイト*を定義します。 サイトとは、1 つのローカル エリア ネットワーク (LAN)、または高速の光ファイバー ネットワークで接続された 2 つのネットワークなど、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。 Lync Server サイトは、Active Directory ドメインサービスサイトと Microsoft Exchange Server サイトとは別の概念であることに注意してください。 Lync Server サイトは、Active Directory サイトに対応している必要はありません。

<div>

## <a name="site-types"></a>サイトの種類

各サイトは、少なくとも1つのフロントエンドプールまたは Standard Edition サーバー、または*ブランチサイト*を含む*セントラルサイト*です。 各ブランチサイトは1つのセントラルサイトと関連付けられ、ブランチサイトのユーザーは、関連付けられたセントラルサイトのサーバーからほとんどの Lync Server 機能を利用します。

各分岐サイトには、次のいずれかが含まれます。

  - *Survivable Branch Appliance (SBA)*。これは、Lync server レジストラーと Windows server で実行されている仲介サーバーを備えた業界標準のブレードサーバーです。 Survivable Branch Appliance には、公衆交換電話網 (PSTN) ゲートウェイも含まれています。 Survivable Branch アプライアンスは、25 ~ 1000 ユーザーの支店向けサイト向けに設計されています。

  - *Survivable Branch server (SBS)*: 指定されたハードウェア要件を満たし、Lync server レジストラーと仲介サーバーソフトウェアがインストールされているサーバーです。 これを、PSTN ゲートウェイ、または電話サービス プロバイダーへの SIP トランクに接続する必要があります。 Survivable Branch Server は、1000と5000のユーザーを含むブランチサイト向けに設計されています。

  - PSTN ゲートウェイ、および必要に応じて*仲介サーバー*。 このようなサーバーの役割の詳細については、「 [Lync server 2013 のサーバーの役割](lync-server-2013-server-roles.md)」を参照してください。

セントラルサイトへの弾力性のあるワイドエリアネットワーク (WAN) リンクを備えたブランチオフィスでは、3番目のオプション (PSTN ゲートウェイ) と、必要に応じて仲介サーバーを使用できます。 回復性の低いリンクを使用する支店のサイトでは、Survivable Branch Appliance または Survivable Branch Server を使用する必要があります。これにより、広域ネットワーク障害の時間の回復性が提供されます。 たとえば、Survivable Branch Appliance または Survivable Branch Server が展開されているサイトでは、ブランチサイトをセントラルサイトに接続している WAN が停止している場合でも、ユーザーはエンタープライズ音声通話の発信と受信を行うことができます。 Survivable Branch Appliance、Survivable Branch Server、復元性の詳細については、計画ドキュメントの「 [Lync server 2013 でのエンタープライズボイスの回復性の計画](lync-server-2013-planning-for-enterprise-voice-resiliency.md)」を参照してください。

</div>

<div>

## <a name="site-topologies"></a>サイトトポロジ

展開には、少なくとも1つのセントラルサイトを含める必要があります。また、0を複数のブランチサイトに含めることができます。 各ブランチサイトは、1つのセントラルサイトと関連付けられています。 セントラルサイトは、プレゼンスや会議など、ブランチサイトでローカルにホストされていない支社サイトへの Lync Server サービスを提供します。

複数のサイトがある場合は、さまざまなサイトでフロントエンドプールを組み合わせて、障害回復機能を有効にすることができます。 詳細については、「 [Lync Server 2013 での高可用性と障害回復のサポート](lync-server-2013-high-availability-and-disaster-recovery-support.md)」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のサーバーの役割](lync-server-2013-server-roles.md)  
[Lync Server 2013 での高可用性および障害復旧のサポート](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[Lync Server 2013 でのエンタープライズ VoIP の復旧の計画](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

