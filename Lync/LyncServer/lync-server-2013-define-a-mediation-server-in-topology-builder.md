---
title: 'Lync Server 2013: トポロジビルダーで仲介サーバーを定義する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f1356217b9effe3f2282f6931b601e84aa46770
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>Lync Server 2013 でのトポロジビルダーでの仲介サーバーの定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-25_

このトピックの手順に従って、トポロジビルダーを使用して、まだエンタープライズ Voip を展開していないサイトで、フロントエンドプールと共に管理されているスタンドアロンの仲介サーバーまたはプールを定義します。

[管理者] グループのメンバーであるアカウントを使用してトポロジを定義できます。

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>フロントエンドプールに併置した仲介サーバーの定義

このトピックの手順に従って、トポロジビルダーを使用して、エンタープライズ Voip を展開していないサイトのフロントエンドプールに併置されている仲介サーバーを定義します。

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>フロントエンドプールに仲介サーバーを追加するには

1.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

2.  [トポロジビルダー] のコンソールツリーで、フロントエンドプールを定義するサイト名を展開します。

3.  コンソールツリーで、使用するフロントエンドプールの種類を右クリックし、[**新しいフロントエンドプール**] をクリックします。

4.  [**併置されたサーバーの役割の選択**] ページが表示されるまで、**新しいフロントエンド プールの定義**ウィザードを進めます。

5.  [併置された**サーバーの役割を選択**してください] で、オプションの [**仲介サーバーの検索**] をオンにします。
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>選択したフロントエンドプールの種類が Enterprise Edition の場合、仲介サーバーコンポーネントは、そのフロントエンドプールのすべてのフロントエンドサーバーにインストールされます。</P>
    > <LI>
    > <P>仲介サーバーによって使用される next-hop<STRONG>プール</STRONG>は、仲介サーバーが併置されているフロントエンドプールになります。</P>
    > <LI>
    > <P>仲介サーバーで使用される<STRONG>エッジプール</STRONG>は、仲介サーバーが併置されているフロントエンドプールと同じエッジプールになります。</P></LI></UL>

    
    </div>

6.  [**既定**にする] をクリックして、Microsoft Office Communications Server 2007 R2 から PSTN に通話をルーティングするために、このフロントエンドプールを使用するように設定します。

