---
title: Microsoft Teams の会議室での認証
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
description: Microsoft Teams 会議室の最新の認証を構成する方法について説明します。
ms.openlocfilehash: 41a65743e5da851dd8e0197e9382deaf696cd9ec
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662582"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft Teams の会議室での認証

Microsoft Teams Rooms デバイスのアカウント管理は、アプリケーション レベルで処理されます。 アプリケーションは Microsoft Teams、Skype for Business、Exchange に接続し、通話と会議のエクスペリエンスを有効にする会議室アカウントのリソースを取得します。 デバイスは、常にオンの機能、通話シナリオ (通話プランで構成されたデバイス)、およびこれらのデバイスに実装されるカスタム ロックダウン メカニズムを許可するように、アカウントに依存しません。 つまり、これらのデバイスの認証は、エンド ユーザーのデバイスとは異なる方法で行います。  

Microsoft 365 または Office 365 で Microsoft Teams Rooms デバイスを使用しているすべてのお客様に対して、最新の認証をお勧めします。 Exchange サーバーまたは Skype for Business サーバーのオンプレミス展開がある場合は[](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)、Azure Active Directory (Azure AD) を使用してハイブリッドモダン認証を構成して、最新の認証を有効にします。

最新の認証は、Microsoft Teams Rooms バージョン 4.4.25.0 以降でサポートされています。

## <a name="modern-authentication"></a>先進認証

Microsoft Teams Rooms アプリケーションで最新の認証を使用する場合、Microsoft Teams、Exchange、Skype for Business に接続するために Active Directory 認証ライブラリ (ADAL) が使用されます。 Microsoft Teams Rooms デバイスは共有デバイスであり、夜間の再起動を実行してスムーズに機能し、重要なオペレーティング システム、ドライバー、ファームウェア、またはアプリケーションの更新プログラムを取得します。 最新の認証メカニズムでは、OAuth 2.0 のリソース所有者パスワード資格情報承認付与タイプを使用します。これはユーザーの介入を必要としません。 [](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) これは、ユーザー アカウントと Microsoft Teams Rooms アプリケーションで使用されるリソース アカウントの間で、最新の認証のしくみの主な違いの 1 つです。 このため、Microsoft Teams Rooms リソース アカウントは、多要素認証 (MFA)、スマート カード認証、またはクライアント証明書ベースの認証 (すべてエンド ユーザーが使用できる) を使用するように構成する必要はありません。

