---
title: 'Lync Server 2013: トポロジビルダーでゲートウェイを定義する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c9e57ad4e3d8c1692731bcfd4a56dc5c3d05bda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>Lync Server 2013 でのトポロジビルダーでのゲートウェイの定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-04_

次の手順に従って、トポロジビルダーを使用して、エンタープライズ Voip を有効にしているユーザー向けに、仲介サーバーを関連付け、PSTN (公衆交換電話網) への接続を提供できる*ピア*を定義します。 仲介サーバーへのピアは、SIP トランクを構成することによって、接続先のインターネットテレフォニーサービスプロバイダー (ITSP) の PSTN ゲートウェイ、IP PBX、またはセッション境界コントローラー (SBC) にすることができます。

<div>


> [!NOTE]  
> このトピックでは、次の説明に従って、少なくとも1つのセントラルサイトまたはスタンドアロンの仲介サーバーを持つ少なくとも1つのセントラルサイトに、少なくとも1つの内部のフロントエンドプールまたは Standard Edition サーバーを設定していることを前提としています。 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013</A>で、展開ドキュメントの<A href="lync-server-2013-publish-the-topology.md">lync server 2013 でトポロジを公開</A>します。 また、このトピックでは、組織が lync のエンタープライズ voip の<A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">ソフトウェア2013前提</A>条件を満たしていることを確認していることを前提としています。 lync<A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">でのエンタープライズ voip のセキュリティと構成の前提条件について説明します。サーバー 2013</A>。



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>仲介サーバーのピアを定義するには

1.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

2.  [Lync Server 2013、サイト名、共有コンポーネント] の順にクリックし、[ **Pstn ゲートウェイ**] ノードを右クリックして、[**新しい pstn ゲートウェイ**] をクリックします。
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  [**新規 IP/PSTN ゲートウェイの定義**] で、ピアの完全修飾ドメイン名 (FQDN) または IP アドレスを入力して、[**次へ**] をクリックします。
    
    ![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定した場合は、仲介サーバーのピアの IP アドレスではなく、FQDN を指定する必要があります。

    
    </div>

4.  新しい PSTN ゲートウェイの IP アドレスのリッスン モード (IPv4 または IPv6) を定義し、[**次へ**] をクリックします。
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  PSTN ゲートウェイのルート トランクを定義します。 トランクは、仲介サーバーと、組で一意に識別されたゲートウェイの間の論理的な接続です。
    
    {仲介サーバーの FQDN、仲介サーバーのリッスンポート (TLS または TCP): ゲートウェイ IP と FQDN、ゲートウェイリッスンポート}
    
      - トポロジビルダーで PSTN ゲートウェイを定義する場合は、トポロジに PSTN ゲートウェイを正常に追加するためにルートトランクを定義する必要があります。
    
      - ルート トランクは、関連する PSTN ゲートウェイが削除されるまで削除できません。
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  [ **IP/PSTN ゲートウェイのリスニングポート**] に、PSTN ゲートウェイのルートトランクと関連付けられる仲介サーバーからの SIP メッセージについて、ゲートウェイ、PBX、または SBC が使用するリスニングポートを入力します。 (既定では、ポートは、PSTN ゲートウェイ、PBX、または SBC 上のトランスポート層セキュリティ (TLS) 用の伝送制御プロトコル (TCP) および5067用の5066です。 ブランチサイトの Survivable Branch Appliance では、既定のポートは TCP 用の5081で、TLS の場合は5082です。)

7.  [**SIP 転送プロトコル**] でピアが使用する転送タイプをクリックし、[**OK**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強くお勧めします。

    
    </div>

8.  [**関連付けられた仲介サーバー**] で、この PSTN ゲートウェイのルートトランクに関連付ける仲介サーバープールを選択します。

9.  [**関連付けられた仲介サーバーポート**] に、仲介サーバーがゲートウェイからの SIP メッセージに使用するリスニングポートを入力します。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 で複数のトランクがサポートされている場合、複数の PSTN ゲートウェイとの通信に使用するために、複数の SIP シグナリングポートを仲介サーバーで定義できます。 トランクを定義する場合、<STRONG>関連する仲介サーバーポート</STRONG>は、仲介サーバーで許可されている各プロトコルのリスニングポートの範囲内にある必要があります。 このポート範囲は、「Lync Server 2013 および仲介プール」に定義されています。 対象の仲介サーバープールを右クリックし、[<STRONG>プロパティの編集</STRONG>] を選択します。 Specify the port range in the <STRONG>Listening ports</STRONG> field.

    
    </div>

10. [**完了**] をクリックします。

<div>


> [!IMPORTANT]  
> この手順を完了する前に、定義したピアが実行されていて、指定した FQDN または IP アドレスを使用していることを確認してください。



</div>

次に、トポロジにピアを追加するには、展開ドキュメントの「 [Lync Server 2013 でトポロジを公開](lync-server-2013-publish-the-topology.md)する」の手順に従います。 トポロジビルダーを使用してトポロジを作成または変更するたびにトポロジを公開する必要があります。そのため、Lync Server を実行しているサーバーのファイルをインストールするためにデータを使用することができます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのトポロジビルダーでのトランクの変更](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

