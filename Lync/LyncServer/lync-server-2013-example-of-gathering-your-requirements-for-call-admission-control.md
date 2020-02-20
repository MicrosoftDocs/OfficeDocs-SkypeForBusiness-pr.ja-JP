---
title: 通話受付管理の要件の収集例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64731e324b93cb4baff85f36ad342016d3b68738
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a>例: Lync Server 2013 での通話受付管理の要件の収集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

この例では、通話受付管理 (CAC) の計画および実装方法を示します。これは大まかに次の作業で構成されます。

1.  すべてのネットワーク ハブおよびバックボーン (** ネットワーク地域とも呼ばれます) を特定します。

2.  各ネットワーク地域の CAC を管理する Lync Server 中央サイトを特定します。

3.  各ネットワーク地域に接続される*ネットワーク サイト*を特定および定義します。

4.  WAN への接続が帯域幅に制限されている各ネットワークサイトについて、WAN 接続の帯域幅の容量と、該当する場合は、ネットワーク管理者が Lync Server メディアトラフィックに設定した帯域幅制限を説明します。 WAN への接続に帯域幅の制限がないサイトは含める必要はありません。

5.  ネットワークの各サブネットをネットワーク サイトに関連付けます。

6.  ネットワーク地域間のリンクをマップします。 各リンクについて、帯域幅の容量と、ネットワーク管理者が Lync Server メディアトラフィックに対して行った制限を説明します。

7.  ネットワーク地域のすべてのペア間のルートを定義します。

<div>

## <a name="gather-the-required-information"></a>必要な情報の収集

通話受付管理の準備を行うには、次の手順で示されている情報を収集します。

1.  ネットワーク地域を特定します。 ネットワーク地域とは、ネットワーク バックボーンまたはネットワーク ハブを示します。
    
    ネットワーク バックボーンまたはネットワーク ハブとは、異なる LAN またはサブネット間の情報交換用パスを提供して、ネットワークの様々な部分を相互接続するコンピューター ネットワーク インフラストラクチャの一部です。 バックボーンは、小規模ロケーションから地理的に広範囲な地域まで、様々なネットワークを繋ぐことができます。 通常、バックボーンの処理能力はバックボーンに接続するネットワークの処理能力よりも高くなっています。
    
    このトポロジ例では、3 つのネットワーク地域が存在します。 北アメリカ、EMEA、および APAC。 ネットワーク地域にはネットワーク サイトのコレクションが含まれます。 ネットワーク管理者と協力して、組織のネットワーク地域を定義します。

2.  各ネットワーク地域が関連付けられている中央サイトを特定します。 中央サイトには少なくとも1つのフロントエンドサーバーが含まれており、ネットワーク地域の WAN 接続を通過するすべてのメディアトラフィックについて CAC を管理する Lync Server の展開です。
    
    **3 つのネットワーク地域に分けられたエンタープライズ ネットワークの例**
    
    ![3つのネットワーク地域を含むネットワークトポロジの例](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "3つのネットワーク地域を含むネットワークトポロジの例")  
    
    <div>
    

    > [!NOTE]
    > Multiprotocol Label Switching (MPLS) ネットワークは、それぞれの地理的な場所が対応するネットワーク サイトを有する、ネットワーク地域として表される必要があります。 詳細については、「計画」のドキュメントの「<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Lync Server を使用した MPLS ネットワーク上の通話受付管理 (Lync Server 2013 を使用した</A>場合)」トピックを参照してください。

    
    </div>
    
    前述のネットワークトポロジの例では、3つのネットワーク地域があり、それぞれには CAC を管理する Lync Server 中央サイトがあります。 ネットワーク地域の適切な中央サイトは、地理的な近さによって選ばれます。 メディア トラフィックはネットワーク地域内で最も重くなるため、所有権が地理的な近さで決まることで自己完結型となり、その他の中央サイトが使用できなくなった場合でも、機能し続けます。
    
    この例では、シカゴという名前の Lync Server 展開は、北米地域の中央サイトです。
    
    北米のすべての Lync ユーザーは、シカゴ展開のサーバーに所属しています。 次の表に 3 つすべてのネットワーク地域の中央サイトを示します。
    
    ### <a name="network-regions-and-their-associated-central-sites"></a>ネットワーク地域と関連付けられた中央サイト
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>ネットワーク地域</th>
    <th>中央サイト</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>北アメリカ</p></td>
    <td><p>Chicago</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA</p></td>
    <td><p>北海道</p></td>
    </tr>
    <tr class="odd">
    <td><p>APAC</p></td>
    <td><p>北京</p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > Lync Server トポロジに応じて、同じ中央サイトを複数のネットワーク地域に割り当てることができます。

    
    </div>

