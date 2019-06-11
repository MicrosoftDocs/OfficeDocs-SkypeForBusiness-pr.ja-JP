---
title: 通話受付制御の要件を収集する例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e17d9abb0387f0d77c696487558dec0c915b1651
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a>例: Lync Server 2013 での通話受付制御の要件の収集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

この例では、通話受付管理 (CAC) の計画および実装方法を示します。これは大まかに次の作業で構成されます。

1.  すべてのネットワーク ハブおよびバックボーン (*ネットワーク地域*とも呼ばれます) を特定します。

2.  各ネットワーク領域の CAC を管理する Lync Server セントラルサイトを特定します。

3.  各ネットワーク地域に接続される*ネットワーク サイト*を特定および定義します。

4.  WAN への接続に帯域幅の制約がある各ネットワークサイトについては、WAN 接続の帯域幅の容量と、ネットワーク管理者が Lync Server メディアトラフィック用に設定した帯域幅制限 (該当する場合) について説明します。 WAN への接続に帯域幅の制限がないサイトは含める必要はありません。

5.  ネットワークの各サブネットをネットワーク サイトに関連付けます。

6.  ネットワーク地域間のリンクをマップします。 各リンクについて、帯域幅の容量と、ネットワーク管理者が Lync Server メディアトラフィックに使用した制限事項について説明します。

7.  ネットワーク地域のすべてのペア間のルートを定義します。

<div>

## <a name="gather-the-required-information"></a>必要な情報の収集

通話受付管理の準備を行うには、次の手順で示されている情報を収集します。

1.  ネットワーク地域を特定します。ネットワーク地域とは、ネットワーク バックボーンまたはネットワーク ハブを示します。
    
    ネットワーク バックボーンまたはネットワーク ハブとは、異なる LAN またはサブネット間の情報交換用パスを提供して、ネットワークのさまざまな部分を相互接続するコンピューター ネットワーク インフラストラクチャの一部です。バックボーンは、小規模ロケーションから地理的に広範囲な地域まで、さまざまなネットワークを繋ぐことができます。通常、バックボーンの処理能力はバックボーンに接続するネットワークの処理能力よりも高くなっています。
    
    このトポロジ例では、北アメリカ、EMEA、および APAC の 3 つのネットワーク地域が存在します。 ネットワーク地域にはネットワーク サイトのコレクションが含まれます。 ネットワーク管理者と協力して、組織のネットワーク地域を定義します。

2.  各ネットワーク地域が関連付けられている中央サイトを特定します。 セントラルサイトには、少なくとも1つのフロントエンドサーバーが含まれています。また、ネットワーク領域の WAN 接続を通過するすべてのメディアトラフィックで CAC を管理する Lync Server 展開です。
    
    **3 つのネットワーク地域に分けられたエンタープライズ ネットワークの例**
    
    ![3 つのネットワークリージョンでのネットワークトポロジの例](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "3 つのネットワークリージョンでのネットワークトポロジの例")  
    
    <div>
    

    > [!NOTE]
    > Multiprotocol Label Switching (MPLS) ネットワークは、それぞれの地理的な場所が対応するネットワーク サイトを有する、ネットワーク地域として表される必要があります。 詳細については、計画ドキュメントの「<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">MPLS ネットワークでの、Lync Server 2013 による通話受付制御</A>」トピックを参照してください。

    
    </div>
    
    上記のネットワークトポロジの例では、3つのネットワーク領域があります。それぞれに、CAC を管理する Lync Server セントラルサイトがあります。 ネットワーク地域の適切な中央サイトは、地理的な近さによって選択されます。 メディア トラフィックはネットワーク地域内で最も重くなるため、所有権が地理的な近さで決まることで自己完結型となり、その他の中央サイトが使用できなくなった場合でも、機能し続けます。
    
    この例では、シカゴという名前の Lync Server 展開は北米地域のセントラルサイトです。
    
    北米のすべての Lync ユーザーは、シカゴの展開でサーバーに所属しています。 次の表に 3 つすべてのネットワーク地域の中央サイトを示します。
    
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
    <td><p>シカゴ</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA</p></td>
    <td><p>ロンドン</p></td>
    </tr>
    <tr class="odd">
    <td><p>APAC</p></td>
    <td><p>北京</p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > Lync Server のトポロジによっては、同じセントラルサイトを複数のネットワーク領域に割り当てることができます。

    
    </div>

