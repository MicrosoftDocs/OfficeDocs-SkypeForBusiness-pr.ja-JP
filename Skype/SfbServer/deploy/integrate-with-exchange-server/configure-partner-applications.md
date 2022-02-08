---
title: 2015 年および 2015 年Skype for Business Serverでパートナー アプリケーションを構成Exchange Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: '概要: 2016 年または 2013 年および 2013 年Exchange Serverサーバー認証用Exchange Serverサーバー認証を構成Skype for Business Server。'
ms.openlocfilehash: d7a3b99536524df5422521cdaf45a7e4dac911b3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387215"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>パートナー アプリケーションを構成するには、Skype for Business ServerとExchange Server
 
**概要:** 2016 年または 2016 年Exchange Server 2013 年および 2013 年Exchange Serverサーバー認証を構成Skype for Business Server。
  
サーバー間認証では、通常、相互に通信する必要がある 2 台のサーバーとサードパーティのセキュリティ トークン サーバーが必要です。 サーバー A とサーバー B が通信する必要がある場合は、通常、両方のサーバーがトークン サーバーに接続し、相互に信頼できるセキュリティ トークンを取得します。 その後、サーバー A はそのセキュリティ トークンをサーバー B (またはその逆) に提示して、信頼性と信頼性を保証します。
  
ただし、それは一般的な場合です。 Skype for Business Server、Exchange Server 2016、Exchange Server 2013、および SharePoint Server 2013 は、通信時にサード パーティトークン サーバーを使用する必要はないので、これらのサーバー製品は、セキュリティ トークンを作成できます。別のトークン サーバーが必要です。 (この機能は、Skype for Business Server、Exchange Server 2016、Exchange Server 2013、および SharePoint Server 2013 でのみ使用できます。 その他のサーバー (マイクロソフトのその他のサーバー製品を含む) とのサーバー間認証を設定する必要がある場合は、サードパーティのトークン サーバーを使用する必要があります)。
  
Skype for Business Server と Exchange Server の間でサーバー間認証をセットアップするには、1) 各サーバーに適切な証明書を割り当てる必要があります。2) 各サーバーを他のサーバーのパートナー アプリケーションとして構成する必要があります。つまり、構成する必要があります。Skype for Business Serverパートナー アプリケーションとして使用するには、Exchange Serverのパートナー アプリケーションExchange Server構成する必要Skype for Business Server。
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>クライアントSkype for Business Serverパートナー アプリケーションとして構成Exchange Server

Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 のパートナー アプリケーションとして構成する最も簡単な方法は、Configure-EnterprisePartnerApplication.ps1 スクリプト (Windows PowerShell スクリプト) を実行Exchange Server. このスクリプトを実行するには、Skype for Business Server 認証メタデータ ドキュメントの URL を指定する必要があります。これは通常、Skype for Business Server プールの完全修飾ドメイン名の後にサフィックス /metadata/json/1 を付けます。 次に例を示します。
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Skype for Business Serverをパートナー アプリケーションとして構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange がドライブ C にインストールされ、既定のフォルダー パスを使用すると仮定します)。
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

パートナー アプリケーションを構成した後は、メールボックス サーバーとクライアント アクセス サーバーで インターネット インフォメーション サービス (IIS) を停止して再起動Exchangeをお勧めします。 次のようなコマンドを使用して IIS を再起動すると、コンピューター atl-exchange-001 でサービスが再起動されます。
  
```powershell
iisreset atl-exchange-001
```

このコマンドは、管理シェル内Exchange管理者特権で実行する他のコマンド ウィンドウから実行できます。
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>クライアントExchange Serverパートナー アプリケーションとして構成Skype for Business Server

Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 のパートナー アプリケーションとして構成した後、Exchange Server をパートナー アプリケーションとして構成する必要があります。Skype for Business Server。 これは、Skype for Business Server 管理シェルを使用し、Exchange の認証メタデータ ドキュメントを指定することで実行できます。これは通常、Exchange 自動検出サービスの URI に続いてサフィックス /metadata/json/1 になります。 次に例を示します。
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

このSkype for Business Server、パートナー アプリケーションは [New-CsPartnerApplication コマンドレットを使用して構成](/powershell/module/skype/new-cspartnerapplication?view=skype-ps)されます。 メタデータ URI の指定に加えて、アプリケーション信頼レベルを Full に設定する必要があります。これにより、ユーザー Exchange、領域内の承認されたユーザーの両方を表す可能性があります。 次に例を示します。
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

または、サーバー間認証に関するドキュメントにあるスクリプト コードをコピーして変更Skype for Business Serverパートナー アプリケーションを作成することもできます。 詳細については[、「サーバー間認証 (OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) とパートナー アプリケーションの管理」のSkype for Business Serverを参照してください。
  
Skype for Business Server と Exchange Server の両方のパートナー アプリケーションを正常に構成した場合は、2 つの製品間でサーバー間認証も正常に構成されています。 Skype for Business Serverには、Windows PowerShell コマンドレット [Test-CsExStorageConnect Skype for Business Server Storage ivity](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) が含まれています。に接続Exchange Server。 このコマンドレットは、Exchange Server ユーザーのメールボックスに接続し、そのユーザーの [会話履歴] フォルダーにアイテムを書き込み、そのアイテムを (必要に応じて) 削除することでこれを行います。
  
管理シェルと管理Skype for Business Server Exchange Server統合をテストするには、次のようなコマンドを実行Skype for Business Serverします。
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

前のコマンドでは、SipUri は Exchange Server のアカウントを持つユーザーの SIP アドレスを表します。このコマンドは有効なユーザー アカウントではありません。
  
> [!NOTE]
> このコマンドレットから 401 応答を受け取った場合は、Oauth トークンの受け入れExchangeの既定の構成にはサポートが含けられていない可能性があります。 Oauth を使用する方法の詳細については、「Exchange [2013 で OAuth](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help) 認証を構成する」および「SharePoint」を参照Skype for Business Server。 
  
テストが成功して、接続が確立されたら、オプション機能 (アーカイブの統合、統合連絡先ストアなど) を構成できます。