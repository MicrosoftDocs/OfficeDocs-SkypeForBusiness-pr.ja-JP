---
title: 'Lync Server 2013: パブリック インスタント メッセージング接続の設定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871f513170fcb0491f6732751cfc1b23877526b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>Lync Server 2013 でのパブリック インスタント メッセージング接続の設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-08_

組織で AOL とのパブリックインスタントメッセージング (IM) 接続をサポートしたい場合は、Lync Server Deployment ウィザードを使って証明書を要求することはできません。 代わりに、次の手順を実行します。

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>パブリックインスタントメッセージング接続の設定

1.  フロントエンドサーバーで、[トポロジビルダー] を開きます。 [Edge プール] を展開し、エッジサーバーまたはエッジサーバープールを右クリックします。 [プロパティの編集] を選びます。

2.  [プロパティの編集] の [全般] で、[このエッジプールに対してフェデレーションを有効にする (ポート 5061)] を選択します。 [OK] をクリックします。

3.  [アクション] をクリックし、[トポロジ] を選択し、[発行] を選択します。 トポロジの発行を求められたら、[次へ] をクリックします。 発行が完了したら、[完了] をクリックします。

4.  エッジサーバーで、Lync Server 展開ウィザードを開きます。 [Lync Server System のインストールまたは更新] をクリックし、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。 [実行] をもう一度クリックします。

5.  Lync Server コンポーネントのセットアップで、[次へ] をクリックします。 概要画面には、実行中の操作が表示されます。 展開が完了したら、[ログの表示] をクリックして、利用可能なログファイルを表示します。 [完了] をクリックして展開を完了します。

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>AOL とのパブリック IM 接続をサポートするために、エッジサーバーの外部インターフェイスの証明書要求を作成するには

1.  必要なテンプレートが CA で利用できるようになったら、エッジサーバーから次の Windows PowerShell コマンドレットを使用して証明書を要求します。
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Lync Server で使用されるテンプレートの既定の証明書名は、Web サーバーです。 既定のテンプレート\<とは\>異なるテンプレートを使用する必要がある場合は、テンプレート名のみを指定します。
    
    <div>
    

    > [!IMPORTANT]  
    > 組織で AOL とのパブリック IM 接続をサポートしたい場合は、証明書ウィザードの代わりに Windows PowerShell を使用して、アクセスエッジサービスの外部境界に証明書を割り当てるように要求する必要があります。 これは、証明書ウィザードで証明書を要求するために使用される証明機関 (CA) Web サーバーテンプレートがクライアント EKU 構成をサポートしていないためです。 Windows PowerShell を使用して証明書を作成する前に、CA 管理者がクライアント EKU をサポートする新しいテンプレートを作成して展開する必要があります。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

