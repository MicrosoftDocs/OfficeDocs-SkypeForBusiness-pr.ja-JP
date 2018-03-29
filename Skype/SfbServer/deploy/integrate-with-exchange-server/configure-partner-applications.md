---
title: ビジネス サーバー 2015 と Exchange Server の Skype のパートナーのアプリケーションを構成します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: '概要: ビジネス サーバー 2015 2016 の Exchange Server や Exchange Server 2013 と Skype のサーバー認証を構成します。'
ms.openlocfilehash: d7b3d93126c5b2db06e5f7343f5636b3c305d7c8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-partner-applications-in-skype-for-business-server-2015-and-exchange-server"></a>ビジネス サーバー 2015 と Exchange Server の Skype のパートナーのアプリケーションを構成します。
 
**の概要:**ビジネス サーバー 2015 2016 の Exchange Server や Exchange Server 2013 と Skype のサーバー認証を構成します。
  
サーバー間認証には、通常、相互に通信する必要がある 2 台のサーバーと、サードパーティのセキュリティ トークン サーバーが必要です。 サーバー A とサーバー B は、通信する必要がある場合、それらのサーバーの両方の通常開始トークン サーバーに接続し、相互に信頼されたセキュリティ トークンを取得します。 そのセキュリティ トークンが、サーバーが本物であり、信頼できることを保証するための手段として、サーバー A からサーバー B (またはサーバー B からサーバー A) に提示されます。
  
ただし、それは一般的な場合です。 ビジネス サーバー 2015、2016 の Exchange Server、Exchange Server 2013 では、SharePoint Server 2013 の Skype は、他と通信するときに、サード ・ パーティ製トークン サーバーを使用する必要はありません。これらのサーバー製品は、トークンに別のサーバーを必要とせずに互いに認めることができるセキュリティ トークンを作成できるためです。 (この機能はビジネス サーバー 2015、2016 の Exchange Server、Exchange Server 2013 では、SharePoint Server 2013 の Skype ではできるだけです。 その他のサーバー (マイクロソフトのその他のサーバー製品を含む) とのサーバー間認証を設定する必要がある場合は、サードパーティのトークン サーバーを使用する必要があります)。
  
Skype ビジネス サーバーと Exchange Server 間でサーバーからサーバーへの認証を設定するのには 2 つの操作を行う必要があります: 1) 各サーバーに適切な証明書を割り当てる必要があります2) 他のサーバーのパートナーのアプリケーションには、各サーバーを構成する必要がありますつまりの Exchange Server では、パートナーのアプリケーションのビジネス サーバー 2015 の Skype を構成する必要がありますし、パートナーのアプリケーションである Exchange Server を構成する必要があります。ビジネス サーバー 2015 の Skype です。
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Skype のビジネスのサーバーを Exchange Server のパートナーのアプリケーションを構成します。

2016 の Exchange Server や Exchange Server 2013 とパートナーのアプリケーションのビジネス サーバー 2015 の Skype を構成する最も簡単な方法は、Exchange Server に付属している Windows PowerShell スクリプトを構成する EnterprisePartnerApplication.ps1 スクリプトを実行するには. このスクリプトを実行するには、ビジネスのサーバー認証メタデータ ドキュメントの Skype の URL を指定する必要があります。通常、Skype のビジネス サーバー 2015 プールの後にサフィックス/metadata/json/1 の完全修飾ドメイン名になります。 例:
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

ビジネス パートナーのアプリケーション サーバー用には、Skype を構成するには、Exchange 管理シェルを開くし、(と仮定すると、Exchange は、ドライブ c: にインストールされているし、既定のフォルダーのパスを使用する) は、次のようなコマンドを実行します。
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

パートナー アプリケーションを構成した後、停止して、Exchange のメールボックスおよびクライアント アクセス サーバーのインターネット インフォメーション サービス (IIS) を再起動することをお勧めします。 コマンドを使用して、次のようなコンピューター atl-exchange-001 のサービスを再起動する、IIS を再起動することができます。
  
```
iisreset atl-exchange-001
```

Exchange 管理シェル内で、または管理者特権で実行して、他のコマンド ウィンドウからこのコマンドを実行することができます。
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>ビジネス サーバーの Skype のパートナー アプリケーションである Exchange Server を構成します。

2016 の Exchange Server や Exchange Server 2013 のパートナーのアプリケーションのビジネス サーバー 2015 の Skype を構成した後は、ビジネス サーバーの Skype のパートナー アプリケーションである Exchange Server を構成する必要があります。 これによってビジネス サーバー管理シェルには、Skype を使用して、exchange は認証メタデータ ドキュメントを指定します。通常サフィックス/metadata/json/1 の後に Exchange 自動検出サービスの URI になります。 例:
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

ビジネス サーバーの Skype は、パートナーのアプリケーションが[新しい CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps)コマンドレットを使用して構成されます。 メタデータの URI を指定するだけでなく設定はアプリケーションの信頼レベルを完全にこれによって、Exchange 自体およびレルム内のすべての権限を持つユーザーを表す。 例:
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

また、ビジネス サーバー 2015 のサーバーからサーバーへの認証について Skype のスクリプト コードを変更することをコピーして、パートナーのアプリケーションを作成できます。 詳細については、[管理サーバーからサーバーへの認証 (OAuth) とビジネス サーバー 2015 の Skype のパートナーのアプリケーション](../../manage/authentication/server-to-server-and-partner-applications.md)の資料を参照してください。
  
ビジネス サーバーと Exchange Server の両方の Skype のパートナーのアプリケーションを正常に構成した場合も正常に構成した 2 つの製品間でのサーバーからサーバーへの認証です。 ビジネス サーバー 2015 の Skype には、[テスト CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps)とすると、そのサーバーからサーバーへの認証が正しく構成されていることを確認できるように、Windows PowerShell コマンドレットが含まれていますビジネス サーバー ・ ストレージ ・ サービスの Skype。Exchange Server に接続できます。 コマンドレットは、Exchange Server のユーザーのメールボックスに接続して、そのユーザーの会話の履歴フォルダーにアイテムを作成、し、その項目を削除する (必要に応じて) します。
  
Skype ビジネス サーバー 2015」および「Exchange Server との統合をテストするには、ビジネス サーバー管理シェルには、Skype から次のようなコマンドを実行します。
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

上記のコマンドでは、SipUri は Exchange Server のアカウントを持つユーザーの SIP アドレスを表します。コマンドは正常に有効なユーザー アカウントではありません。
  
> [!NOTE]
> このコマンドレットから 401 応答を受信する場合はおそらく Exchange の既定の構成には Oauth トークンを許可するためのサポートが含まれていないためです。 Oauth を使用して Exchange の詳細については、 [SharePoint 2013 とビジネス サーバー 2015 の Skype を構成する OAuth 認証](https://go.microsoft.com/fwlink/p/?LinkId=513103)を参照してください。 
  
テストが成功して、接続が確立されたら、オプション機能 (アーカイブの統合、統合連絡先ストアなど) を構成できます。
  

