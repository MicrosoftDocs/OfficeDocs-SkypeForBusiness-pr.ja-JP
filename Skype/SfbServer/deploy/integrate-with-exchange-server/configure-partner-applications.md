---
title: Skype for Business Server 2015 でパートナー アプリケーションを構成し、Exchange Server
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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: '概要: 2016 年または 2016 年Exchange Server 2013 年Exchange Server Skype for Business Server のサーバー認証にサーバーを構成します。'
ms.openlocfilehash: 47f192ce11a48ab4c256ac6a1f499aa24563a725
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110113"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Skype for Business Server および Skype でパートナー アプリケーションを構成Exchange Server
 
**概要:** 2016 年または 2016 年Exchange Server 2013 年Exchange Server Skype for Business Server のサーバー認証にサーバーを構成します。
  
サーバー間認証では、通常、相互に通信する必要がある 2 台のサーバーとサードパーティのセキュリティ トークン サーバーが必要です。 サーバー A とサーバー B が通信する必要がある場合は、通常、両方のサーバーがトークン サーバーに接続し、相互に信頼できるセキュリティ トークンを取得します。 その後、サーバー A はそのセキュリティ トークンをサーバー B (またはその逆) に提示して、信頼性と信頼性を保証します。
  
ただし、それは一般的な場合です。 Skype for Business Server、Exchange Server 2016、Exchange Server 2013、および SharePoint Server 2013 は、通信時にサード パーティトークン サーバーを使用する必要があります。これは、これらのサーバー製品は、別のトークン サーバーを必要とせずに、お客様が受け入れ可能なセキュリティ トークンを作成できるからです。 (この機能は、Skype for Business Server、Exchange Server 2016、Exchange Server 2013、および SharePoint Server 2013 でのみ使用できます。 その他のサーバー (マイクロソフトのその他のサーバー製品を含む) とのサーバー間認証を設定する必要がある場合は、サードパーティのトークン サーバーを使用する必要があります)。
  
Skype for Business Server と Exchange Server の間でサーバー間認証をセットアップするには、1) 適切な証明書を各サーバーに割り当てる必要があります。2) 各サーバーを他のサーバーのパートナー アプリケーションとして構成する必要があります。つまり、Skype for Business Server を Exchange Server のパートナー アプリケーションとして構成し、Exchange Server を Skype for Business Server のパートナー アプリケーションとして構成する必要があります。
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Skype for Business Server をパートナー アプリケーションとして構成Exchange Server

skype for Business Server を Exchange Server 2016 または Exchange Server 2013 のパートナー アプリケーションとして構成する最も簡単な方法は、Exchange Server に含む Configure-EnterprisePartnerApplication.ps1 スクリプトである Windows PowerShell スクリプトを実行する方法です。 このスクリプトを実行するには、Skype for Business Server 認証メタデータ ドキュメントの URL を指定する必要があります。これは通常、Skype for Business Server プールの完全修飾ドメイン名に続いてサフィックス /metadata/json/1 になります。 例:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

パートナー アプリケーションとして Skype for Business Server を構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange が C ドライブにインストールされ、既定のフォルダー パスが使用されていることを前提とします)。
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

パートナー アプリケーションを構成した後、Exchange メールボックスおよびクライアント アクセス サーバーでインターネット インフォメーション サービス (IIS) を停止して再起動してください。 次のようなコマンドを使用して IIS を再起動すると、コンピューター atl-exchange-001 でサービスが再起動されます。
  
```powershell
iisreset atl-exchange-001
```

このコマンドは、Exchange 管理シェル内または管理者特権で実行される他のコマンド ウィンドウから実行できます。
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Skype for business server Exchange Serverパートナー アプリケーションとして構成する方法

Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 のパートナー アプリケーションとして構成した後、Exchange Server を Skype for Business Server のパートナー アプリケーションとして構成する必要があります。 これは、Skype for Business Server 管理シェルを使用し、Exchange の認証メタデータ ドキュメントを指定することで実行できます。通常、これは Exchange 自動検出サービスの URI に続いてサフィックス /metadata/json/1 になります。 例:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

Skype for Business Server では、パートナー アプリケーションは [New-CsPartnerApplication](/powershell/module/skype/new-cspartnerapplication?view=skype-ps) コマンドレットを使用して構成されます。 メタデータ URI の指定に加えて、アプリケーション信頼レベルを Full に設定する必要があります。これにより、Exchange は自身と領域内の承認されたユーザーの両方を表す可能性があります。 例:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

または、Skype for Business Server サーバー間認証のドキュメントにあるスクリプト コードをコピーして変更することで、パートナー アプリケーションを作成できます。 詳細については、「Skype for Business Server でのサーバー間認証 [(OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) およびパートナー アプリケーションの管理」を参照してください。
  
Skype for Business Server と Exchange Server の両方のパートナー アプリケーションを正常に構成した場合は、2 つの製品間でサーバー間認証も正常に構成されています。 Skype for Business Server には、Windows PowerShell コマンドレット [Test-CsExStorageConnectivity](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) が含まれています。これにより、サーバー間認証が正しく構成され、Skype for Business Server Storage Service が Exchange Server に接続できる状態を確認できます。 このコマンドレットは、Exchange Server ユーザーのメールボックスに接続し、そのユーザーの [会話履歴] フォルダーにアイテムを書き込み、そのアイテムを (必要に応じて) 削除することでこれを行います。
  
Skype for Business Server と Skype Exchange Serverの統合をテストするには、Skype for Business Server 管理シェルから次のようなコマンドを実行します。
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

前のコマンドでは、SipUri はアカウントを持つユーザーの SIP アドレスを表Exchange Server。このコマンドは有効なユーザー アカウントではありません。
  
> [!NOTE]
> このコマンドレットから 401 応答を受け取った場合、Exchange の既定の構成には Oauth トークンの受け入れサポートが含けられていない可能性があります。 Exchange での Oauth の使用の詳細については [、「Configure OAuth authentication with SharePoint 2013」および「Skype for Business Server」を参照してください](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help)。 
  
テストが成功して、接続が確立されたら、オプション機能 (アーカイブの統合、統合連絡先ストアなど) を構成できます。