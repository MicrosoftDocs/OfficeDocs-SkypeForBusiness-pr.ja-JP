---
title: 'Lync Server 2013: トポロジビルダーでの仲介サーバーの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f284b793c79ff3dcf8589a60469ed8525426de1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>Lync Server 2013 のトポロジビルダーでの仲介サーバーの定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-03-25_

このトピックの手順に従って、トポロジビルダーを使用して、まだエンタープライズ Voip を展開していないサイトで、スタンドアロンの仲介サーバーまたはフロントエンドプールと併置されているプールを定義します。

Administrators グループのメンバーであるアカウントを使用して、トポロジを定義することができます。

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>フロントエンドプールに併置された仲介サーバーの定義

このトピックの手順に従って、トポロジビルダーを使用して、エンタープライズ Voip がまだ展開されていないサイトのフロントエンドプールに併置された仲介サーバーを定義します。

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>仲介サーバーをフロントエンドプールに追加するには

1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

2.  トポロジビルダーのコンソールツリーで、フロントエンドプールを定義するサイトの名前を展開します。

3.  コンソールツリーで、目的のフロントエンドプールの種類を右クリックし、[**新しいフロントエンドプール**] をクリックします。

4.  [**併置されたサーバーの役割の選択**] ページが表示されるまで、**新しいフロントエンド プールの定義**ウィザードを進めます。

5.  **[併置**されたサーバーの役割の選択] で、[**仲介サーバーの検索**] オプションをオンにします。
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>選択したフロントエンドプールの種類が Enterprise Edition の場合は、そのフロントエンドプールのすべてのフロントエンドサーバーに仲介サーバーコンポーネントがインストールされます。</P>
    > <LI>
    > <P>仲介サーバーで使用される<STRONG>次ホッププール</STRONG>は、仲介サーバーが併置されているフロントエンドプールです。</P>
    > <LI>
    > <P>仲介サーバーで使用される<STRONG>エッジプール</STRONG>は、仲介サーバーが併置されているフロントエンドプールに関連付けられているものと同じエッジプールになります。</P></LI></UL>

    
    </div>

6.  Microsoft Office Communications Server 2007 R2 から PSTN への通話をルーティングするには、[**既定**にする] をクリックして、このフロントエンドプールを使用します。

