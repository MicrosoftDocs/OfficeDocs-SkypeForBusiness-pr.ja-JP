---
title: 'Lync Server 2013: ブランチ サイトの復元ソリューション'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16261d4add87462991c877e85cc6a0ff1e7fdfd4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Lync Server 2013 のブランチ サイトの復元ソリューション

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-12-10_

ブランチ サイトの復元を提供することには明白な利点があります。 特に、セントラルサイトへの接続が切断された場合、ブランチサイトユーザーは引き続きエンタープライズ Voip サービスとボイスメールを使用できます (詳細については、「[サイトの回復力2013の要件](lync-server-2013-branch-site-resiliency-requirements.md)」を参照してください)。 ただし、ユーザー数が 25 に満たないサイトでは、復元ソリューションによる十分な投資利益が得られない場合があります。

ブランチ サイトの復元を実現するには、3 つの方法があります。次の表は、組織に最適な方法を判断するのに役立ちます。

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>条件</th>
<th>推奨されるオプション</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ブランチ サイトに 25 から 1,000 ユーザーが所属しており、投資収益率が全面的な展開をサポートしない、またはローカル管理者がいない場合</p></td>
<td><p>存続可能ブランチ アプライアンス</p>
<p>Survivable Branch Appliance は、業界標準のブレードサーバーであり、Windows Server 2008 R2 で実行されている Lync Server レジストラーと仲介サーバーが含まれています。 Survivable Branch Appliance には、公衆交換電話網 (PSTN) ゲートウェイも含まれています。 認定されたサードパーティ製デバイス (Survivable Branch Appliance (SBA) 認定プログラムで Microsoft パートナーによって開発されたもの) は、WAN の障害が発生した場合に、継続的な PSTN 接続を提供しますが、これらの機能はセントラルサイトのフロントエンドサーバーに依存するため、弾力性のあるプレゼンスと会議を提供しません。</p>
<p>Survivable Branch アプライアンスの詳細について&quot;は、このトピックの&quot;後半の「Survivable branch Appliance の詳細」を参照してください。</p>
<p><strong>注:</strong>Survivable Branch アプライアンスでも SIP トランクを使用することにした場合は、Survivable Branch Appliance ベンダーにお問い合わせください。組織に最も適したサービスプロバイダーについては、こちらをご覧ください。</p></td>
</tr>
<tr class="even">
<td><p>ブランチサイトでの1000と2000ユーザーの間のホスト、回復可能な WAN 接続の不足、Lync Server 管理者のトレーニング</p></td>
<td><p>Survivable Branch Server または2つの Survivable Branch アプライアンス。</p>
<p>Survivable Branch Server は、Lync Server レジストラーと仲介サーバーソフトウェアがインストールされている、Windows Server 会議の指定したハードウェア要件です。 これを、PSTN ゲートウェイ、または電話サービス プロバイダーへの SIP トランクに接続する必要があります。</p>
<p>Survivable ブランチサーバーの詳細について&quot;は、このトピックの&quot;後半の「Survivable branch Server の詳細」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>最大5000ユーザー向けの音声機能だけでなく、プレゼンスと会議の機能が必要な場合、Lync Server 管理者のトレーニングを受けることができます。</p></td>
<td><p>ブランチ サイトとしてではなく、Standard Edition サーバーが含まれるセントラル サイトとして展開します。</p>
<p>フルスケールの Lync Server 展開では、WAN の障害が発生した場合に、継続的な PSTN 接続、回復可能なプレゼンス、会議が提供されます。</p>
<p>このソリューションの準備の詳細については、「 <a href="lync-server-2013-planning-for-your-organization.md">Lync server 2013 向けの組織計画</a>」、「 <a href="lync-server-2013-determining-your-system-requirements.md">lync server 2013 のシステム要件を決定</a>する」、「 <a href="lync-server-2013-determining-your-infrastructure-requirements.md">lync server 2013 のインフラストラクチャ要件</a>、および計画ドキュメントの関連セクション」を参照してください。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>復元のトポロジ

次の図は、ブランチ サイトの復元性を確保するうえで推奨されるトポロジを示しています。

**ブランチ サイトの復元オプション**

![音声ブランチの復元性オプション](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "音声ブランチの復元性オプション")

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>存続可能ブランチ アプライアンスの詳細