3.  それぞれのネットワーク地域で、帯域幅に制限がない WAN 接続を有するネットワーク サイト (オフィスまたは場所) すべてを特定します。 これらのサイトは帯域幅の制限がないため、CAC 帯域幅ポリシーを適用する必要はありません。
    
    次の表に示されている例では、3 つのネットワーク サイトには帯域幅の制限がある WAN リンクがありません: ニューヨーク、シカゴ、およびデトロイト。
    
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
    <td><p>シカゴ</p></td>
    <td><p>北アメリカ</p></td>
    </tr>
    <tr class="odd">
    <td><p>デトロイト</p></td>
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
    <td><p>ポートランド</p></td>
    <td><p>北アメリカ</p></td>
    </tr>
    </tbody>
    </table>
    
    **帯域幅の制限がない 3 つのネットワーク サイト (シカゴ、ニューヨーク、デトロイト) および WAN 帯域幅の制限がある 3 つのネットワーク サイト (ポートランド、リノ、アルバカーキ) を持つ CAC ネットワーク地域、北アメリカ**
    
    ![WAN の帯域幅によって制約]されたネットワークサイトの例(images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "WAN の帯域幅によって制約")されたネットワークサイトの例  

5.  帯域幅の制限がある WAN リンクに対して、次の項目を決定します。
    
      - すべての同時音声セッションに対して設定する全体的な帯域幅制限。 新しいオーディオセッションによってこの制限を超過すると、Lync Server ではセッションの開始が許可されません。
    
      - 個々のオーディオセッションごとに設定する帯域幅の制限。 既定の CAC 帯域幅制限は 175 kbps ですが、管理者が変更することができます。
    
      - すべての同時ビデオセッションに対して設定する全体的な帯域幅制限。 新しいビデオセッションによってこの制限を超過する場合、Lync Server ではセッションの開始が許可されません。
    
      - 個々のビデオセッションに対して設定する帯域幅の制限。 既定の CAC 帯域幅制限は 700 kbps ですが、管理者が変更することができます。
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a>WAN 帯域幅の制約情報 (kbps の帯域幅) を備えたネットワークサイト
    
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
    <th>BW Limit</th>
    <th>オーディオ制限</th>
    <th>オーディオセッションの制限</th>
    <th>ビデオの制限</th>
    <th>ビデオセッションの制限</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>アルバカーキ</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>5,000</p></td>
    <td><p>2000</p></td>
    <td><p>175</p></td>
    <td><p>1400</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>リノ</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>1万</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="odd">
    <td><p>ポートランド</p></td>
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
    <td><p>シカゴ</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    </tr>
    <tr class="even">
    <td><p>デトロイト</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    </tr>
    </tbody>
    </table>


