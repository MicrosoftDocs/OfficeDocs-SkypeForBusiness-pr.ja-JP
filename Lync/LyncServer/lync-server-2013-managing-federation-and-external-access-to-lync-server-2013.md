---
title: 'Lync Server 2013: Lync Server 2013 へのフェデレーションおよび外部アクセスの管理'
TOCTitle: Lync Server 2013 へのフェデレーションおよび外部アクセスの管理
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48271594
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 へのフェデレーションおよび外部アクセスの管理

 

_**トピックの最終更新日:** 2015-03-09_

外部ユーザーをサポートするには、最初に、エッジ サーバーまたはエッジ プールを展開する必要があります。 エッジ サーバーの展開の詳細については、「展開」のドキュメントの「[Lync Server 2013 での外部ユーザー アクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。

Lync Server 2013 の内部展開のインストールと構成が終わると、組織の内部ユーザーは、Active Directory ドメイン サービス (AD DS) で SIP アカウントを持つ他の内部ユーザーと共同作業ができます。共同作業には、インスタント メッセージの送受信、プレゼンス状態の更新、電話会議 (「会議」とも呼ばれます) への参加などがあります。外部ユーザー アクセスを有効にして構成し、サポートされる外部ユーザーが内部 Lync Server ユーザーと共同作業できるかどうかを制御します。外部ユーザーには、展開のリモート ユーザー、フェデレーション ユーザー (パブリック インスタント メッセージング (IM) サービス プロバイダーのサポートされるユーザーを含む)、XMPP フェデレーション、および電話会議への匿名参加者などのユーザーがあります。

展開に Lync Server 2013 の エッジ サーバーまたは エッジ プールのインストールが含まれている場合は、外部ユーザー アクセス、他の SIP フェデレーション ドメインのメンバーとの通信、SIP フェデレーション プロバイダー、および XMPP フェデレーション ユーザーに関する数多くのオプションによって、可能な通信の種類の範囲が大きく拡大します。エッジ サーバーまたは エッジ プールをセットアップした後、提供する外部ユーザー アクセスの種類を有効にして、外部アクセスを制御するためのポリシーを構成します。Lync Server 2013 では、Lync Server コントロール パネル、Lync Server 管理シェル、またはその両方を使用して、外部ユーザー アクセスおよびポリシーを有効にして構成します。これらの管理ツールの詳細については、「操作」のドキュメントの「[Lync Server 2013 管理ツール](lync-server-2013-lync-server-administrative-tools.md)」、「[Lync Server 2013 管理シェル](lync-server-2013-lync-server-management-shell.md)」、および「[Lync Server 2013 管理ツールをインストールする](lync-server-2013-install-lync-server-administrative-tools.md)」を参照してください。


> [!IMPORTANT]
> 外部ユーザー アクセスの構成およびポリシーを設計する場合は、ポリシーの優先度およびポリシーの適用方法について理解しておく必要があります。あるポリシー レベルで適用されている Lync Server ポリシー設定が、他のポリシー レベルで適用されている設定によって無効になることがあります。Lync Server ポリシーの優先順位は、ユーザー ポリシーが最も高く、サイト ポリシー、グローバル ポリシー (優先度が最も低い) と続きます。つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。



組織の外部ユーザー アクセス サポートが既に有効になっている場合でも、既定では、リモート ユーザー アクセス、フェデレーション ユーザー アクセスなど、外部ユーザー アクセスをサポートするポリシーは構成されません。外部ユーザー アクセスを制御するには、1 つ以上のポリシーを構成し、各ポリシーでサポートする外部ユーザー アクセスの種類を指定する必要があります。これには、次の外部アクセス ポリシーが含まれます。

  - **グローバル ポリシー**   エッジ サーバーの展開時に作成されます。既定では、グローバル ポリシーで有効になっている外部ユーザー アクセス オプションはありません。外部ユーザー アクセスをグローバル レベルでサポートするには、1 種類以上の外部ユーザー アクセス オプションをサポートするようにグローバル ポリシーを構成します。グローバル ポリシーは組織のすべてのユーザーに適用されますが、サイト ポリシーとユーザー ポリシーはグローバル ポリシーよりも優先されます。グローバル ポリシーを削除しても、ポリシー自体が削除されるのではなく、既定の設定にリセットされます。

  - **サイト ポリシー**   外部ユーザー アクセスのサポートを特定のサイトに限定するために、1 つ以上のサイト ポリシーを作成し、構成できます。サイト ポリシーの構成はグローバル ポリシーよりも優先されますが、サイト ポリシーで指定されたサイトだけが対象となります。たとえば、グローバル ポリシーでリモート ユーザー アクセスが有効になっていても、特定のサイトのリモート ユーザー アクセスを無効にするサイト ポリシーを指定できます。既定では、サイト ポリシーはそのサイトのすべてのユーザーに適用されますが、特定のユーザーにユーザー ポリシーを割り当てることで、サイト ポリシーの設定を無効にすることができます。

  - **ユーザー ポリシー**   リモート ユーザー アクセスのサポートを特定のユーザーに限定するために、1 つ以上のユーザー ポリシーを作成し、構成できます。ユーザー ポリシーの構成はグローバル ポリシーやサイト ポリシーよりも優先されますが、そのユーザー ポリシーが割り当てられている特定のユーザーだけが対象となります。たとえば、グローバル ポリシーとサイト ポリシーでリモート ユーザー アクセスを有効にしても、リモート ユーザー アクセスを無効にするユーザー ポリシーを指定し、そのポリシーを特定のユーザーに割り当てることができます。ユーザー ポリシーを作成した場合、ポリシーを有効にするには、1 人以上のユーザーに適用する必要があります。

どの構成設定およびポリシーを作成または編集する必要があるかを判断するには、次の判断ポイントを参照してください。

**ドメインの内部ユーザーおよび外部ユーザーが、インスタント メッセージング、Web 会議、および音声/ビデオを使用して共同作業することを許可するか。**

トピック「[Lync Server 2013 でのリモート ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-remote-user-access.md)」および「[Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)」の説明のとおりに設定を構成します。

**匿名ユーザーが、展開内のユーザーがホストする電話会議に招待され、参加することを許可するか。**

トピック「[Lync Server 2013 での匿名ユーザー サポートのための会議ポリシーの割り当て](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)」、「[Lync Server 2013 での会議ポリシーの作成または変更](lync-server-2013-create-or-modify-a-conferencing-policy.md)」、および「[Lync Server 2013 での会議ポリシー設定の参照](lync-server-2013-conferencing-policy-settings-reference.md)」の説明のとおりに設定を構成します。

**ユーザーが、SIP フェデレーション ドメインの連絡先と通信することを許可するか。**

トピック「[Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-federated-user-access.md)」、「[Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)」、および「[Lync Server 2013 での組織の SIP フェデレーション ドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)」の説明のとおりに設定を構成します。

**SIP フェデレーション ドメインとの通信を有効化した場合、XMPP フェデレーション パートナーの連絡先との通信を有効化するか。**

トピック「[Lync Server 2013 での XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)」および「[Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)」の説明のとおりに設定を構成します。

**SIP フェデレーション ドメインとの通信を有効化した場合、SIP フェデレーションの自動検出を有効化するか。**

トピック「[Lync Server 2013 でのフェデレーション パートナーの検出の有効化または無効化](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)」の説明のとおりに設定を構成します。

**SIP フェデレーション ドメインとの通信を有効化した場合、フェデレーションからの連絡先に対して、アーカイブを使用しているため通信がアーカイブされる可能性があることを通知する免責事項の送信を有効化するか。**

トピック「[Lync Server 2013 でのフェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)」の説明のとおりに設定を構成します。

**ユーザーに対して SIP フェデレーション プロバイダーとの通信を許可して、Windows Live Messenger、AOL、Yahoo\! などのパブリック プロバイダーと通信できるようにするか。**

トピック「[Lync Server 2013 でのパブリック ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-public-user-access.md)」、「[Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)」、および「[Lync Server 2013 での公開 SIP フェデレーション プロバイダーの作成または編集](lync-server-2013-create-or-edit-public-sip-federated-providers.md)」の説明のとおりに設定を構成します。


> [!IMPORTANT]
> <UL>
> <LI>
> <P>2012 年 9 月 1 日の時点で、Microsoft Lync パブリック IM 接続のユーザー サブスクリプション ライセンス ("PIC USL") を新規または更新契約において購入することができなくなりました。アクティブなライセンスをお持ちのお客様は、サービスの停止日まで Yahoo! Messenger とのフェデレーションを引き続きご利用いただけます。AOL と Yahoo! に関しては、2014 年 6 月の終了日が発表されています。詳細については、「<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリック インスタント メッセンジャーの接続のサポート</A>」を参照してください。</P>
> <LI>
> <P>PIC USL は、ユーザー単位および月単位のサブスクリプション ライセンスであり、Lync Server または Office Communications Server と Yahoo! Messenger とのフェデレーションを行うにはこのライセンスが必要です。Microsoft がこのサービスを提供できるのは、Yahoo! からのサポートを条件とするものでしたが、その基盤となる契約の終了が近づいてきました。</P>
> <LI>
> <P>Lync は組織間を接続したり世界中のユーザーと接続したりするための、これまで以上の強力なツールとなります。Windows Live Messenger とのフェデレーションを行うのに、Lync Standard CAL を超えてユーザー/デバイス ライセンスを追加する必要はありません。Skype フェデレーションがこのリストに追加されることで、Lync ユーザーは IM および音声を使用して数億のユーザーにアクセスできます。</P></LI></UL>



**Microsoft Office 365、Microsoft Lync Online、および Microsoft Lync Online 2010 を実行するホストされるプロバイダーである SIP フェデレーション プロバイダーとの通信をユーザーに許可するか。**

トピック「[Lync Server 2013 での公開 SIP フェデレーション プロバイダーの作成または編集](lync-server-2013-create-or-edit-public-sip-federated-providers.md)」、「[Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)」、および「[Lync Server 2013 でのホスト SIP フェデレーション プロバイダーの作成または編集](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)」の説明のとおりに設定を構成します。

**一部のユーザーのホーム サーバーは社内展開にあり、他のユーザーはオンライン環境のホーム サーバーに構成されている分割ドメイン (ハイブリッドとも呼ばれます) で展開が構成されているか。**

トピック「[Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-federated-user-access.md)」、「[Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)」、および「[Lync Server 2013 でのホスト SIP フェデレーション プロバイダーの作成または編集](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)」の説明のとおりに設定を構成します。

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
<th>[フェデレーションと外部アクセス] のタブ (横方向) フェデレーションまたは外部アクセスの種類 (縦方向)</th>
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
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Lync Server 2013 でのリモート ユーザー アクセスを制御するポリシーの構成</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモート ユーザー アクセスの有効化または無効化</a></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>SIP フェデレーションからの連絡先</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成</a></p>
<p></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013 でのフェデレーション パートナーの検出の有効化または無効化</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Lync Server 2013 でのフェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013 での組織の SIP フェデレーション ドメインの管理</a></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>XMPP フェデレーションからの連絡先</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Lync Server 2013 での XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理</a></p></td>
</tr>
<tr class="even">
<td><p>分割ドメイン/ハイブリッド ユーザー</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013 でのフェデレーション ユーザー アクセスを制御するポリシーの構成</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Lync Server 2013 でのホスト SIP フェデレーション プロバイダーの作成または編集</a></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>パブリック IM サービスの連絡先</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Lync Server 2013 でのパブリック ユーザー アクセスを制御するポリシーの構成</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013 での公開 SIP フェデレーション プロバイダーの作成または編集</a></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>会議や電話会議への匿名ユーザー アクセス</p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Lync Server 2013 での匿名ユーザー サポートのための会議ポリシーの割り当て</a></p>
<div>

> [!NOTE]
>「<a href="lync-server-2013-create-or-modify-a-conferencing-policy.md">Lync Server 2013 での会議ポリシーの作成または変更</a>」および「<a href="lync-server-2013-conferencing-policy-settings-reference.md">Lync Server 2013 での会議ポリシー設定の参照</a>」に説明されている、[電話会議ポリシー] の構成設定も考慮する必要があります。

</div></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


ユーザーは、組織の外部ユーザー アクセスを有効にしていない場合でも、外部ユーザー アクセスの制御に使用する任意のポリシーを含む、外部ユーザー アクセス設定を構成できます。ただし、構成したポリシーおよびその他の設定は、組織で外部ユーザー アクセスを有効にしていなければ、実際には使用できません。外部ユーザー アクセスが無効になっている場合やサポートする外部ユーザー アクセス ポリシーが構成されていない場合、外部ユーザーは組織のユーザーと通信できません。

エッジ展開は、エッジ サポートの構成方法に応じて、外部ユーザーの種類を認証し (匿名ユーザーは例外。匿名ユーザーは、会議を作成して参加者を招待した時に匿名の参加者に送信される会議 ID とパスキーによって認証)、アクセスを制御します。通信を制御するために、展開の内側と外側のユーザーが互いに通信する方法を定義する 1 つ以上のポリシーおよび設定を構成できます。ポリシーと設定には、特定のサイトまたはユーザーについて 1 つ以上の種類の外部ユーザー アクセスを有効にするために作成および構成できるサイト ポリシーおよびユーザー ポリシーに加えて、外部ユーザー アクセスの既定のグローバル ポリシーが含まれます。

## このセクション中

  - [Lync Server 2013 での組織の外部アクセス ポリシーの管理](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Lync Server 2013 での組織のアクセス エッジ構成の管理](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Lync Server 2013 での組織の SIP フェデレーション ドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Lync Server 2013 での組織の SIP フェデレーション プロバイダーの管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Lync Online の顧客のためのフェデレーション サポートの構成](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

