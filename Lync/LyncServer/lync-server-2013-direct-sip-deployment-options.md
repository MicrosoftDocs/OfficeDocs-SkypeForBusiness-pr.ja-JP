---
title: 'Lync Server 2013: 直接 SIP 展開のオプション'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e521e1665361e15fffdf1e058731d04bc2eb9aa4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Lync Server 2013 の直接 SIP 展開のオプション

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

ここでは、直接 SIP 接続を展開するトポロジの例について説明します。

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Lync Server スタンドアロン

このセクションに記載されているいずれかの展開を組織が使用している場合は、一部またはすべての組織の単独テレフォニーソリューションとして Lync Server 2013 を使用できます。 このセクションでは、次の展開について詳細に説明します。

  - **増分展開:** このオプションでは、既存の構内交換業者 (PBX) インフラストラクチャがあり、組織内の小規模なグループまたはチームにエンタープライズ Voip を段階的に導入することを前提としています。

  - **Lync Server VoIP のみの展開:** このオプションは、従来のテレフォニーインフラストラクチャを持たないサイトでエンタープライズ voip を展開することを検討していることを前提としています。

<div>

## <a name="incremental-deployment"></a>増分展開

増分展開では、Lync Server 2013 は個別のチームまたは部署の単独テレフォニーソリューションですが、組織内の残りのユーザーは引き続き PBX を使用します。 この段階的な展開戦略では、管理されたパイロットプログラムを使用して、企業に IP テレフォニーを導入することができます。 Microsoft ユニファイドコミュニケーションが最適に提供する必要があるワークグループはエンタープライズ Voip に移行されますが、他のユーザーは既存の PBX に保持されます。 必要に応じて、他のワークグループをエンタープライズ Voip に移行できます。

[増分] オプションは、共通の通信要件を持つユーザーグループを明確に定義していて、集中管理を行う場合にお勧めします。 このオプションは、地理的な地域に散らばっている teams または部署がある場合にも効果的です。長距離の料金を節約することが重要です。 実際、このオプションは、メンバーが世界中に散在している可能性がある仮想チームを作成するのに役立ちます。 変化するビジネス要件に迅速に対応するために、このようなチームを作成、変更、または消滅させることができます。

次の図は、PBX の背後にエンタープライズ Voip を展開するための一般的なトポロジを示しています。 これは、増分展開で推奨されるトポロジです。

**増分展開オプション**

![部門別移行オプションの図](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "部門別移行オプションの図")

<div>


> [!NOTE]  
> Lync Server の展開を認定された直接 SIP パートナーに接続している場合は、仲介サーバーと PBX との間の公衆交換電話網 (PSTN) ゲートウェイは必要ありません。 認定された直接 SIP パートナーの一覧については、「Microsoft 統合コミュニケーション」 <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>() を参照してください。



</div>

<div>


> [!NOTE]  
> この図に示されているメディアパスは、メディアバイパスが有効になっています (推奨構成)。 メディアバイパスを無効にすることを選択すると、メディアパスが仲介サーバーを経由してルーティングされます。



</div>

このトポロジでは、選択した部門またはワークグループがエンタープライズ Voip に対して有効になります。 PSTN ゲートウェイは、VoIP (Voice over Internet Protocol) 対応ワークグループを PBX にリンクします。 エンタープライズ Voip が有効になっているユーザー (リモートワーカーを含む) は、IP ネットワークを介して通信します。 エンタープライズ voip ユーザーから PSTN への通話、およびエンタープライズ Voip が有効になっていない同僚は、適切な PSTN ゲートウェイにルーティングされます。 PBX システム上にある同僚または PSTN 上の発信者からの通話は、PSTN ゲートウェイにルーティングされ、通話をルーティングのために Lync Server に転送します。

エンタープライズ Voip を既存の PBX インフラストラクチャに接続する場合は、次の2つの構成が推奨されます。これは、pbx の背後にある PBX とエンタープライズ Voip の背後にあるエンタープライズ voip です。

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>PBX の背後のエンタープライズ Voip

エンタープライズ Voip が PBX の背後に展開されると、PSTN からのすべての通話が PBX で到着し、PSTN ゲートウェイにエンタープライズ Voip ユーザーへの通話をルーティングし、pbx ユーザーを pbx に呼び出します。

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>PBX の前面のエンタープライズ Voip

エンタープライズ Voip が PBX の前に展開されている場合、すべての通話は PSTN ゲートウェイに到着します。これにより、エンタープライズ Voip ユーザーの通話が Lync Server にルーティングされ、pbx ユーザーが PBX に電話をかけられます。 エンタープライズ Voip および PBX ユーザーの両方の PSTN への通話は、IP ネットワークを介して、最も費用効率のよい PSTN ゲートウェイにルーティングされます。 次の表に、この構成の長所と短所を示します。

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>エンタープライズ Voip を PBX の前面に展開する場合の利点と欠点

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>メリット</th>
<th>デメリット</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PBX では、エンタープライズ Voip が有効になっていないユーザーも引き続き提供されます。</p></td>
<td><p>既存のゲートウェイでは、必要な機能や容量がサポートされない場合があります。</p></td>
</tr>
<tr class="even">
<td><p>PBX は以前のすべてのデバイスを処理します。</p></td>
<td><p>PBX から仲介サーバーへのゲートウェイからのトランクが必要です。 サービスプロバイダーからさらにトランクが必要になることがあります。</p></td>
</tr>
<tr class="odd">
<td><p>エンタープライズ Voip ユーザーは同じ電話番号を保持します。</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Lync Server VoIP のみの展開

エンタープライズ Voip では、新しいビジネスと既存のビジネス向けの新しい office サイトも提供しており、PBX の統合または大量の展開と保守を気にせずに、完全な機能を備えた VoIP ソリューションを実装する機会があります。ip-pbx インフラストラクチャのコスト。 このソリューションは、オンサイトワーカーとリモートワーカーの両方をサポートしています。

この展開では、すべての呼び出しが IP ネットワークを経由してルーティングされます。 PSTN への通話は、適切な PSTN ゲートウェイにルーティングされます。 Lync 2013 または Lync Phone Edition は、softphone として機能します。 ユーザーが管理する PBX 電話がないため、リモート通話コントロールは使用できず、不要です。 ボイスメールおよび自動応答サービスは、「Exchange ユニファイドメッセージング (UM) のオプションの展開によって利用できます。

<div>


> [!NOTE]  
> Lync Server 2013 をサポートするために必要なネットワークインフラストラクチャに加えて、VoIP のみの展開では、fax マシンとアナログデバイスをサポートするために、小規模の認定されたゲートウェイを使用できます。



</div>

次の図は、VoIP のみの展開の一般的なトポロジを示しています。

**VoIP のみの展開オプション**

![Greenfield の展開オプション](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfield の展開オプション")

<div>


> [!NOTE]  
> この図に示されているメディアパスは、メディアバイパスが有効になっています (推奨構成)。 メディアバイパスを無効にすることを選択すると、メディアパスが仲介サーバーを経由してルーティングされます。



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