6.  ネットワーク内のすべてのサブネットについて、関連付けられたネットワークサイトを指定します。
    
    <div>
    

    > [!IMPORTANT]
    > ネットワークサイトが帯域幅の制約を受けていない場合でも、ネットワーク内のすべてのサブネットがネットワークサイトと関連付けられている必要があります。 これは、通話受付制御がサブネット情報を使用して、どのネットワークサイトでエンドポイントが配置されているかを判断するためです。 セッションの両方の当事者の場所が決定されると、通話受付制御によって、通話を確立するための十分な帯域幅があるかどうかを判断できます。 帯域幅の制限がないリンクを経由してセッションが確立されると、通知が生成されます。<BR>オーディオ/ビデオエッジサーバーを展開する場合、各エッジサーバーのパブリック IP アドレスが、エッジサーバーが展開されているネットワークサイトと関連付けられている必要があります。 A/V エッジサーバーの各パブリック IP アドレスは、サブネットマスクが32のサブネットとして、ネットワーク構成の設定に追加されている必要があります。 たとえば、シカゴに A/V エッジサーバーを展開している場合、それらのサーバーの各外部 IP アドレスに対して、サブネットマスク32を持つサブネットを作成し、そのサブネットにネットワークサイトシカゴを関連付けます。 パブリック IP アドレスの詳細については、計画ドキュメントの「 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Lync Server 2013 の外部の A/V ファイアウォールとポートの要件を確認</A>する」を参照してください。

    
    </div>
    
    <div>
    

    > [!NOTE]
    > ネットワークに存在するが、サブネットに関連付けられていない、または IP アドレスを含むサブネットがネットワークサイトに関連付けられていない IP アドレスのリストを指定して、キー正常性インジケータ (KHI) アラートが発生します。 このアラートは8時間以内に複数回発生することはありません。 関連する通知情報と例を以下に示します。<BR><STRONG>ソース:</STRONG>CS 帯域幅ポリシーサービス (コア)<BR><STRONG>イベント番号:</STRONG> 36034<BR><STRONG>レベル:</STRONG> 2<BR><STRONG>説明:</STRONG>次の IP アドレスのサブネット: &lt;ip アドレス&gt;の一覧が構成されていないか、サブネットがネットワークサイトに関連付けられていません。<BR><STRONG>原因:</STRONG>対応する IP アドレスのサブネットがネットワーク構成の設定で見つからないか、サブネットがネットワークサイトに関連付けられていません。<BR><STRONG>解像度:</STRONG>上記の IP アドレスの一覧に対応するサブネットをネットワーク構成の設定に追加し、すべてのサブネットをネットワークサイトに関連付けます。<BR>たとえば、アラートの IP アドレス一覧に10.121.248.226 と10.121.249.20 が指定されている場合、これらの IP アドレスはサブネットに関連付けられていないか、または関連付けられているサブネットがネットワークサイトに属していません。 10.121.248.0/24 および 10.121.249.0/24 がこれらのアドレスに対応するサブネットである場合、次の手順でこの問題を解決することができます。 
    > <OL>
    > <LI>
    > <P>IP アドレス 10.121.248.226 が 10.121.248.0/24 サブネットに関連付けられていること、および IP アドレス 10.121.249.20 が 10.121.249.0/24 サブネットに関連付けられていることを確認します。</P>
    > <LI>
    > <P>10.121.248.0/24 および 10.121.249.0/24 サブネットがそれぞれネットワーク サイトに関連付けられていることを確認します。</P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a>ネットワークサイトと関連サブネット (kbps の帯域幅)
    
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
    <th>BW Limit</th>
    <th>オーディオ制限</th>
    <th>オーディオセッションの制限</th>
    <th>ビデオの制限</th>
    <th>ビデオセッションの制限</th>
    <th>サブネット</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>アルバカーキ</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>5,000</p></td>
    <td><p>2000</p></td>
    <td><p>175</p></td>
    <td><p>1400</p></td>
    <td><p>700</p></td>
    <td><p>172.29.79.0/23、157.57.215.0/25、172.29.90.0/23、172.29.80.0/24</p></td>
    </tr>
    <tr class="even">
    <td><p>リノ</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>1万</p></td>
    <td><p>4000</p></td>
    <td><p>175</p></td>
    <td><p>2800</p></td>
    <td><p>700</p></td>
    <td><p>157.57.210.0/23、172.28.151.128、25</p></td>
    </tr>
    <tr class="odd">
    <td><p>ポートランド</p></td>
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
    <td><p>シカゴ</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>(制限なし)</p></td>
    <td><p>157.57.211.0/23、172.28.152.128、25</p></td>
    </tr>
    <tr class="even">
    <td><p>デトロイト</p></td>
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


