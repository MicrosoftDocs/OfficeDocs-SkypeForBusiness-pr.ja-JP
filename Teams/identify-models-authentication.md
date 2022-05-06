---
title: Microsoft Teamsの ID モデルと認証
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2020
ms.topic: reference
ms.service: msteams
ms.reviewer: anwara
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: クラウド専用やハイブリッドなど、Microsoft Teamsのさまざまな ID モデルについて説明します。 多要素認証についても説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c12e7242241c8c6d7ac03bc3c66804198acd746e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836065"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Microsoft Teamsの ID モデルと認証

Microsoft Teamsは、Microsoft 365とOffice 365で使用できるすべての ID モデルをサポートします。これには次のものがあります。

- **クラウド専用**: ユーザー アカウントは、Microsoft 365またはOffice 365で作成および管理され、Azure Active Directory (Azure AD) に格納されます。 ユーザー サインイン資格情報 (アカウント名とパスワード) は、Azure ADによって検証されます。

- **ハイブリッド**: ユーザー アカウントは通常、オンプレミスの Active Directory Domain Services (AD DS) フォレストで管理されます。 構成に応じて、資格情報の検証は、Azure AD、AD DS、またはフェデレーション ID プロバイダーによって行うことができます。 このモデルでは、AD DS から Azure AD Connect を使用してAzure ADするディレクトリ同期が使用されます。

詳細については、「[Microsoft 365 ID モデルとAzure AD」を](/microsoft-365/enterprise/about-microsoft-365-identity)参照してください。

## <a name="configurations"></a>設定

使用する ID モデルと構成の組織の決定に応じて、実装手順が異なる場合があります。

Microsoft 365またはOffice 365と ID モデルをまだデプロイしていない場合は、次の表を使用します。 

|ID モデル |展開チェックリスト  |その他の情報  |
|---------|---------|---------|
|すべて     |<ol type="1"><li>Microsoft 365とOffice 365プランのオプションを比較し、サブスクリプションとテナントを取得します。</li><li>テナントのMicrosoft 365またはOffice 365組織を作成します。</li><li>テナントのMicrosoft 365ライセンスまたはOffice 365 ライセンスを購入する</li><li>ドメインと管理者ユーザー アカウントを構成します。</li></ol>  |<ul><li>[Office 365プラン オプション](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</li><li>[ビジネス プランのMicrosoft 365を比較する](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[サブスクリプション ライセンスを購入または削除する](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[サブスクリプションにライセンスを追加する](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[ビジネス向けのMicrosoft 365を設定する](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[セットアップ ウィザードを使用してドメインを追加する](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365)は、お手伝いします。  |
|クラウド ID     |<ul><li>Microsoft 365 管理センターを使用してユーザー アカウントを作成する</li></ul> |<ul><li>[ユーザーの追加とライセンスの割り当て](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|ハイブリッド ID     |<ol type="1"><li>Azure AD Connectをインストールします。</li><li>ディレクトリ同期を構成します。</li><li>AD DS ツールを使用してユーザーとグループを管理します。</li></ol> |<ul><li>[ディレクトリ同期を設定する](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|フェデレーション認証を使用したハイブリッド ID    |<ol type="1"><li>AD FS などのフェデレーション ID プロバイダーをインストールして構成します。</li><li>Azure AD Connectをインストールし、ディレクトリ同期とフェデレーション認証を構成します。</li><li>AD DS ツールを使用してユーザーとグループを管理します。</li></ol> |<ul><li>[AD FS の配置を計画する](/previous-versions/azure/azure-services/dn151324(v=azure.100))</li><li>[チェックリスト: フェデレーション サーバー ファームを配置する](/previous-versions/azure/azure-services/dn528856(v=azure.100))</li><li>[AD FS に対してエクストラネット アクセスを構成する](/previous-versions/azure/azure-services/dn528859(v=azure.100))</li><li>[AD FS と Azure AD の間の信頼を確立する](/previous-versions/azure/azure-services/jj205461(v=azure.100))</li><li>[AD FS によるシングル サインオンを確認および管理する](/previous-versions/azure/azure-services/jj151809(v=azure.100))</li><li>[ディレクトリ同期を設定する](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>複数要素の認証

パスワードは、コンピューターまたはオンライン サービスにサインインするための最も一般的な認証方法ですが、最も脆弱です。 ユーザーは簡単なパスワードを選択し、異なるコンピューターやサービスへの複数のサインインに同じパスワードを使用できます。 

サインインのセキュリティを強化するには、多要素認証 (MFA) を使用します。これには、パスワードと次のような追加の検証方法の両方が必要です。

- ユーザーが確認コードを入力する必要がある電話に送信されるテキスト メッセージ。
- 電話。
- Microsoft Authenticatorスマートフォン アプリ。
- ハイブリッド ID とフェデレーション認証で使用できるその他の方法。

MFA は、Microsoft Teamsを含む任意のMicrosoft 365またはOffice 365プランでサポートされます。 少なくとも、サービス[管理者などの管理者ロールが割り当てられている](/microsoft-365/admin/add-users/about-admin-roles)アカウントには MFA が必要Teams強くお勧めします。

また、MFA をユーザーにロールアウトする必要もあります。 ユーザーが MFA に登録されると、次回サインインすると、追加の確認方法の設定を求めるメッセージが表示されます。 

詳細については、「[Microsoft 365の多要素認証」を](/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)参照してください。