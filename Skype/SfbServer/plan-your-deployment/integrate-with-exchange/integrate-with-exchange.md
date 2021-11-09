---
title: Skype for Business と Exchange の統合の計画
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: '概要: このトピックでは、2016 年または 2013 年Skype for Business Server 2016 Exchange Serverと統合Exchange Serverしてください。'
ms.openlocfilehash: 8613f080aa878c5111a4c69c38b77f9c16606b26
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844130"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Skype for Business と Exchange の統合の計画
 
**概要:** このトピックでは、2016 年または 2013 年Skype for Business Server 2016 Exchange Serverと統合Exchange Serverしてください。
  
アプリケーションとサーバーをSkype for Business Server Exchange Serverする前に、Exchange ServerとSkype for Business Serverが完全にインストールされ、実行されていることを確認する必要があります。 
  
インストール方法の詳細についてはExchange ServerバージョンExchange Serverの「計画と展開」のドキュメントを参照Exchange。 
   
サーバーが稼働した後、サーバー間認証証明書をサーバー間認証証明書とサーバー間認証証明書の両方Skype for Business Server割りExchange Server。これらの証明書を使用Skype for Business Server、Exchange Serverを交換し、相互に通信することができます。 証明書をインストールExchange Server、Auth 証明書という名前の自己署名証明書Microsoft Exchange Server作成されます。 ローカル コンピューター証明書ストアにあるこの証明書は、サーバー間認証に使用する必要Exchange Server。 サーバーでの証明書の割り当てExchange Server詳細については[、「Configure Mail Flow」および「クライアント アクセス」を参照してください](/exchange/configure-mail-flow-and-client-access-exchange-2013-help)。
  
たとえばSkype for Business Serverサーバー間認証証明書Skype for Business Server既存の証明書を使用できます。たとえば、既定の証明書を OAuthTokenIssuer 証明書として使用できます。 Skype for Business Serverを使用すると、次の条件を提供するサーバー間認証の証明書として任意の Web サーバー証明書を使用できます。
  
- 証明書の [Subject] (サブジェクト) フィールドに SIP ドメインの名前が含まれている。
    
- これと同じ証明書がすべてのフロントエンド サーバーで OAuthTokenIssuer 証明書として構成されている。
    
- 証明書の長さが 2,048 ビット以上。
    
サーバー間認証証明書の詳細については、「Skype for Business Serverサーバー間認証証明書をサーバーに割り当てる」を[参照](../../manage/authentication/assign-a-server-to-server-certificate.md)Skype for Business Server。
  
証明書が割り当てられたら、自動検出サービスを構成する必要Exchange Server。 このExchange Server自動検出サービスは、ユーザー プロファイルを構成し、ユーザーがシステムにログオンするときにExchangeサービスへのアクセスを提供します。 ユーザーが autodiscover サービスに電子メール アドレスとパスワードを入力すると、このサービスからユーザーへ次の情報が提供されます。
  
- 内部接続と外部接続の両方に関する接続Exchange Server。
    
- ユーザーのメールボックス サーバーの場所。
    
- 空き時間情報、ユニファイド メッセージング、およびオフライン アドレス帳などの Outlook 機能の URL。
    
- Outlook Anywhere のサーバー設定。
    
自動検出サービスを構成してから、自動検出サービスとSkype for Business Server統合Exchange Server。 自動検出サービスが構成されているかどうかを確認するには、Exchange Server 管理シェルから次のコマンドを実行し、AutoDiscoverServiceInternalUri プロパティの値を確認します。
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

この値が空白の場合、autodiscover サービスに URI を割り当てる必要があります。 通常、この URI は次のように表示されます。 https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
autodiscover の URI は、次のようなコマンドを実行することによって割り当てられます。
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

自動検出サービスの詳細については、「 [自動検出サービス」を参照してください](/Exchange/architecture/client-access/autodiscover)。
  
自動検出サービスが構成された後で、OAuth 構成設定のSkype for Business Server変更する必要があります。これにより、自動検出Skype for Business Server場所を確認できます。 OAuth 構成設定を変更するには、Skype for Business Server管理シェル内から次のコマンドSkype for Business Server実行します。 このコマンドを実行する場合は、Exchange Server で実行されている自動検出サービスに URI を指定し **、autodiscover.svc** を使用して **autodiscover.xml** ではなくサービスの場所をポイントします (サービスで使用される XML ファイルを指します)。
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 前のコマンドの Identity パラメーターは省略可能です。これは、OAuth 構成Skype for Business Serverの単一のグローバル コレクションしか持てないのでです。 とりわけ、この少し簡単なコマンドを使用して自動検出 URL を構成できます。 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> OAuth というテクノロジは、多くの大手 Web サイトで使用されている標準的な認証プロトコルです。OAuth では、ユーザーの資格情報とパスワードがコンピューター間で渡されることはありません。その代わりに、セキュリティ トークンの交換に基づいて認証と承認が行われます。これらのトークンによって、特定のリソースのセットに対する特定の時間のアクセスが許可されます。 
  
