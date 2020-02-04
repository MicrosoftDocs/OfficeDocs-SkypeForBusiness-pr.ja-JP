---
title: Lync Server 2013 および Exchange Server 2013 でパートナーアプリケーションを構成する
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
ms.openlocfilehash: c60e018a86ec0838791d5fc46845460b5f039f23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Microsoft Lync Server 2013 および Microsoft Exchange Server 2013 でパートナーアプリケーションを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-12_

サーバー間認証には、通常、相互に通信する必要がある2つのサーバーと、サードパーティのセキュリティトークンサーバーという3つのエンティティが含まれます。 2つのサーバー (サーバー A とサーバー B など) が通信する必要がある場合は、通常、これらの両方のサーバーが、トークンサーバーに連絡して、相互に信頼されたセキュリティトークンを取得することから始まります。 サーバー A は、そのセキュリティトークンをサーバー B に提示し (その逆も可能)、信頼性と信頼性の両方を保証する手段として提供されます。

ただし、それは一般的な場合です。 Lync Server 2013、Microsoft Exchange Server 2013、および Microsoft SharePoint Server 2013 は、相互に通信するときに、サードパーティのトークンサーバーを使用する必要はありません。これは、これらのサーバー製品では、個別のトークンサーバーを必要とせずに、相互に受け入れ可能なセキュリティトークンを作成できるためです。 (この機能は、Lync Server 2013、Exchange 2013、および SharePoint Server 2013 でのみ利用できます。 その他のサーバー (マイクロソフトのその他のサーバー製品を含む) とのサーバー間認証を設定する必要がある場合は、サードパーティのトークン サーバーを使用する必要があります)。

Lync Server と Exchange の間のサーバー間認証をセットアップするには、次の2つの操作を行う必要があります。 1) 各サーバーに適切な証明書を割り当てる必要があります。さらに、2) 各サーバーを他のサーバーのパートナーアプリケーションとして構成する必要があります。つまり、このため、Lync server 2013 を Exchange 2013 のパートナーアプリケーションとして構成する必要があります。つまり、lync Server 2013 のパートナーアプリケーションとなるように Exchange 2013 を構成する必要があります。

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>Lync Server 2013 を Exchange 2013 のパートナーアプリケーションとして構成する

Lync Server 2013 を Exchange 2013 のパートナーアプリケーションとして構成するには、Configure-EnterprisePartnerApplication スクリプトを実行するのが最も簡単な方法です。これには、Exchange 2013 に付属する Windows PowerShell スクリプトを使用します。 このスクリプトを実行するには、Lync Server authentication metadata ドキュメントの URL を指定する必要があります。通常、これは Lync Server 2013 プールの完全修飾ドメイン名の後にサフィックス/metadata/json/1. が表示されます。 次に例を示します。

    https://atl-cs-001.litwareinc.com/metadata/json/1

パートナーアプリケーションとして Lync Server を構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange がドライブ C にインストールされていること、および既定のフォルダーパスを使用していることを前提としています)。

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

パートナーアプリケーションを構成した後、Exchange メールボックスとクライアントアクセスサーバーでインターネットインフォメーションサービス (IIS) を停止して再起動することをお勧めします。 次のようなコマンドを使用して、IIS を再起動することができます。これは、コンピューターの atl-exchange-001 のサービスを再起動します。

    iisreset atl-exchange-001

このコマンドは、Exchange 管理シェルから、または他のコマンドウィンドウで、管理者特権で実行できます。

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>Lync Server 2013 のパートナーアプリケーションとなるように Exchange 2013 を構成する

Lync Server 2013 を Exchange 2013 のパートナーアプリケーションとして構成した後、Lync Server のパートナーアプリケーションとなるように Exchange を構成する必要があります。 この操作を行うには、Lync Server 管理シェルを使用し、Exchange の認証メタデータドキュメントを指定します。通常、これは Exchange 自動検出サービスの URI に続けてサフィックス/metadata/json/1. を指定します。 次に例を示します。

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

Lync Server では、[新しい-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))コマンドレットを使用してパートナーアプリケーションを構成します。 メタデータ URI の指定に加えて、アプリケーションの信頼レベルも完全に設定する必要があります。これにより、Exchange は、レルム内の権限を持つすべてのユーザーを表すことができます。 次に例を示します。

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

または、Lync Server 2013 サーバー間認証のドキュメントにあるスクリプトコードをコピーして変更することで、パートナーアプリケーションを作成することもできます。 詳細については、「 [Lync server 2013 でサーバー間認証 (OAuth) とパートナーアプリケーションを管理する](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。

Lync Server と Exchange の両方にパートナーアプリケーションを正しく設定した場合、2つの製品間のサーバー間認証も正常に構成されていることを意味します。 Lync Server 2013 には Windows PowerShell コマンドレット[CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))が含まれています。これにより、サーバー間の認証が正しく構成されていること、および Lync Server ストレージサービスが Exchange 2013 に接続できることを確認できます。 このコマンドレットでは、Exchange 2013 ユーザーのメールボックスに接続し、そのユーザーの [会話履歴] フォルダーにアイテムを書き込んで、必要に応じてそのアイテムを削除します。

Lync server 2013 と Exchange 2013 の統合をテストするには、Lync Server 管理シェルで次のようなコマンドを実行します。

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

上記のコマンドでは、Si24> は Exchange 2013 上のアカウントを持つユーザーの SIP アドレスを表します。このコマンドは、無効なユーザアカウントであるため失敗します。

テストが成功して、接続が確立されたら、オプション機能 (アーカイブの統合、統合連絡先ストアなど) を構成できます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

