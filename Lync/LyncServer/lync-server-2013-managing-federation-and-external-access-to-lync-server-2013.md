---
title: 'Lync Server 2013: Lync Server 2013 へのフェデレーションおよび外部アクセスの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 155ee98a7386368d90fd549d920cdfe77c05cb6e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>Lync Server 2013 へのフェデレーションおよび外部アクセスの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-07_

外部ユーザーをサポートするには、最初に、エッジ サーバーまたはエッジ プールを展開する必要があります。 エッジサーバーの展開の詳細については、「展開」のドキュメントの「Deployment [external user access In Lync Server 2013](lync-server-2013-deploying-external-user-access.md) 」を参照してください。

Lync Server 2013 の内部展開をインストールして構成すると、組織内の内部ユーザーは、Active Directory ドメインサービス (AD DS) に SIP アカウントを持つ他の内部ユーザーと共同作業を行うことができます。 共同作業には、インスタント メッセージの送受信、プレゼンス状態の更新、電話会議 (「会議」とも呼ばれます) への参加などがあります。 サポートされている外部ユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御するために、外部ユーザーアクセスを有効にして構成します。 外部ユーザーには、展開のリモート ユーザー、フェデレーション ユーザー (パブリック インスタント メッセージング (IM) サービス プロバイダーのサポートされるユーザーを含む)、XMPP フェデレーション、および電話会議への匿名参加者などのユーザーがあります。

展開に Lync Server 2013 エッジサーバーまたはエッジプールのインストールが含まれていた場合、考えられる通信の種類の範囲は、外部ユーザーアクセスのさまざまなオプション、他の SIP フェデレーションドメインのメンバーとの通信、SIP フェデレーションプロバイダー、および XMPP フェデレーションユーザーによって大幅に拡張されます。 エッジサーバーまたはエッジプールを設定したら、指定する外部ユーザーアクセスの種類を有効にし、外部アクセスを制御するポリシーを構成します。 Lync Server 2013 では、タスクの要件に基づいて Lync server コントロールパネル、Lync Server 管理シェル、またはその両方を使用して、外部ユーザーアクセスとポリシーを有効にし、構成します。 これらの管理ツールの詳細については、「操作」のドキュメントの「 [lync server 2013 管理ツール](lync-server-2013-lync-server-administrative-tools.md)」、「操作」のドキュメントの「lync Server [2013 management Shell](lync-server-2013-lync-server-management-shell.md) 」、および「操作」のドキュメントの「lync server [2013 管理ツールのインストール](lync-server-2013-install-lync-server-administrative-tools.md)」を参照してください。

<div>


> [!IMPORTANT]  
> 外部ユーザー アクセスの構成およびポリシーを設計する場合は、ポリシーの優先度およびポリシーの適用方法について理解しておく必要があります。 あるポリシー レベルで適用されている Lync Server ポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。 Lync Server ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。



</div>

組織の外部ユーザー アクセス サポートが既に有効になっている場合でも、既定では、リモート ユーザー アクセス、フェデレーション ユーザー アクセスなど、外部ユーザー アクセスをサポートするポリシーは構成されません。 外部ユーザー アクセスを制御するには、1 つ以上のポリシーを構成し、各ポリシーでサポートする外部ユーザー アクセスの種類を指定する必要があります。 これには、次の外部アクセス ポリシーが含まれます。

  - **グローバル ポリシー**   グローバル ポリシーは、エッジ サーバーを展開する際に作成されます。 既定では、グローバル ポリシーではどの外部ユーザー アクセス オプションも有効ではありません。 グローバル レベルで外部ユーザー アクセスをサポートするには、1 つ以上の外部ユーザー アクセス オプションをサポートするようにグローバル ポリシーを構成します。 グローバル ポリシーは組織内のすべてのユーザーに適用されますが、サイト ポリシーとユーザー ポリシーはグローバル ポリシーをオーバーライドします。 グローバル ポリシーを削除することはできません。 代わりに、既定の設定にリセットします。

  - **サイト ポリシー**   外部ユーザー アクセスのサポートを特定のサイトに限定するために、1 つ以上のサイト ポリシーを作成および構成できます。 サイト ポリシーの構成はグローバル ポリシーの構成よりも優先されますが、対象になるのはサイト ポリシーで指定された特定のサイトだけです。 たとえば、グローバル ポリシーでリモート ユーザー アクセスが有効になっていても、特定のサイトのリモート ユーザー アクセスを無効にするサイト ポリシーを指定することが可能です。 既定では、サイト ポリシーはそのサイトのすべてのユーザーに適用されますが、特定のユーザーにユーザー ポリシーを割り当てて、サイト ポリシーの設定を無効にすることができます。

  - **ユーザー ポリシー**   リモート ユーザー アクセスのサポートを特定のユーザーに限定するために、1 つ以上のユーザー ポリシーを作成および構成できます。 ユーザー ポリシーの構成はグローバル ポリシーやサイト ポリシーよりも優先されますが、そのユーザー ポリシーが割り当てられている特定のユーザーのみを対象にします。 たとえば、グローバル ポリシーとサイト ポリシーでリモート ユーザー アクセスが有効になっていても、リモート ユーザー アクセスを無効にするユーザー ポリシーを指定して、そのポリシーを特定のユーザーに割り当てることは可能です。 ユーザー ポリシーを作成した場合は、1 人以上のユーザーに適用しないと、実際には使用できません。