自動検出サービスの構成に加えて、サービスの DNS レコードを作成して、そのサービスをポイントExchange Server。 たとえば、自動検出サービスが autodiscover.litwareinc.com にある場合は、Exchange Server の完全修飾ドメイン名 (atl-exchange-001.litwareinc.com など) に解決される autodiscover.litwareinc.com の DNS レコードを作成する必要があります。
  
Skype for Business Server と Exchange Online を統合する場合は、「オンプレミス Skype for Business Server と[Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)の間の統合を構成する」を参照してください。それ以外の場合は、「Skype for Business Server と Exchange Server を統合する」を[参照](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)してください。
  
## <a name="feature-support"></a>機能のサポート
<a name="feature_support"> </a>

>[!Important]
> Skype for Businessサービスを含む以下の Exchange 統合がサポートされなくなった後、オンラインは 2021 年 7 月 31 日に廃止されます。

次の表は、オンラインまたはオンプレミスのさまざまな組み合わせでサポートされる機能の詳細を示ExchangeおよびSkype for Business。
  
|&nbsp;|Exchange 2016/2013/2010 (オンプレミス) + Skype for Business Server (オンプレミス)|Exchange Online + Skype for Business Server (オンプレミス)**|**Exchange 2010 (オンプレミス) + Skype for Business Online|Exchange 2016/2013(オンプレミス) + Skype for Business Online**|**Exchange Online + Skype for Business Online|
|:-----|:-----|:-----|:-----|:-----|:-----|
|プレゼンス イン Outlook   |Y   |Y   |Y   |Y   |Y   |
|IM、PSTN 通話、電話Skypeビデオ通話を経由して、電子メールからOutlookする   |Y   |Y   |Y   |Y   |Y   |
|オンライン会議のスケジュール設定と参加は、Outlook   |Y   |Y   |Y   |Y   |Y   |
|プレゼンス イン Outlook Web App   |Y   |Y   |N   |×   |Y   |
|IM、PSTN 通話、OWA メールSkypeビデオ通話による応答   |Y   |Y   |N   |×   |Y   |
|オンライン会議をスケジュールし、会議に参加Outlook Web App   |Y   |Y   |N   |×   |Y   |
|モバイル クライアントでの IM/Presence   |Y   |Y   |Y   |Y   |Y   |
|モバイル クライアントでのオンライン会議への参加   |Y   |Y   |Y   |Y   |Y   |
|予定表の空き時間情報Outlookに基づいて状態を公開する   |Y   |Y   |Y   |Y   |Y   |
|連絡先リスト (統合連絡先ストア経由)   |Y (Exchange 2016/2013)   |Y   |N   |×   |Y   |
|高解像度の連絡先写真 (Lync 2013 または Skype for Businessクライアントが必要です。 LWA、モバイル アプリ、Lync 2010、Lync for Mac、その他の古いクライアントではサポートされていません)。   |Y (Exchange 2016/2013)   |Y   |N   |Y   |Y   |
|会議の委任   |Y   |Y   |Y   |Y   |Y   |
|会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる   |Y   |Y   |Y   |Y   |Y   |
|アーカイブ コンテンツ (IM と会議) Exchange   |Y (Exchange 2016/2013)   |Y   |N   |×   |Y   |
|アーカイブされたコンテンツを検索する   |Y (Exchange 2016/2013)   |Y   |N   |×   |Y   |
|ExchangeUM ボイス メール   |Y   |Y   |N   |×   |×   |
|サーバー側の会話の履歴   |Y   |Y   |N   |Y   |Y   |

> [!NOTE]
> クラウド ボイスメール Online、Skype for Business 2019、Skype for Business Server 2015、Lync Server 2013 でサポートされる Skype for Business Server サービスがあります。
> 

## <a name="see-also"></a>関連項目
<a name="feature_support"> </a>

[オンプレミスのサーバーとサーバー間の統合Skype for Business Server構成Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[オンプレミスとオンラインの間Skype for Business OAuth Exchange構成する](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[アプリケーションSkype for Business Server統合Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[2013 Exchange Server Lync Server 2013、Skype for Business Online、または Lync Server 2013 ハイブリッド展開と統合する方法](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-hybrid-deployments)
  
[パートナー アプリケーションを構成するには、Skype for Business ServerとMicrosoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)