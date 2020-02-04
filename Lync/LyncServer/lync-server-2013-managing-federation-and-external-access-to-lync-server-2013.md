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
ms.openlocfilehash: 9dadc455389d95c91996b75928def8f03b06c64e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>Lync Server 2013 へのフェデレーションおよび外部アクセスの管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-07_

エッジサーバーまたはエッジプールの展開は、外部ユーザーをサポートするための最初の手順です。 エッジサーバーの展開の詳細については、展開ドキュメントの「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。

Lync Server 2013 の内部展開をインストールして構成した後、組織内の内部ユーザーは、Active Directory ドメインサービス (AD DS) に SIP アカウントを持つ他の内部ユーザーと共同作業を行うことができます。 共同作業には、インスタントメッセージの送受信、プレゼンス状態の更新、会議 (「会議」とも呼ばれます) の参加が含まれます。 外部ユーザーアクセスを有効にして構成し、サポートされている外部ユーザーが内部の Lync Server ユーザーと共同作業できるかどうかを制御します。 外部ユーザーには、展開のリモートユーザー、フェデレーションユーザー (パブリックインスタントメッセージング (IM) サービスプロバイダーのサポートされているユーザーを含む)、XMPP フェデレーション、および会議の匿名参加者を含めることができます。

展開に Lync Server 2013 エッジサーバーまたはエッジプールのインストールが含まれている場合は、可能な通信の種類の範囲が、外部ユーザーアクセスのさまざまなオプションと、他の SIP フェデレーションドメインのメンバーとの通信に大きく拡張されています。SIP フェデレーションプロバイダーと XMPP フェデレーションされたユーザー。 エッジサーバーまたはエッジプールをセットアップした後、提供する外部ユーザーアクセスの種類を有効にし、外部アクセスを制御するためのポリシーを構成します。 Lync server 2013 では、lync Server コントロールパネル、Lync Server 管理シェル、またはその両方を使用して、外部ユーザーのアクセスとポリシーを有効にし、構成することができます。 これらの管理ツールの詳細については、「運用ドキュメントの[Lync server 2013 管理ツール](lync-server-2013-lync-server-administrative-tools.md)」、「運用ドキュメントの[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)」、「運用ドキュメント」の「lync server [2013 管理ツールをインストール](lync-server-2013-install-lync-server-administrative-tools.md)する」を参照してください。

<div>


> [!IMPORTANT]  
> 外部ユーザーアクセスの構成とポリシーを設計する場合は、ポリシーの優先順位とポリシーの適用方法を理解しておく必要があります。 1つのポリシーレベルで適用される Lync Server ポリシーの設定は、別のポリシーレベルで適用されている設定を上書きすることができます。 Lync Server ポリシーの優先順位: ユーザーポリシー (ほとんどの影響) によってサイトポリシーが上書きされ、サイトポリシーがグローバルポリシーを上書きします (最も影響が少なくなります)。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。



</div>

既定では、組織で外部ユーザーアクセスのサポートを有効にしている場合でも、リモートユーザーアクセス、フェデレーションされたユーザーアクセスなどの外部ユーザーアクセスをサポートするようにポリシーは構成されません。 外部ユーザーアクセスの使用を制御するには、1つ以上のポリシーを構成して、各ポリシーでサポートされている外部ユーザーアクセスの種類を指定する必要があります。 これには、次の外部アクセスポリシーが含まれます。

  - **グローバルポリシー**   エッジサーバーを展開すると、グローバルポリシーが作成されます。 既定では、グローバルポリシーで外部ユーザーアクセスオプションは有効になっていません。 グローバルレベルで外部ユーザーのアクセスをサポートするには、1つ以上の種類の外部ユーザーアクセスオプションをサポートするようにグローバルポリシーを構成します。 グローバルポリシーは組織内のすべてのユーザーに適用されますが、サイトポリシーとユーザーポリシーはグローバルポリシーを上書きします。 グローバルポリシーを削除しても、削除されることはありません。 代わりに、既定の設定にリセットします。

  - **サイトポリシー**   1 つ以上のサイトポリシーを作成し、構成して、特定のサイトへの外部ユーザーアクセスのサポートを制限することができます。 サイト ポリシーの構成はグローバル ポリシーよりも優先されますが、サイト ポリシーで指定されたサイトだけが対象となります。 たとえば、グローバルポリシーでリモートユーザーアクセスを有効にする場合、特定のサイトのリモートユーザーアクセスを無効にするサイトポリシーを指定することができます。 既定では、サイトポリシーはそのサイトのすべてのユーザーに適用されますが、サイトポリシー設定を上書きするユーザーポリシーをユーザーに割り当てることができます。

  - **ユーザーポリシー**   1 つまたは複数のユーザーポリシーを作成および構成して、リモートユーザーアクセスのサポートを特定のユーザーに制限することができます。 ユーザーポリシーの構成は、グローバルポリシーおよびサイトポリシーを上書きしますが、ユーザーポリシーが割り当てられている特定のユーザーに対してのみ設定されます。 たとえば、グローバルポリシーとサイトポリシーでリモートユーザーアクセスを有効にすると、リモートユーザーアクセスを無効にするユーザーポリシーを指定して、そのユーザーポリシーを特定のユーザーに割り当てることができます。 ユーザーポリシーを作成する場合は、それを有効にする前に1人以上のユーザーに適用する必要があります。

