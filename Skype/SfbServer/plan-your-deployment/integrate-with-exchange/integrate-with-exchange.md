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
description: '概要: Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 と統合する方法については、このトピックを参照してください。'
ms.openlocfilehash: f2a9dfc718b7891a0cbe9b7b1455df24531a6ed0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810102"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Skype for Business と Exchange の統合の計画
 
**概要:** Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 と統合する方法については、このトピックを参照してください。
  
Skype for Business Server と Exchange Server を統合する前に、Exchange Server と Skype for Business Server の両方が完全にインストールされ、稼働されていることを確認する必要があります。 
  
Exchange のインストールの詳細についてはExchange Serverバージョンの「Exchange Server Planning and Deployment」のドキュメントを参照してください。 
   
サーバーを稼働状態にした後、Skype for Business Server とサーバー間の両方にサーバー間認証証明書を割り当Exchange Server。これらの証明書を使用すると、Skype for Business Server Exchange Server情報を交換し、相互に通信できます。 証明書をインストールExchange Server、認証証明書という名前の自己署名証明書Microsoft Exchange Server作成されます。 ローカル コンピューターの証明書ストアにあるこの証明書は、ローカル コンピューター上のサーバー間認証にExchange Server。 メール フローとクライアント アクセスの構成に関するページExchange Server証明書の割り当 [てについて詳](https://go.microsoft.com/fwlink/p/?LinkId=268540)しくは、「メール フローとクライアント アクセスの構成」をご覧ください。
  
Skype for Business Server の場合は、既存の Skype for Business Server 証明書をサーバー間認証証明書として使用できます。たとえば、既定の証明書を OAuthTokenIssuer 証明書として使用できます。 Skype for Business Server では、次の場合に備え、任意の Web サーバー証明書をサーバー間認証の証明書として使用できます。
  
- 証明書の [Subject] (サブジェクト) フィールドに SIP ドメインの名前が含まれている。
    
- これと同じ証明書がすべてのフロントエンド サーバーで OAuthTokenIssuer 証明書として構成されている。
    
- 証明書の長さが 2,048 ビット以上。
    
Skype for Business Server のサーバー間認証証明書の詳細については、「Skype [for Business Server](../../manage/authentication/assign-a-server-to-server-certificate.md)へのサーバー間認証証明書の割り当て」を参照してください。
  
証明書が割り当てられた後、証明書の自動検出サービスを構成Exchange Server。 このExchange Server、自動検出サービスはユーザー プロファイルを構成し、ユーザーがシステムにログオンするときに Exchange サービスへのアクセスを提供します。 ユーザーが autodiscover サービスに電子メール アドレスとパスワードを入力すると、このサービスからユーザーへ次の情報が提供されます。
  
- 内部接続と外部接続の両方に関する接続Exchange Server。
    
- ユーザーのメールボックス サーバーの場所。
    
- 空き時間情報、ユニファイド メッセージング、およびオフライン アドレス帳などの Outlook 機能の URL。
    
- Outlook Anywhere のサーバー設定。
    
Skype for Business Server と自動検出サービスを統合する前に、自動検出サービスをExchange Server。 自動検出サービスが構成されているかどうかを確認するには、Exchange Server 管理シェルから次のコマンドを実行し、AutoDiscoverServiceInternalUri プロパティの値を確認します。
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

この値が空白の場合、autodiscover サービスに URI を割り当てる必要があります。 通常、この URI は次のように表示されます。 https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
autodiscover の URI は、次のようなコマンドを実行することによって割り当てられます。
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

自動検出サービスの詳細については、「自動検出サービス」 [を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=268542)。
  
自動検出サービスの構成が完了したら、Skype for Business Server の OAuth 構成設定を変更する必要があります。これにより、Skype for Business Server は自動検出サービスの場所を確認できます。 Skype for Business Server の OAuth 構成設定を変更するには、Skype for Business Server 管理シェル内から次のコマンドを実行します。 このコマンドを実行する場合は、必ず Exchange Server で実行されている自動検出サービスの URI を指定し **、autodiscover.svc** を使用して **autodiscover.xml** ではなくサービスの場所 (サービスで使用される XML ファイルを指します) をポイントするようにします。
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 前のコマンドの Identity パラメーターは省略可能です。これは、Skype for Business Server では OAuth 構成設定のグローバル コレクションを 1 つしか持てないからです。 特に、この少し簡単なコマンドを使用して自動検出 URL を構成できます。 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> OAuth というテクノロジは、多くの大手 Web サイトで使用されている標準的な認証プロトコルです。OAuth では、ユーザーの資格情報とパスワードがコンピューター間で渡されることはありません。その代わりに、セキュリティ トークンの交換に基づいて認証と承認が行われます。これらのトークンによって、特定のリソースのセットに対する特定の時間のアクセスが許可されます。 
  
自動検出サービスの構成に加えて、サービスの DNS レコードを作成して、サービスをポイントExchange Server。 たとえば、自動検出サービスが autodiscover.litwareinc.com にある場合は、Exchange Server の完全修飾ドメイン名 (atl-exchange-001.litwareinc.com など) に解決される autodiscover.litwareinc.com の DNS レコードを作成する必要があります。
  
Skype for Business Server と Exchange Online を統合する場合、次の手順はオンプレミスの [Skype for Business Server](../../deploy/integrate-with-exchange-server/outlook-web-app.md)と Outlook Web App の間の統合の構成です。それ以外の場合は [、「Skype for Business Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)と Exchange Server の統合」を参照してください。
  
## <a name="feature-support"></a>機能のサポート
<a name="feature_support"> </a>

>[!Important]
> Skype for Business Online は、サービスを含む以下の Exchange 統合がサポートされなくなった後、2021 年 7 月 31 日に廃止されます。

次の表に、Exchange と Skype for Business のオンラインまたはオンプレミスのさまざまな組み合わせでサポートされる機能の詳細を示します。
  
||**Exchange 2016/2013/2010 (オンプレミス) + Skype for Business Server (オンプレミス)**|**Exchange Online + Skype for Business Server (オンプレミス)**|**Exchange 2010 (オンプレミス) + Skype for Business Online**|**Exchange 2016/2013 (オンプレミス) + Skype for Business Online**|**Exchange Online + Skype for Business Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook でのプレゼンス  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook 電子メールからの IM、PSTN 通話、Skype 通話またはビデオ通話による応答  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook を使用してオンライン会議をスケジュールおよび参加する  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook Web App でのプレゼンス  <br/> |Y  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|OWA 電子メールからの IM、PSTN 通話、Skype 通話またはビデオ通話による応答  <br/> |Y  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|会議を通じてオンライン会議をスケジュールOutlook Web App  <br/> |Y  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|モバイル クライアントでの IM/プレゼンス  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|モバイル クライアントでオンライン会議に参加する  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook 予定表の空き時間情報に基づいて状態を公開する  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|連絡先リスト (統合連絡先ストア経由)  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|高解像度の連絡先の写真 (Lync 2013 または Skype for Business クライアントが最低限必要です。 LWA、モバイル アプリ、Lync 2010、Lync for Mac、その他の古いクライアントではサポートされていません)。  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |×  <br/> |Y  <br/> |Y  <br/> |
|会議の委任  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|不明な会話の履歴と通話ログがユーザーの Exchange メールボックスに書き込まれる  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Exchange でのコンテンツのアーカイブ (IM および会議)  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|アーカイブされたコンテンツを検索する  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|Exchange UM ボイス メール  <br/> |Y  <br/> |Y  <br/> |×  <br/> |×  <br/> |×  <br/> |
|サーバー側の会話履歴  <br/> |Y  <br/> |Y  <br/> |×  <br/> |Y  <br/> |Y  <br/> |

> [!NOTE]
> There is a Cloud Voicemail service which is supported for Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015, and Lync Server 2013.
> 

## <a name="see-also"></a>関連項目
<a name="feature_support"> </a>

[オンプレミスの Skype for Business Server と組織の間の統合をOutlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Skype for Business Online とオンプレミスの Exchange の間の OAuth の構成](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Skype for Business Server と Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Exchange Server 2013 と Lync Server 2013、Skype for Business Online、または Lync Server 2013 ハイブリッド展開を統合する方法](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Skype for Business Server および Microsoft Exchange Server でパートナー アプリケーションを構成する](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
