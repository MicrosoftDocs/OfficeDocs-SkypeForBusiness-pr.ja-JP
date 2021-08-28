---
title: 2015 年および 2015 年Skype for Business Serverでパートナー アプリケーションを構成Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 4d88676b3c2cfc01935388b49b120ca99d1b7025
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607614"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>パートナー アプリケーションを構成するには、Skype for Business ServerとExchange Server
 
**概要:** 2016 年または 2016 年Exchange Server 2013 年および 2013 年Exchange Serverサーバー認証を構成Skype for Business Server。
  
サーバー間認証では、通常、相互に通信する必要がある 2 台のサーバーとサードパーティのセキュリティ トークン サーバーが必要です。 サーバー A とサーバー B が通信する必要がある場合は、通常、両方のサーバーがトークン サーバーに接続し、相互に信頼できるセキュリティ トークンを取得します。 その後、サーバー A はそのセキュリティ トークンをサーバー B (またはその逆) に提示して、信頼性と信頼性を保証します。
  
ただし、それは一般的な場合です。 Skype for Business Server、Exchange Server 2016、Exchange Server 2013、SharePoint Server 2013 は、通信時にサードパーティトークン サーバーを使用する必要があります。これは、これらのサーバー製品は、別のトークン サーバーを必要とせずに、お客様が受け入れ可能なセキュリティ トークンを作成できるからです。 (この機能は、Skype for Business Server、Exchange Server 2016、Exchange Server 2013、および SharePoint Server 2013 でのみ使用できます。 その他のサーバー (マイクロソフトのその他のサーバー製品を含む) とのサーバー間認証を設定する必要がある場合は、サードパーティのトークン サーバーを使用する必要があります)。
  
Skype for Business Server と Exchange Server の間でサーバー間認証を設定するには、1) 適切な証明書を各サーバーに割り当てる必要があります。2) 各サーバーを他のサーバーのパートナー アプリケーションとして構成する必要があります。つまり、Skype for Business Server を Exchange Server のパートナー アプリケーションとして構成し、Exchange Server を Skype for Business Server のパートナー アプリケーションとして構成する必要があります。
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>クライアントSkype for Business Serverパートナー アプリケーションとして構成Exchange Server

Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 のパートナー アプリケーションとして構成する最も簡単な方法は、Exchange Server に含む Windows PowerShell スクリプトである Configure-EnterprisePartnerApplication.ps1 スクリプトを実行する方法です。 このスクリプトを実行するには、認証メタデータ ドキュメントの URL を指定Skype for Business Server必要があります。通常、これは、サーバー プールの完全修飾ドメイン名Skype for Business Server接尾辞 /metadata/json/1 が続きます。 次に例を示します。
  
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

Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 のパートナー アプリケーションとして構成した後、Exchange Server を Skype for Business Server のパートナー アプリケーションとして構成する必要があります。 これは、管理シェルを使用して、Skype for Business Serverの認証メタデータ ドキュメントを指定することでExchange。これは通常、自動検出サービスの URI Exchange後にサフィックス /metadata/json/1 が続きます。 次に例を示します。
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

このSkype for Business Server、パートナー アプリケーションは[New-CsPartnerApplication コマンドレットを使用して構成](/powershell/module/skype/new-cspartnerapplication?view=skype-ps)されます。 メタデータ URI の指定に加えて、アプリケーション信頼レベルを Full に設定する必要があります。これにより、ユーザー Exchange、領域内の承認されたユーザーの両方を表す可能性があります。 次に例を示します。
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

または、サーバー間認証に関するドキュメントにあるスクリプト コードをコピーして変更Skype for Business Serverパートナー アプリケーションを作成することもできます。 詳細については[、「サーバー間認証 (OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md)とパートナー アプリケーションの管理」のSkype for Business Serverを参照してください。
  
Skype for Business Server と Exchange Server の両方のパートナー アプリケーションを正常に構成した場合は、2 つの製品間でサーバー間認証も正常に構成されています。 Skype for Business Serverには、Windows PowerShell コマンドレット[Test-CsExStorageConnectivity](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps)が含まれています。これにより、サーバー間認証が正しく構成され、Skype for Business Server Storage Service が Exchange Server に接続できる状態を確認できます。 このコマンドレットは、Exchange Server ユーザーのメールボックスに接続し、そのユーザーの [会話履歴] フォルダーにアイテムを書き込み、そのアイテムを (必要に応じて) 削除することでこれを行います。
  
管理シェルと管理Skype for Business Server Exchange Server統合をテストするには、次のようなコマンドを実行Skype for Business Serverします。
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

前のコマンドでは、SipUri はアカウントを持つユーザーの SIP アドレスを表Exchange Server。このコマンドは有効なユーザー アカウントではありません。
  
> [!NOTE]
> このコマンドレットから 401 応答を受け取った場合は、Oauth トークンの受け入れExchangeの既定の構成にはサポートが含けられていない可能性があります。 Oauth を使用する方法の詳細については、「Exchange [2013](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help)で OAuth 認証を構成する」および「SharePoint」を参照Skype for Business Server。 
  
テストが成功して、接続が確立されたら、オプション機能 (アーカイブの統合、統合連絡先ストアなど) を構成できます。