作成または編集する必要のある構成設定とポリシーを決定するには、次の決定ポイントを参照してください。

**インスタントメッセージング、Web 会議、音声/ビデオを使用して、ドメインの内部および外部ユーザーが共同作業できるようにする必要がありますか?**

「 [Lync server 2013 でリモートユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-remote-user-access.md)」および「 [lync server 2013 でフェデレーションとパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にする」の説明に従って設定を構成します。

**組織内のユーザーによってホストされている会議への参加を匿名ユーザーに許可するかどうかを指定します。**

「Lync server [2013 で](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)会議ポリシーを割り当て、lync server 2013 の会議ポリシーを[作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)する」、「Lync server [2013 の会議ポリシー設定リファレンス](lync-server-2013-conferencing-policy-settings-reference.md)」で説明するように設定を構成します。

**SIP フェデレーションドメイン連絡先との通信をユーザーに許可しますか?**

「Lync server [2013 でフェデレーションされたユーザーアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」、「lync server [2013 でフェデレーションとパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にする」、「lync server [2013 で組織の SIP フェデレーションドメインを管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)する」の説明に従って設定を構成します。

**SIP フェデレーションドメインとの通信を有効にしている場合は、XMPP フェデレーションパートナーの連絡先との通信を有効にしますか?**

「[ポリシーを構成して、Lync server 2013 での XMPP フェデレーションユーザーアクセスを制御する](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)」および「 [lync server 2013 で xmpp フェデレーションパートナーを管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)する」の説明に従って設定を構成します。

**SIP フェデレーションドメインとの通信を有効にしている場合、SIP フェデレーション自動検出を有効にしますか?**

「 [Lync Server 2013 でフェデレーションパートナーの検出を有効または無効](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)にする」のトピックで詳しく説明するように設定を構成します。

**SIP フェデレーションドメインとの通信を有効にしている場合は、アーカイブを使用していて、通信がアーカイブされていることを通知するフェデレーションされた連絡先への免責事項の送信を有効にしますか?**

「 [Lync Server 2013 のフェデレーションパートナーへのアーカイブの免責事項の送信を有効または無効](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)にする」のトピックで詳しく説明するように設定を構成します。

**ユーザーに、Windows Live Messenger、AOL、Yahoo\!などのパブリックプロバイダーとの通信を可能にする SIP フェデレーションプロバイダーとの通信を許可しますか?**

「 [Lync server 2013 でパブリックユーザーアクセスを制御するポリシーを構成する](lync-server-2013-configure-policies-to-control-public-user-access.md)」の説明に従って設定を構成します。 lync server[2013 でフェデレーションとパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にし、 [LYNC server 2013 でパブリック SIP フェデレーションプロバイダーを作成または編集](lync-server-2013-create-or-edit-public-sip-federated-providers.md)します。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。 アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。 サービスが終了するまでの Messenger。 AOL および Yahoo! の2014年6月の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</P>
> <LI>
> <P>Lync は、組織間、および世界各地の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。 Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</P></LI></UL>



</div>

**Microsoft Office 365、Microsoft Lync Online、Microsoft Lync Online 2010 を実行しているホスティングプロバイダーである SIP フェデレーションプロバイダーとの通信をユーザーに許可しますか?**

トピック「 [lync server 2013 でパブリック SIP フェデレーションプロバイダーを作成または編集](lync-server-2013-create-or-edit-public-sip-federated-providers.md)する」、「lync server [2013 でフェデレーションおよびパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にする」、「ホストされている[sip フェデレーションプロバイダーを作成または編集](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)する」の説明に従って設定を構成します。 lync server 2013

**展開は、分割 (ハイブリッド) ドメインで構成されます。一部のユーザーは、オンプレミスの展開でホームサーバーを使用していますが、他のユーザーはオンライン環境でホームサーバーを使用して構成されていますか?**

「Lync server [2013 でフェデレーションされたユーザーのアクセスを制御するためのポリシーを構成する](lync-server-2013-configure-policies-to-control-federated-user-access.md)」、「lync server [2013 でフェデレーションとパブリック IM 接続を有効または無効](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)にする」、「ホストされた[SIP フェデレーションプロバイダーを作成または編集する」 lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)の設定を構成します。

要件を一覧表示するテーブルが必要な場合は、次のようにします。


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
<th>フェデレーションおよび外部アクセス (分散) フェデレーションまたは外部アクセスの種類 (ダウン) のタブ</th>
<th>外部アクセス ポリシー</th>
<th>Access Edge 構成</th>
<th>SIP フェデレーションドメイン</th>
<th>SIP フェデレーション プロバイダー</th>
<th>XMPP フェデレーションパートナー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>リモートユーザー</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Lync Server 2013 でのリモート ユーザー アクセスを制御するポリシーの構成</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモート ユーザー アクセスの有効化または無効化</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>SIP フェデレーション連絡先</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013 でのフェデレーション パートナーの検出の有効化または無効化</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Lync Server 2013 でのフェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013 での組織の SIP フェデレーション ドメインの管理</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>XMPP フェデレーション連絡先</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Lync Server 2013 での XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理</a></p></td>
</tr>
<tr class="even">
<td><p>ドメイン/ハイブリッドユーザーの分割</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Lync Server 2013 でのホスト SIP フェデレーション プロバイダーの作成または編集</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>パブリック IM サービスの連絡先</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Lync Server 2013 でのパブリック ユーザー アクセスを制御するポリシーの構成</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013 での公開 SIP フェデレーション プロバイダーの作成または編集</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>匿名ユーザーによる会議と会議へのアクセス</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Lync Server 2013 での匿名ユーザー サポートのための会議ポリシーの割り当て</a></p>
<div>

> [!NOTE]  
> 会議ポリシーの下で、次の構成設定を検討する必要があります。 <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">Lync server 2013 の会議ポリシーを作成または変更</A>する、 <A href="lync-server-2013-conferencing-policy-settings-reference.md">lync Server 2013 の会議ポリシー設定リファレンス</A>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


外部ユーザーアクセスを制御するために使用するポリシーなど、組織の外部ユーザーアクセスを有効にしていない場合でも、外部ユーザーアクセスの設定を構成できます。 ただし、構成したポリシーとその他の設定は、組織で外部ユーザーのアクセスが有効になっている場合にのみ有効になります。 外部ユーザーのアクセスが無効になっている場合、または外部ユーザーのアクセスポリシーがサポートされていない場合、外部ユーザーは組織のユーザーと通信できません。

エッジ展開では、外部ユーザーの種類 (会議 ID によって認証された匿名ユーザー、会議の作成および参加者の招待時に匿名の参加者に送信されるパスキー) を認証します。edge サポートの構成方法に基づくアクセス。 通信を制御するために、1つまたは複数のポリシーを構成し、展開の内外のユーザーとの通信方法を定義する設定を構成することができます。 ポリシーと設定には、外部ユーザーアクセスの既定のグローバルポリシーに加えて、特定のサイトまたはユーザーに対して1つ以上の種類の外部ユーザーアクセスを有効にするために作成および構成できるサイトとユーザーのポリシーが含まれます。

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 での組織の外部アクセス ポリシーの管理](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Lync Server 2013 での組織のアクセス エッジ構成の管理](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Lync Server 2013 での組織の SIP フェデレーション ドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Lync Server 2013 での組織の SIP フェデレーション プロバイダーの管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Lync Server 2013 での Lync Online ユーザーのフェデレーションサポートの構成](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

