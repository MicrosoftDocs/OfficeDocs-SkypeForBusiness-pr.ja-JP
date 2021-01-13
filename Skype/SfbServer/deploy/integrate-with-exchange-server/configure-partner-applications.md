---
title: Skype for Business Server 2015 および Exchange Server でパートナー アプリケーションを構成する
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
description: '概要: Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server のサーバー間認証を構成します。'
ms.openlocfilehash: a707836a43965f477dc037f71bb68cbda8c8e96c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834047"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Skype for Business Server および Exchange Server でパートナー アプリケーションを構成する
 
**概要:** Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server のサーバー間認証を構成します。
  
サーバー間認証では、通常、相互に通信する必要がある 2 台のサーバーとサードパーティのセキュリティ トークン サーバーが必要です。 サーバー A とサーバー B が通信する必要がある場合は、通常、両方のサーバーがトークン サーバーに接続し、相互に信頼できるセキュリティ トークンを取得します。 その後、サーバー A は、そのセキュリティ トークンをサーバー B (またはその逆) に、その信頼性と信頼性を保証する方法として提示します。
  
ただし、それは一般的な場合です。 Skype for Business Server、Exchange Server 2016、Exchange Server 2013、および SharePoint Server 2013 は、お客様が通信するときにサードパーティのトークン サーバーを使用する必要があります。これは、これらのサーバー製品が、別のトークン サーバーを必要とせずに、お客様が受け入れ可能なセキュリティ トークンを作成できるためです。 (この機能は、Skype for Business Server、Exchange Server 2016、Exchange Server 2013、および SharePoint Server 2013 でのみ使用できます。 その他のサーバー (マイクロソフトのその他のサーバー製品を含む) とのサーバー間認証を設定する必要がある場合は、サードパーティのトークン サーバーを使用する必要があります)。
  
Skype for Business Server と Exchange Server の間でサーバー間認証を設定するには、1) 各サーバーに適切な証明書を割り当てる必要があります。2) 各サーバーを他のサーバーのパートナー アプリケーションとして構成する必要があります。つまり、Skype for Business Server を Exchange Server のパートナー アプリケーションとして構成し、skype for Business Server のパートナー アプリケーションとして Exchange Server を構成する必要があります。
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Skype for Business Server をパートナー アプリケーションとして構成Exchange Server

Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 のパートナー アプリケーションとして構成する最も簡単な方法は、Configure-EnterprisePartnerApplication.ps1 スクリプト (Exchange Server に組み込む Windows PowerShell スクリプト) を実行する方法です。 このスクリプトを実行するには、Skype for Business Server 認証メタデータ ドキュメントの URL を指定する必要があります。これは通常、Skype for Business Server プールの完全修飾ドメイン名の後にサフィックス /metadata/json/1 が続きます。 例:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Skype for Business Server をパートナー アプリケーションとして構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange が C ドライブにインストールされ、既定のフォルダー パスが使用されている場合)。
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

パートナー アプリケーションを構成した後、Exchange メールボックスおよびクライアント アクセス サーバーでインターネット インフォメーション サービス (IIS) を停止して再起動してください。 次のようなコマンドを使用して IIS を再起動できます。これにより、コンピューター atl-exchange-001 上のサービスが再起動されます。
  
```powershell
iisreset atl-exchange-001
```

このコマンドは、Exchange 管理シェル 内から実行するか、管理者特権で実行する他のコマンド ウィンドウから実行できます。
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Skype for Business Exchange Serverパートナー アプリケーションとして構成する

Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 のパートナー アプリケーションとして構成した後、skype for Business Server のパートナー アプリケーションとして Exchange Server を構成する必要があります。 これは、Skype for Business Server 管理シェルを使用して、Exchange の認証メタデータ ドキュメントを指定することで実行できます。これは通常、Exchange 自動検出サービスの URI の後にサフィックス /metadata/json/1 が続きます。 例:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

Skype for Business Server では、パートナー アプリケーションは [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) コマンドレットを使用して構成されます。 メタデータ URI を指定する以外に、アプリケーション信頼レベルを Full に設定する必要があります。これにより、Exchange 自体と領域内の承認されたユーザーの両方を表す可能性があります。 例:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

または、Skype for Business Server のサーバー間認証のドキュメントにあるスクリプト コードをコピーして変更することで、パートナー アプリケーションを作成することもできます。 詳細については、Skype for Business Server のサーバー間認証 [(OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) およびパートナー アプリケーションの管理に関する記事を参照してください。
  
Skype for Business Server と Exchange Server の両方に対してパートナー アプリケーションを正常に構成した場合は、2 つの製品間のサーバー間認証も正常に構成されています。 Skype for Business Server には、Windows PowerShell コマンドレット [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) が含まれています。これにより、サーバー間認証が正しく構成され、Skype for Business Server ストレージ サービスが Exchange Server に接続可能な状態を確認できます。 このコマンドレットでは、Exchange Server ユーザーのメールボックスに接続し、そのユーザーの [会話履歴] フォルダーにアイテムを書き込み、(必要に応じて) そのアイテムを削除します。
  
Skype for Business Server と Exchange Server の統合をテストするには、Skype for Business Server 管理シェルから次のようなコマンドを実行します。
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

上のコマンドでは、SipUri は、アカウントを持つユーザーの SIP アドレスを表Exchange Server。コマンドは失敗しますが、これは有効なユーザー アカウントではありません。
  
> [!NOTE]
> このコマンドレットから 401 応答を受け取った場合は、Exchange の既定の構成に Oauth トークンの受け入れサポートが含けられていない可能性があります。 Exchange での Oauth の使用の詳細については [、「SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=513103)と Skype for Business Server で OAuth 認証を構成する」を参照してください。 
  
テストが成功して、接続が確立されたら、オプション機能 (アーカイブの統合、統合連絡先ストアなど) を構成できます。
