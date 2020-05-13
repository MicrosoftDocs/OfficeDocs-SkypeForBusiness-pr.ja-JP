---
title: 'Lync Server 2013: Lync フェデレーションのセットアップ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27b955def7b7648f274125353673d6973afb59b7
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>Lync Server 2013 での Lync フェデレーションのセットアップ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-03-27_

エッジ サーバーが既に展開されている場合、フェデレーション シナリオ機能は簡単に追加できます。 エッジ サーバーがまだセットアップされていない場合は、これを最初に行う必要があります。 詳細については、「展開」のドキュメントの「計画」のドキュメントの「planning [for external user](lync-server-2013-planning-for-external-user-access.md) Access in lync server [2013 in lync server](lync-server-2013-deploying-external-user-access.md) 2013」を参照してください。

<div>


> [!NOTE]  
> XMPP フェデレーション、Lync フェデレーション、またはパブリック インスタント メッセージング接続を組み合わせてセットアップする場合、これらを同時に展開することもできれば、1 つずつ展開することもできます。トポロジ ビルダーと Lync Server 管理シェルを通じてオプションを構成し、1 つ、2 つ、または 3 つすべてのフェデレーションの種類のオプションを構成した後でエッジ サーバーで展開ウィザードを実行すると、必要な手順の数が少なくてすみます。



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>トポロジ ビルダーと展開ウィザードで Lync フェデレーションをセットアップする

1.  フロントエンド サーバーでトポロジ ビルダーを開きます。エッジ プールを展開し、エッジ サーバーまたはエッジ サーバー プールを右クリックします。[プロパティの編集] をクリックします。

2.  [全般] の下の [プロパティの編集] で、[このエッジ プールのフェデレーションの有効化 (ポート 5061)] を選択します。[OK] をクリックします。

3.  [アクション] をクリックし、[トポロジ]、[公開] の順にクリックします。トポロジの公開を確認するプロンプトが表示されたら、[次へ] をクリックします。公開が完了したら、[完了] をクリックします。

4.  エッジ サーバーで、Lync Server 展開ウィザードを開きます。[Lync Server システムのインストールまたは更新] をクリックして、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。[再実行] をクリックします。

5.  [Lync Server コンポーネントのセットアップ] で、[次へ] をクリックします。概要画面に、実行された処理が表示されます。展開が完了したら、[ログの表示] をクリックして、利用可能なログ ファイルを表示します。[完了] をクリックして、展開を完了します。
    
    <div>
    

    > [!IMPORTANT]  
    > このオプションを選ぶことは可能ですが、組織内の 1 つのエッジ プールまたはエッジ サーバーのみ、フェデレーション用に外部に公開できます。パブリック インスタント メッセージング (IM) ユーザーを含め、フェデレーション ユーザーによるすべてのアクセスが同じエッジ プールまたは単一エッジサーバーを通過します。たとえば、ニューヨークとロンドンにそれぞれ展開されているエッジ プールまたは単一エッジ サーバーが展開に含まれている場合、ニューヨークのエッジ プールまたは単一エッジ サーバーでフェデレーション サポートを有効にすると、フェデレーション ユーザーの信号トラフィックはニューヨークのエッジ プールまたは単一エッジ サーバーを通過します。これは、ロンドンのユーザーとの通信の場合でも同じです。ただし、ロンドンの内部ユーザーがロンドンのフェデレーション ユーザーを呼び出す場合は、音声ビデオ トラフィックにロンドンのプールまたはエッジ サーバーを使用します。

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>パートナーとのフェデレーションを構成する

