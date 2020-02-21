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
ms.openlocfilehash: 37843e85f5da250b3cb3d8e0fa4cdccdf506176d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-sites-for-lync-server-2013"></a>Lync server 2013 の lync Server サイト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-16_

Lync Server では、Lync Server コンポーネントを含むネットワーク上の*サイト*を定義します。 サイトとは、1 つのローカル エリア ネットワーク (LAN) または高速の光ファイバー ネットワークで接続された 2 つのネットワークのように、高速で遅延の少ないネットワークによる良好な接続が保たれているコンピューターの集合です。 Lync Server サイトは、Active Directory ドメインサービスサイトと Microsoft Exchange Server サイトとは別の概念であることに注意してください。 Lync Server サイトは、Active Directory サイトに対応する必要はありません。

<div>

## <a name="site-types"></a>サイトの種類

各サイトは、少なくとも1つのフロントエンドプールまたは Standard Edition サーバー、または*ブランチサイト*を含む*セントラルサイト*です。 各ブランチサイトは1つの中央サイトに関連付けられ、ブランチサイトのユーザーは、関連付けられた中央サイトのサーバーからほとんどの Lync Server 機能を取得します。

各ブランチ サイトは、次のいずれかを含みます。

  - *存続可能 Branch Appliance (SBA)*。これは、Lync server レジストラーと、Windows server を実行している仲介サーバーを備えた業界標準のブレードサーバーです。 存続可能ブランチアプライアンスには、公衆交換電話網 (PSTN) ゲートウェイも搭載されています。 存続可能 Branch アプライアンスは、ユーザーが 25 ~ 1000 のブランチサイト向けに設計されています。

  - *存続可能ブランチサーバー (SBS)*。これは、指定されたハードウェア要件を満たし、Lync server レジストラーおよび仲介サーバーソフトウェアがインストールされている、Windows server を実行しているサーバーです。 これを、PSTN ゲートウェイ、または電話サービス プロバイダーへの SIP トランクに接続する必要があります。 存続可能ブランチサーバーは、1000と5000のユーザーが関係するブランチサイト用に設計されています。

  - PSTN ゲートウェイ、およびオプションの仲介サーバー**。 このおよびその他のサーバーの役割の詳細については、「 [Lync server 2013 のサーバーの役割](lync-server-2013-server-roles.md)」を参照してください。

セントラル サイトへの復元力のあるワイド エリア ネットワーク (WAN) リンクを備えるブランチ オフィスでは、3 番目のオプションである PSTN ゲートウェイを (必要に応じて仲介サーバーも) 使用できます。 あまり回復不能なリンクを持つ支社のサイトでは、存続可能 Branch Appliance または存続可能ブランチサーバーを使用する必要があります。これにより、広域ネットワーク障害の時間内で復元性が提供されます。 たとえば、存続可能 Branch Appliance または存続可能 Branch Server が展開されているサイトでは、ブランチサイトを中央サイトに接続している WAN がダウンしている場合でも、ユーザーはエンタープライズ Voip 通話を確立したり、受信したりできます。 存続可能 Branch Appliance、存続可能 Branch Server、および復元の詳細については、「計画」のドキュメントの「 [planning For Enterprise Voice 弾力性 In Lync server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) 」を参照してください。

</div>

<div>

## <a name="site-topologies"></a>サイト トポロジ

展開には、少なくとも1つの中央サイトが含まれている必要があります。また、ゼロには多数のブランチサイトを含めることができます。 各ブランチサイトは、1つの中央サイトに関連付けられています。 中央サイトは、プレゼンスや会議など、ブランチサイトでローカルにホストされていないブランチサイトに Lync Server サービスを提供します。

複数のサイトがある場合は、異なるサイトのフロントエンド プールどうしをペアリングして、障害復旧の機能を有効にできます。 詳細については、「 [Lync Server 2013 の高可用性と障害復旧のサポート](lync-server-2013-high-availability-and-disaster-recovery-support.md)」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のサーバーの役割](lync-server-2013-server-roles.md)  
[Lync Server 2013 での高可用性および障害復旧のサポート](lync-server-2013-high-availability-and-disaster-recovery-support.md)  


[Lync Server 2013 でのエンタープライズ Voip の復元の計画](lync-server-2013-planning-for-enterprise-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