どの構成設定およびポリシーを作成または編集する必要があるかを判断するには、次の判断ポイントを参照してください。

**ドメインの内部ユーザーおよび外部ユーザーが、インスタント メッセージング、Web 会議、および音声/ビデオを使用して共同作業することを許可するか。**

トピック「 [lync server 2013 でリモートユーザーアクセスを制御するポリシーを構成する](lync-server-2013-configure-policies-to-control-remote-user-access.md)」、および「 [lync server 2013 でフェデレーションとパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にする」の説明のとおりに設定を構成します。

**匿名ユーザーが、展開内のユーザーがホストする電話会議に招待され、参加することを許可するか。**

トピック「lync server [2013 での匿名ユーザーのサポートのための会議](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)ポリシーの割り当て」、「lync server [2013 での会議ポリシーの作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)」、および「 [lync server 2013 の会議ポリシー設定の参照](lync-server-2013-conferencing-policy-settings-reference.md)」の説明のとおりに設定を構成します。

**ユーザーが、SIP フェデレーション ドメインの連絡先と通信することを許可するか。**

「Lync server [2013 でフェデレーションユーザーアクセスを制御するポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」、「 [Enable or disable FEDERATION and public IM Connectivity in lync server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)」、および「 [lync server 2013 での組織の SIP フェデレーションドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)」の説明のとおりに設定を構成します。

**SIP フェデレーション ドメインとの通信を有効化した場合、XMPP フェデレーション パートナーの連絡先との通信を有効化するか。**

トピック「 [configure policies to CONTROL The Lync server 2013 での xmpp フェデレーションユーザーアクセスを制御する](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)」および「 [lync server 2013 で xmpp フェデレーションパートナーを管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)する」の説明のとおりに設定を構成します。

**SIP フェデレーションドメインとの通信を有効にしている場合は、SIP フェデレーションの自動検出を有効にしますか。**

トピック「 [Lync Server 2013 でのフェデレーションパートナーの検出の有効化または無効化](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)」に記載されているとおりに設定を構成します。

**SIP フェデレーション ドメインとの通信を有効化した場合、フェデレーションからの連絡先に対して、アーカイブを使用しているため通信がアーカイブされる可能性があることを通知する免責事項の送信を有効化するか。**

トピック「 [Lync Server 2013 でのフェデレーションパートナーへのアーカイブ免責事項の送信を有効または無効](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)にする」で説明されているとおりに設定を構成します。

**ユーザーに、Windows Live Messenger、AOL、Yahoo などのパブリックプロバイダーとの通信を可能にする SIP フェデレーションプロバイダーとの通信を許可する \! かどうか。**

トピック「lync server [2013 でパブリックユーザーアクセスを制御するようにポリシーを構成する](lync-server-2013-configure-policies-to-control-public-user-access.md)」の説明に従って設定を構成します。 lync server[2013 の [フェデレーションとパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)]、および[lync SERVER 2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集](lync-server-2013-create-or-edit-public-sip-federated-providers.md)を行います。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。 アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。 メッセンジャーサービスが終了するまでの期間。 AOL および Yahoo! の2014年6月の寿命の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</P>
> <LI>
> <P>Lync は、組織間や世界中の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。 Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</P></LI></UL>



</div>

**ユーザーが、Microsoft 365、Microsoft Lync Online、Microsoft Lync Online 2010 を実行しているホストされているプロバイダーである SIP フェデレーションプロバイダーとの通信を許可するかどうか。**

トピック「lync server [2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集](lync-server-2013-create-or-edit-public-sip-federated-providers.md)」、「 [Enable or disable FEDERATION and public IM Connectivity in lync server 2013」](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 、および「 [create or Edit Hosted SIP フェデレーションプロバイダ lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md) 」の説明のとおりに設定を構成します。

**一部のユーザーのホーム サーバーは社内展開にあり、他のユーザーはオンライン環境のホーム サーバーに構成されている分割ドメイン (ハイブリッドとも呼ばれます) で展開が構成されているか。**

トピック「lync server [2013 でフェデレーションユーザーアクセスを制御するためのポリシーの構成](lync-server-2013-configure-policies-to-control-federated-user-access.md)」、「 [Enable or disable FEDERATION and public IM connectivity in lync server 2013」](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 、および「 [Create or Edit Hosted SIP フェデレーションプロバイダ lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md) 」の説明のとおりに設定を構成します。

次に、要件を一覧表示した表を示します。


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>フェデレーションのタブと外部アクセス (経由) フェデレーションまたは外部アクセスの種類 (下)</th>
<th>外部アクセス ポリシー</th>
<th>アクセス エッジ構成</th>
<th>SIP フェデレーション ドメイン</th>
<th>SIP フェデレーション プロバイダー</th>
<th>XMPP フェデレーション パートナー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>リモート ユーザー</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスを制御するポリシーの構成</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモートユーザーアクセスを有効または無効にする</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>SIP フェデレーションからの連絡先</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションユーザーアクセスを制御するポリシーの構成</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013 でのフェデレーションパートナーの検出を有効または無効にする</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Lync Server 2013 でのフェデレーションパートナーへのアーカイブ免責事項の送信を有効または無効にする</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013 での組織の SIP フェデレーションドメインの管理</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>XMPP フェデレーションからの連絡先</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションユーザーアクセスを制御するポリシーの構成</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Lync Server 2013 での XMPP フェデレーションユーザーアクセスを制御するポリシーの構成</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Lync Server 2013 での XMPP フェデレーションパートナーの管理</a></p></td>
</tr>
<tr class="even">
<td><p>分割ドメイン/ハイブリッド ユーザー</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でフェデレーションユーザーアクセスを制御するポリシーの構成</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">ホスト SIP フェデレーションプロバイダー Lync Server 2013 を作成または編集する</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>パブリック IM サービスの連絡先</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Lync Server 2013 でのパブリックユーザーアクセスを制御するポリシーの構成</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>会議や電話会議への匿名ユーザー アクセス</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Lync Server 2013 で匿名ユーザーをサポートするための会議ポリシーの割り当て</a></p>
<div>

> [!NOTE]  
> また、「会議ポリシー: lync <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">server 2013 での会議ポリシーの作成または変更」</A>および「 <A href="lync-server-2013-conferencing-policy-settings-reference.md">lync Server 2013 の会議ポリシー設定リファレンス</A>」の下にある次の構成設定を考慮する必要があります。


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


ユーザーは、組織の外部ユーザー アクセスを有効にしていない場合でも、外部ユーザー アクセスの制御に使用する任意のポリシーを含む、外部ユーザー アクセス設定を構成できます。ただし、構成したポリシーおよびその他の設定は、組織で外部ユーザー アクセスを有効にしていなければ、実際には使用できません。外部ユーザー アクセスが無効になっている場合やサポートする外部ユーザー アクセス ポリシーが構成されていない場合、外部ユーザーは組織のユーザーと通信できません。

エッジ展開は、エッジ サポートの構成方法に応じて、外部ユーザーの種類を認証し (匿名ユーザーは例外。匿名ユーザーは、会議を作成して参加者を招待した時に匿名の参加者に送信される会議 ID とパスキーによって認証)、アクセスを制御します。通信を制御するために、展開の内側と外側のユーザーが互いに通信する方法を定義する 1 つ以上のポリシーおよび設定を構成できます。ポリシーと設定には、特定のサイトまたはユーザーについて 1 つ以上の種類の外部ユーザー アクセスを有効にするために作成および構成できるサイト ポリシーおよびユーザー ポリシーに加えて、外部ユーザー アクセスの既定のグローバル ポリシーが含まれます。

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での外部アクセスポリシーの管理](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Lync Server 2013 での組織のアクセスエッジ構成の管理](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Lync Server 2013 での組織の SIP フェデレーションドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Lync Server 2013 での組織の SIP フェデレーションプロバイダーの管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Lync Server 2013 での XMPP フェデレーションパートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Lync Server 2013 で Lync Online 顧客のフェデレーションサポートを構成する](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

