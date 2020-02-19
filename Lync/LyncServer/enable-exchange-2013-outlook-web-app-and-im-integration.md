---
title: Exchange 2013 の Outlook Web App および IM 統合を有効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da4289f663d62d1638c0f669e17a5e318e0788d3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Exchange 2013 の Outlook Web App および IM 統合を有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-19_

Exchange 2013 Outlook Web Access (OWA) および Lync Server 2013 とのインスタントメッセージング (IM) の統合を有効にするには、Exchange 2013 クライアントアクセスサーバー (CAS) サーバーを、信頼されたアプリケーションサーバーとして Lync Server 2013 トポロジに追加する必要があります。

<div>

## <a name="to-create-a-trusted-application-pool"></a>信頼済みアプリケーション プールを作成するには

1.  Lync Server 2013 管理シェルを起動します。

2.  次のコマンドレットを実行します。
    
        Get-CsSite
    
    これで、プールを作成する siteName に対応する siteID が取得されます。 詳細については、「Lync Server 2013 Management Shell」のドキュメントの「[取得-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) 」を参照してください。

3.  次のコマンドレットを実行します。
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    詳細については、「Lync Server 2013 Management Shell」のドキュメントの「 [「new-cstrustedapplicationpool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) 」を参照してください。
    
    Exchange Server の FQDN を Exchange OWA 証明書のサブジェクト名 (SN) またはサブジェクトの別名 (SAN) として構成する必要があります。
    
    Exchange OWA で、プールの FQDN も信頼されていることを確認します。
    
    <div>
    

    > [!IMPORTANT]  
    > CAS サーバーが、Exchange 2013 ユニファイドメッセージング (UM) を実行しているのと同じサーバー上に併置されて<EM>いない</EM>場合は、この手順の残りの手順をスキップして、このトピックで後述する「EXCHANGE 2013 CAS サーバーの信頼されたアプリケーションを作成する」の手順を実行します。 CAS サーバーが、Exchange 2013 ユニファイドメッセージング (UM) を実行しているのと同じサーバー上に併置されている場合は、この手順の手順を実行します。このトピックで後述する「Exchange 2013 CAS サーバーの信頼されたアプリケーションを作成する」の手順を実行しないでください。

    
    </div>

4.  **Enable-CsTopology** を実行します。

5.  トポロジ ビルダーを開き、既存のトポロジをダウンロードします。

6.  左側のウィンドウで、[**信頼済みアプリケーション サーバー**] が表示されるまでツリーを展開します。

7.  [**信頼されたアプリケーション サーバー**] ノードを展開します。

8.  これで、Exchange 2013 CAS サーバーが信頼済みアプリケーションサーバーとして表示されるようになります。

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>Exchange 2013 CAS サーバーの信頼されたアプリケーションを作成するには

1.  Lync Server 2013 管理シェルを起動します。

2.  CAS サーバーが、Exchange 2013 ユニファイドメッセージング (UM) を実行しているのと同じサーバーに併置されて*いない*場合は、次のコマンドレットを実行します。
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    詳細については、「Lync Server 2013 Management Shell」のドキュメントの「 [「new-cstrustedapplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) 」を参照してください。

3.  **Enable-CsTopology** を実行します。

4.  トポロジ ビルダーの左側のウィンドウで、[**信頼済みアプリケーション サーバー**] が表示されるまでツリーを展開します。

5.  [**信頼済みアプリケーション サーバー**] ノードを展開します。

6.  これで、Exchange 2013 CAS サーバーが信頼済みアプリケーションサーバーとして表示されるようになります。

</div>

</div>

<span> </span>

</div>

</div>

</div>

