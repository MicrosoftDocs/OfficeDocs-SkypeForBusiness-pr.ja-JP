---
title: ハイブリッド ビジネスの Skype の複数のフォレスト環境を構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 次のセクションでは、ハイブリッド シナリオでは、ビジネス機能のための Skype を提供するリソースとユーザーのフォレスト モデルでは複数のフォレストを持つ環境を構成する方法のガイダンスを提供します。
ms.openlocfilehash: 72c0a91c3a5a90b4ec83eb5f71a5601ccfb48bb1
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295363"
---
# <a name="configure-a-multi-forest-environment-for-hybrid-skype-for-business"></a>ハイブリッド ビジネスの Skype の複数のフォレスト環境を構成します。
 
次のセクションでは、ハイブリッド シナリオでは、ビジネス機能のための Skype を提供するリソースとユーザーのフォレスト モデルでは複数のフォレストを持つ環境を構成する方法のガイダンスを提供します。 
  
![ハイブリッド用のマルチ フォレスト環境](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="validate-the-forest-topology"></a>フォレストのトポロジを検証します。

複数のユーザー フォレストがサポートされます。 以下の点について留意してください。 
  
- フォレストのユーザーの 1 つまたは複数のユーザーのフォレストの展開は、Skype ビジネス サーバー用の単一の展開が必要があります。
    
- ハイブリッド構成でサポートされているバージョンの Lync Server および Skype ビジネス サーバーは、 [Skype ビジネス サーバーと Office 365 の間のハイブリッド接続の計画](plan-hybrid-connectivity.md)では、[トポロジの要件](plan-hybrid-connectivity.md#BKMK_Topology)を参照してください。
    
- ビジネス サーバーの Skype を含むフォレストを含めることはできませんが 1 つまたは複数のフォレストで Exchange Server を展開できます。 最新の累積的な更新プログラムを適用することを確認します。
    
- オンプレミスとオンラインのさまざまな組み合わせに関するサポートの条件および制限を含む、Exchange Server との共存に関する詳細については、[Plan to integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md) の「[機能のサポート](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)」を参照してください。
    
詳細については、[システム要件](../plan/system-requirements.md)を参照してください。
  
## <a name="user-homing-considerations"></a>ユーザーの所属に関する考慮事項

Skype ホーム設置型またはオンラインの Exchange を持つことができますは、施設内に置かれているビジネスのユーザーにします。 Skype オンライン ビジネスのユーザーにする必要があります Exchange Online を使用の最適なエクスペリエンスです。ただし、これは必要ではありません。 オンプレミスの Exchange は、いずれの場合もビジネス用の Skype を実装する必要はありません。
  
## <a name="configure-forest-trusts"></a>フォレストの信頼を構成します。

必要な信頼は、リソース フォレストと各ユーザー フォレストの間の双方向の推移的な信頼です。 複数のユーザー フォレストがある場合、クロス フォレスト認証を有効にするには、これらのフォレストの信頼のそれぞれに名前サフィックス ルーティングを有効にすることが重要です。 手順については、「[フォレストの信頼を管理する](https://technet.microsoft.com/en-us/library/cc772440.aspx)」を参照してください。 
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>ビジネス用の Skype をホストしているフォレストにアカウントを同期します。

フォレスト内の無効なユーザー オブジェクトとして提供するときに Skype ビジネス サーバーは 1 つのフォレスト (リソース フォレスト) の導入の機能の 1 つまたは複数の他のフォレスト (フォレストのアカウント) のユーザーに、他のフォレスト内のユーザーを表す必要がある場所の Skypeビジネス サーバーが配置されます。 Microsoft 個人情報管理など、id 管理製品では、展開およびプロビジョニングし、Skype のビジネス サーバーが展開されているフォレストにアカウントのフォレストからユーザーを同期するように構成する必要があります。 ビジネス サーバーの無効なユーザー オブジェクトとして Skype をホストしているフォレストにユーザーを同期する必要があります。 Azure Active Directory の接続は正しく同期しない連絡先 Skype で使用するための Azure AD にするため、ユーザーは、Active Directory 連絡先オブジェクトとして同期できません。
  
任意の複数のフォレスト構成に関係なく、Skype をビジネスのサーバーのホストは同じフォレスト内に存在する任意の有効なユーザーの機能も提供できます。
  
適切な ID 同期を実現するには、次の属性を同期する必要があります。 
  
|**ユーザー フォレスト**|**リソース フォレスト**|
|:-----|:-----|
|選択されたアカウント リンク属性  <br/> |選択されたアカウント リンク属性  <br/> |
|mail   <br/> |mail   <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
[選択されたアカウント リンク属性](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/)は、ソース アンカーとして使用されます。 使用する場合は、変更不可能な別の属性を使っている場合がありますこれを行います。だけに AD FS 要求ルールを編集し、AAD の接続の構成中に、属性を選択することを確認します。
  
フォレスト間で Upn が同期されない操作を行います。 複数のフォレストで同じ UPN を使用できないため、ユーザー フォレストごとに一意の UPN を使用する必要があることを、Microsoft はテスト中に確認しました。 そのため、UPN を同期する場合と同期しない場合の 2 つの可能性が提示されました。 
  
- 場合は各ユーザーのフォレストからの一意の UPN は、リソース フォレスト内の関連付けられている無効なオブジェクトに同期されませんでした、シングル サインオン (SSO) 分割されるには、少なくともサインイン試行 (ユーザーにパスワードを保存するオプションが選択されていると仮定した場合)。 ビジネス クライアント用の Skype、SIP または UPN 値が同じであることと仮定します。 このシナリオでの SIP アドレスは user@company.com ですが、ユーザー フォレスト内の有効であるオブジェクトの UPN は実際には user@contoso.company.com なので、最初のログイン試行が失敗し、ユーザーに資格情報の入力を求めるメッセージが表示されます。 正しい実際の UPN を入力すると、ユーザー フォレスト内のドメイン コントローラーに対する認証要求が完了し、サインインは成功します。
    
- 各ユーザー フォレストから一意の UPN をリソース フォレストに関連付けられている無効なオブジェクトと同期すると、AD FS 認証は失敗します。 照合ルールによりリソース フォレスト内のオブジェクトに UPN が見つかりますが、無効であるため、認証には使用できません。 
    
## <a name="create-an-office-365-tenant"></a>Office 365 テナントの作成

次に、展開で使用する Office 365 テナントをプロビジョニングする必要があります。 詳細については、[ライセンス、サブスクリプション、アカウント、およびマイクロソフトのクラウド サービスのテナント](https://docs.microsoft.com/en-us/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)を参照してください。 
  
## <a name="configure-active-directory-federation-services"></a>Active Directory フェデレーション サービスを構成します。

テナントを作成したら、各ユーザーのフォレストの Active Directory フェデレーション サービス (AD FS) を構成する必要があります。 ここでは、各フォレストに一意の SIP および SMTP アドレスと、ユーザー プリンシパル名 (UPN) があると仮定しています。 AD FS オプションは、ここではシングル サインオン (SSO) を取得します。 パスワード同期を備えた DirSync もサポートされていて、AD FS の代わりに使用することもできます。 
  
対応する SIP/SMTP および UPN がある展開のみがテストされています。 一致する SIP と SMTP、Upn がないと、Exchange の統合と SSO に関する問題などの機能を制限する可能性があります。 
  
各フォレストのユーザーの一意な SIP と SMTP と UPN を使用する場合を除き、AD FS の導入場所にかかわらず、SSO 問題にも実行できます。 
  
- AD FS ファームが各ユーザー フォレストに展開された状態での、リソース/ユーザー フォレスト間の一方向または双方向の信頼。すべてのユーザーは共通の SIP/SMTP ドメインを共有しますが、ユーザー フォレストごとに一意の UPN を共有します。 
    
- AD FS ファームがリソース フォレストのみに展開された状態での、リソース/ユーザー フォレスト間の双方向の信頼。すべてのユーザーは共通の SIP/SMTP ドメインを共有しますが、ユーザー フォレストごとに一意の UPN を共有します。 
    
AD FS ファームを各ユーザー フォレストに配置し、フォレストごとに一意の SIP/SMTP/UPN を使用することで、両方の問題が解決します。認証試行中に、特定のユーザー フォレストにあるアカウントのみが検索および照合されます。これは、よりシームレスな認証プロセスを実現するのに役立ちます。 
  
これは、Windows Server 2012 R2 AD FS の標準的な展開であり、先に進む前に正常に動作している必要があります。 手順については、「[Office 365 用 AD FS 2012 R2 をインストールする方法 (英語)](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)」を参照してください。 
  
展開が完了したら、先ほど選択したソース アンカーに一致するように要求規則を編集する必要があります。 AD FS MMC で、[依存関係者を信頼するには、 **Microsoft Office 365 Id のプラットフォーム**を右クリックし、[**要求規則の編集**] をクリックします。 最初のルールを編集し、ObjectSID を**結び**に変更します。 
  
![マルチ フォレストの [規則の編集] 画面](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>AAD Connect の構成

AAD Connect は、さまざまなフォレストの間、およびフォレストと Office 365 の間でアカウントをマージするために使用します。AAD Connect はリソース フォレストに展開することをお勧めします。複数のフォレストと Office 365 を同期できる必要がありますが、これは Dirsync ではサポートされていません。 
  
AAD Connect では、オンプレミス フォレスト間でアカウントが同期されません。AD コネクタを使用して、(FIM やそれと類似した製品により) オンプレミス フォレスト間で既に同期されているオブジェクトが読み取られます。次に、フィルター規則を利用して、メタバース内の対応する有効であるオブジェクトと無効であるオブジェクトの両方の単一表現が作成され、その単一のマージ済みオブジェクトが Office 365 にレプリケートされます。 
  
処理が完了して AAD Connect でマージされている途中にメタバースのオブジェクトを調べると、次のような画面が表示されます。 
  
![マルチ フォレストのメタバース オブジェクトの画面](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
緑色の強調表示された属性は、Office 365 からマージされた、黄色は、ユーザー フォレストから、青色のリソース フォレストからです。 
  
これは、テスト ユーザーであり、できること、sourceAnchor と、ユーザーからの cloudSourceAnchor は、AAD の接続が確認し、リソース フォレスト内のオブジェクト、Office 365 からここ 1101 は、結びが以前に選択を参照してください。 できた上の表示にこのオブジェクトをマージします。 
  
詳細については、 [Azure Active Directory と統合、設置ディレクトリ](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/)を参照してください。 
  
AAD の接続をインストールする、次の既定値を使用します。 
  
1. サインインの 1 つの AD FS が既に展開および作業:**を構成しない**を選択します。
    
2. ディレクトリの接続: すべてのドメインを追加します。
    
3. 設置ディレクトリ内のユーザーを識別する:**ユーザーの id が複数のディレクトリに存在**するかを選択し、 **ObjectSID**属性および**msExchangeMasterAccountSID**属性を選択します。
    
4. Azure AD でユーザーを識別する: ソース アンカー:[適切な sourceAnchor 属性を選択すると](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/)、ユーザー プリンシパル名が**userPrincipalName**を読んだ後に選択した属性を選択します。
    
5.  オプション機能: Exchange のハイブリッド展開があるかどうかを選択します。
    
    > [!NOTE]
    >  Exchange Online のみを使用している場合は、CNAME のリダイレクトが原因で、自動検出中に OAuth のエラーの問題が発生する可能性があります。 これを修正する、Skype からビジネス サーバー管理シェルの次のコマンドレットを実行して、Exchange の自動検出 URL を設定する必要があります。
  
    セット-CsOAuthConfiguration-ExchangeAutoDiscoverURL https://<span>autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    
6.  AD FS ファーム: [**既存の Windows Server 2012 R2 AD FS ファームを使用します**] を選択し、AD FS サーバーの名前を入力します。
    
7.  ウィザードを完了し、必要な検証を実行します。
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>ビジネス サーバー用の Skype のハイブリッド接続を構成します。

ビジネスのハイブリッドの Skype を設定するためのベスト プラクティスに従います。 詳細情報については、[ハイブリッドの接続を計画](plan-hybrid-connectivity.md)し、[ハイブリッド接続の構成](configure-hybrid-connectivity.md)を参照してください。 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>ハイブリッド接続を Exchange Server を構成します。

必要に応じて、Exchange ハイブリッドを構成するためのベスト プラクティスに従います。 詳細については、 [Exchange Server のハイブリッド展開](https://technet.microsoft.com/en-us/library/jj200581%28v=exchg.150%29.aspx)を参照してください。 
  

