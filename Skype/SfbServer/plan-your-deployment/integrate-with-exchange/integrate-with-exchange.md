---
title: Skype for Business と Exchange の統合の計画
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: '概要: ビジネスのサーバー 2015 2016 の Exchange Server や Exchange Server 2013 の Skype を統合する方法の詳細については、このトピックを確認します。'
ms.openlocfilehash: 3c71509fc05ecabdf34f1d6ce8ec4f1a7af523be
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Skype for Business と Exchange の統合の計画
 
**の概要:** ビジネス サーバーの 2015 2016 の Exchange Server や Exchange Server 2013 の Skype を統合する方法の詳細については、このトピックを確認します。
  
Skype ビジネス サーバー 2015 と Exchange Server を統合すると、前に Exchange Server およびビジネス サーバー 2015 の Skype の両方がインストールされていると完全に起動して実行を行う必要があります。 
  
Exchange Server のインストール方法の詳細については、Exchange のバージョンの Exchange Server の計画と展開のドキュメントを参照してください。 
  
ビジネス サーバー 2015 の Skype をインストールする方法の詳細は、[ビジネス サーバー 2015 の Skype の導入](../../deploy/deploy.md)を参照してください。
  
サーバーが稼働するいると、割り当てる必要がありますサーバーからサーバーへの認証の証明書両方 Skype ビジネス サーバー 2015 と Exchange Server です。これらの証明書は、ビジネス サーバー 2015 と Exchange Server は、情報を交換し、互いに通信するために Skype を使用できます。 Exchange Server をインストールすると、名前の自己署名証明書認証証明書の Microsoft Exchange Server が作成します。 Exchange Server でサーバーからサーバーへの認証にはローカル コンピューターの証明書ストアに、この証明書を使用してください。 Exchange Server で証明書を割り当てる方法の詳細は、[メール フローの構成とクライアントのアクセス](https://go.microsoft.com/fwlink/p/?LinkId=268540)を参照してください。
  
ビジネス サーバー 2015 の Skype のとして使用できます、既存の Skype ビジネス サーバー証明書をサーバーからサーバーへの認証証明書です。など、既定の証明書は、OAuthTokenIssuer の証明書としても使用できます。 ビジネス サーバー 2015 の Skype では、サーバーからサーバーへの認証用の証明書を提供するように Web サーバー証明書を使用できます。
  
- 証明書の [Subject] (サブジェクト) フィールドに SIP ドメインの名前が含まれている。
    
- これと同じ証明書がすべてのフロントエンド サーバーで OAuthTokenIssuer 証明書として構成されている。
    
- 証明書の長さが 2,048 ビット以上。
    
ビジネス サーバー 2015 の Skype のサーバーからサーバーへの認証の証明書に関する詳細については、 [Skype のビジネス サーバー 2015 にサーバーからサーバーへの認証証明書の割り当て](../../manage/authentication/assign-a-server-to-server-certificate.md)を参照してください。
  
証明書が割り当てられると、Exchange Server の自動検出サービスを構成する必要がありますし。 Exchange Server では、自動検出サービスは、ユーザー プロファイルを構成し、ユーザーがシステムにログオンすると、Exchange サービスへのアクセスを提供します。 ユーザーが autodiscover サービスに電子メール アドレスとパスワードを入力すると、このサービスからユーザーへ次の情報が提供されます。
  
- Exchange Server への内部および外部の両方の接続の接続情報です。
    
- ユーザーのメールボックス サーバーの場所です。
    
- 空き時間情報、ユニファイド メッセージング、およびオフライン アドレス帳などの Outlook 機能の URL。
    
- Outlook Anywhere のサーバー設定。
    
ビジネス サーバー 2015 と Exchange Server の Skype を統合する前に、自動検出サービスを構成する必要があります。 Exchange Server 管理シェルから次のコマンドを実行して AutoDiscoverServiceInternalUri プロパティの値をチェックするには、自動検出サービスが構成されているかどうかを確認することができます。
  
```
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

この値が空白の場合、autodiscover サービスに URI を割り当てる必要があります。 通常この URI は次のようになります。https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
autodiscover の URI は、次のようなコマンドを実行すると割り当てられます。
  
```
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

自動検出サービスについての詳細は、[自動検出サービスを理解する](https://go.microsoft.com/fwlink/p/?LinkId=268542)を参照してください。
  
ビジネス サーバー OAuth 構成設定の Skype を変更する必要がありますし、自動検出サービスの構成が完了した後これにより、その Skype をビジネスのサーバーの自動検出サービスの場所を知っていること。 ビジネス サーバー 2015 の Skype の OAuth 構成設定を変更するには、ビジネス サーバー管理シェルの Skype 内で次のコマンドを実行します。 このコマンドを実行するときは必ず、Exchange Server では、上で実行する自動検出サービスへの URI を指定することと、 **autodiscover.svc**を使用して、 **autodiscover.xml** (これは XML ファイルを指すのではなくサービスの場所をポイントすることサービスを使用)。
  
```
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> 上記のコマンドの Id パラメーターは省略可能です。Skype ビジネス サーバーだけでは、OAuth 構成設定のグローバル コレクションが 1 つにするためです。 特に、つまり、このわずかに簡単なコマンドを使用して自動検出 URL を構成することができます。 
  
> [!NOTE]
> セット-CsOAuthConfiguration-ExchangeAutodiscoverUrl"https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
  
> [!NOTE]
> OAuth というテクノロジは、多くの大手 Web サイトで使用されている標準的な認証プロトコルです。OAuth では、ユーザーの資格情報とパスワードがコンピューター間で渡されることはありません。その代わりに、セキュリティ トークンの交換に基づいて認証と承認が行われます。これらのトークンによって、特定のリソースのセットに対する特定の時間のアクセスが許可されます。 
  
自動検出サービスを構成するだけでなくも、Exchange Server を指しているサービス用の DNS レコードを作成する必要があります。 たとえば、autodiscover.litwareinc.com で、自動検出サービスがある場合必要 autodiscover.litwareinc.com (たとえば、Exchange Server の完全修飾ドメイン名を解決するための DNS レコードを作成するにはatl の交換-001.litwareinc.com)。
  
[ビジネス サーバー 2015 と Outlook Web App の設置型の Skype の間の統合の構成](../../deploy/integrate-with-exchange-server/outlook-web-app.md)で、次の手順は、ビジネスのサーバーで Exchange のオンラインの Skype を統合する場合、それ以外の場合のビジネス サーバー 2015 の統合の Skype の[を参照してください。Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)です。
  
## <a name="feature-support"></a>機能のサポート
<a name="feature_support"> </a>

次の表では、Exchange およびビジネス用の Skype のオンラインのまたは施設内でのさまざまな組み合わせでサポートされる機能について説明します。
  
||**(設置型) の Exchange 2016、2013/2010 + (設置型) でのビジネス サーバー 2015 の Skype**|**Exchange オンライン + (設置型) でのビジネス サーバー 2015 の Skype**|**(設置型) に Exchange 2010 + Skype のオンライン ビジネス**|**Exchange 2016/2013(on premises) + Skype のオンライン ビジネス**|**Exchange オンライン + Skype のオンライン ビジネス**|
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
|連絡先の写真を高解像度 (Lync 2013 の必要がありますか最低限のビジネス クライアント用の Skype です。 LWA、モバイル アプリ、Lync 2010、Lync for Mac、その他の古いクライアントではサポートされない)  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |
|会議の委任  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|不在着信の会話の履歴とログの呼び出しは、ユーザーの exchange メールボックスに書き込まれます。  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|Exchange でのコンテンツのアーカイブ (IM および会議)  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|アーカイブされたコンテンツの検索  <br/> |Y (Exchange 2016/2013 が必要)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Exchange UM ボイス メール  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |Y  <br/> |
|サーバー側の会話履歴  <br/> |Y  <br/> |Y  <br/> |N  <br/> |Y  <br/> |Y  <br/> |
   
## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。
<a name="feature_support"> </a>

#### 

[統合ビジネス サーバー 2015 の Skype を設置し、Outlook Web App の構成します。](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[設置型のビジネスのオンラインの Skype と Exchange との間の OAuth を構成します。](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Skype をビジネス サーバー 2015 が Exchange Server との統合します。](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Lync Server 2013、Skype のビジネス オンライン、または Lync Server 2013 ハイブリッド展開を使用して Exchange Server 2013 を統合する方法](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[ビジネス サーバー 2015 と Microsoft Exchange Server の Skype のパートナーのアプリケーションを構成します。](https://go.microsoft.com/fwlink/p/?LinkId=746495)