3.  それぞれのネットワーク地域で、帯域幅に制限がない WAN 接続を有するネットワーク サイト (オフィスまたは場所) すべてを特定します。 これらのサイトは帯域幅の制限がないため、CAC 帯域幅ポリシーを適用する必要はありません。
    
    次の表に示されている例では、3 つのネットワークサイトには帯域幅の制限がある WAN リンクがありません: ニューヨーク、シカゴ、およびデトロイト。
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a>WAN 帯域幅による制限がないネットワーク サイト
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>ネットワーク サイト</th>
    <th>ネットワーク地域</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>ニューヨーク</p></td>
    <td><p>北アメリカ</p></td>
    </tr>
    <tr class="even">
    <td><p>Chicago</p></td>
    <td><p>北アメリカ</p></td>
    </tr>
    <tr class="odd">
    <td><p>市</p></td>
    <td><p>北アメリカ</p></td>
    </tr>
    </tbody>
    </table>


4.  それぞれのネットワーク地域で、帯域幅の制限がある WAN リンクを介してネットワーク地域に接続しているすべてのネットワーク サイトを特定します。
    
    音声およびビデオの品質を確実なものにできるように、これらの帯域幅の制限があるネットワーク サイトは、WAN を監視し、ネットワーク地域への、およびネットワーク地域からのメディア (音声またはビデオ) トラフィック フローを制限する CAC 帯域幅ポリシーを使用することをお勧めします。
    
    次の表に示されている例では、WAN 帯域幅による制限がある 3 つのネットワーク サイトが存在します。 ポートランド、リノ、およびアルバカーキ。
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a>WAN 帯域幅による制限があるネットワーク サイト
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>ネットワーク サイト</th>
    <th>ネットワーク地域</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>アルバカーキ</p></td>
    <td><p>北アメリカ</p></td>
    </tr>
    <tr class="even">
    <td><p>リノ</p></td>
    <td><p>北アメリカ</p></td>
    </tr>
    <tr class="odd">
    <td><p>支店</p></td>
    <td><p>北アメリカ</p></td>
    </tr>
    </tbody>
    </table>
    
    **帯域幅の制限がない 3 つのネットワーク サイト (シカゴ、ニューヨーク、デトロイト) および WAN 帯域幅の制限がある 3 つのネットワーク サイト (ポートランド、リノ、アルバカーキ) を持つ CAC ネットワーク地域、北アメリカ**
    
    ![WAN 帯域幅による制限があるネットワークサイトの例](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "WAN 帯域幅による制限があるネットワークサイトの例")  

5.  帯域幅の制限がある WAN リンクに対して、次の項目を決定します。
    
      - すべての同時音声セッションに対して設定したい全体的な帯域幅制限。 新しいオーディオセッションでこの制限を超過すると、Lync Server ではセッションの開始が許可されなくなります。
    
      - それぞれ個別の音声セッションに対して設定したい帯域幅制限。既定の CAC 帯域幅制限は 175 kbps ですが、管理者はこれを変更することができます。
    
      - すべての同時ビデオ セッションに対して設定したい全体的な帯域幅制限。 新しいビデオセッションでこの制限を超過した場合、Lync Server ではセッションの開始が許可されません。
    
      - それぞれ個別のビデオ セッションに対して設定したい帯域幅制限。 既定の CAC 帯域幅制限は 700 kbps ですが、管理者はこれを変更することができます。
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a>WAN 帯域幅制限情報 (帯域幅は kbps で表示) とネットワーク サイト
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>ネットワーク サイト</th>
    <th>ネットワーク地域</th>
    <th>BW 制限</th>
    <th>音声制限</th>
    <th>音声セッション制限</th>
    <th>ビデオ制限</th>
    <th>ビデオ セッション制限</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>アルバカーキ</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>5,000</p></td>
    <td><p>2,000</p></td>
    <td><p>175</p></td>
    <td><p>1400</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>リノ</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>10,000</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="odd">
    <td><p>支店</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>5,000</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>ニューヨーク</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    </tr>
    <tr class="odd">
    <td><p>Chicago</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    </tr>
    <tr class="even">
    <td><p>市</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    </tr>
    </tbody>
    </table>


