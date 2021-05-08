---
title: 認証のMicrosoft Teams ミーティング
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-collaboration
description: 最新の認証を構成する方法についてMicrosoft Teams ミーティング
ms.openlocfilehash: 93577c74005c8ad266739da0991f31e384a57ba6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117485"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>認証のMicrosoft Teams ミーティング

デバイスのアカウントMicrosoft Teams ミーティングは、アプリケーション レベルで処理されます。 アプリケーションは、Microsoft Teams、Skype for Business、Exchange に接続して、会議室アカウントのリソースを取得して、通話や会議のエクスペリエンスを有効にできます。 デバイスは、常時接続機能、呼び出しシナリオ (通話プランで構成されたデバイスの場合)、およびこれらのデバイスに実装されるカスタム ロックダウン メカニズムを許可するために、アカウントに依存しません。 つまり、これらのデバイスの認証は、エンド ユーザー デバイスとは異なる方法で行います。  

最新の認証は、すべてのお客様が、Microsoft Teams ミーティング または Microsoft 365 デバイスを使用Office 365。 Exchange サーバーまたは Skype for Business サーバーのオンプレミス デプロイがある場合は、最新の認証を使用するように[](/office365/enterprise/hybrid-modern-auth-overview)Azure Active Directory (Azure AD) を使用してハイブリッド最新認証を構成します。

最新の認証は、Microsoft Teams ミーティング 4.4.25.0 以降でサポートされています。

## <a name="modern-authentication"></a>先進認証

Microsoft Teams ミーティング アプリケーションで最新の認証を使用する場合、Active Directory 認証ライブラリ (ADAL) を使用して、Microsoft Teams、Exchange、Skype for Business に接続します。 デバイスMicrosoft Teams ミーティング共有デバイスであり、夜間再起動を実行して、スムーズに機能し、重要なオペレーティング システム、ドライバー、ファームウェア、またはアプリケーションの更新プログラムを取得します。 最新の認証メカニズムでは、OAuth 2.0 でリソース [所有者](/azure/active-directory/develop/v2-oauth-ropc) のパスワード資格情報承認付与の種類が使用されます。ユーザーの介入は必要ありません。 これは、ユーザー アカウントに対する最新の認証のしくみと、アプリケーションで使用されるリソース アカウントの主な違いの 1 Microsoft Teams ミーティングです。 このため、Microsoft Teams ミーティング リソース アカウントは、多要素認証 (MFA)、スマート カード認証、またはクライアント証明書ベースの認証 (すべてエンド ユーザーが使用できる) を使用するように構成することはできません。

