---
title: 'Lync Server 2013: Lync Server フェデレーションに使用するエッジ プールのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68969c0e7be81eca835661e3fb6a19f1565e623f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>Lync Server 2013 での Lync Server フェデレーションに使用するエッジ プールのフェールオーバー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-17_

Lync Server フェデレーションが構成されている Edge プールが停止している場合は、フェデレーションが機能するために別のエッジプールを使用するようにフェデレーションを変更する必要があります。

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>Lync Server Federation に使用されるエッジプールのフェールオーバー

1.  フロントエンドサーバーで、[トポロジビルダー] を開きます。 [ **Edge プール**] を展開して、フェデレーション用に現在構成されているエッジサーバープールまたはエッジサーバープールを右クリックします。 [**プロパティの編集**] を選びます。

2.  [**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] をオフにします。 **[OK]** をクリックします。

3.  [ **Edge プール**] を展開して、フェデレーションに使用するエッジサーバーまたはエッジサーバープールを右クリックします。 [**プロパティの編集**] を選びます。

4.  [**プロパティの編集**] の [**全般**] で、[**このエッジプールに対してフェデレーションを有効にする (ポート 5061)**] を選択します。 **[OK]** をクリックします。

5.  [**アクション**] をクリックし、[**トポロジ**] を選択し、[**発行**] を選択します。 **トポロジの発行**を求められたら、[**次へ**] をクリックします。 発行が完了したら、[**完了**] をクリックします。

6.  エッジサーバーで、Lync Server 展開ウィザードを開きます。 [ **Lync Server System のインストールまたは更新**] をクリックし、[ **lync Server コンポーネントのセットアップまたは削除**] をクリックします。 [**実行] をもう一度**クリックします。

7.  Lync Server コンポーネントのセットアップで、[**次へ**] をクリックします。 概要画面には、実行中の操作が表示されます。 展開が完了したら、[**ログの表示**] をクリックして、利用可能なログファイルを表示します。 [**完了**] をクリックして展開を完了します。
    
    問題のあるエッジプールを含むサイトにまだ実行されているフロントエンドサーバーが含まれている場合は、これらのフロントエンドプールの Web 会議サービスと A/V 会議サービスを更新して、まだ実行中のリモートサイトでエッジプールを使用する必要があります。 詳細については、「 [Lync Server 2013 でフロントエンドプールに関連付けられているエッジプールを変更する](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での、XMPP フェデレーションに使用するエッジ プールのフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[Lync Server 2013 での Lync Server フェデレーションまたは XMPP フェデレーションに使用するエッジ プールのフェールバック](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Lync Server 2013 でのエッジ サーバーの障害復旧](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

