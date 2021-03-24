---
title: Skype for Business と Exchange の統合の計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: '概要: Skype for Business Server を 2016 年または 2013 年 2013 年Exchange Server統合する方法については、このトピックExchange Serverしてください。'
ms.openlocfilehash: 6b2fdab1a25db7d56c99e965877cb684d102da36
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098673"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Skype for Business と Exchange の統合の計画
 
**概要:** Skype for Business Server を 2016 年または 2013 年 2013 年Exchange Server統合するExchange Serverしてください。
  
Skype for Business Server と Exchange Server を統合する前に、Exchange Server と Skype for Business Server の両方が完全にインストールされ、実行されていることを確認する必要があります。 
  
インストール方法の詳細についてはExchange Server Exchange のExchange Serverの「計画と展開」のドキュメントを参照してください。 
   
サーバーが稼働した後、Skype for Business Server とサーバー間の両方にサーバー間認証証明書を割り当てるExchange Server。これらの証明書を使用すると、Skype for Business Server Exchange Server情報を交換し、相互に通信できます。 証明書をインストールExchange Server、Auth 証明書という名前の自己署名証明書Microsoft Exchange Server作成されます。 ローカル コンピューター証明書ストアにあるこの証明書は、サーバー間認証に使用する必要Exchange Server。 証明書の割り当て方法の詳細については、「Exchange Serverメール フローの構成」および「クライアント アクセス」 [を参照してください](/exchange/configure-mail-flow-and-client-access-exchange-2013-help)。
  
Skype for Business Server では、既存の Skype for Business Server 証明書をサーバー間認証証明書として使用できます。たとえば、既定の証明書を OAuthTokenIssuer 証明書として使用できます。 Skype for Business Server では、次の条件を提供するサーバー間認証の証明書として任意の Web サーバー証明書を使用できます。
  
- 証明書の [Subject] (サブジェクト) フィールドに SIP ドメインの名前が含まれている。
    
- これと同じ証明書がすべてのフロントエンド サーバーで OAuthTokenIssuer 証明書として構成されている。
    
- 証明書の長さが 2,048 ビット以上。
    
Skype for Business Server のサーバー間認証証明書の詳細については、「Skype for Business Server にサーバー間認証証明書を割り当てる」を [参照してください](../../manage/authentication/assign-a-server-to-server-certificate.md)。
  
証明書が割り当てられたら、自動検出サービスを構成する必要Exchange Server。 このExchange Server自動検出サービスは、ユーザー プロファイルを構成し、ユーザーがシステムにログオンするときに Exchange サービスへのアクセスを提供します。 ユーザーが autodiscover サービスに電子メール アドレスとパスワードを入力すると、このサービスからユーザーへ次の情報が提供されます。
  
- 内部接続と外部接続の両方に関する接続Exchange Server。
    
- ユーザーのメールボックス サーバーの場所。
    
- 空き時間情報、ユニファイド メッセージング、およびオフライン アドレス帳などの Outlook 機能の URL。
    
- Outlook Anywhere のサーバー設定。
    
自動検出サービスは、Skype for Business Server とクライアント サーバーを統合する前に構成するExchange Server。 自動検出サービスが構成されているかどうかを確認するには、Exchange Server 管理シェルから次のコマンドを実行し、AutoDiscoverServiceInternalUri プロパティの値を確認します。
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

この値が空白の場合、autodiscover サービスに URI を割り当てる必要があります。 通常、この URI は次のように表示されます。 https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
autodiscover の URI は、次のようなコマンドを実行することによって割り当てられます。
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

自動検出サービスの詳細については、「 [自動検出サービス」を参照してください](/Exchange/architecture/client-access/autodiscover)。
  
