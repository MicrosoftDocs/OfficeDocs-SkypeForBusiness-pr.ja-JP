---
title: 'Lync Server 2013: XMPP フェデレーションに使用するエッジプールのフェールオーバー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 182bc427c7b4faf3bd937bd58af8ca1d4d9c7d77
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013 での XMPP フェデレーションに使用するエッジプールのフェールオーバー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

組織内に XMPP フェデレーションに使用するプールとして指定されたエッジ プールが 1 つあるとします。このプールがダウンした場合、XMPP フェデレーションを再び機能させるには、XMPP フェデレーションをフェールオーバーして別のエッジ プールを使用する必要があります。

エッジ プールを初めてインストールし、XMPP フェデレーションを有効にするときに、1 つのエッジ プールではなく、すべてのエッジ プールで XMPP フェデレーションの外部 DNS SRV レコードを設定することで障害復旧プロセスを簡素化できます。 これらの SRV レコードには、それぞれ異なる優先順位が設定されている必要があります。 すべての XMPP フェデレーション トラフィックは、優先順位が最も高い SRV レコードを使用してプールを通過します。 XMPP フェデレーションの有効化およびセットアップの詳細については、「 [Lync Server 2013 での xmpp フェデレーションの設定](lync-server-2013-setting-up-xmpp-federation.md)」を参照してください。

次の手順では、EdgePool1 は XMPP フェデレーションをホストしていた元のプールを表し、EdgePool2 は XMPP フェデレーションをこれからホストするプールを表します。

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>XMPP フェデレーションに使用するエッジ プールのフェールオーバー

1.  (現在ダウンしているエッジ プール以外の) 別のエッジ プールをまだ展開していない場合は、そのプールを展開します。 詳細については、「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。

2.  XMPP フェデレーションをホストする新しいエッジ プール (EdgePool2) の各エッジ サーバーで、次のコマンドレットを実行します。
    
        Stop-CsWindowsService

3.  XMPP フェデレーション ルートを変更して EdgePool2 を指すようにするには、次のコマンドレットを実行します。
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    この例で、Site2 は XMPP フェデレーション ルートをこれからホストするエッジ プールを含むサイトを表します。また、EdgeServer2.contoso.com はそのプール内のエッジ サーバーの FQDN です。

4.  外部 DNS サーバーで、XMPP フェデレーションの DNS A レコードを変更して、EdgeServer2.contoso.com を指すようにします。

5.  XMPP フェデレーションをホストする新しいエッジ プールに解決される、XMPP フェデレーションの DNS SRV レコードがまだない場合は、次の例に示すように、このレコードを追加する必要があります。この SRV レコードには、ポート値 5269 が含まれている必要があります。
    
        _xmpp-server._tcp.contoso.com

6.  XMPP フェデレーションをホストする新しいエッジ プールで、ポート 5269 が外部に開いていることを確認します。

7.  XMPP フェデレーションをホストする新しいエッジ プール内のすべてのエッジ サーバーでサービスを開始します。
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

