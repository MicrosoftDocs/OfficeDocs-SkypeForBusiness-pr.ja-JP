---
title: Skype for Business Server 2015 および Exchange Server でパートナーアプリケーションを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '概要: Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server のサーバー認証を構成します。'
ms.openlocfilehash: 9512d271b23f26afcb1ef6385a1a6dd5d513c948
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797078"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Skype for Business Server および Exchange Server でパートナーアプリケーションを構成する
 
**概要:** Exchange Server 2016 または Exchange Server 2013 および Skype for Business Server 用にサーバー認証を構成します。
  
サーバー間認証には、通常、相互に通信する必要がある 2 台のサーバーと、サードパーティのセキュリティ トークン サーバーが必要です。 サーバー A とサーバー B が通信する必要がある場合は、通常、どちらのサーバーも、トークンサーバーに連絡し、相互に信頼されたセキュリティトークンを取得することから始まります。 そのセキュリティ トークンが、サーバーが本物であり、信頼できることを保証するための手段として、サーバー A からサーバー B (またはサーバー B からサーバー A) に提示されます。
  
ただし、それは一般的な場合です。 Skype for Business Server、Exchange Server 2016、Exchange Server 2013、および SharePoint Server 2013 は、相互に通信するときに、サードパーティのトークンサーバーを使用する必要はありません。これは、これらのサーバー製品では、個別のトークンサーバーを必要とせずに、相互に受け入れ可能なセキュリティトークンを作成できるためです。 (この機能は、Skype for Business Server、Exchange Server 2016、Exchange Server 2013、および SharePoint Server 2013 でのみ利用できます。 その他のサーバー (マイクロソフトのその他のサーバー製品を含む) とのサーバー間認証を設定する必要がある場合は、サードパーティのトークン サーバーを使用する必要があります)。
  
Skype for Business Server と Exchange Server の間のサーバー間認証をセットアップするには、2つの操作を行う必要があります。 1) 各サーバーに適切な証明書を割り当てる必要があります。さらに、2) 各サーバーを他のサーバーのパートナーアプリケーションとして構成する必要があります。つまり、Skype for Business Server を Exchange Server のパートナーアプリケーションとして構成する必要があります。つまり、Skype のパートナーアプリケーションとして Exchange server を構成する必要があります。Business Server の場合。
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Skype for Business Server を Exchange Server のパートナーアプリケーションとして構成する

Exchange server 2016 または Exchange Server 2013 とのパートナーアプリケーションとして Skype for Business Server を構成する最も簡単な方法は、Configure-EnterprisePartnerApplication スクリプトを実行することです。これは、Exchange Server に付属する Windows PowerShell スクリプトです。 このスクリプトを実行するには、Skype for Business Server authentication metadata ドキュメントの URL を指定する必要があります。通常、これは、Skype for Business サーバープールの完全修飾ドメイン名に続けてサフィックス/metadata/json/1. を指定します。 次に例を示します。
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Skype for Business Server をパートナーアプリケーションとして構成するには、Exchange 管理シェルを開き、次のようなコマンドを実行します (Exchange がドライブ C にインストールされていること、および既定のフォルダーパスを使用していることを前提としています)。
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

パートナーアプリケーションを構成した後、Exchange メールボックスとクライアントアクセスサーバーでインターネットインフォメーションサービス (IIS) を停止して再起動することをお勧めします。 次のようなコマンドを使用して、IIS を再起動することができます。これは、コンピューターの atl-exchange-001 のサービスを再起動します。
  
```powershell
iisreset atl-exchange-001
```

このコマンドは、Exchange 管理シェルから、または他のコマンドウィンドウで、管理者特権で実行できます。
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Skype for Business Server のパートナーアプリケーションとなるように Exchange Server を構成する

Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 のパートナーアプリケーションとして構成した後、Exchange Server を Skype for Business Server のパートナーアプリケーションとして構成する必要があります。 これを行うには、Skype for Business Server 管理シェルを使用し、Exchange の認証メタデータドキュメントを指定します。通常、これは Exchange 自動検出サービスの URI に続けてサフィックス/metadata/json/1. を指定します。 次に例を示します。
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

Skype for Business Server では、 [CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps)コマンドレットを使用してパートナーアプリケーションを構成します。 メタデータ URI の指定に加えて、アプリケーションの信頼レベルも完全に設定する必要があります。これにより、Exchange は、レルム内の権限を持つすべてのユーザーを表すことができます。 次に例を示します。
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

または、Skype for Business Server server のサーバー間認証ドキュメントにあるスクリプトコードをコピーして変更することで、パートナーアプリケーションを作成することもできます。 詳細については、「 [Skype For Business server のサーバー間認証 (OAuth) とパートナーアプリケーションを管理](../../manage/authentication/server-to-server-and-partner-applications.md)する」を参照してください。
  
Skype for Business Server と Exchange Server の両方に対してパートナーアプリケーションが正常に設定されている場合は、2つの製品間のサーバー間認証も正常に構成されています。 Skype for Business Server には Windows PowerShell コマンドレット[CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps)が含まれています。これにより、サーバー間認証が正しく構成されていること、および skype For Business Server ストレージサービスが Exchange server に接続できることを確認できます。 このコマンドレットでは、これを行うには、Exchange Server ユーザーのメールボックスに接続し、そのユーザーの [会話履歴] フォルダーにアイテムを書き込み、そのアイテムを削除します (必要に応じて)。
  
Skype for business Server と Exchange Server の統合をテストするには、Skype for Business Server 管理シェルから次のようなコマンドを実行します。
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

上記のコマンドでは、Si24> は Exchange Server のアカウントを持つユーザーの SIP アドレスを表します。このコマンドは、無効なユーザアカウントであるため失敗します。
  
> [!NOTE]
> このコマンドレットから401応答を受信した場合は、おそらく、Exchange の既定の構成に Oauth トークンの受け入れのサポートが含まれていないことが原因として考えられます。 Exchange での Oauth の使用について詳しくは、「 [SharePoint 2013 および Skype For Business Server での oauth 認証の構成](https://go.microsoft.com/fwlink/p/?LinkId=513103)」をご覧ください。 
  
テストが成功して、接続が確立されたら、オプション機能 (アーカイブの統合、統合連絡先ストアなど) を構成できます。
