---
title: Microsoft Teams 会議室での認証
ms.author: czawideh
author: cazawideh
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
description: Microsoft Teams Rooms の最新の認証を構成する方法についてMicrosoft Teamsします。
ms.openlocfilehash: 6489ec29fa0745fda6e70c89dd821c8c72645ddc
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503764"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft Teams 会議室での認証

Microsoft Teams Rooms のアカウント管理は、アプリケーション レベルで処理されます。 アプリケーションは、Microsoft Teams、Skype for Business、Exchange に接続して、リソース アカウントのリソースを取得して、呼び出しと会議のエクスペリエンスを有効にします。 Teams会議室では、専用のリソース アカウントを使用して、常時接続機能、呼び出しシナリオ (通話プランで構成されたデバイスの場合)、カスタム ロックダウン メカニズムを使用できます。 つまり、Teams Rooms の認証は、エンドユーザー デバイスとは異なる方法で行います。  

最新の認証は、すべてのお客様が Microsoft Teams や Microsoft 365 を使用Office 365。 Exchange サーバーまたは Skype for Business サーバーのオンプレミス デプロイがある場合は、Azure Active Directory (Azure AD) を使用してハイブリッド最新認証[](/office365/enterprise/hybrid-modern-auth-overview)を構成して、最新の認証を有効にします。

最新の認証は、Microsoft Teams Rooms バージョン 4.4.25.0 以降でサポートされています。

## <a name="modern-authentication"></a>先進認証

Microsoft Teams Rooms アプリケーションで最新の認証を使用する場合、Active Directory 認証ライブラリ (ADAL) を使用して Microsoft Teams、Exchange、Skype for Business に接続します。 最新の認証メカニズムでは、OAuth 2.0 でリソース [所有者](/azure/active-directory/develop/v2-oauth-ropc) のパスワード資格情報承認付与の種類が使用されます。ユーザーの介入は必要ありません。 これは、ユーザー アカウントに対する最新の認証のしくみと、Microsoft Teams Rooms で使用されるリソース アカウントの主な違いの 1 つです。 このため、Microsoft Teams Rooms リソース アカウントは、多要素認証 (MFA)、スマート カード認証、またはクライアント証明書ベースの認証 (すべてエンド ユーザーが使用できる) を使用するように構成することはできません。

Microsoft Teams Rooms デバイスとエンド ユーザー デバイスでの最新の認証のしくみのもう 1 つの主な違いは、この付与の種類を使用する場合にデバイス情報が渡されないので、Azure Active Directory と エンドポイント マネージャー でデバイス レベルの条件付きアクセス ポリシーを適用するためにリソース アカウントを使用できない点です。 代わりに、「[Teams Meeting Rooms with Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230) の管理」に示されているガイダンスを使用して、デバイスを Microsoft エンドポイント マネージャー に登録し、コンプライアンス ポリシーを適用できます。

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>Microsoft Teams Rooms で最新の認証を有効にする

会議室Microsoft Teams Skype for Business と Exchange で最新の認証を使用するには、Microsoft Teams Rooms で最新の認証のクライアント側の設定を有効にします。 これは、デバイス設定または XML 構成ファイルで行います。

> [!NOTE]
> 最新の認証のクライアント側設定を有効にする前に、最新の認証を使用するように環境が正しく設定されていることを確認してください。

### <a name="using-device-settings"></a>デバイス設定の使用

1. [Microsoft Teams] で、[**その他 ]**(**...) に移動します**。
    
2. **[設定**] を選択し、デバイス管理者のユーザー名とパスワードを入力します。
3. [アカウント] タブ **に移動** し、[最新の認証] **をオンに** し、[保存して **終了] を選択します**。

### <a name="using-the-xml-config-file"></a>XML 構成ファイルの使用

このファイルSkypeSettings.xml、次のように、最新の認証 XML 要素を **True** に設定します。

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

設定を適用するには、「XML 構成ファイル[を使用して Microsoft Teams会議室の本体設定をリモートで管理する」を参照してください](xml-config-file.md)。

## <a name="prepare-your-environment-for-modern-authentication"></a>最新の認証用に環境を準備する