6.  ネットワークのすべてのサブネットに対し、関連付けられるネットワーク サイトを指定します。
    
    <div>
    

    > [!IMPORTANT]
    > すべてのサブネットは、たとえネットワーク サイトに帯域幅の制限がない場合でも、ネットワーク サイトに関連付けられる必要があります。 これは、通話受付管理はサブネット情報を使用してエンドポイントがどのネットワーク サイトに配置されているかを判断するためです。 セッションにおける両者の場所が決定した時、通話受付管理は通話を確立するのに十分な帯域幅があるかどうかを判断します。 帯域幅の制限がないリンクを介してセッションが確立した時、通知が生成されます。<BR>音声ビデオエッジサーバーを展開する場合は、エッジサーバーが展開されているネットワークサイトに各エッジサーバーのパブリック IP アドレスが関連付けられている必要があります。 音声ビデオエッジサーバーの各パブリック IP アドレスは、サブネットマスク32のサブネットとして、ネットワーク構成設定に追加する必要があります。 たとえば、をシカゴに展開する場合は、これらのサーバーの外部 IP アドレスごとに、サブネットマスク32を持つサブネットを作成し、ネットワークサイトシカゴとそのサブネットを関連付けます。 パブリック IP アドレスの詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Lync Server 2013 の外部の音声ビデオファイアウォールおよびポート要件を決定</A>する」を参照してください。

    
    </div>
    
    <div>
    

    > [!NOTE]
    > 主要状態インジケーター (KHI) 通知が発行され、ネットワークに存在している IP アドレスの一覧を指定します。ここで指定される一覧は、サブネットと関連付けられていないか、IP アドレスを含むサブネットがネットワーク サイトと関連付けられていません。 この通知は 8 時間に 1 回しか発行されません。 関連する通知の情報および例は以下の通りです。<BR><STRONG>ソース:</STRONG>CS 帯域幅ポリシーサービス (コア)<BR><STRONG>イベント番号:</STRONG> 36034<BR><STRONG>レベル:</STRONG> 2<BR><STRONG>説明:</STRONG>次の IP アドレスのサブネット: &lt;ip アドレス&gt;の一覧が構成されていないか、またはサブネットがネットワークサイトに関連付けられていません。<BR><STRONG>原因:</STRONG>対応する IP アドレスのサブネットがネットワーク構成設定にないか、またはサブネットがネットワークサイトに関連付けられていません。<BR><STRONG>解決策:</STRONG>前述の IP アドレスリストに対応するサブネットをネットワーク構成設定に追加し、すべてのサブネットをネットワークサイトに関連付けます。<BR>たとえば、通知に表示された IP アドレス リストが 10.121.248.226 および 10.121.249.20 であった場合、これらの IP アドレスがサブネットに関連付けられていないか、または関連付けられているサブネットがネットワーク サイトに属していないかのどちらかになります。10.121.248.0/24 および 10.121.249.0/24 がこれらのアドレスに対応するサブネットである場合、次の手順でこの問題を解決することができます。 
    > <OL>
    > <LI>
    > <P>IP アドレス 10.121.248.226 が 10.121.248.0/24 サブネットに関連付けられていること、および IP アドレス 10.121.249.20 が 10.121.249.0/24 サブネットに関連付けられていることを確認します。</P>
    > <LI>
    > <P>10.121.248.0/24 および 10.121.249.0/24 サブネットがそれぞれネットワーク サイトに関連付けられていることを確認します。</P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a>ネットワーク サイトと関連付けられたサブネット (帯域幅は kbps で表示)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>ネットワーク サイト</th>
    <th>ネットワーク地域</th>
    <th>BW 制限</th>
    <th>音声制限</th>
    <th>音声セッション制限</th>
    <th>ビデオ制限</th>
    <th>ビデオ セッション制限</th>
    <th>サブネット</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>アルバカーキ</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>5,000</p></td>
    <td><p>2,000</p></td>
    <td><p>175</p></td>
    <td><p>1400</p></td>
    <td><p>700</p></td>
    <td><p>172.29.79.0/23、157.57.215.0/25、172.29.90.0/23、172.29.80.0/24</p></td>
    </tr>
    <tr class="even">
    <td><p>リノ</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>10,000</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    <td><p>157.57.210.0/23、172.28.151.128/25</p></td>
    </tr>
    <tr class="odd">
    <td><p>支店</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>5,000</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    <td><p>172.29.77.0/24 10.71.108.0/24、157.57.208.0/23</p></td>
    </tr>
    <tr class="even">
    <td><p>ニューヨーク</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24</p></td>
    </tr>
    <tr class="odd">
    <td><p>Chicago</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>157.57.211.0/23、172.28.152.128/25</p></td>
    </tr>
    <tr class="even">
    <td><p>市</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>172.29.78.0/24 10.71.109.0/24、157.57.209.0/23</p></td>
    </tr>
    </tbody>
    </table>


