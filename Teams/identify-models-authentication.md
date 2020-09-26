---
title: Microsoft Teams の id モデルと認証
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2020
ms.topic: reference
ms.service: msteams
ms.reviewer: anwara
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: クラウド限定やハイブリッドなど、Microsoft Teams のさまざまな id モデルについて説明します。 また、多要素認証についても説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 40a06ce75c3ae7a4f85eb1c93064ba3d80c13fc0
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277117"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Microsoft Teams の id モデルと認証

Microsoft Teams では、次のような Microsoft 365 および Office 365 で利用できるすべての id モデルをサポートしています。

- **クラウドのみ**: ユーザーアカウントは、Microsoft 365 または Office 365 で作成および管理され、Azure Active Directory (azure AD) に保存されます。 ユーザーのサインイン資格情報 (アカウント名とパスワード) は、Azure AD によって検証されます。

- **ハイブリッド**: ユーザーアカウントは、通常、オンプレミスの Active Directory ドメインサービス (AD DS) フォレストで管理されます。 資格情報の検証は、構成に応じて Azure AD、AD DS、またはフェデレーションされた id プロバイダーによって行うことができます。 このモデルでは、Azure AD Connect を使用して、AD DS から Azure AD へのディレクトリ同期を使用します。

詳細については、「 [Microsoft 365 id モデルと AZURE AD](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity)」を参照してください。

## <a name="configurations"></a>設定

使用している id モデルと構成に関する組織の決定に応じて、実装の手順は異なる場合があります。

まだ Microsoft 365 または Office 365 と id モデルを展開していない場合は、次の表を使用します。 

|ID モデル |展開チェックリスト  |その他の情報  |
|---------|---------|---------|
|すべて     |<ol type="1"><li>Microsoft 365 と Office 365 プランのオプションを比較して、サブスクリプションとテナントを取得します。</li><li>テナント用の Microsoft 365 または Office 365 組織を作成します。</li><li>テナントの Microsoft 365 または Office 365 ライセンスを購入する</li><li>ドメインと管理者のユーザーアカウントを構成します。</li></ol>  |<ul><li>[Office 365 プランのオプション](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Microsoft 365 for business プランの比較](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[サブスクリプションライセンスを購入または削除する](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[サブスクリプションにライセンスを追加する](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[一般法人向け Microsoft 365 のセットアップ](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[セットアップウィザードを使用してドメインを追加する](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) を使用すると、お客様のサポートを受けることができます。  |
|クラウド id     |<ul><li>Microsoft 365 管理センターを使用してユーザーアカウントを作成する</li></ul> |<ul style="list-style-type:none"><li>[ユーザーを追加してライセンスを割り当てる](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|ハイブリッド id     |<ol type="1"><li>Azure AD Connect をインストールします。</li><li>ディレクトリ同期を構成します。</li><li>AD DS ツールを使って、ユーザーとグループを管理します。</li></ol> |<ul style="list-style-type:none"><li>[ディレクトリ同期をセットアップする](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|フェデレーション認証によるハイブリッド id    |<ol type="1"><li>フェデレーションされた id プロバイダー (AD FS など) をインストールして構成します。</li><li>Azure AD Connect をインストールし、ディレクトリ同期とフェデレーション認証を構成します。</li><li>AD DS ツールを使って、ユーザーとグループを管理します。</li></ol> |<ul><li>[AD FS の配置を計画する](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[チェックリスト: フェデレーション サーバー ファームを配置する](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[AD FS に対してエクストラネット アクセスを構成する](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[AD FS と Azure AD の間の信頼を確立する](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[AD FS によるシングル サインオンを確認および管理する](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[ディレクトリ同期をセットアップする](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>複数要素の認証

パスワードは、コンピューターまたはオンラインサービスにサインインするための最も一般的な認証方法ですが、最も脆弱なパスワードでもあります。 ユーザーは、簡単なパスワードを選択して、同じパスワードを複数のコンピューターやサービスに対して複数のサインインに使用できます。 

サインインのセキュリティレベルをさらに高めるには、多要素認証 (MFA) を使用します。これには、パスワードと、次のような追加の検証方法の両方が必要です。

- ユーザーが確認コードを入力する必要がある電話に送信されるテキストメッセージ。
- 通話。
- Microsoft Authenticator スマートフォンアプリ。
- ハイブリッド id とフェデレーション認証で利用できるその他の方法。

MFA は、microsoft Teams を含む Microsoft 365 または Office 365 プランでサポートされています。 少なくとも、Teams サービス管理者のような [管理者の役割が割り当てら](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)れたアカウントには、MFA が必要であることを強くお勧めします。

また、MFA もユーザーにロールアウトする必要があります。 ユーザーが MFA に登録されると、次回サインインしたときに、追加の確認方法を設定するように求めるメッセージが表示されます。 

詳細については、「 [Microsoft 365 の多要素認証](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)」を参照してください。
