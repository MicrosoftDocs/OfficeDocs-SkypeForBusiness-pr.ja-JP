---
title: 'Lync Server 2013: SEFAUtil ツールの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ff23a228710ecc934e2984f27c63351ccf6d32
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>SEFAUtil ツールを Lync Server 2013 に展開する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-30_

グループ通話ピックアップを展開および管理するには、SEFAUtil リソースキットツールを使用する必要があります。 このツールは、Lync Server 2013 リソースキットツールに含まれています。 SEFAUtil をインストールする前に、信頼されたアプリケーションプールをトポロジに含める必要があり、信頼済みアプリケーションとして SEFAUtil を指定し、トポロジを有効にする必要があります。

<div>


> [!IMPORTANT]  
> Microsoft 統合コミュニケーション管理 API (UCMA) 3.0 コア SDK は、SEFAUtil ツールの実行を計画している任意のコンピューターにインストールする必要があります。



</div>

SEFAUtil は、展開内の任意のフロントエンドプールで実行できます。

<div>


> [!NOTE]  
> SEFAUtil の実行の詳細については、Technet の記事「How to get SEFAutil running?」を参照してください。 at <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>



</div>

<div>

## <a name="to-deploy-sefautil"></a>SEFAUtil を展開するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  SEFAUtil ツールは、信頼されたアプリケーションプールの一部であるコンピューターでのみ実行できます。 必要に応じて、SEFAUtil の実行を計画しているフロントエンドプールの信頼されたアプリケーションプールを定義します。 コマンド ラインで、次のコマンドを実行します。
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  SEFAUtil ツールを信頼済みアプリケーションとして定義します。 コマンド ラインで、次のコマンドを実行します。
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > 必要に応じて、別のポートを使用することができます。

    
    </div>

5.  変更したトポロジを有効にします。 コマンド ラインで、次のコマンドを実行します。
    
        Enable-CsTopology

6.  手順3で作成した信頼されたアプリケーションプールにあるフロントエンドサーバーに、Lync Server 2013 リソースキットツールをインストールします。

7.  SEFAUtil ツールが正常に実行されていることを、次のように確認します。
    
    1.  管理者特権を使用して Windows コマンドプロンプトからツールを実行し、展開内のユーザーの着信転送設定を表示します。
        
        <div>
        

        > [!NOTE]  
        > このツールは、うえの「Lync Server 2013」にあります。

        
        </div>
    
    2.  ユーザーの着信転送設定を表示します。 コマンド ラインで、次のコマンドを実行します。
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        ユーザーの着信転送設定が表示されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

