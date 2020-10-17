---
title: 'Lync Server 2013: トポロジビルダーでの追加トランクの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e8e5650492cc51b024b03cc0c92f64ff46d818b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504644"
---
# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>Lync Server 2013 のトポロジビルダーでの追加トランクの定義

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-04_

次の手順に従って、トポロジビルダーを使用して、 *ピア* を仲介サーバーに関連付けることができる追加のトランクを定義します。 ピアは、公衆交換電話網 (PSTN) への接続を備えたエンタープライズ Voip が有効なユーザーを提供します。 ピアとなるのは、PSTN ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC) などです。 トランクは、仲介サーバーとピア間のこの接続を定義します。 仲介サーバーごとに複数のトランクを定義できます。 仲介サーバーは、複数のピアと関連付けることができます。

トランクとは、仲介サーバーと、組で一意に識別されるゲートウェイとの間の論理接続のことです。

{仲介サーバーの FQDN、仲介サーバーのリッスンポート (TLS または TCP): ゲートウェイ IP および FQDN、ゲートウェイリッスンポート}

<div>


> [!NOTE]  
> このトピックでは、展開に関するドキュメントの「 <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013 のトポロジを定義</A> する」の説明に従って、少なくとも1つの併置またはスタンドアロンの仲介サーバーまたはスタンドアロンの仲介サーバーまたはプールを持つ、PSTN ゲートウェイとルートトランクをセットアップしていることを前提としています。



</div>

<div>


> [!NOTE]  
> このトピックでは、「展開」のドキュメントの「 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front end pool Or Standard edition 2013 server</A> 」の説明に従って、少なくとも1つの中央サイトに少なくとも1つのフロントエンドプールまたは standard edition サーバーを設定していることを前提 <A href="lync-server-2013-publish-the-topology.md">2013</A> としています。



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>仲介サーバーとゲートウェイピアの間に追加のトランクを定義するには

1.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

2.  [Lync Server 2013] の下にあるサイト名、[ **共有コンポーネント**] で、 **トランク** ノードを右クリックし、[ **新しいトランク**] をクリックします。
    
    ![Lync Server トポロジビルダーのファイル構造画面](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server トポロジビルダーのファイル構造画面")

3.  [**新しいトランクの定義**] で、トランクを一意に識別するためのフレンドリ名を指定します。 2 つのトランクに同じ名前を付けることはできません。
    
    <div>
    

    > [!NOTE]  
    > トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定する場合は、仲介サーバーのピアの IP アドレスの代わりに、FQDN を指定する必要があります。

    
    </div>

4.  [**PSTN ゲートウェイの関連付け**] で、PSTN ゲートウェイ ピアを選択してこのトランクと関連付けます。
    
    ![トランクの PSTN ゲートウェイピアのプロパティ設定](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "トランクの PSTN ゲートウェイピアのプロパティ設定")

5.  [ **Pstn ゲートウェイのリスニングポート**] で、このトランクに関連付けられる仲介サーバーからのピア (pstn ゲートウェイ、ip-pbx、または SBC) が SIP メッセージを受信するリスニングポートを入力します。 既定のピア ポートは、伝送制御プロトコル (TCP) 用が 5066 で、トランスポート層セキュリティ (TLS) 用が 5067 です。 既定の存続可能 Branch Appliance ポートは、TCP の場合は5081、TLS の場合は5082です。

6.  [**SIP トランスポート プロトコル**] で、ピアが使用するトランスポートの種類をクリックします。
    
    <div>
    

    > [!NOTE]  
    > セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強くお勧めします。

    
    </div>

7.  [ **関連付けられている仲介サーバー**] で、仲介サーバープールを選択して、このピアのルートトランクに関連付けます。

8.  [ **関連付けられている仲介サーバーのポート**] で、仲介サーバーがピアから SIP メッセージを受信するリスニングポートを入力します。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 で複数のトランクがサポートされている場合、2つのトランクが同じ<STRONG>関連付けられた仲介サーバーのポート</STRONG>と、 <STRONG>IP/PSTN ゲートウェイのリスニングポート</STRONG>で構成できません。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 で複数のトランクがサポートされている場合、複数のピアと通信するために、複数の SIP 信号ポートを仲介サーバーに対して定義できます。 トランクを定義する場合、 <STRONG>関連する仲介サーバーのポート</STRONG> 番号は、仲介サーバーによって許可されている各プロトコルのリスニングポートの範囲内にある必要があります。 このポート範囲は、「Lync Server 2013 および仲介サーバープール」で定義されています。 関連する仲介サーバープールを右クリックし、[ <STRONG>プロパティの編集</STRONG>] を選択します。 [<STRONG>リッスン ポート</STRONG>] フィールドでポート範囲を指定します。

    
    </div>

9.  [ **OK **] をクリックします。

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

