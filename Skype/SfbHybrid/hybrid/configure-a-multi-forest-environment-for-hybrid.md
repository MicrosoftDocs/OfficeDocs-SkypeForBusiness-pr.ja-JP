---
title: リソース フォレスト トポロジの展開
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 次のセクションでは、ハイブリッド シナリオで機能を提供するために、リソース/ユーザー フォレスト モデルに複数のフォレストがある環境を構成する方法について説明します。
ms.openlocfilehash: d622b225c03002e96c7f613a25d31fc047a52b5d8eb751364c62e9ad608d3edd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277452"
---
# <a name="deploy-a-resource-forest-topology"></a>リソース フォレスト トポロジの展開

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
次のセクションでは、ハイブリッド シナリオで機能を提供するために、リソース/ユーザー フォレスト モデルに複数のフォレストがある環境を構成する方法について説明します。 
  
![ハイブリッド用マルチフォレスト環境](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>トポロジの要件

複数のユーザー フォレストがサポートされています。 以下の点にご注意ください。 
    
- ハイブリッド構成でサポートされているバージョンの Lync Server および Skype for Business Serverについては、「ハイブリッド接続の計画[」を参照してください](plan-hybrid-connectivity.md)。
    
- Exchange Serverは、1 つ以上のフォレストに展開できます。このフォレストに含まれるフォレストが含まれている場合と含Skype for Business Server。 最新の累積的な更新プログラムが適用されている必要があります。
    
- Exchange Server との共同存在の詳細については、「Skype for Business と Exchange を統合する計画」の「機能サポート」を[参照してください](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)。 [](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)
    
  
## <a name="user-homing-considerations"></a>ユーザーのホーミングに関する考慮事項

Skype for Businessユーザーは、オンプレミスまたはオンラインExchangeを持つ可能性があります。 Teamsユーザーは、最適なエクスペリエンスExchange Onlineを使用する必要があります。ただし、これは必須ではありません。 Exchangeい場合は、オンプレミスのデータをSkype for Businessする必要はありません。
  
## <a name="configure-forest-trusts"></a>フォレストの信頼を構成する

リソース フォレスト トポロジでは、Skype for Business Serverをホストするリソース フォレストは、アクセスするユーザーのアカウントを含む各アカウント フォレストを信頼する必要があります。 

複数のユーザー フォレストがある場合は、フォレスト間認証を有効にするには、これらのフォレストの信頼ごとに Name Suffix Routing が有効になっている必要があります。 手順については、「フォレストの [信頼の管理」を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772440(v=ws.11))。 

別のフォレストExchange Server展開し、Exchange が Skype for Business ユーザーに機能を提供している場合は、Exchange をホストするフォレストホスト Skype for Business Server を信頼する必要があります。 たとえば、アカウント フォレストExchange展開されている場合は、アカウントとフォレスト間の 2 Skype for Business信頼が必要です。
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>アカウントをフォレスト ホスティング サーバーに同期Skype for Business

1 Skype for Business Server (リソース フォレスト) に展開されているが、1 つ以上の他のフォレスト (アカウント フォレスト) のユーザーに機能を提供すると仮定します。 この場合、他のフォレスト内のユーザーは、展開されているフォレスト内の無効なユーザー Skype for Business Serverする必要があります。

アカウント フォレストから展開されているフォレストにユーザーをプロビジョニングおよび同期するには、Microsoft Identity Manager などの ID 管理製品を使用Skype for Business Server必要があります。 ユーザーは、無効なユーザー オブジェクトとしてホストしているSkype for Business Serverに同期する必要があります。 ユーザーは Active Directory 連絡先オブジェクトとして同期できません。この場合、Azure Active Directory Connectが Azure AD に適切に同期され、Skype。
  
複数フォレスト構成に関係なく、フォレスト ホスト Skype for Business Server同じフォレストに存在する有効なユーザーに機能を提供できます。
  
適切な ID 同期を取得するには、次の属性を同期する必要があります。 
  
|**ユーザー フォレスト**|**リソース フォレスト**|
|:-----|:-----|
|選択したアカウント リンク属性  <br/> |選択したアカウント リンク属性  <br/> |
|mail  <br/> |mail  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
選択 [したアカウント リンク属性](/azure/active-directory/hybrid/plan-connect-design-concepts) がソース アンカーとして使用されます。 使用する別の不変属性がある場合は、その属性を使用できます。AAD 要求の構成中AD FS クレーム ルールを編集し、属性をConnectしてください。
  
フォレスト間で UPN を同期しない。 複数のフォレストで同じ UPN を使用できないので、ユーザー フォレストごとに一意の UPN を使用する必要があります。 その結果、UPN を同期するか、同期しないかの 2 つの可能性があります。 
  
- 各ユーザー フォレストの一意の UPN がリソース フォレスト内の関連付けられた無効なオブジェクトに同期されていない場合、少なくとも最初のサインイン試行でシングル サインオン (SSO) が壊れます (ユーザーがパスワードを保存するオプションを選択した場合)。 このクライアントSkype for Business、SIP/UPN 値は同じと仮定します。 このシナリオの SIP アドレスは user@company.com ですが、ユーザー フォレスト内の有効なオブジェクトの UPN は実際には user@contoso.company.com なので、最初のログイン試行は失敗し、ユーザーは資格情報の入力を求めるメッセージが表示されます。 正しい UPN を入力すると、ユーザー フォレスト内のドメイン コントローラーに対して認証要求が完了し、サインインが成功します。
    
- 各ユーザー フォレストの一意の UPN がリソース フォレスト内の関連付けられた無効なオブジェクトに同期されている場合、FS 認証AD失敗します。 一致するルールは、リソース フォレスト内のオブジェクトの UPN を検索します。これは無効にされ、認証に使用できません。 
    
## <a name="create-a-microsoft-365-organization"></a>組織をMicrosoft 365する

展開で使用する組織Microsoft 365準備する必要があります。 詳細については、「サブスクリプション、ライセンス、アカウント、および Microsoft のクラウド 製品のテナント」 [を参照してください](/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)。 
  
## <a name="configure-active-directory-federation-services"></a>Active Directory フェデレーション サービスの構成

テナントを作成したら、各ユーザー フォレストで Active Directory フェデレーション サービス (AD FS) を構成する必要があります。 これは、フォレストごとに一意の SIP アドレスと SMTP アドレスとユーザー プリンシパル名 (UPN) を持っている必要があります。 AD FS はオプションで、シングル サインオン (SSO) を取得するためにここで使用されます。 DirSync with Password Sync もサポートされ、FS の代ADできます。 
  
SIP/SMTP と UPN が一致する展開だけがテストされました。 SIP/SMTP/UPN が一致しない場合、統合や SSO の問題など、機能Exchange低下する可能性があります。 
  
各フォレストのユーザーに一意の SIP/SMTP/UPN を使用しない限り、FS の展開場所に関係なく、SSO の問題AD発生します。 
  
- AD FS ファームが各ユーザー フォレストに展開されているリソース/ユーザー フォレスト間の一方通行または 2 ウェイの信頼は、すべてのユーザーが共通の SIP/SMTP ドメインを共有しますが、ユーザー フォレストごとに固有の UPN を共有します。 
    
- AD FS ファームがリソース フォレストにのみ展開されているリソース/ユーザー フォレスト間の 2 つの方法の信頼は、すべてのユーザーが共通の SIP/SMTP ドメインを共有しますが、ユーザー フォレストごとに固有の UPN を共有します。 
    
各ユーザー フォレストAD FS ファームを配置し、フォレストごとに一意の SIP/SMTP/UPN を使用することで、両方の問題を解決します。 認証の試行中に、特定のユーザー フォレスト内のアカウントだけが検索され、一致します。 これにより、よりシームレスな認証プロセスが提供されます。 
  
この展開は、FS の R2 Windows Server 2012標準AD展開し、続行する前に動作する必要があります。 手順については[、「FS 2012 R2 for ADインストール方法」を参照Microsoft 365。](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx) 
  
展開後、前に選択したソース アンカーと一致するクレーム ルールを編集する必要があります。 [AD FS MMC] の [証明書利用者信頼] で、[Microsoft 365 **ID プラットフォーム**] または [Microsoft Office 365 ID プラットフォーム]**を** 右クリックし、[クレーム ルールの編集] を **選択します**。 最初のルールを編集し、ObjectSID を **employeeNumber に変更します**。 
  
![複数フォレストの [ルールの編集] 画面](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>AAD の構成Connect

リソース フォレスト トポロジでは、リソース フォレストとアカウント フォレストの両方のユーザー属性が Azure AD に同期されている必要があります。 Microsoft では、ユーザー アカウントAD Connectが有効になっているすべてのフォレストと、ユーザー ID を含むフォレストからユーザー ID を同期してマージSkype for Business。 詳細については[、「Configure Azure AD Connect for Skype for Business」をTeams。](configure-azure-ad-connect.md)

Azure AD Connectは、アカウントフォレストとリソース フォレスト間の同期をオンプレミスで提供しない点に注意してください。 これは、前述のように、Microsoft Identity Managerまたは類似の製品を使用して構成する必要があります。
  
完了すると、Azure AD Connectがマージされ、メタバース内のオブジェクトを確認すると、次のような何かが表示されます。 
  
![マルチフォレスト Metaverse オブジェクト画面](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
緑の強調表示された属性は、Microsoft 365から結合され、黄色はユーザー フォレストから、青はリソース フォレストからの属性です。 
  
この例では、Azure AD Connect は、ユーザーからの sourceAnchor と cloudSourceAnchor と、Microsoft 365 のリソース フォレスト オブジェクト (この場合は 1101-以前に選択した employeeNumber) を識別しています。 Azure AD Connectは、このオブジェクトを上記のオブジェクトにマージできたのです。 
  
詳細については、「オンプレミス のディレクトリ[とディレクトリを統合する」を参照](/azure/active-directory/hybrid/whatis-hybrid-identity)Azure Active Directory。 
  
Azure AD Connectは、次の場合を除き、既定値を使用してインストールする必要があります。 
  
1. シングル サインイン - FS が既に展開AD動作している場合: [構成しない] **を選択します**。
    
2. Connectを追加する: すべてのドメインを追加します。
    
3. オンプレミス ディレクトリ内のユーザーを識別する: [ユーザー **ID** が複数のディレクトリに存在する] を選択し **、ObjectSID** 属性と **msExchangeMasterAccountSID 属性を選択** します。
    
4. Azure AD のユーザーを識別する: ソース アンカー: 読み取った後に選択した属性を選択する [SourceAnchor](/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute)属性の選択、 ユーザー プリンシパル名 - **userPrincipalName**。
    
5.  オプション機能: ハイブリッドを展開Exchange選択します。
    
    > [!NOTE]
    >  このエラーのみをExchange Online、CNAME リダイレクトが原因で自動検出中に OAuth エラーが発生する可能性があります。 これを修正するには、次のコマンドレットを Exchange管理シェルから実行して、自動検出 URL Skype for Business Serverする必要があります。
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  AD FS ファーム: [FS ファームに既存の Windows Server 2012 **R2** ADを使用する] を選択し、FS サーバーのAD入力します。
    
7.  ウィザードを完了し、必要な検証を実行します。
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>ハイブリッド接続を構成Skype for Business Server

ハイブリッドの構成に関するベスト プラクティスSkype for Business従います。 詳細については、「ハイブリッド接続の計画 [」および「](plan-hybrid-connectivity.md) ハイブリッド接続の [構成」を参照してください](configure-hybrid-connectivity.md)。 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>ハイブリッド接続を構成Exchange Server

必要に応じて、ハイブリッドを構成するためのベスト プラクティスExchange従います。 詳細については、「ハイブリッド展開[Exchange Serverを参照してください](/exchange/exchange-hybrid)。 