開始する前に、ID モデルを使用する ID モデルをOffice 365確認Azure AD。 詳細については、「Office 365 [ID](/Office365/Enterprise/about-office-365-identity) モデルとAzure Active Directoryハイブリッド ID とディレクトリ同期 」を参照Microsoft 365[または](/Office365/Enterprise/plan-for-directory-synchronization)Office 365。

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>最新の認証を有効にする (Microsoft 365 または Office 365

最新の認証を有効にするには、「Exchange Onlineで最新の認証を有効にする[」をExchange Online](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。

Microsoft Teams Rooms デバイスが Exchange Online と Teams で正常にサインインできると検証するまで、Exchange Online の基本認証ポリシーを削除したり、テナントの基本認証を無効にしたりしなことをお勧めします。

Exchange Online で基本認証を無効にする方法の詳細については、「Exchange Online で基本認証を[無効にする」を参照してください](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)。

## <a name="hybrid-modern-authentication"></a>ハイブリッド最新の認証

オンプレミスの Exchange サーバーまたは Skype for Business サーバーに対する認証を確実に成功するには、Microsoft Teams Rooms で使用されるリソース アカウントが Azure AD から承認を取得するように構成されていることを確認する必要があります。

Teamsの認証フローは、認証の構成によって異なります。 マネージド ドメインを使用しているお客様の場合、Teams Rooms では、[OAuth 2.0 リソース](/azure/active-directory/develop/v2-oauth-ropc)所有者パスワード資格情報と一緒に Azure Active Directory。 ただし、フェデレーション ドメインを使用しているお客様の場合は、[OAuth 2.0 SAML Bearer Assertion](/azure/active-directory/develop/v2-saml-bearer-assertion) Flow使用されます。

> [!NOTE]
> ID プロバイダーは、特定の構成または設定が必要な場合があります。この構成または設定は、Azure Active DirectoryまたはOffice 365。 Teams Rooms での認証の構成に関するヘルプが必要な場合は、ID プロバイダーにお問い合わせください。


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>会議室に固有Microsoft Teams前提条件

ハイブリッド トポロジで最新の認証を有効にするための前提条件については、「ハイブリッド最新認証の概要」と「オンプレミスの Skype for Business および Exchange サーバーで使用するための前提条件」を[参照してください](/office365/enterprise/hybrid-modern-auth-overview)。 この記事で説明されている前提条件はすべて適用されます。

ただし、Microsoft Teams Rooms では、最新の認証[](https://tools.ietf.org/html/rfc6749#section-1.3.3)にリソース所有者のパスワード資格情報の承認と基になる REST API が使用されます。このため、Microsoft Teams Rooms に固有の点に注意する必要があります。

- 2016 CU8 以降Exchange Server、または 2019 CU1 以降Exchange Server必要があります。
- 2015 CU5 以降Skype for Business Server 2019 以降Skype for Business Server必要があります。
- MFA は、使用しているトポロジに関係なくサポートされていません。
- Microsoft Teams会議室では、SIP と UPN の不一致はサポートされていません。 同じ UPN Microsoft Teams SIP を持つ会議室アカウントを作成して、機能する必要があります。
- Azure AD でサポートされているサード パーティの認証プロバイダーを使用する場合は、WS-Trust を介したアクティブな認証フローをサポートする必要があります。
- アプリケーションで構成されたリソース アカウントには、デバイス レベルの条件付きアクセス ポリシーを使用しない。 そうすると、サインイン エラーが発生します。 代わりに、「Intune を使用した会議室Microsoft Intune Teamsの管理」で公開されているガイダンスを使用して、デバイスを Microsoft Intuneし、コンプライアンス ポリシー[を適用します](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。

### <a name="configure-exchange-server"></a>構成Exchange Server

ハイブリッドモダン認証を有効にするにはExchange Serverハイブリッド最新認証を使用Exchange Serverを構成する[方法に関するページを参照してください](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="configure-skype-for-business-server"></a>構成Skype for Business Server

Skype for Business Server を使用してハイブリッド最新の認証を有効にするには、ハイブリッド最新認証を使用Skype for Businessを構成する方法[に関するページを参照してください](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>削除または無効化Skype for Business削除Exchange

セットアップでハイブリッド最新認証が許可されていない場合、または Exchange または Skype for Business のハイブリッド最新認証を削除または無効にする必要がある場合は、「Skype for Business と Exchange からの[](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)ハイブリッド最新認証の削除または無効化」を参照してください。

### <a name="azure-ad-conditional-access"></a>Azure AD条件付きアクセス

IP/場所ベースのアクセス用に Microsoft Teams Rooms で使用されるリソース アカウントを構成できます。 詳細については、「条件付きアクセス [: 場所でアクセスをブロックする」を参照してください](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)。

その他の条件付きアクセス ポリシーはサポートされていません。 デバイスのコンプライアンスの詳細については、「Intune を使用した会議室Teams[管理する」を参照してください](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。