7.  Lync Server の通話受付管理では、ネットワーク地域間の接続は*地域リンク*と呼ばれます。 各地域リンクに対し、ネットワーク サイトでしたように、次の項目を決定します。
    
      - すべての同時音声セッションに対して設定したい全体的な帯域幅制限。 新しいオーディオセッションでこの制限を超過すると、Lync Server ではセッションの開始が許可されなくなります。
    
      - それぞれ個別の音声セッションに対して設定したい帯域幅制限。既定の CAC 帯域幅制限は 175 kbps ですが、管理者はこれを変更することができます。
    
      - すべての同時ビデオ セッションに対して設定したい全体的な帯域幅制限。 新しいビデオセッションでこの制限を超過した場合、Lync Server ではセッションの開始が許可されません。
    
      - それぞれ個別のビデオ セッションに対して設定したい帯域幅制限。 既定の CAC 帯域幅制限は 700 kbps ですが、管理者はこれを変更することができます。
    
    **関連付けられた帯域幅制限とネットワーク地域リンク**
    
    ![3つの地域間の制限の例](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "3つの地域間の制限の例")  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a>地域リンク帯域幅情報 (帯域幅は kbps で表示)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>地域リンク名</th>
    <th>第 1 の地域</th>
    <th>第 2 の地域</th>
    <th>BW 制限</th>
    <th>音声制限</th>
    <th>音声セッション制限</th>
    <th>ビデオ制限</th>
    <th>ビデオ セッション制限</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-リンク</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>EMEA</p></td>
    <td><p>50,000</p></td>
    <td><p>20,000</p></td>
    <td><p>175</p></td>
    <td><p>14000</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC リンク</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>25,000</p></td>
    <td><p>10,000</p></td>
    <td><p>175</p></td>
    <td><p>7000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


8.  ネットワーク地域のすべてのペア間のルートを定義します。
    
    <div>
    

    > [!NOTE]
    > 北アメリカと APAC の間のルートには、両者を直接接続する地域リンクがないため、2 つのリンクが必要になります。

    
    </div>
    
    ### <a name="region-routes"></a>地域ルート
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>地域ルート名</th>
    <th>第 1 の地域</th>
    <th>第 2 の地域</th>
    <th>地域リンク</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-ルート</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>EMEA</p></td>
    <td><p>NA-EMEA-リンク</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC-ルート</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>EMEA-APAC リンク</p></td>
    </tr>
    <tr class="odd">
    <td><p>NA-APAC-ルート</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>APAC</p></td>
    <td><p>NA-EMEA-LINK, EMEA-APAC-LINK</p></td>
    </tr>
    </tbody>
    </table>


9.  単一のリンク (*サイト間*リンクと呼ばれます) で直接接続されているネットワーク サイトのペアに対して、次の項目を決定します。
    
      - すべての同時音声セッションに対して設定したい全体的な帯域幅制限。 新しいオーディオセッションでこの制限を超過すると、Lync Server ではセッションの開始が許可されなくなります。
    
      - それぞれ個別の音声セッションに対して設定したい帯域幅制限。既定の CAC 帯域幅制限は 175 kbps ですが、管理者はこれを変更することができます。
    
      - すべての同時ビデオ セッションに対して設定したい全体的な帯域幅制限。 新しいビデオセッションでこの制限を超過した場合、Lync Server ではセッションの開始が許可されません。
    
      - それぞれ個別のビデオ セッションに対して設定したい帯域幅制限。 既定の CAC 帯域幅制限は 700 kbps ですが、管理者はこれを変更することができます。
    
    **リノとアルバカーキ間のサイト間リンクに対する帯域幅処理能力および帯域幅制限を示すCAC ネットワーク地域、北アメリカ**
    
    ![WAN 帯域幅による制限があるネットワークサイトの例](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "WAN 帯域幅による制限があるネットワークサイトの例")  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a>2 つのネットワーク サイト間のサイト間リンクの帯域幅情報 (帯域幅は kbps で表示)
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>サイト間リンク名</th>
    <th>第 1 のサイト</th>
    <th>第 2 のサイト</th>
    <th>BW 制限</th>
    <th>音声制限</th>
    <th>音声セッション制限</th>
    <th>ビデオ制限</th>
    <th>ビデオ セッション制限</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>リノ-Albu-リンク</p></td>
    <td><p>リノ</p></td>
    <td><p>アルバカーキ</p></td>
    <td><p>20,000</p></td>
    <td><p>12000</p></td>
    <td><p>175</p></td>
    <td><p>5,000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a>次のステップ

必要な情報を収集した後は、Lync Server 管理シェルまたは Lync Server コントロールパネルを使用して CAC 展開を実行できます。

<div>


> [!NOTE]
> Lync Server コントロールパネルを使用してほとんどのネットワーク構成タスクを実行できますが、サブネットとサイト間リンクを作成するには、Lync Server 管理シェルを使用する必要があります。 詳細については、「Lync Server Management Shell」のドキュメントを参照してください。<STRONG>このコマンドレット</STRONG>と<STRONG>get-csnetworkintersitepolicy</STRONG>コマンドレットを参照してください。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