Lync Server Survivable Branch Appliance には、次のコンポーネントが含まれています。

  - ユーザー認証、登録、通話ルーティングのためのレジストラー

  - レジストラーと PSTN ゲートウェイ間の信号を処理する仲介サーバー

  - WAN の停止時に代替トランスポートとして PSTN に通話をルーティングする PSTN ゲートウェイ

  - ローカル ユーザーのデータ記憶域用 SQL Server Express

Survivable Branch Appliance には、PSTN trunks、アナログポート、イーサネットアダプターも含まれています。

セントラルサイトへのブランチサイトの WAN 接続が利用できなくなった場合、内部ブランチユーザーは引き続き Survivable Branch Appliance レジストラーに登録され、Survivable Branch Appliance 接続を使用して中断した音声サービスを取得しますを選びます。 自宅またはその他のリモートの場所から接続しているブランチ サイトのユーザーは、ブランチ サイトへの WAN リンクが使用できない場合にセントラル サイトのレジストラー サーバーに登録されることができます。 これらのユーザーはすべての統合コミュニケーション機能を使用できますが、唯一の例外は、ブランチ サイトへの着信通話がボイス メールに転送されることです。 WAN 接続が使用可能になると、ブランチ サイトのユーザーはすべての機能を再び使用できるようになります。 Survivable Branch Appliance へのフェールオーバーもサービスの復元でも、IT 管理者が存在している必要はありません。

Lync Server は、ブランチサイトで最大2つの Survivable ブランチアプライアンスをサポートしています。

<div>


> [!NOTE]  
> Lync Server Survivable Branch Appliance をホームとして使用しているユーザーは、新しいチャットルームを作成したり、既存のルームの会議室カードを表示したりすることはできません。



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>存続可能ブランチ アプライアンスの展開の概要

Survivable Branch Appliance は、Microsoft との提携により、元の機器メーカーによって製造され、付加価値の小売店に代わって展開されます。 この展開は、Lync Server がセントラルサイトに展開されている場合、またはブランチサイトへの WAN 接続が行われていて、ブランチサイトユーザーがエンタープライズ Voip を有効にしている場合にのみ発生します。

これらのフェーズの詳細については、「 [Survivable Branch Appliance または server を Lync Server 2013 に](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md)展開する」を参照してください。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>段階</th>
<th>ステップ</th>
<th>ユーザー権限</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Survivable Branch Appliance の Active Directory ドメインサービスのセットアップ</p></td>
<td><p><strong>セントラル サイトにおいて:</strong></p>
<ol>
<li><p>ブランチサイトに Survivable Branch Appliance をインストールしてアクティブ化する技術者のドメインユーザーアカウント (またはエンタープライズ id) を作成します。</p></li>
<li><p>Active Directory Domain Services で、Survivable Branch Appliance の完全修飾ドメイン名 (FQDN) が適用されたコンピューターアカウントを作成します。</p></li>
<li><p>Topology Builder で、Survivable Branch Appliance を作成して公開します。</p></li>
</ol></td>
<td><p>技術者のユーザー アカウントは、RTCUniversalSBATechnicians のメンバーである必要があります。 Survivable Branch アプライアンスは、RTCSBAUniversalServices グループに属している必要があります。これは、Topology Builder を使用すると自動的に発生します。</p></td>
</tr>
<tr class="even">
<td><p>Survivable Branch アプライアンスをインストールしてアクティブ化します。</p></td>
<td><p><strong>ブランチ サイトにおいて:</strong></p>
<ol>
<li><p>Survivable Branch アプライアンスをイーサネットポートと PSTN ポートに接続します。</p></li>
<li><p>Survivable Branch Appliance を起動します。</p></li>
<li><p>セントラルサイトで Survivable Branch Appliance 用に作成したドメインユーザーアカウントを使用して、Survivable Branch Appliance をドメインに参加します。 コンピューター アカウントで作成された FQDN に一致する FQDN と IP アドレスを設定します。</p></li>
<li><p>OEM のユーザーインターフェイスを使用して、Survivable Branch Appliance を構成します。</p></li>
<li><p>PSTN 接続をテストします。</p></li>
</ol></td>
<td><p>技術者のユーザー アカウントは、RTCUniversalSBATechnicians のメンバーである必要があります。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a>存続可能ブランチ サーバーの詳細

[Topology Builder] で、ブランチサイトを作成し、そのサイトに Survivable Branch Server を追加してから、役割をインストールするコンピューターで Lync Server Deployment ウィザードを実行します。

</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

