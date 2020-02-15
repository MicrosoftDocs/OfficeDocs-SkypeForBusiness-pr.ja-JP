---
title: 'Lync Server 2013: Exchange Server 2013 との統合の前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c92f88d35e573f0914698db28ddcf1fa54967f97
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 を統合するための前提条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-04-22_

Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 を統合するには、事前にすべての前提条件の手順が完了していることを確認する必要があります。 ご想像のとおり、Exchange 2013 と Lync Server 2013 の両方が完全にインストールされ、稼働しているまで、統合を行うことができません。 Exchange のインストールの詳細については、「Exchange 2013 の計画[http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)と展開に関するドキュメント」を参照してください。 Lync Server 2013 のインストールの詳細については、「計画と[http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)展開に関するドキュメント」を参照してください。

サーバーが稼働していて、サーバー間認証証明書を Lync Server 2013 と Exchange 2013 の両方に割り当てる必要があります。これらの証明書を使用すると、Lync Server と Exchange が情報を交換したり、互いに通信したりすることができます。 Exchange 2013 をインストールすると、Microsoft Exchange Server Auth 証明書という名前の自己署名証明書が自動的に作成されます。 この証明書は、ローカルコンピューターの証明書ストアにあり、Exchange 2013 上のサーバー間認証に使用する必要があります。 Exchange 2013 での証明書の割り当ての詳細については、「」の「 [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)メールフローおよびクライアントアクセスを構成する」を参照してください。

Lync Server 2013 では、既存の Lync Server 証明書をサーバー間認証証明書として使用できます。たとえば、既定の証明書を OAuthTokenIssuer 証明書として使用することもできます。 Lync Server 2013 では、次のような場合に、任意の Web サーバー証明書をサーバー間認証の証明書として使用できます。

  - 証明書の [Subject] (サブジェクト) フィールドに SIP ドメインの名前が含まれている。

  - これと同じ証明書がすべてのフロントエンド サーバーで OAuthTokenIssuer 証明書として構成されている。

  - 証明書の長さが 2,048 ビット以上。

Microsoft Lync Server 2013 のサーバー間認証証明書の詳細については、「[サーバー間認証証明書を Microsoft Lync server 2013 に割り当てる](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)」を参照してください。

証明書が割り当てられたら、Exchange 2013 で自動検出サービスを構成する必要があります。 Exchange 2013 では、自動検出サービスによってユーザープロファイルが構成され、ユーザーがシステムにログオンしたときに Exchange サービスにアクセスできるようになります。 ユーザーが autodiscover サービスに電子メール アドレスとパスワードを入力すると、このサービスからユーザーへ次の情報が提供されます。

  - Exchange 2013 への内部接続と外部接続の両方の接続情報。

  - ユーザーのメールボックス サーバーの場所。

  - 空き時間情報、ユニファイド メッセージング、およびオフライン アドレス帳などの Outlook 機能の URL。

  - Outlook Anywhere のサーバー設定。

Lync Server 2013 と Exchange 2013 を統合する前に、自動検出サービスを構成する必要があります。 Exchange 管理シェルから次のコマンドを実行し、AutoDiscoverServiceInternalUri プロパティの値を確認することによって、自動検出サービスが構成されているかどうかを確認できます。

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

この値が空白の場合、autodiscover サービスに URI を割り当てる必要があります。通常、この URI は次のようになります。

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

autodiscover の URI は、次のようなコマンドを実行することによって割り当てられます。

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

自動検出サービスの詳細については、「」の「自動[http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)検出サービスについて」を参照してください。

自動検出サービスを構成した後、Lync Server OAuth 構成設定を変更する必要があります。これにより、Lync Server は自動検出サービスを検出する場所を認識できます。 Lync Server 2013 で OAuth 構成設定を変更するには、Lync Server 管理シェルで次のコマンドを実行します。 このコマンドを実行する場合は、Exchange サーバー上で実行されている自動検出サービス**への URI**を指定してください。また、このサービスで使用される xml ファイルを指す、自動検出サービスの場所を指定**するには**、次のようにします。

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> 上記のコマンドの Identity パラメーターは省略可能です。これは、Lync Server では、OAuth 構成設定のグローバルコレクションを1つだけ持つことができるからです。 このことは、次のような簡単なコマンドを使用して自動検出 URL を構成できることを意味します。<BR>Set-CsOAuthConfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"<BR>OAuth というテクノロジは、多くの大手 Web サイトで使用されている標準的な認証プロトコルです。OAuth では、ユーザーの資格情報とパスワードがコンピューター間で渡されることはありません。その代わりに、セキュリティ トークンの交換に基づいて認証と承認が行われます。これらのトークンによって、特定のリソースのセットに対する特定の時間のアクセスが許可されます。



</div>

自動検出サービスの構成に加えて、Exchange サーバーをポイントするサービスの DNS レコードも作成する必要があります。 たとえば、自動検出サービスが autodiscover.litwareinc.com にある場合は、Exchange サーバーの完全修飾ドメイン名に解決される autodiscover.litwareinc.com 用の DNS レコードを作成する必要があります (たとえば、atl-exchange-001.litwareinc.com)

</div>

<span> </span>

</div>

</div>

</div>