Microsoft Teams ミーティング デバイスとエンド ユーザー デバイスでの最新の認証のしくみのもう 1 つの主な違いは、リソース アカウントを使用して Azure Active Directory と エンドポイント マネージャー のデバイス レベルの条件付きアクセス ポリシーを適用できない点です。この付与の種類を使用する場合、デバイス情報は渡されません。 代わりに、「Teams Meeting Rooms with Intune の管理」に示されているガイダンスを使用して、デバイスを Microsoft エンドポイント マネージャー に登録し、コンプライアンス[ポリシーを適用できます](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>デバイスで最新の認証Microsoft Teams ミーティングする

Microsoft Teams ミーティング Skype for Business および Exchange で最新の認証を使用するには、Microsoft Teams ミーティング デバイスで最新の認証のクライアント側の設定を有効にします。 これは、デバイス設定または XML 構成ファイルで行います。

> [!NOTE]
> 最新の認証のクライアント側設定を有効にする前に、最新の認証を使用するように環境が正しく設定されていることを確認してください。

### <a name="using-device-settings"></a>デバイス設定の使用

1. Microsoft Team Rooms デバイスで、[詳細]**(... ) に移動します**。
    
2. **[設定]** を選択し、デバイス管理者のユーザー名とパスワードを入力します。
3. [アカウント] タブ **に移動** し、[最新の認証] **をオンに** し、[保存して **終了] を選択します**。

### <a name="using-the-xml-config-file"></a>XML 構成ファイルの使用

このファイルSkypeSettings.xml、次のように、最新の認証 XML 要素を **True** に設定します。

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

設定を適用するには、「XML 構成ファイル[を使用Microsoft Teams ミーティング本体の設定をリモートで管理する」を参照してください](xml-config-file.md)。

## <a name="prepare-your-environment-for-modern-authentication"></a>最新の認証用に環境を準備する

開始する前に、Office 365 および Azure の ID モデルで使用する ID AD。 ID モデルと id モデルの詳細[Office 365、Azure Active Directory](/Office365/Enterprise/about-office-365-identity)のハイブリッド ID とディレクトリ同期に関するページMicrosoft 365[参照Office 365。](/Office365/Enterprise/plan-for-directory-synchronization)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>最新の認証を有効にする (Microsoft 365 または Office 365

最新の認証を有効にするには、「Exchange Online で最新の認証を有効[にする」をExchange Online。](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) Skype for Business Online を使用する場合は、Skype for Business Online に対して最新の認証が有効になっていることを確認する必要があります。 詳細については、「Skype for Business Online: Enable your tenant for modern authentication 」[を参照してください](https://aka.ms/SkypeModernAuth)。

Microsoft Teams ミーティング デバイスが Exchange Online、Teams、Skype for Business Online で正常にサインインできると検証するまで、Exchange Online の基本認証ポリシーを削除したり、テナントの基本認証を無効にしたりし、お勧めします。

アプリケーションで基本認証を無効にする方法の詳細については、「Exchange Online で基本認証を無効[にする」をExchange Online。](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)

## <a name="hybrid-modern-authentication"></a>ハイブリッド最新の認証

オンプレミスの Exchange サーバーまたは Skype for Business サーバーに対する認証を確実に成功するには、azure AD から承認を取得するように Microsoft Teams ミーティング で使用されるリソース アカウントが構成されていることを確認する必要があります。 

Teams ミーティングは、認証の構成によって異なります。 マネージド ドメインを使用しているお客様の場合、Teams ミーティング で[OAuth 2.0 リソース](/azure/active-directory/develop/v2-oauth-ropc)所有者パスワード資格情報を使用Azure Active Directory。 ただし、フェデレーション ドメインを使用しているお客様の場合は[、OAuth 2.0 SAML ベアラー アサーション](/azure/active-directory/develop/v2-saml-bearer-assertion)Flow使用されます。

> [!NOTE]
> ID プロバイダーは、特定の構成または設定を必要とする場合があります。この構成または設定は、Azure Active DirectoryまたはOffice 365。 認証を構成する方法についてサポートが必要な場合は、ID プロバイダーに問い合Teams ミーティング。


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>アプリケーションに固有のMicrosoft Teams ミーティング

ハイブリッド トポロジで最新の認証を有効にするための前提条件については、「ハイブリッド最新の認証の概要」と「オンプレミスの Skype for Business および Exchange サーバーで使用するための前提条件」[を参照してください](/office365/enterprise/hybrid-modern-auth-overview)。 この記事で説明されている前提条件はすべて適用されます。

ただし、Microsoft Teams ミーティング は最新の認証にリソース[所有者](https://tools.ietf.org/html/rfc6749#section-1.3.3)のパスワード資格情報の承認と基になる REST API を使用します。このため、Microsoft Teams ミーティング に固有の点に注意する必要がある重要な違いは次のとおりです。

- 2016 CU8 以降Exchange Server 2019 CU1 以降Exchange Server必要があります。
- 2015 CU5 以降Skype for Business Server 2019 以降Skype for Business Server必要があります。
- MFA は、使用しているトポロジに関係なくサポートされていません。
- Microsoft Teams ミーティング SIP と UPN の不一致はサポートされていません。 動作するには、同Microsoft Teams ミーティング UPN と SIP を持つアカウントを作成する必要があります。
- Azure AD でサポートされているサード パーティの認証プロバイダーを使用する場合は、WS-Trust を介したアクティブな認証フローをサポートする必要があります。
- アプリケーションで構成されたリソース アカウントには、デバイス レベルの条件付きアクセス ポリシーを使用しない。 そうすると、サインイン エラーが発生します。 代わりに、Intune を使用した Microsoft Intune Teams 会議室の管理に関するページで公開されているガイダンスを使用して、Microsoft Intune デバイスを登録し、コンプライアンス[ポリシーを適用します](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。

### <a name="configure-exchange-server"></a>構成Exchange Server

ハイブリッド最新認証を有効にするにはExchange Serverハイブリッド最新認証を使用Exchange Serverを構成する方法[に関するページを参照してください](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="configure-skype-for-business-server"></a>構成Skype for Business Server

Skype for Business Server を使用してハイブリッド最新の認証を有効にするには、ハイブリッド最新認証を使用Skype for Businessを構成する方法[に関するページを参照してください](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>ファイルの削除またはSkype for BusinessとExchange

セットアップでハイブリッド最新認証が許可されていない場合、または Exchange または Skype for Business のハイブリッド最新認証を削除または無効にする必要がある場合は、「Skype for Business および Exchange からハイブリッドモダン認証を削除または無効化する」を参照[してください。](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)

### <a name="azure-ad-conditional-access"></a>Azure AD条件付きアクセス

IP/場所ベースのアクセスにMicrosoft Teams ミーティングリソース アカウントを構成できます。 詳細については、「条件付きアクセス [: 場所によるアクセスのブロック」を参照してください](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)。

その他の条件付きアクセス ポリシーはサポートされていません。 デバイスのコンプライアンスの詳細については、「Intune を使用して会議室Teams[管理する」を参照してください](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。