7.  1つ以上のピアのフロントエンドプールへの関連付けが終了したら、[**完了**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > エンタープライズ Voip 展開プロセスの次の手順に進む前に、仲介サーバープール (つまり、仲介サーバーコンポーネントがあるフロントエンドプール) が、指定した Fqdn を使用していることを確認してください。

    
    </div>

8.  次に、展開ガイドのドキュメントの「 [Lync server 2013 のトポロジを公開](lync-server-2013-publish-the-topology.md)する」の手順に従って仲介サーバーをトポロジに追加してから、必要に応じて仲介サーバーのリッスンポートを変更する次の手順に進みます。 トポロジビルダーを使用してトポロジを定義または変更するたびに、トポロジを公開する必要があります。

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>スタンドアロンの仲介サーバーの定義

このトピックの手順に従って、トポロジビルダーを使用して、エンタープライズ Voip がまだ展開されていないサイトで、スタンドアロンの仲介サーバーまたはプールを定義します。

このサイトでフロントエンドプールに併置された仲介サーバーを既に展開している場合は、このセクションをスキップして、lync server 2013 での[仲介サーバーのファイルのインストール](lync-server-2013-install-the-files-for-mediation-server.md)を実行してから、 [lync server 2013 でのトランクの構成](lync-server-2013-configuring-trunks.md)に進むことができます。

<div>


> [!NOTE]  
> このセクションでは、「 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">lync server 2013 でのフロントエンドプールまたは Standard Edition サーバーの定義と構成</A>」の説明に従って、少なくとも1つのフロントエンドプールを事前にセットアップし、展開ガイドのドキュメントの「 <A href="lync-server-2013-publish-the-topology.md">lync server 2013 でトポロジを公開</A>することを前提としています。



</div>

<div>

## <a name="to-add-a-mediation-server"></a>仲介サーバーを追加するには

1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

2.  トポロジビルダーのコンソールツリーで、仲介サーバーを定義するサイトの名前を展開します。

3.  コンソールツリーで、[**仲介プール**] ノードを右クリックし、[**仲介サーバープール**] をクリックします。

4.  [**新しい仲介プールの定義**] で、仲介サーバープールの完全修飾ドメイン名 (FQDN) を入力します。

5.  次に、以下のいずれかの操作を行います。
    
      - プールに複数の仲介サーバーを展開して高可用性を提供する場合は、[**複数のコンピュータープール**] を選択します。
        
        <div>
        

        > [!NOTE]  
        > 複数の仲介サーバーがある仲介サーバープールをサポートするには、DNS 負荷分散を展開する必要があります。 詳細については、「計画」のドキュメントの「Using dns Load balancing on <A href="lync-server-2013-dns-load-balancing.md">Lync server 2013</A> 」の「dns 負荷分散を使用する」セクションを参照してください。

        
        </div>
    
      - 高可用性を必要としないためにプールに仲介サーバーを1つだけ展開する場合は、[**単一コンピューターのプール**] を選択します。 以下のステップは省略してください。

6.  前の手順で [**複数のコンピュータープール**] を選択した場合は、[**このプール内のコンピューターの定義**] 項目の [**コンピューターの fqdn**] をクリックし、プール内の各サーバーの fqdn を入力して、[**追加**] をクリックします。 プールに追加するその他のすべての仲介サーバーに対してこの手順を繰り返します。 プール内のすべてのコンピューターを定義したら、[**次へ**] をクリックします。

7.  [**次ホップの選択**] ページで、[**次ホッププール**] をクリックし、この仲介サーバープールを使用するフロントエンドプールの FQDN をクリックして、[**次へ**] をクリックします。

8.  [**エッジ サーバーの選択**] ページで、次のどちらかの操作を行います。
    
      - エンタープライズ Voip が有効になっている外部ユーザーに PSTN 接続を提供する場合は、[**この仲介サーバーで使用されるエッジプールを選択して**ください] で、この仲介サーバープールを使用してこれらの外部ユーザーに pstn 接続を提供するエッジサーバープールの FQDN をクリックし、[**次へ**] をクリックします。
    
      - 外部ユーザーのエンタープライズ Voip を有効にする予定がない場合、または内部ネットワークの外部にいるときにユーザーに PSTN 接続を提供しない場合は、[**次へ**] をクリックします。

9.  次に、展開に関するドキュメントの「 [Lync server 2013 のトポロジを公開](lync-server-2013-publish-the-topology.md)する」の手順に従って、仲介サーバーをトポロジに追加します。 トポロジビルダーを使用してトポロジを構築または変更するたびに、トポロジを公開する必要があります。これにより、データを使用して、Lync Server を実行しているサーバーのファイルをインストールすることができます。 次のステップに進み、必要に応じて仲介サーバー上のリッスン ポートを変更します。

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>仲介サーバーのリッスンポートの定義

このトピックの手順に従って、トポロジビルダーを使用して、仲介サーバーまたはプールがゲートウェイピアからの着信接続を受け入れるリスニングポートを定義します。

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>仲介サーバーのリッスンポートを変更するには

1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

2.  トポロジビルダーのコンソールツリーで、[**仲介プール**] ノードを展開し、以前に作成した仲介サーバーを右クリックします。

3.  既定では、仲介サーバー上の SIP リスニングポートは、Lync Server からの tls トラフィック用の5070です。5067は、ピア (ゲートウェイ、PBXes、または sbc) からの TLS トラフィック用です。 TCP ポートは既定で無効になっています。 TLS をサポートしていないゲートウェイがある場合は、TCP ポートを有効にする必要があります。

4.  必要な TLS または TCP リッスンポートの範囲を指定します。仲介サーバーは、PSTN ゲートウェイからの着信接続を受け付けます。
    
    <div>
    

    > [!NOTE]  
    > [<STRONG>TCP ポートの有効化</STRONG>] がオフになっている場合は、TCP ポート範囲を入力する必要はありません。 この設定はオプションです。

    
    </div>

次に、「lync server [2013 の仲介サーバーのファイルをインストールする](lync-server-2013-install-the-files-for-mediation-server.md)」の手順に従って、 [lync server 2013 の [トポロジビルダー] でゲートウェイを定義](lync-server-2013-define-a-gateway-in-topology-builder.md)し、各仲介サーバーにファイルをインストールします。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

