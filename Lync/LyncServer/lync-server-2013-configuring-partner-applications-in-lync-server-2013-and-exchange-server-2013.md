---
title: Lync Server 2013 および Exchange Server 2013 でのパートナーアプリケーションの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d6eb00b5efcd811d0fbf1397bce5f8b965c9110
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 でのパートナーアプリケーションの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-12_

サーバー間認証には、通常、3 つのエンティティが関与します。相互に通信する必要がある 2 つのサーバーと、サードパーティのセキュリティ トークン サーバーです。通信する必要がある 2 つのサーバー (サーバー A とサーバー B など) は、通常、最初にトークン サーバーに接続して、相互に信頼されたセキュリティ トークンを取得します。そのセキュリティ トークンが、サーバーが本物であり、信頼できることを保証するための手段として、一方のサーバーからもう一方のサーバー (サーバー A からサーバー B、またはサーバー B からサーバー A) に提示されます。

ただし、それは一般的な場合です。 Lync Server 2013、Microsoft Exchange Server 2013、および Microsoft SharePoint Server 2013 では、相互に通信する際にサードパーティのトークンサーバーを使用する必要はありません。これは、これらのサーバー製品では、別のトークンサーバーを使用せずに相互に受け付けることができるセキュリティトークンを作成できるからです。 (この機能は、Lync Server 2013、Exchange 2013、および SharePoint Server 2013 でのみ使用できます。 その他のサーバー (マイクロソフトのその他のサーバー製品を含む) とのサーバー間認証を設定する必要がある場合は、サードパーティのトークン サーバーを使用する必要があります)。

Lync Server と Exchange の間のサーバー間認証をセットアップするには、2つのことを行う必要があります。 1) 各サーバーに適切な証明書を割り当てる必要があります。および 2) 各サーバーを、他のサーバーのパートナーアプリケーションとして構成する必要があります。つまり、Lync Server 2013 を Exchange 2013 のパートナーアプリケーションとして構成し、Lync 2013 Server のパートナーアプリケーションとして Exchange 2013 を構成する必要があることを意味します。

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>Lync Server 2013 を Exchange 2013 のパートナーアプリケーションとして構成する

Exchange 2013 で Lync Server 2013 をパートナーアプリケーションとして構成する最も簡単な方法は、Exchange 2013 に付属する Windows PowerShell スクリプトを実行して、Configure-EnterprisePartnerApplication スクリプトを実行することです。 このスクリプトを実行するには、Lync Server 認証メタデータドキュメントの URL を指定する必要があります。これは通常、Lync Server 2013 プールの完全修飾ドメイン名の後にサフィックス/metadata/json/1. が続きます。 例:

    https://atl-cs-001.litwareinc.com/metadata/json/1

Lync Server をパートナーアプリケーションとして構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange がドライブ C: にインストールされており、既定のフォルダーパスを使用していることを前提としています)。

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

パートナーアプリケーションを構成した後、Exchange メールボックスサーバーおよびクライアントアクセスサーバーでインターネットインフォメーションサービス (IIS) を停止および再起動することをお勧めします。 IIS を再起動するには、次のようなコマンドを使用します。これにより、コンピュータ atl-fs-01 でサービスが再起動されます。

    iisreset atl-exchange-001

このコマンドは、Exchange 管理シェルまたは管理者特権で実行されている他の任意のコマンドウィンドウから実行できます。

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>Lync Server 2013 のパートナーアプリケーションとしての Exchange 2013 の構成

Lync Server 2013 を Exchange 2013 のパートナーアプリケーションとして構成した後、Exchange を Lync Server のパートナーアプリケーションとして構成する必要があります。 これは、Lync Server 管理シェルを使用して、Exchange 用の認証メタデータドキュメントを指定することによって行うことができます。これは通常、Exchange 自動検出サービスの URI の後にサフィックス/metadata/json/1. が続きます。 例:

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

Lync Server では、 [get-cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))コマンドレットを使用してパートナーアプリケーションを構成します。 メタデータ URI の指定に加えて、アプリケーションの信頼レベルも完全に設定する必要があります。これにより、Exchange は、その領域内の権限のあるユーザーとその両方を表すことができます。 例:

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

または、Lync Server 2013 のサーバー間認証のドキュメントで検出されたスクリプトコードをコピーして変更することによって、パートナーアプリケーションを作成することもできます。 詳細については、「 [Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。

Lync Server と Exchange の両方に対してパートナーアプリケーションが正常に構成されている場合は、2つの製品間のサーバー間認証も正常に構成されていることを意味します。 Lync Server 2013 には、Windows PowerShell コマンドレット[test-csexstorageconnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))が含まれています。このコマンドレットを使用すると、サーバー間認証が正しく構成されており、Lync Server Storage Service が Exchange 2013 に接続できることを確認できます。 このコマンドレットでは、Exchange 2013 ユーザーのメールボックスに接続して、そのユーザーの会話履歴フォルダーにアイテムを書き込み、必要に応じてそのアイテムを削除することによって、これを実行します。

Lync Server 2013 と Exchange 2013 の統合をテストするには、Lync Server 管理シェルで次のようなコマンドを実行します。

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

上記のコマンドで、Si31> i は、Exchange 2013 上のアカウントを持つユーザーの SIP アドレスを表します。これは有効なユーザーアカウントではないので、コマンドは失敗します。

テストが成功して、接続が確立されたら、オプション機能 (アーカイブの統合、統合連絡先ストアなど) を構成できます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

