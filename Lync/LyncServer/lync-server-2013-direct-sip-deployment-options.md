---
title: 'Lync Server 2013: 直接 SIP 展開のオプション'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 277b64346dc17815438f2ac34da58f36d2b150f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Lync Server 2013 の直接 SIP 展開のオプション

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

このトピックでは、直接 SIP 接続を展開するためのトポロジの例を紹介します。

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server スタンドアロン

このセクションで説明されている展開のいずれかを使用している組織では、Lync Server 2013 を1つまたは複数の組織の唯一のテレフォニーソリューションとして使うことができます。 このセクションでは、次の展開について詳しく説明します。

  - **段階的展開:** このオプションは、既存の構内交換会社 (PBX) インフラストラクチャを使用していて、組織内の小規模なグループまたはチームにエンタープライズボイスを段階的に導入することを前提としています。

  - **Lync Server の VoIP のみの展開:** このオプションは、従来のテレフォニーインフラストラクチャを使用していないサイトでのエンタープライズ voip の展開を検討していることを前提としています。

<div>

## <a name="incremental-deployment"></a>段階的な展開

段階的展開では、Lync Server 2013 は個々のチームまたは部署向けの唯一のテレフォニーソリューションであり、組織内の他のユーザーは引き続き PBX を使用しています。 この段階的展開戦略では、管理されたパイロットプログラムを通じて、企業に IP テレフォニーを導入する方法が1つあります。 Microsoft ユニファイドコミュニケーションで利用するのに最適な通信が必要なワークグループは、他のユーザーが既存の PBX に移動しても、エンタープライズ Voip に移行されます。 必要に応じて、追加のワークグループをエンタープライズ Voip に移行できます。

通信要件が共通であり、一元管理に対応しているユーザーグループが明確に定義されている場合は、増分オプションをお勧めします。 このオプションは、地理的な広い範囲を超えるチームまたは部門を使用していて、長距離通話料金の節約が重要である場合にも有効です。 実際には、このオプションは、世界中でメンバーが散在している可能性のある仮想チームを作成する場合に便利です。 このようなチームを作成、変更、または解除して、変化するビジネス要件に迅速に対応することができます。

次の図は、PBX でのエンタープライズボイスの展開のための一般的なトポロジを示しています。 これは、段階的展開に推奨されるトポロジです。

**段階的な展開オプション**

![部門の移行オプションの図](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "部門の移行オプションの図")

<div>


> [!NOTE]  
> Lync Server の展開を認定された直接 SIP パートナーに接続している場合は、仲介サーバーと PBX の間の公衆交換電話網 (PSTN) ゲートウェイは必要ありません。 認定された直接 SIP パートナーのリストについては、Microsoft ユニファイドコミュニケーションの<A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>オープンな相互運用性プログラムの web サイトを参照してください。



</div>

<div>


> [!NOTE]  
> この図に示されているメディアパスでは、メディアのバイパスが有効になっています (推奨される構成)。 メディアのバイパスを無効にすると、メディアパスは仲介サーバー経由でルーティングされます。



</div>

このトポロジでは、選択した部署またはワークグループがエンタープライズ Voip に対して有効になっています。 PSTN ゲートウェイは、Voice over Internet Protocol (VoIP) 対応ワークグループを PBX にリンクします。 リモートワーカーなどのエンタープライズ Voip を有効にしているユーザーは、IP ネットワーク経由で通信できます。 エンタープライズボイスユーザーから PSTN への通話、およびエンタープライズ Voip を有効にしていない同僚が、適切な PSTN ゲートウェイにルーティングされます。 PBX システムまたは PSTN 上の発信者からの通話は PSTN ゲートウェイにルーティングされます。これにより、ルーティング用の Lync Server への通話が転送されます。

相互運用性を確保するために、エンタープライズボイスを既存の PBX インフラストラクチャに接続するための推奨される構成が2つあります。 pbx でのエンタープライズ voip と、pbx の前のエンタープライズボイス。

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>PBX 経由のエンタープライズ Voip

エンタープライズ Voip が PBX を介して展開されると、PSTN からのすべての通話が PBX に到着し、PSTN ゲートウェイへのエンタープライズボイスユーザーへの通話のルーティング、および pbx ユーザーへの着信が pbx に転送されます。

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>PBX の前のエンタープライズボイス

エンタープライズボイスが PBX の前に展開されている場合、すべての通話が PSTN ゲートウェイに到着します。これにより、エンタープライズボイスユーザーの通話が Lync Server に転送され、pbx ユーザーが pbx に発信します。 エンタープライズボイスと PBX ユーザーの両方からの PSTN への通話は、IP ネットワーク経由で、最もコスト効率の高い PSTN ゲートウェイにルーティングされます。 次の表は、この構成の長所と短所を示しています。

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>PBX の前にエンタープライズボイスを展開する場合の長所と短所

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>利点</th>
<th>不都合</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PBX では、エンタープライズ Voip を有効にしていないユーザーの場合もあります。</p></td>
<td><p>既存のゲートウェイは、必要な機能や容量をサポートしていない可能性があります。</p></td>
</tr>
<tr class="even">
<td><p>PBX は、以前のすべてのデバイスを処理します。</p></td>
<td><p>PBX と仲介サーバーのゲートウェイからのトランクが必要です。 サービスプロバイダからさらに trunks が必要な場合があります。</p></td>
</tr>
<tr class="odd">
<td><p>エンタープライズボイスのユーザーは、同じ電話番号をそのまま使うことができます。</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Lync Server の VoIP のみの展開

エンタープライズ Voip では、新しいビジネスと、既存のビジネス向けの新しい office サイトも提供され、PBX の統合または大量の展開とメンテナンスを気にせずに、完全な機能を備えた VoIP ソリューションを導入する機会があります。IP PBX インフラストラクチャのコスト。 このソリューションは、オンサイトとリモートの両方のワーカーをサポートしています。

この展開では、すべての通話が IP ネットワーク経由でルーティングされます。 PSTN への通話は、適切な PSTN ゲートウェイにルーティングされます。 Lync 2013 または Lync Phone Edition は、softphone として機能します。 リモート通話コントロールは、ユーザーが制御できる PBX 電話がないため、不要になります。 ボイスメールと自動応答サービスは、オプションの展開である Exchange ユニファイドメッセージング (UM) で利用できます。

<div>


> [!NOTE]  
> VoIP のみの展開では、Lync Server 2013 をサポートするために必要なネットワークインフラストラクチャに加えて、小型の認定されたゲートウェイを使用して、fax 機器とアナログデバイスをサポートすることができます。



</div>

次の図は、VoIP のみの展開の一般的なトポロジを示しています。

**VoIP のみの展開オプション**

![Greenfidle 展開オプション](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle 展開オプション")

<div>


> [!NOTE]  
> この図に示されているメディアパスでは、メディアのバイパスが有効になっています (推奨される構成)。 メディアのバイパスを無効にすると、メディアパスは仲介サーバー経由でルーティングされます。



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

