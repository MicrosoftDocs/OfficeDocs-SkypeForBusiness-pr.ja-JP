---
title: 'Lync Server 2013: パブリックインスタントメッセージング接続の設定'
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
ms.openlocfilehash: e4b3efe4e5d8e5cb84631969205842e56024394c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>Lync Server 2013 でのパブリックインスタントメッセージング接続の設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-08_

組織で AOL とのパブリック インスタント メッセージング (IM) 接続をサポートする必要がある場合は、Lync Server 展開ウィザードを使用して証明書を要求することはできません。代わりに、以下の手順を実行します。

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>パブリック インスタント メッセージング接続の設定

1.  フロントエンド サーバーで、トポロジ ビルダーを開きます。エッジ プールを展開し、エッジ サーバーまたはエッジ サーバー プールを右クリックして、[プロパティの編集] を選択します。

2.  [全般] の下の [プロパティの編集] で、[このエッジ プールのフェデレーションの有効化 (ポート 5061)] を選択します。[OK] をクリックします。

3.  [アクション] をクリックし、[トポロジ]、[公開] の順にクリックします。トポロジの公開を確認するプロンプトが表示されたら、[次へ] をクリックします。公開が完了したら、[完了] をクリックします。

4.  エッジ サーバーで、Lync Server 展開ウィザードを開きます。[Lync Server システムのインストールまたは更新] をクリックして、[Lync Server コンポーネントのセットアップまたは削除] をクリックします。[再実行] をクリックします。

5.  [Lync Server コンポーネントのセットアップ] で、[次へ] をクリックします。概要画面に、実行されたアクションが表示されます。展開が完了したら、[ログの表示] をクリックして、参照できるログ ファイルを表示します。 [完了] をクリックして、展開を完了します。

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>AOL とのパブリック IM 接続をサポートするために、エッジ サーバーの外部インターフェイス用に証明書要求を作成するには

1.  必要なテンプレートが CA で利用できる場合、エッジ サーバーで次の Windows PowerShell コマンドレットを使用して証明書を要求します。
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Lync Server で使用されるテンプレートの既定の証明書名は Web サーバーです。 既定のテンプレート\<とは\>異なるテンプレートを使用する必要がある場合にのみ、テンプレート名を指定します。
    
    <div>
    

    > [!IMPORTANT]  
    > 組織で AOL とのパブリック IM 接続をサポートする必要がある場合は、証明書ウィザードではなく Windows PowerShell を使用して、アクセスエッジサービスの外部エッジに証明書を割り当てるよう要求する必要があります。 これは、証明書を要求するために証明書ウィザードが使用する証明機関 (CA) Web サーバー テンプレートが、クライアント EKU 構成をサポートしていないためです。 Windows PowerShell を使用して証明書を作成する前に、CA 管理者はクライアント EKU をサポートする新しいテンプレートを作成して展開する必要があります。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

