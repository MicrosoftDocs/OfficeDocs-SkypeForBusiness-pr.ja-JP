---
title: ハイブリッド ビジネスの Skype の複数のフォレスト環境を構成します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/17/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 960ab8a3-352d-4b18-bc01-55b35f30ca0d
description: 次のセクションでは、ハイブリッド シナリオでは、ビジネス機能のための Skype を提供するリソースとユーザーのフォレスト モデルでは複数のフォレストを持つ環境を構成する方法のガイダンスを提供します。
ms.openlocfilehash: ea2e650925dee8851419baca2a64d70585b19036
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-multi-forest-environment-for-hybrid-skype-for-business"></a>ハイブリッド ビジネスの Skype の複数のフォレスト環境を構成します。
 
次のセクションでは、ハイブリッド シナリオでは、ビジネス機能のための Skype を提供するリソースとユーザーのフォレスト モデルでは複数のフォレストを持つ環境を構成する方法のガイダンスを提供します。 
  
![ハイブリッド用のマルチ フォレスト環境](../../media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="validate-the-forest-topology"></a>フォレスト トポロジの検証

複数のユーザー フォレストがサポートされます。以下の点について留意してください。 
  
- 1 つのユーザー フォレストまたは複数のユーザー フォレストの展開では、Skype ビジネス サーバー用の単一の展開が必要があります。
    
- ハイブリッド構成でサポートされているバージョンの Lync Server および Skype ビジネス サーバーは、[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間のハイブリッド接続の計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)での[トポロジの要件](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_Topology)を参照してください。
    
- ビジネス サーバーの Skype を含むフォレストを含めることはできませんが 1 つまたは複数のフォレストで Exchange Server を展開できます。 最新の累積的な更新プログラムを適用することを確認します。
    
- Exchange Server との共存の詳細については、サポートを含む条件とさまざまな組み合わせでの制限の設置とオンラインで参照してください[ビジネスとの交換用 Skype を統合する計画](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)の[サポート機能](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。
    
詳細については、 [Skype のビジネス サーバー 2015 の環境の要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)を参照してください。
  
## <a name="user-homing-considerations"></a>ユーザーの所属に関する考慮事項

Skype ホーム設置型またはオンラインの Exchange を持つことができますは、施設内に置かれているビジネスのユーザーにします。 Skype オンライン ビジネスのユーザーにする必要があります Exchange Online を使用の最適なエクスペリエンスです。ただし、これは必要ではありません。 オンプレミスの Exchange は、いずれの場合もビジネス用の Skype を実装する必要はありません。
  
## <a name="configure-forest-trusts"></a>フォレストの信頼の構成

必要な信頼は、リソース フォレストと各ユーザー フォレストの間の双方向の推移的な信頼です。 複数のユーザー フォレストがある場合、クロス フォレスト認証を有効にするには、これらのフォレストの信頼のそれぞれに名前サフィックス ルーティングを有効にすることが重要です。 手順については、[フォレストの信頼を管理する](https://technet.microsoft.com/en-us/library/cc772440.aspx)を参照してください。 
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>ビジネス用の Skype をホストしているフォレストにアカウントを同期します。

フォレスト内の無効なユーザー オブジェクトとして提供するときに Skype ビジネス サーバーは 1 つのフォレスト (リソース フォレスト) の導入の機能の 1 つまたは複数の他のフォレスト (フォレストのアカウント) のユーザーに、他のフォレスト内のユーザーを表す必要がある場所の Skypeビジネス サーバーが配置されます。 Microsoft 個人情報管理など、id 管理製品では、展開およびプロビジョニングし、Skype のビジネス サーバーが展開されているフォレストにアカウントのフォレストからユーザーを同期するように構成する必要があります。 ビジネス サーバーの無効なユーザー オブジェクトとして Skype をホストしているフォレストにユーザーを同期する必要があります。 Azure Active Directory の接続は正しく同期しない連絡先 Skype で使用するための Azure AD にするため、ユーザーは、Active Directory 連絡先オブジェクトとして同期できません。
  
任意の複数のフォレスト構成に関係なく、Skype をビジネスのサーバーのホストは同じフォレスト内に存在する任意の有効なユーザーの機能も提供できます。
  
適切な ID 同期を実現するには、次の属性を同期する必要があります。 
  
|**ユーザー フォレスト**|**リソース フォレスト**|
|:-----|:-----|
|選択されたアカウント リンク属性  <br/> |選択されたアカウント リンク属性  <br/> |
|mail   <br/> |mail   <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP OriginatorSID  <br/> |
   
[アカウント リンクの属性を選択](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/)するは、元のアンカーとして使用されます。 使用したい他の不変属性がある場合は、それを使用してもかまいませんが、AAD Connect の構成時に AD FS 要求規則を編集して、その属性を選択することを忘れないでください。
  
UPN のフォレスト間で同期されません。 複数のフォレストで同じ UPN を使用できないため、ユーザー フォレストごとに一意の UPN を使用する必要があることを、Microsoft はテスト中に確認しました。 そのため、UPN を同期する場合と同期しない場合の 2 つの可能性が提示されました。 
  
-  各ユーザー フォレストの一意の UPN をリソース フォレスト内の関連付けられている無効であるオブジェクトに同期しない場合、少なくとも最初のサインイン試行でシングル サインオンが切断されます (ユーザーがパスワードを保存するオプションを選択したものとしています)。SfB クライアントでは、SIP/UPN の値が同じであると仮定しています。このシナリオでの SIP アドレスは user@company.com ですが、ユーザー フォレスト内の有効であるオブジェクトの UPN は実際には user@contoso.company.com なので、最初のログイン試行が失敗し、ユーザーに資格情報の入力を求めるメッセージが表示されます。正しい実際の UPN を入力すると、ユーザー フォレスト内のドメイン コントローラーに対する認証要求が完了し、サインインは成功します。
    
- 各ユーザー フォレストの一意の UPN をリソース フォレスト内の関連付けられている無効であるオブジェクトに同期する場合、AD FS 認証は失敗します。照合ルールによりリソース フォレスト内のオブジェクトに UPN が見つかりますが、無効であるため、認証には使用できません。 
    
## <a name="create-an-office-365-tenant"></a>Office 365 テナントの作成

次に、展開で使用する Office 365 テナントをプロビジョニングする必要があります。 詳細については、 [Office 365 の準備の手順](https://social.technet.microsoft.com/wiki/contents/articles/22808.office-365-provisioning-steps.aspx)を参照してください。 
  
## <a name="configure-ad-fs"></a>AD FS の構成

テナントができたら、次に、各ユーザー フォレストで Active Directory フェデレーション サービス (AD FS) を構成する必要があります。ここでは、各フォレストに一意の SIP および SMTP アドレスと、ユーザー プリンシパル名 (UPN) があると仮定しています。AD FS はオプションで、ここではシングル サインオンを実現するために使用します。パスワード同期を備えた DirSync もサポートされていて、AD FS の代わりに使用することもできます。 
  
対応する SIP/SMTP および UPN がある展開のみがテストされています。対応する SIP/SMTP/UPN がないと、Exchange 統合やシングル サインオンに関する問題が発生するなど、機能が低下する可能性があります。 
  
各フォレストのユーザーの一意な SIP と SMTP と UPN を使用する場合を除き、シングル サインオン (SSO) の問題には、AD FS の導入場所にかかわらずにでも実行できます。 
  
- AD FS ファームが各ユーザー フォレストに展開された状態での、リソース/ユーザー フォレスト間の一方向または双方向の信頼。すべてのユーザーは共通の SIP/SMTP ドメインを共有しますが、ユーザー フォレストごとに一意の UPN を共有します。 
    
- AD FS ファームがリソース フォレストのみに展開された状態での、リソース/ユーザー フォレスト間の双方向の信頼。すべてのユーザーは共通の SIP/SMTP ドメインを共有しますが、ユーザー フォレストごとに一意の UPN を共有します。 
    
AD FS ファームを各ユーザー フォレストに配置し、フォレストごとに一意の SIP/SMTP/UPN を使用することで、両方の問題が解決します。認証試行中に、特定のユーザー フォレストにあるアカウントのみが検索および照合されます。これは、よりシームレスな認証プロセスを実現するのに役立ちます。 
  
これは、Windows Server 2012 R2 AD FS の標準的な展開であり、先に進む前に正常に動作している必要があります。 手順については、 [Office 365 AD FS 2012 R2 のインストール方法](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)を参照してください。 
  
展開が完了したら、先ほど選択したソース アンカーに一致するように要求規則を編集する必要があります。AD FS MMC の [証明書利用者の信頼] で、[Microsoft Office 365 ID プラットフォーム] を右クリックし、[要求規則の編集] をクリックします。最初の規則を編集して、ObjectSID を employeeNumber に変更します。 
  
![マルチ フォレストの [規則の編集] 画面](../../media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>AAD Connect の構成

AAD Connect は、さまざまなフォレストの間、およびフォレストと Office 365 の間でアカウントをマージするために使用します。AAD Connect はリソース フォレストに展開することをお勧めします。複数のフォレストと Office 365 を同期できる必要がありますが、これは Dirsync ではサポートされていません。 
  
AAD Connect では、オンプレミス フォレスト間でアカウントが同期されません。AD コネクタを使用して、(FIM やそれと類似した製品により) オンプレミス フォレスト間で既に同期されているオブジェクトが読み取られます。次に、フィルター規則を利用して、メタバース内の対応する有効であるオブジェクトと無効であるオブジェクトの両方の単一表現が作成され、その単一のマージ済みオブジェクトが Office 365 にレプリケートされます。 
  
処理が完了して AAD Connect でマージされている途中にメタバースのオブジェクトを調べると、次のような画面が表示されます。 
  
![マルチ フォレストのメタバース オブジェクトの画面](../../media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
緑色で強調表示されている属性は Office 365 からマージされたもので、黄色はユーザー フォレストから、青色はリソース フォレストからマージされたものです。 
  
これはテスト ユーザーです。AAD Connect でユーザー フォレストとリソース フォレストのオブジェクトから、および Office 365 から sourceAnchor と cloudSourceAnchor が識別されたことが確認できます。上記の例では "1101" であり、これは先ほど選択した employeeNumber です。続いて、このオブジェクトを上記の内容にマージできています。 
  
詳細については[、オンプレミス ユーザーは、Azure Active Directory との統合](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/)」を参照してください。 
  
AAD Connect のインストールでは、ほとんどは既定値を使用することをお勧めします。ただし、以下の手順は例外です。 
  
1.  シングル サインインを導入済みの AD FS を使用する作業と選択を構成しません。
    
2. ディレクトリの接続 - すべてのドメインを追加 
    
3.  設置ディレクトリ内のユーザーを識別する:**ユーザーの id が複数のディレクトリに存在**するかを選択し、 **ObjectSID** 、 **msExchangeMasterAccountSID**属性を選択します。
    
4. Azure AD でユーザーを識別する: ソース アンカーを読むと[良い sourceAnchor の属性を選択すると](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/)選択した属性を選択、ユーザー プリンシパル名が**userPrincipalName**
    
5.  -他のオプションの機能は、Exchange ハイブリッドが配置されてかがあるかどうかを選択します。
    
    > [!NOTE]
    >  Exchange Online のみを使用している場合は、CNAME のリダイレクトが原因で、自動検出中に OAuth のエラーの問題が発生する可能性があります。 これを修正する、Skype からビジネス サーバー管理シェルの次のコマンドレットを実行して、Exchange の自動検出 URL を設定する必要があります。
  
    セット CsOAuthConfiguration ExchangeAutoDiscoverURLhttps://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    
6.  AD FS ファーム: [**既存の Windows Server 2012 R2 AD FS ファームを使用します**] を選択し、AD FS サーバーの名前を入力します。
    
7.  ウィザードを完了し、必要な検証を実行します。
    
## <a name="configure-hybrid-mode-for-skype-for-business-server"></a>Skype for Business Server のハイブリッド モードを構成する

ビジネスのハイブリッドの Skype を設定するためのベスト プラクティスに従います。 計画の詳細については、 [Skype のビジネス サーバー 2015 のハイブリッド展開を計画](https://technet.microsoft.com/en-us/library/jj205403.aspx)を参照してくださいし、構成情報は、 [Skype のビジネスをオンラインで構成するハイブリッド](https://technet.microsoft.com/en-us/library/jj204669.aspx)を参照してください。 
  
## <a name="configure-hybrid-mode-for-exchange-server"></a>Exchange Server のハイブリッド モードを構成する

必要に応じて、Exchange ハイブリッドを構成するためのベスト プラクティスに従います。 詳細については、 [Exchange Server のハイブリッド展開](https://technet.microsoft.com/en-us/library/jj200581%28v=exchg.150%29.aspx)を参照してください。 
  

