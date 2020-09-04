---
title: Skype for Business と Exchange の統合の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: d5d2a50e3b3b376bc27a407313944a31dc1352f6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359263"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Skype for Business と Exchange の統合の計画
 
**概要:** このトピックでは、Skype for Business Server を Exchange Server 2016 または Exchange Server 2013 と統合する方法について説明します。
  
Skype for Business Server と Exchange Server を統合する前に、Exchange Server と Skype for business Server の両方が完全にインストールされ、稼働していることを確認する必要があります。 
  
Exchange Server のインストールの詳細については、使用している Exchange のバージョンの Exchange Server の計画と展開に関するドキュメントを参照してください。 
   
サーバーが稼働状態になったら、Skype for Business Server と Exchange Server の両方にサーバー間認証証明書を割り当てる必要があります。これらの証明書を使用すると、Skype for Business Server と Exchange Server が情報を交換したり、互いに通信したりすることができます。 Exchange Server をインストールすると、Microsoft Exchange Server Auth Certificate という名前の自己署名証明書が作成されます。 この証明書は、ローカルコンピューターの証明書ストアにあります。これは、Exchange Server のサーバー間認証に使用する必要があります。 Exchange Server での証明書の割り当ての詳細については、「 [Configure Mail Flow And Client Access](https://go.microsoft.com/fwlink/p/?LinkId=268540)」を参照してください。
  
Skype for Business Server の場合は、既存の Skype for Business Server 証明書をサーバー間認証証明書として使用できます。たとえば、既定の証明書を OAuthTokenIssuer 証明書として使用することもできます。 Skype for Business Server を使用すると、次のように、任意の Web サーバー証明書をサーバー間認証の証明書として使用できます。
  
- 証明書の [Subject] (サブジェクト) フィールドに SIP ドメインの名前が含まれている。
    
- これと同じ証明書がすべてのフロントエンド サーバーで OAuthTokenIssuer 証明書として構成されている。
    
- 証明書の長さが 2,048 ビット以上。
    
Skype for business Server のサーバー間認証証明書の詳細については、「 [サーバー間認証証明書を skype For Business server に割り当てる](../../manage/authentication/assign-a-server-to-server-certificate.md)」を参照してください。
  
証明書が割り当てられた後、Exchange Server で自動検出サービスを構成する必要があります。 Exchange Server では、自動検出サービスによってユーザープロファイルが構成され、ユーザーがシステムにログオンすると Exchange サービスにアクセスできるようになります。 ユーザーが autodiscover サービスに電子メール アドレスとパスワードを入力すると、このサービスからユーザーへ次の情報が提供されます。
  
- Exchange Server への内部接続と外部接続の両方の接続情報。
    
- ユーザーのメールボックスサーバーの場所。
    
- 空き時間情報、ユニファイド メッセージング、およびオフライン アドレス帳などの Outlook 機能の URL。
    
- Outlook Anywhere のサーバー設定。
    
Skype for Business Server と Exchange Server を統合するには、自動検出サービスを構成する必要があります。 Exchange Server 管理シェルから次のコマンドを実行し、AutoDiscoverServiceInternalUri プロパティの値を確認することによって、自動検出サービスが構成されているかどうかを確認できます。
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

この値が空白の場合、autodiscover サービスに URI を割り当てる必要があります。 通常、この URI は次のようになります。 https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
autodiscover の URI は、次のようなコマンドを実行することによって割り当てられます。
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

自動検出サービスの詳細については、「 [自動検出サービス](https://go.microsoft.com/fwlink/p/?LinkId=268542)」を参照してください。
  
自動検出サービスを構成したら、Skype for Business Server OAuth 構成設定を変更する必要があります。これにより、Skype for Business Server が自動検出サービスの場所を知ることができます。 Skype for business Server で OAuth 構成設定を変更するには、Skype for Business Server 管理シェルで次のコマンドを実行します。 このコマンドを実行する場合は、Exchange サーバー上で実行されている自動検出サービスへの URI を指定してください。また、 **autodiscover.xml** (サービスが使用する XML ファイルを指す) ではなく、サービスの場所を指すように**自動検出**を使用することもできます。
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 上記のコマンドの Identity パラメーターは省略可能です。これは、Skype for Business Server では、OAuth 構成設定のグローバルコレクションを1つだけ持つことができるからです。 このことは、次のような簡単なコマンドを使用して自動検出 URL を構成できることを意味します。 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> OAuth というテクノロジは、多くの大手 Web サイトで使用されている標準的な認証プロトコルです。OAuth では、ユーザーの資格情報とパスワードがコンピューター間で渡されることはありません。その代わりに、セキュリティ トークンの交換に基づいて認証と承認が行われます。これらのトークンによって、特定のリソースのセットに対する特定の時間のアクセスが許可されます。 
  
自動検出サービスの構成に加えて、Exchange サーバーをポイントするサービスの DNS レコードも作成する必要があります。 たとえば、自動検出サービスが autodiscover.litwareinc.com にある場合は、Exchange サーバーの完全修飾ドメイン名 (たとえば、atl-exchange-001.litwareinc.com) に解決される autodiscover.litwareinc.com 用の DNS レコードを作成する必要があります。
  
Skype for Business Server を Exchange Online と統合する場合は、 [オンプレミスの skype For Business server と Outlook Web App との統合を構成](../../deploy/integrate-with-exchange-server/outlook-web-app.md)する次の手順を実行します。それ以外の場合は、「 [統合 Skype for Business Server with exchange server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)」を参照してください。
  
## <a name="feature-support"></a>機能のサポート
<a name="feature_support"> </a>

>[!Important]
> Skype for Business Online は、2021年7月31日に廃止されます。次に示すサービスを含む Exchange 統合がサポートされなくなります。

次の表では、Exchange と Skype for Business のオンラインまたはオンプレミスのさまざまな組み合わせでサポートされる機能について詳しく説明します。
  
||**Exchange 2016/2013/2010 (オンプレミス) + Skype for Business Server (オンプレミス)**|**Exchange Online + Skype for Business Server (オンプレミス)**|**Exchange 2010 (オンプレミス) + Skype for Business Online**|**Exchange 2016/2013 (オンプレミス) + Skype for Business Online**|**Exchange Online + Skype for Business Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Outlook でのプレゼンス  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook メールからの IM、PSTN 通話、Skype 通話、またはビデオ通話による応答  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook を使用してオンライン会議のスケジュールを設定して参加する  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook Web App でのプレゼンス  <br/> |Y  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|OWA メールからの IM、PSTN 通話、Skype 通話、またはビデオ通話による応答  <br/> |Y  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|Outlook Web App を使用したオンライン会議のスケジュールと参加  <br/> |Y  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|モバイルクライアントでの IM/プレゼンス  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|モバイルクライアントでのオンライン会議への参加  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Outlook 予定表の空き時間情報に基づく状態の公開  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|連絡先リスト (統合連絡先ストア経由)  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|高解像度の連絡先写真 (Lync 2013 または Skype for Business クライアントが最低限必要です。 LWA、モバイルアプリ、Lync 2010、Lync for Mac、その他の以前のクライアントではサポートされていません。  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |×  <br/> |Y  <br/> |Y  <br/> |
|会議の委任  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|不在着信した会話の履歴と通話ログはユーザーの exchange メールボックスに書き込まれる  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Exchange のアーカイブコンテンツ (IM および会議)  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|アーカイブされたコンテンツの検索  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |×  <br/> |×  <br/> |Y  <br/> |
|Exchange UM ボイスメール  <br/> |Y  <br/> |Y  <br/> |×  <br/> |×  <br/> |×  <br/> |
|サーバー側の会話履歴  <br/> |Y  <br/> |Y  <br/> |×  <br/> |Y  <br/> |Y  <br/> |

> [!NOTE]
> Skype for Business Online、Skype for Business Server 2019、Skype for Business Server 2015、Lync Server 2013 でサポートされているクラウドボイスメールサービスがあります。
> 

## <a name="see-also"></a>関連項目
<a name="feature_support"> </a>

[オンプレミスの Skype for Business Server と Outlook Web App 間の統合を構成する](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[オンプレミスの Skype for Business Online と Exchange 間で OAuth を構成する](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Skype for Business Server と Exchange Server の統合](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Exchange Server 2013 を Lync Server 2013、Skype for Business Online、または Lync Server 2013 ハイブリッド展開と統合する方法](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Skype for Business Server と Microsoft Exchange Server でのパートナーアプリケーションの構成](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
