---
title: 'Lync Server 2013: ブランチサイトの復元ソリューション'
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
ms.openlocfilehash: 25541f7681ece7b299d6e4c8076fb190382650ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512984"
---
# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Lync Server 2013 のブランチサイトの復元ソリューション

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-12-10_

ブランチサイトの復元を組織に提供することには明らかな利点があります。 特に、セントラルサイトへの接続が失われた場合、ブランチサイトのユーザーは引き続きエンタープライズ Voip サービスとボイスメールを使用できます (ボイスメール再ルーティング設定を構成する場合は、「 [Lync Server 2013 のブランチサイトの復元要件](lync-server-2013-branch-site-resiliency-requirements.md)」を参照してください)。 ただし、ユーザー数が25を超えるサイトでは、復元ソリューションによって十分な投資回収が得られない場合があります。

ブランチ サイトの復元を実現するには、3 つの方法があります。次の表は、組織に最適な方法を判断するのに役立ちます。

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>もしも</th>
<th>推奨されるオプション</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ブランチ サイトに 25 から 1000 ユーザーが所属しており、投資収益率が全面的な展開をサポートしない、またはローカル管理者がいない場合</p></td>
<td><p>存続可能ブランチ アプライアンス</p>
<p>存続可能 Branch Appliance は、Windows Server 2008 R2 上で Lync Server レジストラーと仲介サーバーを実行する業界標準のブレードサーバーです。 存続可能ブランチアプライアンスには、公衆交換電話網 (PSTN) ゲートウェイも搭載されています。 認定されたサードパーティ製のデバイス (存続可能 Branch Appliance (SBA) 修飾/証明プログラムで Microsoft パートナーが開発したもの) は、WAN 障害が発生した場合にも継続的な PSTN 接続を提供しますが、これらの機能は中央サイトのフロントエンドサーバーに依存しているため、回復可能なプレゼンスと会議を提供しません。</p>
<p>存続可能ブランチアプライアンスの詳細については、 &quot; &quot; このトピックで後述する「存続可能 Branch Appliance details」を参照してください。</p>
<p><strong>注:</strong> 存続可能ブランチアプライアンスで SIP トランクも使用することにした場合は、存続可能 Branch Appliance ベンダーに問い合わせて、組織に最適なサービスプロバイダーについて確認してください。</p></td>
</tr>
<tr class="even">
<td><p>ブランチサイトで1000と2000のユーザーをホストし、回復可能な WAN 接続がなく、専任の Lync Server 管理者が利用できるようになります。</p></td>
<td><p>存続可能ブランチサーバーまたは2つの存続可能 Branch アプライアンス。</p>
<p>存続可能ブランチサーバーは、Lync Server レジストラーおよび仲介サーバーソフトウェアがインストールされている、指定されたハードウェア要件を満たす Windows Server です。 これを、PSTN ゲートウェイ、または電話サービス プロバイダーへの SIP トランクに接続する必要があります。</p>
<p>存続可能ブランチサーバーの詳細については、 &quot; &quot; このトピックで後述する「存続可能 Branch Server details」を参照してください。</p></td>
</tr>
<tr class="odd">
<td><p>最大5000ユーザーのための音声機能に加えて、プレゼンスおよび会議機能が必要な場合、および専任の Lync Server 管理者を使用できるようにする</p></td>
<td><p>ブランチ サイトとしてではなく、Standard Edition サーバーが含まれるセントラル サイトとして展開します。</p>
<p>フルスケールの Lync Server の展開では、WAN の障害発生時に、継続的な PSTN 接続と回復性のあるプレゼンスと会議が提供されます。</p>
<p>このソリューションの準備の詳細については、「 <a href="lync-server-2013-planning-for-your-organization.md">Lync server 2013 の組織の計画</a>」、「 <a href="lync-server-2013-determining-your-system-requirements.md">lync server 2013 のシステム要件の決定</a>」、「 <a href="lync-server-2013-determining-your-infrastructure-requirements.md">lync server 2013 のインフラストラクチャ要件の決定</a>」、および「計画」のドキュメントの関連するセクションを参照してください。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>復元のトポロジ

次の図は、ブランチ サイトの復元の推奨されるトポロジを示しています。

**ブランチ サイトの復元オプション**

![音声ブランチの復元性オプション](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "音声ブランチの復元性オプション")

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>存続可能ブランチ アプライアンスの詳細

