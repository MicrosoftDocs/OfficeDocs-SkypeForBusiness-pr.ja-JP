---
title: 'Lync Server 2013: トポロジビルダーでゲートウェイを定義する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40881b38c83ebf254a60773060b642d183b7dfaa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>Lync Server 2013 のトポロジビルダーでゲートウェイを定義する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-04_

次の手順に従って、トポロジビルダーを使用して、エンタープライズ Voip が有効なユーザーの公衆交換電話網 (PSTN) への接続を提供するための仲介サーバーを関連付けることができる*ピア*を定義します。 仲介サーバーへのピアとは、PSTN ゲートウェイ、ip-pbx、または SIP トランクを構成して接続するインターネットテレフォニーサービスプロバイダー (ITSP) のセッションボーダーコントローラー (SBC) のことです。

<div>


> [!NOTE]  
> このトピックでは、「展開」のドキュメントの「 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front end pool Or Standard edition 2013 2013 server</A> 」で説明されているように、少なくとも1つの中央サイトに、またはスタンドアロンの仲介サーバーを使用<A href="lync-server-2013-publish-the-topology.md"></A>して少なくとも1つの中央サイトに内部フロントエンドプールまたは standard edition サーバーをセットアップしていることを前提 また、このトピックでは、インフラストラクチャが lync server 2013 の「<A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">エンタープライズ voip の前提</A>条件」および「セキュリティと構成の前提条件」で説明されている前提条件を満たしていることを前提としています ( <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">lync Server 2013 のエンタープライズ voip の</A>場合)。



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>仲介サーバーのピアを定義するには

1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

2.  [Lync Server 2013] の下で、サイト名、[共有コンポーネント] の順にクリックし、[ **pstn**ゲートウェイ] ノードを右クリックして、[**新しい pstn ゲートウェイ**] をクリックします。
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  [**新規 IP/PSTN ゲートウェイの定義**] で、ピアの完全修飾ドメイン名 (FQDN) または IP アドレスを入力して、[**次へ**] をクリックします。
    
    ![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定する場合は、仲介サーバーのピアの IP アドレスの代わりに、FQDN を指定する必要があります。

    
    </div>

4.  新しい PSTN ゲートウェイの IP アドレスのリッスン モード (IPv4 または IPv6) を定義し、[**次へ**] をクリックします。
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  PSTN ゲートウェイのルート トランクを定義します。 トランクとは、仲介サーバーと、組で一意に識別されるゲートウェイとの間の論理接続のことです。
    
    {仲介サーバーの FQDN、仲介サーバーのリッスンポート (TLS または TCP): ゲートウェイ IP および FQDN、ゲートウェイリッスンポート}
    
      - トポロジビルダーで PSTN ゲートウェイを定義するときは、PSTN ゲートウェイをトポロジに正常に追加するために、ルートトランクを定義する必要があります。
    
      - ルート トランクは、関連する PSTN ゲートウェイが削除されるまで削除できません。
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  [ **IP/PSTN ゲートウェイのリッスンポート**] の下に、PSTN ゲートウェイのルートトランクに関連付けられる仲介サーバーからの SIP メッセージに対して、ゲートウェイ、PBX、または SBC が使用するリスニングポートを入力します。 既定では、PSTN ゲートウェイ、PBX、または SBC のトランスポート層セキュリティ (TLS) には、伝送制御プロトコル (TCP) および5067のポートが5066になっています。 ブランチサイトの存続可能ブランチアプライアンスでは、既定のポートは TCP の場合は5081、TLS の場合は5082です。

7.  [**SIP 転送プロトコル**] でピアが使用する転送タイプをクリックし、[**OK**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強くお勧めします。

    
    </div>

8.  [**関連付けられている仲介サーバー**] で、この PSTN ゲートウェイのルートトランクに関連付ける仲介サーバープールを選択します。

9.  [**関連付けられている仲介サーバーのポート**] で、仲介サーバーがゲートウェイからの SIP メッセージに使用するリスニングポートを入力します。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 で複数のトランクがサポートされている場合、複数の PSTN ゲートウェイとの通信に使用するために、複数の SIP シグナリングポートを仲介サーバーに対して定義できます。 トランクを定義する場合、<STRONG>関連する仲介サーバーのポート</STRONG>は、仲介サーバーによって許可されている各プロトコルのリッスンポートの範囲内にする必要があります。 このポート範囲は、「Lync Server 2013 および仲介プール」で定義されています。 目的の仲介サーバープールを右クリックし、[<STRONG>プロパティの編集</STRONG>] を選択します。 [<STRONG>リッスン ポート</STRONG>] フィールドでポート範囲を指定します。

    
    </div>

10. [**完了**] をクリックします。

<div>


> [!IMPORTANT]  
> このステップを終了する前に、定義されたピアが実行中で、指定した FQDN または IP アドレスを使用していることを確認してください。



</div>

次に、トポロジにピアを追加するには、「展開」のドキュメントの「 [Publish the topology In Lync Server 2013](lync-server-2013-publish-the-topology.md) 」の手順に従います。 トポロジビルダーを使用してトポロジを構築または変更するたびに、トポロジを公開する必要があります。これにより、データを使用して、Lync Server を実行しているサーバーのファイルをインストールすることができます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のトポロジビルダーでのトランクの変更](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

