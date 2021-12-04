---
title: Microsoft Teams 会議室での認証
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
description: Microsoft Teams Rooms の最新の認証を構成する方法について学習します
ms.openlocfilehash: 9f173759ed2b615bdfcae6c54c2c5e431c197d04
ms.sourcegitcommit: 7eb66cb2955b17e89e1c162b6ca1b9bdb18189b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2021
ms.locfileid: "61306302"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft Teams 会議室での認証

Microsoft Teams Rooms デバイスのアカウント管理は、アプリケーション レベルで処理されます。 アプリケーションは、Microsoft Teams、Skype for Business、Exchange に接続して、会議室アカウントのリソースを取得して、通話や会議のエクスペリエンスを有効にできます。 デバイスは、専用のリソース アカウントを使用して、常時接続機能、呼び出しシナリオ (通話プランで構成されたデバイスの場合)、およびこれらのデバイスに実装されるカスタム ロックダウン メカニズムを可能にします。 つまり、これらのデバイスの認証は、エンド ユーザー デバイスとは異なる方法で行います。  

最新の認証は、Microsoft Teams Rooms と Microsoft 365 または Office 365 を使用しているすべてのお客様に推奨されます。 Exchange サーバーまたは Skype for Business サーバーのオンプレミス デプロイがある場合は、Azure Active Directory (Azure AD)[](/office365/enterprise/hybrid-modern-auth-overview)を使用してハイブリッド最新認証を構成して、最新の認証を有効にします。

最新の認証は、Microsoft Teams Rooms バージョン 4.4.25.0 以降でサポートされています。

## <a name="modern-authentication"></a>先進認証

Microsoft Teams Rooms アプリケーションで最新の認証を使用する場合、Active Directory 認証ライブラリ (ADAL) を使用して Microsoft Teams、Exchange、Skype for Business に接続します。 Microsoft Teams会議室は共有デバイスであり、夜間の再起動を実行して、スムーズに機能し、重要なオペレーティング システム、ドライバー、ファームウェア、アプリケーションの更新プログラムを取得します。 最新の認証メカニズムでは、OAuth 2.0 でリソース [所有者](/azure/active-directory/develop/v2-oauth-ropc) のパスワード資格情報承認付与の種類が使用されます。ユーザーの介入は必要ありません。 これは、ユーザー アカウントに対する最新の認証のしくみと、Microsoft Teams Rooms で使用されるリソース アカウントの主な違いの 1 つです。 このため、Microsoft Teams Rooms リソース アカウントは、多要素認証 (MFA)、スマート カード認証、またはクライアント証明書ベースの認証 (すべてエンド ユーザーが使用できる) を使用するように構成することはできません。

