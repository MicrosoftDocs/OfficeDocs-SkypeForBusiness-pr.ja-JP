---
title: 'Lync Server 2013: トポロジビルダーで追加の trunks を定義する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b18d12762566258051d5fe0e7c71921b9fff160c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>Lync Server 2013 のトポロジビルダーで追加の trunks を定義する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-04_

次の手順に従って、トポロジビルダーを使用して、*ピア*を仲介サーバーに関連付けることができる追加のトランクを定義します。 Peer は、公衆交換電話網 (PSTN) に接続して、エンタープライズ Voip を有効にします。 ピアとなるのは、PSTN ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダー (ITSP) のセッション ボーダー コントローラー (SBC) などです。 トランクは、仲介サーバーとピア間の接続を定義します。 複数の trunks は、仲介サーバーごとに定義できます。 仲介サーバーは、複数のピアに関連付けることができます。

トランクは、仲介サーバーと、組によって一意に識別されたゲートウェイの間の論理的な接続です。

{仲介サーバーの FQDN、仲介サーバーのリッスンポート (TLS または TCP): ゲートウェイ IP と FQDN、ゲートウェイリッスンポート}

<div>


> [!NOTE]  
> このトピックでは、展開ドキュメントの<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync server 2013 の [トポロジビルダーでのゲートウェイの定義</A>] の説明に従って、少なくとも1つの併置またはスタンドアロンの仲介サーバーまたはプールで PSTN ゲートウェイとルートトランクをセットアップしていることを前提としています。



</div>

<div>


> [!NOTE]  
> このトピックでは、「 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 でのフロントエンドプールまたは Standard edition サーバーの定義と構成</A>」で説明したように、少なくとも1つのセントラルサイトで少なくとも1つのフロントエンドプールまたは standard edition サーバーを設定していることを前提としています。 <A href="lync-server-2013-publish-the-topology.md"></A>展開ドキュメントのサーバー2013。



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>仲介サーバーとゲートウェイピアの間に追加のトランクを定義するには

1.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

2.  [Lync Server 2013、サイト名、**共有コンポーネント**] で、[ **Trunks** ] ノードを右クリックし、[**新しいトランク**] をクリックします。
    
    ![Lync Server トポロジビルダーのファイル構造画面](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server トポロジビルダーのファイル構造画面")

3.  [**新しいトランクの定義**] で、トランクを一意に識別するためのフレンドリ名を指定します。 2 つのトランクに同じ名前を付けることはできません。
    
    <div>
    

    > [!NOTE]  
    > トランスポートの種類としてトランスポート層セキュリティ (TLS) を指定した場合は、仲介サーバーのピアの IP アドレスではなく、FQDN を指定する必要があります。

    
    </div>

4.  [**PSTN ゲートウェイの関連付け**] で、PSTN ゲートウェイ ピアを選択してこのトランクと関連付けます。
    
    ![トランク用 PSTN ゲートウェイピアのプロパティ設定](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "トランク用 PSTN ゲートウェイピアのプロパティ設定")

5.  [ **Pstn ゲートウェイのリスニングポート**] で、ピア (pstn ゲートウェイ、IP PBX、または SBC) がこのトランクに関連付けられている仲介サーバーから SIP メッセージを受信するリッスンポートを入力します。 既定のピア ポートは、伝送制御プロトコル (TCP) 用が 5066 で、トランスポート層セキュリティ (TLS) 用が 5067 です。 既定の Survivable Branch Appliance ポートは、TCP と5082の TLS 用の5081です。

6.  [**SIP トランスポート プロトコル**] で、ピアが使用するトランスポートの種類をクリックします。
    
    <div>
    

    > [!NOTE]  
    > セキュリティ上の理由から、TLS を使用できる仲介サーバーにピアを展開することを強くお勧めします。

    
    </div>

7.  [**関連付けられた仲介サーバー**] で、このピアのルートトランクに関連付ける仲介サーバープールを選択します。

8.  [**関連付けられた仲介サーバーのポート**] で、仲介サーバーがピアから SIP メッセージを受信するリスニングポートを入力します。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 で複数のトランクがサポートされている場合、同じ<STRONG>関連の仲介サーバーポート</STRONG>と<STRONG>IP/PSTN ゲートウェイ用のリスニングポート</STRONG>を使用して、異なるトランク名を持つ2つの trunks を構成することはできません。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 で複数のトランクがサポートされているため、複数のピアと通信するために、複数の SIP シグナリングポートを仲介サーバーで定義することができます。 トランクを定義する場合、<STRONG>関連する仲介サーバーのポート</STRONG>番号は、仲介サーバーで許可されている各プロトコルのリッスンポートの範囲内である必要があります。 このポート範囲は、「Lync Server 2013 および仲介サーバープール」に定義されています。 関連する仲介サーバープールを右クリックし、[<STRONG>プロパティの編集</STRONG>] を選択します。 Specify the port range in the <STRONG>Listening ports</STRONG> field.

    
    </div>

9.  [**OK**] をクリックします。

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

