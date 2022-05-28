---
title: Microsoft Teams Roomsでの認証
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-collaboration
description: Microsoft Teams Roomsの先進認証を構成する方法について説明します
ms.openlocfilehash: 5667b4bc2ab356ff9776282a6142a22abd33caa1
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760879"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft Teams Roomsでの認証

Microsoft Teams Roomsのアカウント管理は、アプリケーション レベルで処理されます。 アプリケーションは、Microsoft Teams、Skype for Business、Exchangeに接続して、リソース アカウントのリソースを取得して、通話と会議のエクスペリエンスを有効にします。 Teams Roomsでは、専用のリソース アカウントを使用して、常時オン機能、通話シナリオ (通話プランで構成されたデバイスの場合)、カスタム ロックダウン メカニズムを許可します。 つまり、Teams Roomsの認証は、エンド ユーザー デバイスとは異なる方法で行われます。  

最新の認証は、Microsoft 365またはOffice 365でMicrosoft Teams Roomsを使用するすべてのお客様にお勧めします。 Exchange サーバーまたはSkype for Business サーバーのオンプレミスデプロイがある場合は、最新の認証を使用できるように、Azure Active Directory (Azure AD) を使用して[ハイブリッド先進認証](/office365/enterprise/hybrid-modern-auth-overview)を構成します。

最新の認証は、Microsoft Teams Rooms バージョン 4.4.25.0 以降でサポートされています。

## <a name="modern-authentication"></a>先進認証

Microsoft Teams Rooms アプリケーションで先進認証を使用する場合、Active Directory 認証ライブラリ (ADAL) は、Microsoft Teams、Exchange、およびSkype for Businessに接続するために使用されます。 最新の認証メカニズムでは、OAuth 2.0 の [リソース所有者パスワード資格情報](/azure/active-directory/develop/v2-oauth-ropc) 承認付与の種類が使用されます。これは、ユーザーの介入を必要としません。 これは、ユーザー アカウントに対する先進認証の動作と、Microsoft Teams Roomsで使用されるリソース アカウントの主な違いの 1 つです。 このため、多要素認証 (MFA)、スマート カード認証、またはクライアント証明書ベースの認証 (すべてエンド ユーザーが使用できる) を使用するように、Microsoft Teams Rooms リソース アカウントを構成しないでください。

Microsoft Teams Rooms デバイスとエンド ユーザー デバイスでの先進認証のしくみのもう 1 つの重要な違いは、リソース アカウントを使用してデバイス レベルの条件付きアクセス ポリシーをAzure Active Directoryに適用できず、この許可の種類を使用するときにデバイス情報が渡されないためエンドポイント マネージャーです。 代わりに、デバイスをMicrosoft エンドポイント マネージャーに登録し、コンプライアンス ポリシーを適用できます。 詳細については、「[条件付きアクセスとIntuneコンプライアンスのMicrosoft Teams Rooms](conditional-access-and-compliance-for-devices.md)」を参照してください。

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>Microsoft Teams Roomsで先進認証を有効にする

Microsoft Teams RoomsがSkype for BusinessとExchangeで先進認証を使用するには、Microsoft Teams Roomsで先進認証のクライアント側の設定を有効にします。 これは、デバイス設定または XML 構成ファイルで行うことができます。

> [!NOTE]
> 先進認証のクライアント側設定を有効にする前に、最新の認証を使用するように環境が正しく設定されていることを確認してください。

### <a name="using-device-settings"></a>デバイス設定の使用

1. Microsoft Teams Roomsで、**その他** (**...**) に移動します。
    
2. **設定** 選択し、デバイス管理者のユーザー名とパスワードを入力します。
3. **[アカウント**] タブに移動し、[**先進認証**] をオンにし、[**保存して終了]** を選択します。

### <a name="using-the-xml-config-file"></a>XML 構成ファイルの使用

SkypeSettings.xml ファイルで、次のように最新の認証 XML 要素を **True** に設定します。

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

この設定を適用するには、「[MICROSOFT TEAMS ROOMS コンソール設定を XML 構成ファイルでリモートで管理する」を参照](xml-config-file.md)してください。

## <a name="prepare-your-environment-for-modern-authentication"></a>先進認証用の環境を準備する

開始する前に、Office 365と Azure AD で使用する ID モデルを理解しておいてください。 詳細については、[Office 365 ID モデルとAzure Active Directory](/Office365/Enterprise/about-office-365-identity)に関するMicrosoft 365[またはOffice 365のハイブリッド ID とディレクトリの同期を参照](/Office365/Enterprise/plan-for-directory-synchronization)してください。

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Microsoft 365またはOffice 365で先進認証を有効にする

Exchange Onlineの先進認証を有効にするには、「[Exchange Onlineで先進認証を有効にする」を](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)参照してください。