Microsoft Teams Rooms デバイスとエンド ユーザー デバイスでの最新の認証のしくみのもう 1 つの主な違いは、リソース アカウントを使用して Azure Active Directory と エンドポイント マネージャー のデバイスレベルの条件付きアクセス ポリシーを適用できない点です。デバイス情報は、この付与の種類を使用するときに渡されません。 代わりに、「Microsoft エンドポイント マネージャー Teams で会議室を管理する」に示されているガイダンスを使用して、Microsoft エンドポイント マネージャー にデバイスを登録し、コンプライアンス[ポリシーを適用できます](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Microsoft Teams Rooms デバイスで最新の認証を有効にする

Microsoft Teams 会議室が Skype for Business と Exchange で最新の認証を使用するには、Microsoft Teams Rooms で最新の認証のクライアント側の設定を有効にします。 これは、デバイス設定または XML 構成ファイルで行います。

> [!NOTE]
> 最新の認証のクライアント側設定を有効にする前に、最新の認証を使用するように環境が正しく設定されていることを確認してください。

### <a name="using-device-settings"></a>デバイス設定の使用

1. [Microsoft Teams] で、[**詳細]** **(... ) に移動します**。
    
2. **[設定]** を選択し、デバイス管理者のユーザー名とパスワードを入力します。
3. [アカウント] タブ **に移動** し、[最新の認証] **をオンに** し、[保存して **終了] を選択します**。

### <a name="using-the-xml-config-file"></a>XML 構成ファイルの使用

このファイルSkypeSettings.xml、次のように、最新の認証 XML 要素を **True** に設定します。

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

設定を適用するには、「XML 構成ファイルを使用して Microsoft Teams Rooms コンソール設定をリモートで[管理する」を参照してください](xml-config-file.md)。

## <a name="prepare-your-environment-for-modern-authentication"></a>最新の認証用に環境を準備する

開始する前に、ID モデルを使用する ID モデルをOffice 365確認Azure AD。 詳細については、ID モデル[](/Office365/Enterprise/about-office-365-identity)と id モデルOffice 365、Azure Active Directory のハイブリッド ID とディレクトリ同期に関するページMicrosoft 365[参照Office 365。](/Office365/Enterprise/plan-for-directory-synchronization)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>最新の認証を有効にする (Microsoft 365 または Office 365

認証の最新の認証を有効にするには、「Exchange Online で最新の認証を有効[にする」をExchange Online。](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)

Microsoft Teams Rooms デバイスが Exchange Online と Teams で正常にサインインできると検証するまで、Exchange Online の基本認証ポリシーを削除したり、テナントの基本認証を無効にしたりしなことをお勧めします。

アプリケーションで基本認証を無効にする方法の詳細については、「Exchange Online で基本認証を無効[にする」をExchange Online。](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)

## <a name="hybrid-modern-authentication"></a>ハイブリッド最新の認証

オンプレミスの Exchange サーバーまたは Skype for Business サーバーに対する認証を確実に成功するには、Microsoft Teams Rooms で使用されるリソース アカウントが Azure AD から承認を取得するように構成されていることを確認する必要があります。

Teamsの認証フローは、認証の構成によって異なります。 マネージド ドメインを使用しているお客様の場合、Teams Rooms では[、OAuth 2.0 リソース](/azure/active-directory/develop/v2-oauth-ropc)所有者パスワード資格情報と一緒に Azure Active Directory。 ただし、フェデレーション ドメインを使用しているお客様の場合は[、OAuth 2.0 SAML ベアラー アサーション](/azure/active-directory/develop/v2-saml-bearer-assertion)Flow使用されます。

> [!NOTE]
> ID プロバイダーは、特定の構成または設定が必要な場合があります。この構成または設定は、Azure Active DirectoryまたはOffice 365。 Teams Rooms での認証の構成に関するヘルプが必要な場合は、ID プロバイダーにお問い合わせください。


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>会議室に固有Microsoft Teams前提条件

ハイブリッド トポロジで最新の認証を有効にするための前提条件については、「ハイブリッド最新認証の概要」と「オンプレミスの認証サーバーおよびオンプレミスのサーバーで使用するための[前提条件Skype for Business説明Exchangeされています](/office365/enterprise/hybrid-modern-auth-overview)。 この記事で説明されている前提条件はすべて適用されます。

ただし、Microsoft Teams Rooms では、最新の[](https://tools.ietf.org/html/rfc6749#section-1.3.3)認証にリソース所有者のパスワード資格情報の承認と基になる REST API が使用されます。このため、Microsoft Teams Rooms に固有の点に注意する必要がある重要な違いは次のとおりです。

- 2016 CU8 以降Exchange Server 2019 CU1 以降Exchange Server必要があります。
- 2015 CU5 以降Skype for Business Server 2019 以降Skype for Business Server必要があります。
- MFA は、使用しているトポロジに関係なくサポートされていません。
- Microsoft Teams会議室では、SIP と UPN の不一致はサポートされていません。 同じ UPN Microsoft Teams SIP を持つ会議室アカウントを作成して、機能する必要があります。
- Azure AD でサポートされているサード パーティの認証プロバイダーを使用する場合は、WS-Trust を介したアクティブな認証フローをサポートする必要があります。
- アプリケーションで構成されたリソース アカウントには、デバイス レベルの条件付きアクセス ポリシーを使用しない。 そうすると、サインイン エラーが発生します。 代わりに、Intune を使用した Microsoft Intune 会議室の管理に関するページで公開されているガイダンスを使用して、Teamsデバイスを登録し、コンプライアンス ポリシー[を適用します](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。

### <a name="configure-exchange-server"></a>構成Exchange Server

ハイブリッドモダン認証を有効にするにはExchange Serverハイブリッド最新認証を使用Exchange Serverを構成する方法[に関するページを参照してください](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="configure-skype-for-business-server"></a>構成Skype for Business Server

Skype for Business Server を使用してハイブリッド最新の認証を有効にするには、ハイブリッド最新認証を使用Skype for Businessを構成する方法[に関するページを参照してください](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>削除または無効化Skype for Business削除Exchange

セットアップでハイブリッド最新認証が許可されていない場合、または Exchange または Skype for Business のハイブリッド最新認証を削除または無効にする必要がある場合は、「Skype for Business および Exchange からのハイブリッド最新認証の削除または無効化」を[参照](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)してください。

### <a name="azure-ad-conditional-access"></a>Azure AD条件付きアクセス

IP/場所ベースのアクセス用に Microsoft Teams Rooms で使用されるリソース アカウントを構成できます。 詳細については、「条件付きアクセス [: 場所によるアクセスのブロック」を参照してください](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)。

その他の条件付きアクセス ポリシーはサポートされていません。 デバイスのコンプライアンスの詳細については、「Intune を使用した会議室Teams[管理する」を参照してください](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。