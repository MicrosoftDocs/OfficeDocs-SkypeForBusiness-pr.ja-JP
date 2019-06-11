---
title: 'Lync Server 2013: SEFAUtil ツールの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0783ab251359582d232d558da2161a149dea5117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>Deploy the SEFAUtil tool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-30_

グループ通話のピックアップを展開して管理するには、SEFAUtil リソースキットツールを使用する必要があります。 このツールは、Lync Server 2013 リソースキットツールに含まれています。 SEFAUtil をインストールする前に、信頼できるアプリケーションプールをトポロジに設定し、信頼できるアプリケーションとして SEFAUtil を指定して、トポロジを有効にする必要があります。

<div>


> [!IMPORTANT]  
> Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK を、SEFAUtil ツールを実行する予定のすべてのコンピューターにインストールする必要があります。



</div>

SEFAUtil は、展開の任意のフロントエンドプールで実行できます。

<div>


> [!NOTE]  
> SEFAUtil の実行の詳細については、Technet の記事「SEFAutil を実行する方法」を参照してください。 at <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>。



</div>

<div>

## <a name="to-deploy-sefautil"></a>SEFAUtil を展開するには

1.  Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  SEFAUtil ツールは、信頼済みアプリケーション プールに含まれるコンピューターでのみ実行できます。 必要に応じて、SEFAUtil を実行する予定のフロントエンドプールの信頼されたアプリケーションプールを定義します。 コマンド ラインで、次のコマンドを実行します。
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  SEFAUtil ツールを信頼済みアプリケーションとして定義します。コマンド ラインで、次のコマンドを実行します。
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > 必要に応じて、別のポートを使用できます。

    
    </div>

5.  変更を加えたトポロジを有効にします。コマンド ラインで、次のコマンドを実行します。
    
        Enable-CsTopology

6.  手順3で作成した信頼済みアプリケーションプール内のフロントエンドサーバーに Lync Server 2013 リソースキットツールをインストールします。

7.  次のように、SEFAUtil ツールが正常に実行していることを確認します。
    
    1.  管理者特権で Windows コマンド プロンプトからツールを実行し、展開内のユーザーの着信転送設定を表示します。
        
        <div>
        

        > [!NOTE]  
        > このツールは、Reskit の Lync Server 2013 \ にあります。

        
        </div>
    
    2.  ユーザーの着信転送設定を表示します。コマンド ラインで、次のコマンドを実行します。
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        ユーザーの着信転送設定が表示されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

