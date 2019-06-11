---
title: 'Lync Server 2013: Exchange Server 2013 と統合するための前提条件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51bc3ce48756f746b2f2f5c0ce65d08567fea74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 を統合するための前提条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-04-22_

Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 を統合する前に、すべての必須手順が完了していることを確認する必要があります。 場合によっては、Exchange 2013 と Lync Server 2013 の両方が完全にインストールされて実行されるまで、統合を行うことはできません。 Exchange のインストールの詳細については、「Exchange 2013 の計画[http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)と展開に関するドキュメント」を参照してください。 Lync Server 2013 のインストールの詳細については、の計画と[http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)展開に関するドキュメントを参照してください。

サーバーが起動して実行されたら、Lync Server 2013 と Exchange 2013 の両方にサーバー間認証証明書を割り当てる必要があります。これらの証明書を使用すると、Lync Server および Exchange で情報を交換したり、互いに通信したりすることができます。 Exchange 2013 をインストールすると、Microsoft Exchange Server 認証証明書という名前の自己署名証明書が作成されます。 この証明書はローカルコンピューターの証明書ストアに含まれている可能性があります。これは、Exchange 2013 のサーバー間認証に使用する必要があります。 Exchange 2013 での証明書の割り当ての詳細については、「のメールフロー [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)とクライアントアクセスの構成」を参照してください。

Lync Server 2013 の場合は、既存の Lync Server 証明書をサーバー間認証証明書として使うことができます。たとえば、既定の証明書を OAuthTokenIssuer 証明書として使うこともできます。 Lync Server 2013 では、次のような方法で提供されるサーバー間認証用の証明書として、任意の Web サーバー証明書を使用することができます。

  - 証明書の [Subject] (サブジェクト) フィールドに SIP ドメインの名前が含まれている。

  - これと同じ証明書がすべてのフロントエンド サーバーで OAuthTokenIssuer 証明書として構成されている。

  - 証明書の長さが 2,048 ビット以上。

Microsoft Lync Server 2013 のサーバー間認証証明書の詳細については、「[サーバー対サーバー認証証明書を Microsoft Lync server 2013 に割り当てる](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)」を参照してください。

証明書が割り当てられたら、Exchange 2013 で自動検出サービスを構成する必要があります。 Exchange 2013 では、自動検出サービスによってユーザープロファイルが構成され、ユーザーがシステムにログオンしたときに Exchange services へのアクセスが提供されます。 ユーザーが autodiscover サービスに電子メール アドレスとパスワードを入力すると、このサービスからユーザーへ次の情報が提供されます。

  - Exchange 2013 への内部および外部接続の接続情報。

  - ユーザーのメールボックス サーバーの場所。

  - 空き時間情報、ユニファイド メッセージング、およびオフライン アドレス帳などの Outlook 機能の URL。

  - Outlook Anywhere のサーバー設定。

自動検出サービスは、Lync Server 2013 と Exchange 2013 を統合する前に構成する必要があります。 自動検出サービスが構成されているかどうかを確認するには、Exchange 管理シェルから次のコマンドを実行して、AutoDiscoverServiceInternalUri プロパティの値を確認します。

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

この値が空白の場合、autodiscover サービスに URI を割り当てる必要があります。通常、この URI は次のようになります。

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

autodiscover の URI は、次のようなコマンドを実行すると割り当てられます。

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

自動検出サービスの詳細については、の「自動検出サービス[http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)について」を参照してください。

自動検出サービスが構成されたら、Lync Server OAuth 構成の設定を変更する必要があります。これにより、Lync サーバーは自動検出サービスの場所を把握することができます。 Lync Server 2013 で OAuth 構成設定を変更するには、Lync Server 管理シェルで次のコマンドを実行します。 このコマンドを実行する場合は、Exchange サーバーで実行されている自動検出サービスの URI を指定していることを確認し**ます**。また、自動検出を使用して、(xml ファイルを示す)**自動**検出ではなく、サービスの場所を指すようにする必要があります。サービスによって使用される):

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> 上のコマンドの Identity パラメーターは省略可能です。これは、Lync Server では、OAuth 構成設定のグローバルコレクションを1つだけ持つことができるためです。 これは、次のように単純なコマンドを使用して自動検出 URL を構成できることを意味します。<BR>Set-CsOAuthConfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"<BR>OAuth というテクノロジは、多くの大手 Web サイトで使用されている標準的な認証プロトコルです。OAuth では、ユーザーの資格情報とパスワードがコンピューター間で渡されることはありません。その代わりに、セキュリティ トークンの交換に基づいて認証と承認が行われます。これらのトークンによって、特定のリソースのセットに対する特定の時間のアクセスが許可されます。



</div>

自動検出サービスの構成に加えて、Exchange サーバーを参照するサービスの DNS レコードも作成する必要があります。 たとえば、自動検出サービスが autodiscover.litwareinc.com にある場合は、Exchange サーバーの完全修飾ドメイン名に解決される autodiscover.litwareinc.com の DNS レコードを作成する必要があります (たとえば、atl-exchange-001.litwareinc.com)。

</div>

<span> </span>

</div>

</div>

</div>

