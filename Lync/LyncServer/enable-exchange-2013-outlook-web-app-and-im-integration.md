---
title: Exchange 2013 Outlook Web App と IM の統合を有効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69df3f33f0671d3014e90859fd39cc2b85f9558b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Exchange 2013 Outlook Web App と IM の統合を有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

Exchange 2013 Outlook Web Access (OWA) およびインスタントメッセージング (IM) と Lync Server 2013 との統合を有効にするには、信頼されたアプリケーションサーバーとして、Exchange 2013 クライアントアクセスサーバー (CAS) サーバーを Lync Server 2013 トポロジに追加する必要があります。

<div>

## <a name="to-create-a-trusted-application-pool"></a>信頼されたアプリケーションプールを作成するには

1.  Lync Server 2013 Management Shell を起動します。

2.  次のコマンドレットを実行します。
    
        Get-CsSite
    
    これにより、プールを作成している siteName の siteID が返されます。 詳細については、「Lync Server 2013 管理シェルのドキュメントの[入手-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) 」を参照してください。

3.  次のコマンドレットを実行します。
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    詳細については、「Lync Server 2013 管理シェルドキュメントの「[新規-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) 」を参照してください。
    
    Exchange Server の FQDN は、Exchange OWA 証明書のサブジェクト名 (SN)、またはサブジェクトの代替名 (SAN) として構成する必要があります。
    
    Exchange OWA で、プールの FQDN も信頼されていることを確認します。
    
    <div>
    

    > [!IMPORTANT]  
    > CAS サーバーが、Exchange 2013 ユニファイドメッセージング (UM) を実行している同じサーバー上に<EM>ない</EM>場合は、この手順の残りの手順をスキップして、後述する「EXCHANGE 2013 CAS サーバー用の信頼済みアプリケーションを作成する」の手順を実行します。トピック. 使用している CAS サーバーが、Exchange 2013 ユニファイドメッセージング (UM) を実行しているサーバー上にある場合は、この手順を実行して、このトピックで後述する「Exchange 2013 CAS サーバー用に信頼されたアプリケーションを作成する」の手順を実行しないでください。

    
    </div>

4.  **Enable-CsTopology を**実行します。

5.  トポロジビルダーを開き、既存のトポロジをダウンロードします。

6.  左側のウィンドウで、**信頼できるアプリケーションサーバー**に到達するまでツリーを展開します。

7.  [信頼されている**アプリケーションサーバー** ] ノードを展開します。

8.  これで、信頼できるアプリケーションサーバーとして表示された Exchange 2013 CAS サーバーが表示されます。

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>Exchange 2013 CAS サーバー用の信頼できるアプリケーションを作成するには

1.  Lync Server 2013 Management Shell を起動します。

2.  CAS サーバーが Exchange 2013 ユニファイドメッセージング (UM) を実行しているサーバー上に*ない*場合は、次のコマンドレットを実行します。
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    詳細については、「Lync Server 2013 管理シェルドキュメントの「 [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) 」を参照してください。

3.  **Enable-CsTopology を**実行します。

4.  [Topology Builder] の左側のウィンドウで、**信頼できるアプリケーションサーバー**に到達するまでツリーを展開します。

5.  [信頼されている**アプリケーションサーバー** ] ノードを展開します。

6.  これで、信頼できるアプリケーションサーバーとして表示された Exchange 2013 CAS サーバーが表示されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

