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
ms.openlocfilehash: 7df0dd85bac0aa3053fb6a3496d6a13fa1f4a85e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>Lync Server 2013 での Lync フェデレーションのセットアップ

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-03-27_

エッジサーバーまたはサーバーを既に展開している場合は、フェデレーションシナリオ機能を追加することができます。 エッジサーバーをセットアップしていない場合は、最初にこの操作を行う必要があります。 詳細については、「 [Lync server 2013 での外部ユーザーアクセスの計画](lync-server-2013-planning-for-external-user-access.md)」を参照してください。これには、展開ドキュメントの「 [lync server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。

<div>


> [!NOTE]  
> XMPP フェデレーション、Lync フェデレーション、またはパブリックインスタントメッセージング接続の任意の組み合わせを設定する場合は、それらを同時に、または一度に1つずつ展開することができます。 トポロジビルダーと Lync Server 管理シェルを使用してオプションを構成する場合は、1つ、2つ、または3つのフェデレーションの種類のオプションを構成した後で、エッジサーバーで展開ウィザードを実行すると、必要な手順の数を減らすことができます。



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>トポロジビルダーと展開ウィザードでの Lync フェデレーションのセットアップ

1.  フロントエンドサーバーで、[トポロジビルダー] を開きます。 [Edge プール] を展開し、エッジサーバーまたはエッジサーバープールを右クリックします。 [プロパティの編集] を選びます。

2.  [プロパティの編集] の [全般] で、[このエッジプールに対してフェデレーションを有効にする (ポート 5061)] を選択します。 [OK] をクリックします。

3.  [アクション] をクリックし、[トポロジ] を選択し、[発行] を選択します。 トポロジの発行を求められたら、[次へ] をクリックします。 発行が完了したら、[完了] をクリックします。

4.  エッジサーバーで、Lync Server 展開ウィザードを開きます。 [Lync Server System のインストールまたは更新] をクリックし、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。 [実行] をもう一度クリックします。

5.  Lync Server コンポーネントのセットアップで、[次へ] をクリックします。 概要画面には、実行中の操作が表示されます。 展開が完了したら、[ログの表示] をクリックして、利用可能なログファイルを表示します。 [完了] をクリックして展開を完了します。
    
    <div>
    

    > [!IMPORTANT]  
    > このオプションは選択できますが、フェデレーション用に組織内のエッジプールまたはエッジサーバーを1つだけにすることができます。 パブリックインスタントメッセージング (IM) ユーザーを含むフェデレーションユーザーによるすべてのアクセスは、同じエッジプールまたは単一エッジサーバーを通過します。 たとえば、展開に、ニューヨークに展開されたエッジプールまたは1つのエッジサーバーとロンドンに展開された1つのエッジサーバーが含まれており、ニューヨークのプールまたは単一エッジサーバーでフェデレーションサポートを有効にしている場合、フェデレーションユーザーのシグナルトラフィックはニューヨークを通過します。エッジプールまたは単一エッジサーバー。 これは、london ユーザーとの通信でも同じですが、london フェデレーションユーザーを呼び出す London の内部ユーザーは、A/V トラフィック用に London プールまたはエッジサーバーを使用します。

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>パートナーとのフェデレーションを構成する

1.  別の Microsoft Lync Server 2013、Lync Server 2010、Office Communications Server 2007 R2、または Office Communicator 2007 とのフェデレーションを正常に実行するには、次の表からフェデレーションの種類を選択し、DNS SRV レコード、DNS ホスト (A または AAAA) を定義します。IPv6)、およびフェデレーションの種類に適用されるポリシーを構成します。
    
    
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
    <td><p>検出されたパートナードメイン</p></td>
    <td><p>_Tcp _sipfederationtls 形式の SRV レコードを構成します。&lt;SRV レコードの&gt;ポート値が TCP 5061 であり、<strong>このサービスを提供</strong>しているホストが sip として定義されている外部ドメイン名。 &lt;外部ドメイン名&gt; –アクセスエッジサービスの FQDN。 SRV レコードの作成の詳細については、「 <a href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013 での microsoft edge サポートの DNS の構成</a>」を参照してください。</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013 でのフェデレーション パートナーの検出の有効化または無効化</a></p></li>
    </ul></td>
    <td><p>以前のバージョンでは、この種類のフェデレーションを<strong>オープン拡張フェデレーション</strong>として参照しました。 SRV レコードの作成は、この種類のフェデレーションに必要であり、他のパートナーがフェデレーションを検出できるようにするために必要です。</p></td>
    </tr>
    <tr class="even">
    <td><p>許可されたパートナードメイン</p></td>
    <td><p>_Tcp _sipfederationtls 形式の SRV レコードを構成します。&lt;SRV レコードの&gt;ポート値が TCP 5061 であり、<strong>このサービスを提供</strong>しているホストが sip として定義されている外部ドメイン名。 &lt;外部ドメイン名&gt; –アクセスエッジサービスの FQDN。 SRV レコードの作成の詳細については、「 <a href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013 での microsoft edge サポートの DNS の構成</a>」を参照してください。</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p></li>
    </ul></td>
    <td><p>以前のバージョンでは、この種類のフェデレーションを<strong>拡張フェデレーション</strong>として参照しました。 SRV レコードの作成は、この種類のフェデレーションではオプションであり、他のパートナーがフェデレーションを検出できるようにするために使用されます。 これは、<strong>オープン拡張フェデレーション</strong>、または検出された<strong>パートナードメイン</strong>の場合です。</p></td>
    </tr>
    <tr class="odd">
    <td><p>許可されたパートナーサーバー</p></td>
    <td><p>ポリシーでフェデレーションパートナーとして SIP ドメイン名とパートナーエッジサーバーの FQDN を構成する</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Lync Server 2013 での、許可された外部ドメイン向けサポートの構成</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Lync Server 2013 での禁止された外部ドメイン向けサポートの構成</a></p></li>
    </ul></td>
    <td><p>このフェデレーションタイプは、1対1の関係であり、他のフェデレーションパートナーを検出することはできません。 各フェデレーションパートナーは、個別に構成されます。 以前のバージョンでは、これは<strong>直接フェデレーション</strong>と呼ばれていました。</p></td>
    </tr>
    <tr class="even">
    <td><p>ホスティングプロバイダーとパブリック IM プロバイダー</p></td>
    <td><p>この種類のフェデレーションには特定の DNS 要件が定義されていません</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013 での公開 SIP フェデレーション プロバイダーの作成または編集</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Lync Server 2013 でのホスト SIP フェデレーション プロバイダーの作成または編集</a></p></li>
    </ul></td>
    <td><p>このフェデレーションタイプでは、ユーザーに対して構成するサービスとホスティングプロバイダーを定義します。 一般的な使用方法 Windows Live Messenger、Yahoo! などのパブリック IM プロバイダーの構成が含まれます。 および AOL、Lync Online、Office 365 などのホスティングプロバイダー</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>2012年9月1日以降、Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") は、新規または更新契約の購入に使用できなくなりました。 アクティブなライセンスを持っているお客様は、Yahoo! とのフェデレーションを継続できます。 サービスが終了するまでの Messenger。 AOL および Yahoo! の2014年6月の終了日 が発表されました。 詳細については、「 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート</A>」を参照してください。</P>
    > <LI>
    > <P>PIC USL は、Lync Server または Office Communications Server が Yahoo! とのフェデレーションを行うために必要な1か月あたりのユーザーごとのサブスクリプションライセンスです。 Messenger. このサービスを提供するための Microsoft の機能は、Yahoo! からのサポートによって決定されたものであり、その基となる契約は "巻停止" となります。</P>
    > <LI>
    > <P>Lync は、組織間、および世界各地の個人と接続するための強力なツールです。 Windows Live Messenger とのフェデレーションには、Lync 標準 CAL 以外の追加のユーザー/デバイスライセンスは必要ありません。 Skype federation はこのリストに追加されます。 Lync ユーザーは、IM と音声を使用して、数百人の何百万ものユーザーに連絡できます。</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  必要な DNS ホスト (A または AAAA の場合は AAAA) と DNS SRV レコードを定義して構成する

3.  Lync Server コントロールパネルを使用するか、Lync Server 管理シェルと適切なコマンドレットを使用して、ポリシーを定義して構成します。 Lync Server 管理シェルコマンドレットの詳細については、「 [Lync server 2013 のフェデレーションと外部アクセスコマンドレット](https://docs.microsoft.com/powershell/module/skype/)」を参照してください。
    
    <div>
    

    > [!NOTE]  
    > Lync Room System (LRS) では、フェデレーションされた Lync パートナーの開催者によって送信された会議の [参加] ボタンは表示されません。 LRS に表示される会議の参加リンクの場合、送信側の組織は、次のコマンドレットを使用して TNEF を有効にする必要があります。<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>これは LRS 固有のものではないことに注意してください。 また、MAPI プロパティは転送されませんが、Outlook の場合は、outlook と Lync では、会議の出席依頼を開き、会議の URL をクリックすることができます。 TNEFEnabled が true に設定されている場合、Exchange 2013 は、OnlineMeetingExternalLink を含む MAPI プロパティを削除しません。また、アラームに [参加] ボタンが表示されます。

    
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

