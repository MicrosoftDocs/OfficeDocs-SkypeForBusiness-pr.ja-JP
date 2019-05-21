---
title: Skype for Business と Exchange の統合の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: '概要: Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 と統合する方法については、このトピックを参照してください。'
ms.openlocfilehash: f62ad2475fe17668e82b06b1b4a0f19b6a2ee7c8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297401"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Skype for Business と Exchange の統合の計画
 
**概要:** Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 と統合する方法については、このトピックを参照してください。
  
Skype for Business Server と Exchange Server を統合するには、Exchange Server と Skype for Business Server の両方が完全にインストールされ、実行されていることを確認する必要があります。 
  
Exchange Server のインストールの詳細については、使用している Exchange のバージョンの Exchange Server の計画と展開に関するドキュメントを参照してください。 
   
サーバーが起動して実行されたら、サーバーとサーバー間の認証証明書を Skype for Business Server と Exchange Server の両方に割り当てる必要があります。これらの証明書を使用すると、Skype for Business Server と Exchange Server は情報を交換したり、相互に通信したりすることができます。 Exchange Server をインストールすると、Microsoft Exchange Server 認証証明書という名前の自己署名証明書が作成されます。 この証明書はローカルコンピューターの証明書ストアに含まれているため、Exchange Server のサーバー間認証に使用する必要があります。 Exchange Server での証明書の割り当てについて詳しくは、「[メールフローとクライアントアクセスの構成](https://go.microsoft.com/fwlink/p/?LinkId=268540)」をご覧ください。
  
Skype for Business Server の場合は、既存の Skype for Business Server 証明書をサーバー間認証証明書として使うことができます。たとえば、既定の証明書を OAuthTokenIssuer 証明書として使うこともできます。 Skype for Business Server では、次のような方法で提供されるサーバー間認証用の証明書として、任意の Web サーバー証明書を使うことができます。
  
- 証明書の [Subject] (サブジェクト) フィールドに SIP ドメインの名前が含まれている。
    
- これと同じ証明書がすべてのフロントエンド サーバーで OAuthTokenIssuer 証明書として構成されている。
    
- 証明書の長さが 2,048 ビット以上。
    
Skype for Business Server 用のサーバー間認証証明書の詳細については、「[サーバー間認証証明書を skype For Business server に割り当てる](../../manage/authentication/assign-a-server-to-server-certificate.md)」を参照してください。
  
証明書が割り当てられたら、Exchange Server で自動検出サービスを構成する必要があります。 Exchange Server では、自動検出サービスによってユーザープロファイルが構成され、ユーザーがシステムにログオンしたときに Exchange サービスへのアクセスが提供されます。 ユーザーが autodiscover サービスに電子メール アドレスとパスワードを入力すると、このサービスからユーザーへ次の情報が提供されます。
  
- Exchange Server への内部および外部の接続の接続情報。
    
- ユーザーのメールボックスサーバーの場所。
    
- 空き時間情報、ユニファイド メッセージング、およびオフライン アドレス帳などの Outlook 機能の URL。
    
- Outlook Anywhere のサーバー設定。
    
Skype for Business Server および Exchange Server を統合するには、自動検出サービスを構成する必要があります。 自動検出サービスが構成されているかどうかを確認するには、Exchange Server 管理シェルから次のコマンドを実行して、AutoDiscoverServiceInternalUri プロパティの値を確認します。
  
```
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

この値が空白の場合、autodiscover サービスに URI を割り当てる必要があります。 通常、この URI は次のようになります。https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
autodiscover の URI は、次のようなコマンドを実行すると割り当てられます。
  
```
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

自動検出サービスの詳細については、「[自動検出サービス](https://go.microsoft.com/fwlink/p/?LinkId=268542)」を参照してください。
  
自動検出サービスの構成が完了したら、Skype for Business Server OAuth 構成の設定を変更する必要があります。これにより、Skype for Business Server が自動検出サービスの場所を把握することができます。 Skype for Business Server の OAuth 構成設定を変更するには、Skype for Business Server 管理シェルで次のコマンドを実行します。 このコマンドを実行する場合は、Exchange サーバーで実行されている自動検出サービスの URI を指定していることを確認し**ます**。また、自動検出を使用して、(xml ファイルを示す)**自動**検出ではなく、サービスの場所を指すようにする必要があります。サービスによって使用される):
  
```
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 上のコマンドの Identity パラメーターは省略可能です。これは、Skype for Business Server では、OAuth 構成設定のグローバルコレクションを1つだけ持つことができるためです。 これは、次のように単純なコマンドを使用して自動検出 URL を構成できることを意味します。 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "<https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc>" 
> 
> [!NOTE]
> OAuth というテクノロジは、多くの大手 Web サイトで使用されている標準的な認証プロトコルです。OAuth では、ユーザーの資格情報とパスワードがコンピューター間で渡されることはありません。その代わりに、セキュリティ トークンの交換に基づいて認証と承認が行われます。これらのトークンによって、特定のリソースのセットに対する特定の時間のアクセスが許可されます。 
  
自動検出サービスの構成に加えて、Exchange サーバーを参照するサービスの DNS レコードも作成する必要があります。 たとえば、自動検出サービスが autodiscover.litwareinc.com にある場合は、Exchange サーバーの完全修飾ドメイン名に解決される autodiscover.litwareinc.com の DNS レコードを作成する必要があります (たとえば、atl-exchange-001.litwareinc.com)。
  
Skype for Business Server を Exchange Online と統合する場合は、次の手順は[オンプレミスの skype For Business server と Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)との統合を構成することになります。それ以外の場合は、「skype For business [server を exchange と統合する」を参照してください。サーバー](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。
  
## <a name="feature-support"></a>機能のサポート
<a name="feature_support"> </a>

次の表では、Exchange および Skype for Business のオンラインまたはオンプレミスのさまざまな組み合わせでサポートされる機能について詳しく説明します。
  
||**Exchange 2016/2013/2010 (オンプレミス) + Skype for Business Server (オンプレミス)**|**Exchange Online + Skype for Business Server (オンプレミス)**|**Exchange 2010 (オンプレミス) + Skype for Business Online**|**Exchange 2016/2013 (オンプレミス) + Skype for Business Online**|**Exchange Online + Skype for Business Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook でのプレゼンス  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook の電子メールからの IM、PSTN 通話、Skype 通話、またはビデオ通話による返信  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook を使用したオンライン会議の予約と参加  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook Web App でのプレゼンス  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|OWA の電子メールからの IM、PSTN 通話、Skype 通話、またはビデオ通話による返信  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Outlook Web App を使用したオンライン会議の予約と参加  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|モバイル クライアントでの IM/プレゼンス  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|モバイル クライアントでのオンライン会議への参加  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook 予定表の空き時間情報に基づく状態の公開  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|連絡先リスト (統合連絡先ストア経由)  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|高解像度の連絡先写真 (Lync 2013 または Skype for Business クライアントが少なくとも必要です。 LWA、モバイル アプリ、Lync 2010、Lync for Mac、その他の古いクライアントではサポートされない)  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |
|会議の委任  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|不在着信した会話履歴と通話ログはユーザーの exchange メールボックスに書き込まれる  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Exchange でのコンテンツのアーカイブ (IM および会議)  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|アーカイブされたコンテンツの検索  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Exchange UM ボイス メール  <br/> |Y  <br/> |Y  <br/> |N  <br/> |N  <br/> |N  <br/> |
|サーバー側の会話履歴  <br/> |Y  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |

> [!NOTE]
> Skype for Business Online、Skype for business Server 2019、Skype for Business Server 2015、および Lync Server 2013 でサポートされているクラウドボイスメールサービスがあります。
> 

## <a name="see-also"></a>関連項目
<a name="feature_support"> </a>

[オンプレミスの Skype for Business Server と Outlook Web App との統合を構成する](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[オンプレミスの Exchange と Skype for Business Online 間での OAuth の構成](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Skype for Business Server と Exchange Server の統合](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Exchange Server 2013 を Lync Server 2013、Skype for Business Online、または Lync Server 2013 ハイブリッド展開と統合する方法](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Skype for Business Server および Microsoft Exchange Server でパートナーアプリケーションを構成する](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