Microsoft Teams Rooms デバイスがExchange OnlineとTeamsで正常にサインインできることを検証するまで、テナントの基本認証ポリシーをExchange Onlineから削除したり、テナントの基本認証を無効にしたりしないことをお勧めします。

Exchange Onlineでの基本認証の無効化の詳細については、「Exchange Online[の基本認証を無効にする](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)」を参照してください。

## <a name="hybrid-modern-authentication"></a>ハイブリッド先進認証

オンプレミスのExchange サーバーやSkype for Business サーバーに対する認証を成功させるには、Microsoft Teams Roomsで使用されるリソース アカウントが Azure AD から承認を取得するように構成されていることを確認する必要があります。

Teams Rooms認証フローは、認証の構成によって異なります。 マネージド ドメインを使用しているお客様の場合、Teams Roomsは [OAuth 2.0 リソース所有者パスワード資格情報](/azure/active-directory/develop/v2-oauth-ropc)とAzure Active Directoryを使用します。 ただし、フェデレーション ドメインを使用しているお客様には、[OAuth 2.0 SAML Bearer Assertion Flow](/azure/active-directory/develop/v2-saml-bearer-assertion)が使用されます。

> [!NOTE]
> ID プロバイダーには、Azure Active DirectoryまたはOffice 365との統合に固有の構成または設定が必要な場合があります。 Teams Roomsによる認証の構成に関するヘルプが必要な場合は、ID プロバイダーに問い合わせてください。


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Microsoft Teams Roomsに固有の前提条件

ハイブリッド トポロジで先進認証を有効にする前提条件については、[ハイブリッド先進認証の概要と、オンプレミスのSkype for BusinessおよびExchange サーバーで使用するための前提条件](/office365/enterprise/hybrid-modern-auth-overview)について説明します。 この記事で説明したすべての前提条件が適用されます。

ただし、Microsoft Teams Roomsでは[リソース所有者パスワード資格情報](https://tools.ietf.org/html/rfc6749#section-1.3.3)の承認と基になる REST API を最新の認証に使用するため、Microsoft Teams Roomsに固有の点に注意する必要がある重要な違いは次のとおりです。

- 2016 CU8 以降、または 2019 CU1 以降Exchange Server Exchange Server必要があります。
- 2015 CU5 以降、または 2019 以降Skype for Business Server Skype for Business Server必要があります。
- MFA は、使用しているトポロジに関係なくサポートされません。
- Microsoft Teams Roomsでは、SIP と UPN の不一致はサポートされていません。 同じ UPN と SIP を使用してMicrosoft Teams Rooms アカウントを作成する必要があります。
- Azure AD でサポートされているサード パーティの認証プロバイダーを使用する場合は、WS-Trust を介したアクティブな認証フローをサポートする必要があります。
- アプリケーションで構成されたリソース アカウントには、デバイス レベルの条件付きアクセス ポリシーを使用しないでください。 この操作を行うと、サインインエラーが発生します。 代わりに、デバイスをMicrosoft Intuneに登録し、コンプライアンス ポリシーを適用します。 詳細については、「[条件付きアクセスとIntuneコンプライアンスのMicrosoft Teams Rooms](conditional-access-and-compliance-for-devices.md)」を参照してください。

### <a name="configure-exchange-server"></a>Exchange Serverを構成する

Exchange Serverでハイブリッドモダン認証を有効にするには、「ハイブリッド[先進認証を使用するようにオンプレミスExchange Server構成する方法](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)」を参照してください。

### <a name="configure-skype-for-business-server"></a>Skype for Business Serverを構成する

Skype for Business Serverを使用してハイブリッドモダン認証を有効にするには、「[ハイブリッドモダン認証を使用するようにオンプレミスSkype for Business構成する方法](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)」を参照してください。

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Skype for BusinessとExchangeを削除または無効にする

セットアップでハイブリッドモダン認証が許可されていない場合、またはExchangeまたはSkype for Businessのハイブリッドモダン認証を削除または無効にする必要がある場合は、「Skype for Business[とExchangeからのハイブリッド先進認証の削除または無効化](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)」を参照してください。

### <a name="azure-ad-conditional-access"></a>Azure AD の条件付きアクセス

ip/location ベースのアクセスにMicrosoft Teams Roomsで使用されるリソース アカウントを構成できます。 詳細については、「 [条件付きアクセス: 場所別のアクセスをブロック](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)する」を参照してください。

他の条件付きアクセス ポリシーはサポートされていません。 デバイス コンプライアンスの詳細については、「[Microsoft Teams Roomsのサポートされている条件付きアクセスとIntuneコンプライアンス ポリシー」を](supported-ca-and-compliance-policies.md)参照してください。