7.  1つまたは複数のピアのフロントエンドプールへの関連付けが終了したら、[**完了**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > エンタープライズ Voip 展開プロセスの次の手順に進む前に、指定した Fqdn を使用して、仲介サーバープール (たとえば、仲介サーバーコンポーネントが含まれているフロントエンドプール) であることを確認してください。

    
    </div>

8.  次に、展開ガイドドキュメントの「 [Lync server 2013 のトポロジを公開](lync-server-2013-publish-the-topology.md)する」の手順に従って、必要に応じて、仲介サーバーのリッスンポートを変更する次の手順に進みます。 トポロジを定義または変更するには、トポロジビルダーを使用するたびにトポロジを公開する必要があります。

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>スタンドアロンの仲介サーバーを定義する

このトピックの手順に従って、トポロジビルダーを使用して、エンタープライズボイスが以前に展開されていないサイトで、スタンドアロンの仲介サーバーまたはプールを定義します。

このサイトでフロントエンドプールに併置されている仲介サーバーを既に展開している場合は、 [lync server 2013 で trunks を構成](lync-server-2013-configuring-trunks.md)する前に、このセクションをスキップし、[仲介サーバー用のファイルを lync Server 2013 にインストール](lync-server-2013-install-the-files-for-mediation-server.md)することができます。

<div>


> [!NOTE]  
> このセクションでは、既に少なくとも1つのフロントエンドプールをセットアップしていることを前提としています。詳細については、「 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 でフロントエンドプールまたは Standard Edition server を定義して構成</A>する」および「展開ガイドの<A href="lync-server-2013-publish-the-topology.md">lync server 2013 でトポロジを公開</A>する」を参照してください。documentation.



</div>

<div>

## <a name="to-add-a-mediation-server"></a>仲介サーバーを追加するには

1.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

2.  [トポロジビルダー] のコンソールツリーで、仲介サーバーを定義するサイトの名前を展開します。

3.  コンソールツリーで、[**仲介プール**] ノードを右クリックし、[**仲介サーバープール**] をクリックします。

4.  [**新しい仲介プールの定義**] で、仲介サーバープールの完全修飾ドメイン名 (FQDN) を入力します。

5.  次に、以下のいずれかの操作を行います。
    
      - プールに複数の仲介サーバーを展開して高可用性を提供する場合は、[**複数のコンピュータープール**] を選びます。
        
        <div>
        

        > [!NOTE]  
        > 複数の仲介サーバーがある仲介サーバープールをサポートするには、DNS の負荷分散を展開する必要があります。 詳細については、計画ドキュメントの「 <A href="lync-server-2013-dns-load-balancing.md">Lync server 2013 の dns の負荷</A>分散での Dns 負荷分散の使用」セクションを参照してください。

        
        </div>
    
      - 高可用性を必要としないため、プールに1つの仲介サーバーのみを展開する場合は、[**単一コンピュータープール**] を選びます。 以下のステップは省略してください。

6.  前の手順**で複数のコンピュータープール**を選択した場合は、[**このプールのコンピューターを定義**する] 項目で [コンピューターの**fqdn**] をクリックし、プール内の各サーバーの fqdn を入力して、[**追加**] をクリックします。 プールに追加するその他のすべての仲介サーバーについて、この手順を繰り返します。 プール内のすべてのコンピューターを定義したら、[**次へ**] をクリックします。

7.  [**次ホップの選択**] ページで、[**次ホッププール**] をクリックし、この仲介サーバープールを使用するフロントエンドプールの FQDN をクリックして、[**次へ**] をクリックします。

8.  [**エッジ サーバーの選択**] ページで、次のどちらかの操作を行います。
    
      - エンタープライズ Voip が有効になっている外部ユーザーに PSTN 接続を提供する場合は、[**この仲介サーバーで使用されるエッジプールを選択して**ください] で、この仲介サーバープールを使用して、pstn 接続を提供するエッジサーバープールの FQDN をクリックします。それらの外部ユーザーを選び、[**次へ**] をクリックします。
    
      - 外部ユーザーをエンタープライズボイスとして有効にする予定がない場合、または内部ネットワークの外部にいるユーザーに PSTN 接続を提供しない場合は、[**次へ**] をクリックします。

9.  次に、展開ドキュメントの「 [Lync server 2013 でトポロジを公開](lync-server-2013-publish-the-topology.md)する」の手順に従って、仲介サーバーをトポロジに追加します。 トポロジビルダーを使用してトポロジを作成または変更するたびにトポロジを公開する必要があります。これにより、Lync Server を実行しているサーバーのファイルをインストールするためにデータを使用できるようになります。 次の手順に進んで、必要に応じて、仲介サーバーのリッスンポートを変更します。

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>仲介サーバーのリッスンポートを定義する

このトピックの手順に従って、トポロジビルダーを使用してリッスンポートを定義します。仲介サーバーまたはプールは、ゲートウェイピアからの着信接続を受け入れます。

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>仲介サーバーのリッスンポートを変更するには

1.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

2.  [トポロジビルダー] のコンソールツリーで、[**仲介プール**] ノードを展開し、前に作成した仲介サーバーを右クリックします。

3.  既定では、仲介サーバー上の SIP リスニングポートは、Lync Server からの TLS トラフィック用の5070であり5067、ピアからの TLS トラフィック (ゲートウェイ、PBXes、または SBCs) を対象としています。 TCP ポートは既定で無効になっています。 TLS をサポートしていないゲートウェイがある場合は、TCP ポートを有効にする必要があります。

4.  目的の TLS または TCP リッスンポートの範囲を指定する仲介サーバーは、PSTN ゲートウェイからの着信接続を受け入れます。
    
    <div>
    

    > [!NOTE]  
    > [<STRONG>TCP ポートの有効化</STRONG>] がオフになっている場合は、TCP ポート範囲を入力する必要はありません。 この設定はオプションです。

    
    </div>

次に、lync server [2013 のトポロジビルダーでゲートウェイを定義](lync-server-2013-define-a-gateway-in-topology-builder.md)し、「 [lync Server 2013 の仲介サーバー用のファイルをインストール](lync-server-2013-install-the-files-for-mediation-server.md)する」の手順に従って、プール内の各仲介サーバーにファイルをインストールします。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