7.  Lync Server の通話受付制御では、ネットワーク領域間の接続は*地域リンク*と呼ばれます。 各地域のリンクについて、ネットワークサイトの場合と同様に、次のことを確認します。
    
      - すべての同時音声セッションに対して設定する全体的な帯域幅制限。 新しいオーディオセッションによってこの制限を超過すると、Lync Server ではセッションの開始が許可されません。
    
      - 個々のオーディオセッションごとに設定する帯域幅の制限。 既定の CAC 帯域幅制限は 175 kbps ですが、管理者が変更することができます。
    
      - すべての同時ビデオセッションに対して設定する全体的な帯域幅制限。 新しいビデオセッションによってこの制限を超過する場合、Lync Server ではセッションの開始が許可されません。
    
      - 個々のビデオセッションに対して設定する帯域幅の制限。 既定の CAC 帯域幅制限は 700 kbps ですが、管理者が変更することができます。
    
    **帯域幅の制限が関連付けられたネットワーク領域のリンク**
    
    ![3 つの地域間の制限の例](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "3 つの地域間の制限の例")  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a>地域リンクの帯域幅情報 (kbps の帯域幅)
    
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
    <th>First Region</th>
    <th>Second Region</th>
    <th>BW Limit</th>
    <th>オーディオ制限</th>
    <th>オーディオセッションの制限</th>
    <th>ビデオの制限</th>
    <th>ビデオセッションの制限</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>NA-EMEA-リンク</p></td>
    <td><p>北アメリカ</p></td>
    <td><p>EMEA</p></td>
    <td><p>5万</p></td>
    <td><p>2万</p></td>
    <td><p>175</p></td>
    <td><p>14000</p></td>
    <td><p>700</p></td>
    </tr>
    <tr class="even">
    <td><p>EMEA-APAC リンク</p></td>
    <td><p>EMEA</p></td>
    <td><p>APAC</p></td>
    <td><p>25,000</p></td>
    <td><p>1万</p></td>
    <td><p>175</p></td>
    <td><p>7000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


8.  ネットワーク地域のすべてのペア間のルートを定義します。
    
    <div>
    

    > [!NOTE]
    > 北アメリカと APAC の地域間のルートには、直接接続する地域のリンクがないため、2つのリンクが必要です。

    
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
    <th>First Region</th>
    <th>Second Region</th>
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
    <td><p>NA-EMEA-リンク、EMEA-APAC リンク</p></td>
    </tr>
    </tbody>
    </table>


9.  1つのリンク (*サイト間*リンクと呼ばれます) によって直接接続されているネットワークサイトのペアごとに、次のことを確認します。
    
      - すべての同時音声セッションに対して設定する全体的な帯域幅制限。 新しいオーディオセッションによってこの制限を超過すると、Lync Server ではセッションの開始が許可されません。
    
      - 個々のオーディオセッションごとに設定する帯域幅の制限。 既定の CAC 帯域幅制限は 175 kbps ですが、管理者が変更することができます。
    
      - すべての同時ビデオセッションに対して設定する全体的な帯域幅制限。 新しいビデオセッションによってこの制限を超過する場合、Lync Server ではセッションの開始が許可されません。
    
      - 個々のビデオセッションに対して設定する帯域幅の制限。 既定の CAC 帯域幅制限は 700 kbps ですが、管理者が変更することができます。
    
    **Reno とアルバカーキの間にあるサイト間リンクの帯域幅と帯域幅の制限を示す CAC ネットワークの地域 (北アメリカ)**
    
    ![WAN の帯域幅の例によって制約]されたネットワークサイト(images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "WAN の帯域幅の例によって制約")されたネットワークサイト  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a>2つのネットワークサイト間のサイト間リンクの帯域幅情報 (kbps 単位の帯域幅)
    
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
    <th>第1のサイト</th>
    <th>第2のサイト</th>
    <th>BW Limit</th>
    <th>オーディオ制限</th>
    <th>オーディオセッションの制限</th>
    <th>ビデオの制限</th>
    <th>ビデオセッションの制限</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Reno-Albu-サイト間リンク</p></td>
    <td><p>リノ</p></td>
    <td><p>アルバカーキ</p></td>
    <td><p>2万</p></td>
    <td><p>12000</p></td>
    <td><p>175</p></td>
    <td><p>5,000</p></td>
    <td><p>700</p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a>次のステップ

必要な情報を収集した後は、Lync Server 管理シェルまたは Lync Server コントロールパネルを使用して、CAC 展開を実行できます。

<div>


> [!NOTE]
> Lync Server コントロールパネルを使用して、ほとんどのネットワーク構成タスクを実行できますが、サブネットとサイト間リンクを作成するには、Lync Server 管理シェルを使用する必要があります。 詳細については、<STRONG>新しい-CsNetworkSubnet</STRONG>コマンドレットと<STRONG>CsNetworkIntersitePolicy</STRONG>コマンドレットの Lync Server 管理シェルのマニュアルを参照してください。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