自動検出サービスが構成された後、Skype for Business Server OAuth 構成設定を変更する必要があります。これにより、Skype for Business Server は自動検出サービスの場所を確認できます。 Skype for Business Server の OAuth 構成設定を変更するには、Skype for Business Server 管理シェル内から次のコマンドを実行します。 このコマンドを実行する場合は、Exchange Server で実行されている自動検出サービスに URI を指定し **、autodiscover.svc** を使用して **autodiscover.xml** ではなくサービスの場所をポイントします (サービスで使用される XML ファイルを指します)。
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 前のコマンドの Identity パラメーターは省略可能です。これは、Skype for Business Server では、OAuth 構成設定のグローバル コレクションを 1 つしか持てないのでです。 とりわけ、この少し簡単なコマンドを使用して自動検出 URL を構成できます。 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> OAuth というテクノロジは、多くの大手 Web サイトで使用されている標準的な認証プロトコルです。OAuth では、ユーザーの資格情報とパスワードがコンピューター間で渡されることはありません。その代わりに、セキュリティ トークンの交換に基づいて認証と承認が行われます。これらのトークンによって、特定のリソースのセットに対する特定の時間のアクセスが許可されます。 
  
自動検出サービスの構成に加えて、サービスの DNS レコードを作成して、そのサービスをポイントExchange Server。 たとえば、自動検出サービスが autodiscover.litwareinc.com にある場合は、autodiscover.litwareinc.com の DNS レコードを作成し、Exchange Server の完全修飾ドメイン名 (atl-exchange-001.litwareinc.com など) に解決する必要があります。
  
Skype for Business Server と Exchange Online を統合する場合は、「オンプレミス [の Skype for](../../deploy/integrate-with-exchange-server/outlook-web-app.md)Business Server と Outlook Web App の統合を構成する」を参照してください。それ以外の場合は、「Skype for Business Server を Exchange Server と統合する」 [を参照](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)してください。
  
## <a name="feature-support"></a>機能のサポート
<a name="feature_support"> </a>

>[!Important]
> Skype for Business Online は、サービスを含む以下の Exchange 統合がサポートされなくなった後、2021 年 7 月 31 日に廃止されます。

次の表では、Exchange と Skype for Business のオンラインまたはオンプレミスのさまざまな組み合わせでサポートされる機能について説明します。
  
||**Exchange 2016/2013/2010 (オンプレミス) + Skype for Business Server (オンプレミス)**|**Exchange Online + Skype for Business Server (オンプレミス)**|**Exchange 2010 (オンプレミス) + Skype for Business Online**|**Exchange 2016/2013(オンプレミス) + Skype for Business Online**|**Exchange Online + Skype for Business Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook でのプレゼンス  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook の電子メールから IM、PSTN 通話、Skype 通話、またはビデオ通話を介して応答する  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook を通じてオンライン会議をスケジュールして参加する  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|プレゼンス イン Outlook Web App  <br/> |Y  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|IM、PSTN 通話、Skype 通話、または OWA 電子メールからのビデオ通話による応答  <br/> |Y  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|オンライン会議のスケジュール設定と参加は、Outlook Web App  <br/> |Y  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|モバイル クライアントでの IM/Presence  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|モバイル クライアントでのオンライン会議への参加  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook 予定表の空き時間情報に基づいて状態を発行する  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|連絡先リスト (統合連絡先ストア経由)  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|高解像度の連絡先写真 (Lync 2013 または Skype for Business クライアントが少なくとも必要です。 LWA、モバイル アプリ、Lync 2010、Lync for Mac、その他の古いクライアントではサポートされていません)。  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |×  <br/> |Y  <br/> |Y  <br/> |
|会議の委任  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Exchange でのコンテンツのアーカイブ (IM と会議)  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|アーカイブされたコンテンツを検索する  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|Exchange UM ボイス メール  <br/> |Y  <br/> |Y  <br/> |×  <br/> |×  <br/> |×  <br/> |
|サーバー側の会話の履歴  <br/> |Y  <br/> |Y  <br/> |×  <br/> |Y  <br/> |Y  <br/> |

> [!NOTE]
> Skype for Business Online、Skype for Business Server 2019、Skype for Business Server 2015、Lync Server 2013 でサポートされるクラウド ボイスメール サービスがあります。
> 

## <a name="see-also"></a>関連項目
<a name="feature_support"> </a>

[オンプレミスの Skype for Business Server とサーバー間の統合を構成Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Skype for Business Online とオンプレミスの Exchange の間で OAuth を構成する](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Skype for Business Server とビジネス サーバーを統合Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[2013 Exchange Server Lync Server 2013、Skype for Business Online、または Lync Server 2013 ハイブリッド展開と統合する方法](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-hybrid-deployments)
  
[Skype for Business Server および Skype でパートナー アプリケーションを構成Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)