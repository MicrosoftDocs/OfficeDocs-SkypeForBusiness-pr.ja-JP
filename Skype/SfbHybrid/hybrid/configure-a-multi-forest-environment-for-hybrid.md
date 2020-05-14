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
description: 次のセクションでは、ハイブリッドシナリオで Skype for Business 機能を提供するために、リソース/ユーザーフォレストモデルに複数のフォレストがある環境を構成する方法について説明します。
ms.openlocfilehash: cf3a162001756661afd0f204e9968713d9db0f5b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221481"
---
# <a name="deploy-a-resource-forest-topology"></a>リソース フォレスト トポロジの展開
 
次のセクションでは、ハイブリッドシナリオで Skype for Business 機能を提供するために、リソース/ユーザーフォレストモデルに複数のフォレストがある環境を構成する方法について説明します。 
  
![ハイブリッドの複数フォレスト環境](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>トポロジの要件

複数のユーザーフォレストがサポートされています。 以下の点にご注意ください。 
    
- ハイブリッド構成でサポートされている Lync Server および Skype for Business Server のバージョンの[要件](plan-hybrid-connectivity.md#server-version-requirements)については、「 [Plan Hybrid connectivity In Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md)」を参照してください。
    
- Exchange Server は1つ以上のフォレストに展開できます。これには、Skype for Business Server を含むフォレストを含めることができる場合とできない場合があります。 最新の累積更新プログラムが適用されていることを確認します。
    
- オンプレミスとオンラインのさまざまな組み合わせに関するサポートの条件と制限を含む、Exchange Server との共存の詳細については、「 [Plan to a Skype For business And Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)」の「[機能のサポート](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)」を参照してください。
    
  
## <a name="user-homing-considerations"></a>ユーザーのホームの考慮事項

オンプレミスに所属する Skype for Business ユーザーは、オンプレミスまたはオンラインの Exchange を持つことができます。 Skype for Business Online ユーザーは、Exchange Online を使用して最適な環境を実現する必要があります。ただし、これは必須ではありません。 どちらの場合も、Skype for Business を実装するために、オンプレミスの Exchange が必要になることはありません。
  
## <a name="configure-forest-trusts"></a>フォレストの信頼を構成する

リソースフォレストのトポロジでは、Skype for Business Server をホストするリソースフォレストは、それにアクセスするユーザーアカウントを含む各アカウントフォレストを信頼する必要があります。 複数のユーザーフォレストが存在する場合、フォレスト間認証を有効にするには、これらのフォレストの信頼のそれぞれで名前サフィックスルーティングが有効になっていることが重要です。 手順については、「[フォレストの信頼を管理する](https://technet.microsoft.com/library/cc772440.aspx)」を参照してください。 別のフォレストに展開されている Exchange サーバーを使用している場合、Skype for Business ユーザー向けの機能を提供するには、Exchange をホストするフォレストが Skype for Business Server をホストしているフォレストを信頼している必要があります。 たとえば、Exchange がアカウントフォレストに展開されている場合、この構成では、アカウントと Skype for Business の両方のフォレストの間に双ウェイの信頼が必要になります。
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Skype for Business をホストするフォレストにアカウントを同期する

Skype for Business Server が1つのフォレスト (リソースフォレスト) に展開されているが、1つ以上の他のフォレスト (アカウントフォレスト) でユーザーに機能を提供する場合は、他のフォレスト内のユーザーが、Skype for Business Server が展開されているフォレスト内の無効なユーザーオブジェクトとして表される必要があります。 Microsoft Identity Manager などの id 管理製品を展開して、アカウントフォレストから Skype for Business Server が展開されているフォレストにユーザーをプロビジョニングおよび同期するように構成する必要があります。 ユーザーが、Skype for Business Server をホストしているフォレストの無効なユーザーオブジェクトとして同期されている必要があります。 Azure Active Directory Connect は、Skype で使用するために、連絡先を Azure AD に正しく同期しないため、ユーザーを Active Directory 連絡先オブジェクトとして同期することはできません。
  
複数フォレストの構成に関係なく、Skype for Business Server をホストしているフォレストは、同じフォレストに存在する有効なユーザーにも機能を提供できます。
  
適切な id 同期を取得するには、次の属性を同期する必要があります。 
  
|**ユーザーフォレスト**|**リソースフォレスト**|
|:-----|:-----|
|選択されたアカウントリンク属性  <br/> |選択されたアカウントリンク属性  <br/> |
|mail  <br/> |mail  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-の場合は、Sid  <br/> |
   
選択された[アカウントリンク属性](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)がソースアンカーとして使用されます。 使用する必要がある、別の不変の属性がある場合は、これを行うことができます。AD FS の要求ルールを編集して、AAD Connect 構成中に属性を選択する必要があります。
  
フォレスト間で Upn を同期しません。 テスト中に、複数のフォレストで同じ UPN を使用できないため、各ユーザーフォレストに一意の UPN を使用する必要があることがわかりました。 その結果、UPN を同期したり、同期したりしないようにするための2つの可能性が提供されました。 
  
- 各ユーザーフォレストの一意の UPN がリソースフォレスト内の関連付けられた無効なオブジェクトと同期されていない場合、シングルサインオン (SSO) は、少なくとも初回のサインイン (ユーザーがパスワードを保存するオプションを選択したと仮定) に対して中断されます。 Skype for Business クライアントでは、SIP/UPN の値が同じであると仮定します。 このシナリオの SIP アドレスは user@company.com ですが、ユーザーフォレスト内の有効なオブジェクトの UPN は事実上 user@contoso.company.com ので、最初のログイン試行は失敗し、ユーザーは資格情報の入力を求められます。 正しい UPN を入力すると、ユーザーフォレスト内のドメインコントローラーに対して認証要求が完了し、サインインが成功します。
    
- 各ユーザーフォレストからの一意の UPN がリソースフォレスト内の関連付けられている無効なオブジェクトと同期されている場合、AD FS 認証は失敗します。 照合ルールは、無効にされ、認証に使用できなかったリソースフォレスト内のオブジェクトの UPN を検索します。 
    
## <a name="create-a-microsoft-365-or-office-365-organization"></a>Microsoft 365 または Office 365 組織を作成する

次に、展開で使用するために Microsoft 365 または Office 365 組織を準備する必要があります。 詳細については、「 [Microsoft のクラウドサービスのサブスクリプション、ライセンス、アカウント、およびテナント](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)」を参照してください。 
  
## <a name="configure-active-directory-federation-services"></a>Active Directory フェデレーションサービスを構成する

テナントが作成されたら、各ユーザーフォレストで Active Directory フェデレーションサービス (AD FS) を構成する必要があります。 これは、フォレストごとに一意の SIP および SMTP アドレスとユーザープリンシパル名 (UPN) があることを前提としています。 AD FS はオプションであり、シングルサインオン (SSO) を取得するためにここで使用されます。 パスワード同期を使用する DirSync もサポートされており、AD FS の代わりに使用することもできます。 
  
SIP/SMTP および Upn が一致する展開のみがテストされました。 対応する SIP/SMTP/Upn がないと、Exchange 統合および SSO の問題などの機能が低下する可能性があります。 
  
各フォレストのユーザーに対して一意の SIP/SMTP/UPN を使用しない限り、AD FS が展開されている場所に関係なく、SSO の問題が発生する可能性があります。 
  
- AD FS ファームが各ユーザーフォレストに展開されているリソース/ユーザーフォレスト間の一方向または双方向の信頼。すべてのユーザーは共通の SIP/SMTP ドメインを共有しますが、ユーザーフォレストごとに一意の UPN を共有します。 
    
- リソースフォレスト内にのみ展開された AD FS ファームを使用した、リソース/ユーザーフォレスト間の双方向の信頼。すべてのユーザーは共通の SIP/SMTP ドメインを共有しますが、ユーザーフォレストごとに一意の UPN を共有します。 
    
各ユーザーフォレストに AD FS ファームを配置し、フォレストごとに一意の SIP/SMTP/UPN を使用することで、両方の問題を解決します。 認証の試行中に、特定のユーザーフォレスト内のアカウントのみが検索され、照合されます。 これは、よりシームレスな認証プロセスを提供するのに役立ちます。 
  
これは、Windows Server 2012 R2 AD FS の標準的な展開であり、続行する前に動作する必要があります。 手順については、「 [Microsoft 365 または Office 365 の AD FS 2012 R2 をインストールする方法](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)」を参照してください。 
  
いったん展開したら、前に選択したソースアンカーと一致するようにクレームルールを編集する必要があります。 AD FS MMC の [証明書利用者信頼] の下で、[ **microsoft 365 Identity platform** ] または [ **Microsoft Office 365 Identity platform**] を右クリックし、[**要求規則の編集**] を選択します。 最初のルールを編集し、ObjectSID を**employeeNumber**に変更します。 
  
![複数フォレストの [ルールの編集] 画面](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>AAD 接続を構成する

リソースフォレストのトポロジでは、リソースフォレストとすべてのアカウントフォレストのユーザー属性を Azure AD に同期する必要があります。 最も簡単にこれを行うには、Azure AD Connect を使用して、有効になっているユーザーアカウントと Skype for Business が含まれているフォレストの*すべて*のフォレストから、ユーザー id を同期させ、結合するようにします。 詳細については、「 [Skype for business および Teams 用に AZURE AD Connect を構成する](configure-azure-ad-connect.md)」を参照してください。

AAD Connect では、アカウントフォレストとリソースフォレスト間でのオンプレミスの同期は提供されないことに注意してください。 これは、前に説明したように、Microsoft Identity Manager または同様の製品を使用して個別に構成する必要があります。
  
完了後に AAD Connect が結合されると、metaverse 内のオブジェクトを調べると、次のような内容が表示されます。 
  
![複数フォレストの Metaverse オブジェクト画面](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
緑色で強調表示されている属性は、Microsoft 365 または Office 365、ユーザーフォレストから黄色、青がリソースフォレストからマージされました。 
  
これはテストユーザーなので、この1101場合は以前に選択されている employeeNumber である、Microsoft 365 または Office 365 から、cloudSourceAnchor とリソースフォレストオブジェクトを AAD Connect で識別していることを確認できます。 その後、このオブジェクトを上記の表示に結合することができました。 
  
詳細については、「[オンプレミスのディレクトリと Azure Active Directory を統合する](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)」を参照してください。 
  
AAD Connect は、次の点を除き、既定の設定を使用してインストールする必要があります。 
  
1. AD FS が既に展開および稼働しているシングルサインイン。 [**構成しない**] を選択します。
    
2. ディレクトリを接続します。すべてのドメインを追加します。
    
3. オンプレミスディレクトリでユーザーを識別する: [**複数のディレクトリにユーザー id が存在**する] を選択し、 **ObjectSID**属性と**msExchangeMasterAccountSID**属性を選択します。
    
4. [Azure AD でユーザーを識別する: ソースアンカー]:[適切な sourceanchor 属性](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute)(ユーザープリンシパル名- **UserPrincipalName**) を選択した後に選択した属性を選択します。
    
5.  オプション機能: Exchange ハイブリッドが展開されているかどうかを選択します。
    
    > [!NOTE]
    >  Exchange Online のみを使用している場合は、CNAME リダイレクトにより、自動検出の際に OAuth エラーに関して問題が発生する可能性があります。 これを修正するには、Skype for Business Server 管理シェルから次のコマンドレットを実行して、Exchange 自動検出 URL を設定する必要があります。
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  AD FS ファーム: [**既存の Windows Server 2012 R2 AD fs ファームを使用する**] を選択し、ad fs サーバーの名前を入力します。
    
7.  ウィザードを終了し、必要な検証を実行します。
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Skype for Business Server のハイブリッド接続を構成する

Skype for Business ハイブリッドを構成するためのベストプラクティスに従います。 詳細については、「[ハイブリッド接続を計画](plan-hybrid-connectivity.md)する」および「[ハイブリッド接続を構成する](configure-hybrid-connectivity.md)」を参照してください。 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Exchange Server のハイブリッド接続を構成する

必要に応じて、Exchange ハイブリッドを構成するためのベストプラクティスに従います。 詳細については、「 [Exchange Server のハイブリッド展開](https://docs.microsoft.com/exchange/exchange-hybrid)」を参照してください。 
  