1.  別の Microsoft Lync Server 2013、Lync Server 2010、Office Communications Server 2007 R2、または Office Communicator 2007 との正常なフェデレーションをセットアップするには、次の表からフェデレーションの種類を選択し、DNS SRV レコード、DNS ホスト (A または IPv6 用の AAAA) を定義して、フェデレーションの種類に適用されるポリシーを構成します。
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>フェデレーションの種類</th>
    <th>DNS レコード</th>
    <th>ポリシー定義</th>
    <th>メモ</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>検出済みのパートナー ドメイン</p></td>
    <td><p>_Sipfederationtls _tcp &lt; 形式の SRV レコードを構成します。&gt;SRV レコードのポート値が TCP 5061 で、<strong>このサービスを提供するホスト</strong>が sip として定義されている外部ドメイン名。 &lt;外部ドメイン名 &gt; –アクセスエッジサービスの FQDN。 SRV レコードの作成の詳細については、「 <a href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013 でのエッジサポートのための DNS の構成</a>」を参照してください。</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013 でのフェデレーションパートナーの検出を有効または無効にする</a></p></li>
    </ul></td>
    <td><p>以前のバージョンでは、このフェデレーションの種類は、<strong>オープン拡張フェデレーション</strong>と呼ばれていました。この種類のフェデレーションでは、SRV レコードの作成が必要です。その他のパートナーがフェデレーションを検出できるようにします。</p></td>
    </tr>
    <tr class="even">
    <td><p>許可されたパートナー ドメイン</p></td>
    <td><p>_Sipfederationtls _tcp &lt; 形式の SRV レコードを構成します。&gt;SRV レコードのポート値が TCP 5061 で、<strong>このサービスを提供するホスト</strong>が sip として定義されている外部ドメイン名。 &lt;外部ドメイン名 &gt; –アクセスエッジサービスの FQDN。 SRV レコードの作成の詳細については、「 <a href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013 でのエッジサポートのための DNS の構成</a>」を参照してください。</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></p></li>
    </ul></td>
    <td><p>以前のバージョンでは、この種類のフェデレーションは<strong>拡張フェデレーション</strong>と呼ばれていました。 SRV レコードの作成は、この種類のフェデレーションではオプションであり、他のパートナーがフェデレーションを検出できるようにするために使用されます。 もちろん、これは<strong>オープン拡張フェデレーション</strong>、または検出された<strong>パートナードメイン</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p>許可されたパートナー サーバー</p></td>
    <td><p>ポリシーでフェデレーションパートナーとして SIP ドメイン名とパートナーエッジサーバーの FQDN を構成する</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Lync Server 2013 で許可された外部ドメインのサポートを構成する</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Lync Server 2013 で禁止された外部ドメインのサポートを構成する</a></p></li>
    </ul></td>
    <td><p>このフェデレーションの種類は 1 対 1 の関係の定義です。その他のフェデレーション パートナーの検出は許可されません。各フェデレーション パートナーは明示的に構成されます。以前のバージョンでは、これは<strong>直接フェデレーション</strong>と呼ばれていました。</p></td>
    </tr>
    <tr class="even">
    <td><p>ホスティング プロバイダーとパブリック IM プロバイダー</p></td>
    <td><p>このフェデレーションの種類では、特定の DNS 要件は定義されていません。</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でフェデレーションとパブリック IM 接続を有効または無効にする</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013 でのパブリック SIP フェデレーションプロバイダーの作成または編集</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">ホスト SIP フェデレーションプロバイダー Lync Server 2013 を作成または編集する</a></p></li>
    </ul></td>
    <td><p>このフェデレーションの種類では、ユーザーに対して構成するサービスとホスティングプロバイダーを定義します。 一般的には、Windows Live Messenger、Yahoo! などのパブリック IM プロバイダーの構成が含まれます。 および AOL に加えて、Lync Online や Microsoft 365 などのホスティングプロバイダー。</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>2012年9月1日時点で、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規購入時または契約の更新時に購入することができなくなりました。 アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。 メッセンジャーサービスが終了するまでの期間。 AOL および Yahoo! の2014年6月の寿命の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
    > <LI>
    > <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要なユーザーごとの月ごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートに応じて決定されました。これは、使用する基礎となる契約です。</P>
    > <LI>
    > <P>Lync は、組織間や世界中の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションでは、Lync Standard CAL を超えるユーザー/デバイスライセンスを追加する必要はありません。 Skype フェデレーションがこの一覧に追加され、Lync ユーザーが IM と音声を使用して数百人のユーザーにアクセスできるようになります。</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  すべての必要な DNS ホスト (A、または IPv6 では AAAA) と DNS SRV レコードを定義して、構成します。

3.  Lync Server コントロールパネルを使用するか、Lync Server 管理シェルと適切なコマンドレットを使用して、ポリシーを定義および構成します。 Lync Server 管理シェルのコマンドレットの詳細については、「 [Lync server 2013 のフェデレーションと外部アクセスのコマンドレット](https://docs.microsoft.com/powershell/module/skype/)」を参照してください。
    
    <div>
    

    > [!NOTE]  
    > Lync Room System (LRS) は、フェデレーションされた Lync パートナーの開催者から送信された会議の [参加] ボタンを表示しません。 会議参加リンクが LRS に表示されるようにするには、送信側の組織は次のコマンドレットを使用して TNEF を有効にする必要があります。<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>これは LRS 固有ではないことに注意してください。 MAPI プロパティは転送されませんが、Outlook の場合は、会議の招待状を開き、会議の URL をクリックすることで、outlook および Lync は Join リンクを表示しません。 TNEFEnabled が true に設定されている場合、Exchange 2013 は OnlineMeetingExternalLink を含む MAPI プロパティを削除しません。アラームに [参加] ボタンが表示されます。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージングの計画](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Lync Server 2013 へのフェデレーションおよび外部アクセスの管理](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