Microsoft Teams Rooms デバイスとエンド ユーザー デバイスでの最新の認証のしくみのもう 1 つの主な違いは、リソース アカウントを使用して、Azure Active Directory と Endpoint Manager でデバイス情報としてデバイスレベルの条件付きアクセス ポリシーを適用できないという点です。 代わりに、Intune での Teams 会議室の管理に関するガイダンスを使用して、デバイスを Microsoft Endpoint Manager に登録し、コンプライアンス ポリシー [を適用できます](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Microsoft Teams Rooms デバイスで最新の認証を有効にする

Microsoft Teams の会議室で Skype for Business と Exchange で最新の認証を使用するには、Microsoft Teams Rooms デバイスでクライアント側の設定で最新の認証を有効にします。 これは、デバイスの設定または XML 構成ファイルで行います。

> [!NOTE]
> クライアント側の設定で最新の認証を有効にする前に、環境が最新の認証を使用するように正しく設定されていることを確認します。

### <a name="using-device-settings"></a>デバイス設定を使用する

1. Microsoft チーム ルーム デバイスで、[その **他]** **(... ) に移動します**。
    
2. [ **設定]** を選び、デバイス管理者のユーザー名とパスワードを入力します。
3. [アカウント] タブ **に移動** し、最新の認証 **を有効** にし、[保存して終了] **を選択します**。

### <a name="using-the-xml-config-file"></a>XML 構成ファイルの使用

このファイルSkypeSettings.xml、次のように、最新の認証 XML 要素を **True** に設定します。

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

設定を適用するには、「XML 構成ファイルを使用して Microsoft Teams Rooms 本体の設定をリモート [で管理する」を参照してください](xml-config-file.md)。

## <a name="prepare-your-environment-for-modern-authentication"></a>環境をモダン認証用に準備する

始める前に、Office 365 および Azure AD で使用する ID モデルを理解してください。 Office 365 ID モデルと [Azure Active Directory、および Microsoft 365](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) または Office [365](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization)のハイブリッド ID とディレクトリ同期に関する詳細を確認できます。

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Microsoft 365 または Office 365 で最新の認証を有効にする

Exchange Online の最新の認証を有効にする方法については、「Exchange Online で最新の認証を有効にする」を [参照してください](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)。 Skype for Business Online を使用する場合は、Skype for Business Online で最新の認証が有効になっていることを確認する必要があります。 詳細については [、「Skype for Business Online: テナントの最新の認証を有効にする」を参照してください](https://aka.ms/SkypeModernAuth)。

Microsoft Teams Rooms デバイスが Exchange Online、Teams、Skype for Business Online で正常にサインインできると検証するまでは、Exchange Online の基本認証ポリシーを削除したり、テナントの基本認証を無効にしたりしない方法をお勧めします。

Exchange Online での基本認証の無効化の詳細については、「Exchange Online で基本認証を無効にする」を [参照してください](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)。

## <a name="hybrid-modern-authentication"></a>ハイブリッドモダン認証

オンプレミスの Exchange サーバーまたは Skype for Business サーバーに対して認証を成功するには、Microsoft Teams Rooms で使用されるリソース アカウントが Azure AD から認証を取得するように構成されていることを確認する必要があります。 

Teams 会議室の認証フローは、認証構成によって異なります。 管理ドメインを使用しているお客様の場合、Teams Rooms は Azure Active Directory で [OAuth 2.0 リソース](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) 所有者パスワード資格情報を使用します。 ただし、フェデレーション ドメインを使用しているお客様の [場合は、OAuth 2.0 SAML Bearer Assertion Flow が](https://docs.microsoft.com/azure/active-directory/develop/v2-saml-bearer-assertion) 使用されます。

> [!NOTE]
> ID プロバイダーは、Azure Active Directory または 365 との統合に特定の構成またはOffice場合があります。 Teams 会議室での認証の構成に関するヘルプが必要な場合は、ID プロバイダーにお問い合わせください。


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Microsoft Teams の会議室に固有の前提条件

ハイブリッド トポロジでモダン認証を有効にする前提条件については、ハイブリッドモダン認証の概要と、オンプレミスの Skype for Business サーバーと Exchange サーバーで使用するための前提条件について [説明します](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)。 この記事で説明しているすべての前提条件が適用されます。

ただし、Microsoft Teams Rooms[](https://tools.ietf.org/html/rfc6749#section-1.3.3)では、最新の認証にリソース所有者のパスワード資格情報の承認と基になる REST API が使用されます。Microsoft Teams Rooms に固有の重要な違いは次のとおりです。

- 2016 CU8 以降Exchange Server 2019 CU1 以降Exchange Serverが必要です。
- Skype for Business Server 2015 CU5 以降、または Skype for Business Server 2019 以降が必要です。
- MFA は、トポロジに関係なくサポートされません。
- Microsoft Teams Rooms では、SIP と UPN の不一致はサポートされていません。 動作するには、同じ UPN と SIP で Microsoft Teams Rooms アカウントを作成する必要があります。
- Azure AD でサポートされているサード パーティ認証プロバイダーを使用する場合は、WS-Trust を介したアクティブな認証フローをサポートする必要があります。
- アプリケーションで構成されたリソース アカウントに対して、デバイス レベルの条件付きアクセス ポリシーを使用しない。 サインインすると、サインインエラーが発生します。 代わりに、デバイスを Microsoft Intune に登録し、「Intune で Teams 会議室を管理する」で公開されているガイダンスを使用してコンプライアンス ポリシー [を適用します](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。

### <a name="configure-exchange-server"></a>構成Exchange Server

Exchange Server でハイブリッドモダン認証を有効にするには、「ハイブリッドモダン認証を使用Exchange Serverを構成する方法 [」を参照してください](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="configure-skype-for-business-server"></a>Skype for Business Server を構成する

Skype for Business Server でハイブリッドモダン認証を有効にするには、「ハイブリッドモダン認証を使用するために Skype for Business をオンプレミスで構成する方法 [」を参照してください](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)。

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>Skype for Business と Exchange を削除または無効にする

セットアップでハイブリッドモダン認証が許可されていない場合、または Exchange または Skype for Business のハイブリッドモダン認証を削除または無効化する必要がある場合は [、「Skype for Business](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)と Exchange からハイブリッドモダン認証を削除または無効化する」を参照してください。

### <a name="azure-ad-conditional-access"></a>Azure AD条件付きアクセス

IP/場所ベースのアクセス用に Microsoft Teams Rooms で使用するリソース アカウントを構成できます。 詳細については、「条件付きアクセス [: 場所によるアクセスのブロック」を参照してください](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location)。

その他の条件付きアクセス ポリシーはサポートされません。 デバイスのコンプライアンスの詳細については、「Intune で Teams 会議室を管理する」 [を参照してください](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)。  