Lync Server 存続可能 Branch Appliance には、次のコンポーネントが含まれています。

  - ユーザー認証、登録、通話ルーティングのためのレジストラー。

  - レジストラーと PSTN ゲートウェイ間の信号を処理する仲介サーバー

  - WAN の停止時に代替トランスポートとして PSTN に通話をルーティングする PSTN ゲートウェイ

  - ローカル ユーザーのデータ記憶域用 SQL Server Express

存続可能ブランチアプライアンスには、PSTN トランク、アナログポート、およびイーサネットアダプターも含まれています。

中央サイトへのブランチサイトの WAN 接続が使用できなくなった場合、内部ブランチユーザーは引き続き存続可能 Branch Appliance レジストラーに登録され、PSTN への存続可能 Branch Appliance 接続を使用して中断のない音声サービスを取得します。 自宅またはその他のリモートの場所から接続しているブランチ サイトのユーザーは、ブランチ サイトへの WAN リンクが使用できない場合にセントラル サイトのレジストラー サーバーに登録されることができます。 これらのユーザーはすべての統合コミュニケーション機能を使用できますが、唯一の例外は、ブランチ サイトへの着信通話がボイス メールに転送されることです。 WAN 接続が使用可能になると、ブランチ サイトのユーザーはすべての機能を再び使用できるようになります。 存続可能ブランチアプライアンスへのフェールオーバーやサービスの復元では、IT 管理者の存在は必要ありません。

Lync Server は、ブランチサイトで最大2つの存続可能ブランチアプライアンスをサポートします。

<div>


> [!NOTE]  
> Lync Server 存続可能 Branch アプライアンスに所属しているユーザーは、新しいチャットルームを作成したり、既存のルームのルームカードを表示したりすることはできません。



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>存続可能ブランチ アプライアンスの展開の概要

存続可能 Branch Appliance は、Microsoft とのパートナーシップで元の機器メーカーによって製造され、付加価値のある小売業者によって開発されています。 この展開は、Lync Server が中央サイトに展開されていて、ブランチサイトへの WAN 接続が確立されており、ブランチサイトユーザーがエンタープライズ Voip に対して有効になっている場合にのみ発生します。

これらのフェーズの詳細については、「展開」のドキュメントの「 [存続可能ブランチアプライアンスまたはサーバーを Lync server 2013 を使用して展開する](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) 」を参照してください。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>フェーズ</th>
<th>手順</th>
<th>ユーザー権限</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>存続可能ブランチアプライアンスの Active Directory ドメインサービスのセットアップ</p></td>
<td><p><strong>セントラル サイトにおいて:</strong></p>
<ol>
<li><p>ブランチサイトで存続可能 Branch Appliance をインストールしてアクティブ化する技術者のドメインユーザーアカウント (またはエンタープライズ id) を作成します。</p></li>
<li><p>Active Directory ドメインサービスの存続可能 Branch Appliance に、該当する完全修飾ドメイン名 (FQDN) を使用して、コンピューターアカウントを作成します。</p></li>
<li><p>トポロジビルダーで、存続可能 Branch Appliance を作成して発行します。</p></li>
</ol></td>
<td><p>技術者のユーザー アカウントは、RTCUniversalSBATechnicians のメンバーである必要があります。 存続可能 Branch アプライアンスは、RTCSBAUniversalServices グループに属している必要があります。これは、トポロジビルダーを使用したときに自動的に発生します。</p></td>
</tr>
<tr class="even">
<td><p>存続可能ブランチアプライアンスをインストールしてアクティブ化します。</p></td>
<td><p><strong>ブランチ サイトにおいて:</strong></p>
<ol>
<li><p>存続可能 Branch アプライアンスをイーサネットポートおよび PSTN ポートに接続します。</p></li>
<li><p>存続可能 Branch アプライアンスを開始します。</p></li>
<li><p>中央サイトで存続可能ブランチアプライアンス用に作成されたドメインユーザーアカウントを使用して、存続可能 Branch アプライアンスをドメインに参加させる。 コンピューター アカウントで作成された FQDN に一致する FQDN と IP アドレスを設定します。</p></li>
<li><p>OEM ユーザーインターフェイスを使用して、存続可能 Branch Appliance を構成します。</p></li>
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

トポロジビルダーで、ブランチサイトを作成し、そのサイトに存続可能ブランチサーバーを追加した後、役割をインストールするコンピューターで Lync Server 展開ウィザードを実行します。

</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の展開 ](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

