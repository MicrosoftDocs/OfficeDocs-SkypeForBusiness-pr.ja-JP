---
title: 'Lync Server 2013: XMPP フェデレーションに使用するエッジ プールのフェールオーバー'
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
ms.openlocfilehash: 9d1c76dc37ce1abb2d34c474d4144b0894d93a0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013 での、XMPP フェデレーションに使用するエッジ プールのフェールオーバー

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

組織では、1つのエッジプールがプールとして指定されています。 このプールがダウンした場合は、xmpp フェデレーションを再度使用する前に、別のエッジプールを使用するために XMPP フェデレーションをフェイルオーバーする必要があります。

最初に Edge プールをインストールして XMPP フェデレーションを有効にすると、1つの代わりに XMPP のすべてのエッジプールの外部 DNS SRV レコードを設定することで、障害回復プロセスを簡略化できます。 各 SRV レコードには、異なる優先順位を設定する必要があります。 すべての XMPP フェデレーショントラフィックは、最も優先度の高い SRV レコードを持つプールを通過します。 XMPP フェデレーションを有効にしてセットアップする方法について詳しくは、「 [Lync Server 2013 での XMPP フェデレーションの](lync-server-2013-setting-up-xmpp-federation.md)セットアップ」をご覧ください。

次の手順では、EdgePool1 は最初に XMPP フェデレーションをホストしたプールであり、EdgePool2 は XMPP フェデレーションをホストするプールです。

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>XMPP フェデレーションに使用されるエッジプールのフェイルオーバー

1.  (現在ダウンしている) 別の Edge プールをまだ展開していない場合は、そのプールを展開します。 詳細については、「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。

2.  新しいエッジプールの各エッジサーバーで XMPP federation (EdgePool2) をホストするために、次のコマンドレットを実行します。
    
        Stop-CsWindowsService

3.  XMPP フェデレーションルートを EdgePool2 に再ポイントするには、次のコマンドレットを実行します。
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    この例では、Site2 は、XMPP フェデレーションルートをホストするエッジプールが含まれているサイトで、EdgeServer2.contoso.com はそのプールのエッジサーバーの FQDN です。

4.  外部 DNS サーバーで、XMPP フェデレーション用の DNS A レコードを EdgeServer2.contoso.com に変更します。

5.  Xmpp フェデレーション用の DNS SRV レコードをまだ持っていない場合は、次の例のように、それを追加する必要があります。これは、現在 XMPP フェデレーションをホストしています。 この SRV レコードには、5269のポート値を指定する必要があります。
    
        _xmpp-server._tcp.contoso.com

6.  XMPP フェデレーションをホストしている Edge プールのポート5269が外部で開かれていることを確認します。

7.  Edge プール内のすべてのエッジサーバーでサービスを開始します。これで、XMPP フェデレーションがホストされます。
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

