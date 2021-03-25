---
title: Microsoft Teams の ID モデルと認証
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
description: クラウド専用やハイブリッドなど、Microsoft Teams の異なる ID モデルについて説明します。 多要素認証について学習します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dff34a6a56294c8c62295e143f753777875bfbda
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112363"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Microsoft Teams の ID モデルと認証

Microsoft Teams は、Microsoft 365 および Office 365 で利用できるすべての ID モデルをサポートします。このモデルには次のものが含まれます。

- **クラウドのみ**: ユーザー アカウントは、Microsoft 365 または Office 365 で作成および管理され、Azure Active Directory (Azure AD) に保存されます。 ユーザーのサインイン資格情報 (アカウント名とパスワード) は、Azure アカウントによって検証AD。

- **ハイブリッド**: ユーザー アカウントは、通常、オンプレミスの Active Directory ドメイン サービス (AD DS) フォレストで管理されます。 構成によっては、Azure AD DS、AD ID プロバイダーによって資格情報の検証を実行できます。 このモデルでは、Azure AD Connect を使用して、AD DS から Azure AD同期を使用します。

詳細については [、Microsoft 365 ID モデル](/microsoft-365/enterprise/about-microsoft-365-identity)と Azure AD を参照してください。

## <a name="configurations"></a>設定

使用する ID モデルと構成に関する組織の決定に応じて、実装手順が異なる場合があります。

Microsoft 365 または Office 365 と ID モデルをまだ展開していない場合は、次の表を使用します。 

|ID モデル |展開チェックリスト  |その他の情報  |
|---------|---------|---------|
|すべて     |<ol type="1"><li>Microsoft 365 と Office 365 プランのオプションを比較し、サブスクリプションとテナントを取得します。</li><li>テナント用に Microsoft 365 Office 365 組織を作成します。</li><li>Microsoft 365 またはテナントOffice 365 ライセンスを購入する</li><li>ドメインと管理者ユーザー アカウントを構成します。</li></ol>  |<ul><li>[Office 365 プランのオプション](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</li><li>[Microsoft 365 for Business プランを比較する](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[サブスクリプション ライセンスを購入または削除する](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[サブスクリプションにライセンスを追加する](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[一ビジネス向け Microsoft 365 をセットアップする](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[セットアップ ウィザードでドメインを追加する](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack は](https://www.microsoft.com/fasttrack/microsoft-365) 、お客様の支援を受け取る場合に利用できます。  |
|クラウド ID     |<ul><li>Microsoft 365 管理センターでユーザー アカウントを作成する</li></ul> |<ul style="list-style-type:none"><li>[ユーザーを追加してライセンスを割り当てる](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|ハイブリッド ID     |<ol type="1"><li>Azure AD Connect をインストールします。</li><li>ディレクトリ同期を構成します。</li><li>DS ツールを使用してユーザー ADを管理します。</li></ol> |<ul style="list-style-type:none"><li>[ディレクトリ同期を設定する](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|フェデレーション認証を使用したハイブリッド ID    |<ol type="1"><li>フェデレーション ID プロバイダー (AD FS など) をインストールしてADします。</li><li>Azure ADをインストールし、ディレクトリ同期とフェデレーション認証を構成します。</li><li>DS ツールを使用してユーザー ADを管理します。</li></ol> |<ul><li>[AD FS の配置を計画する](/previous-versions/azure/azure-services/dn151324(v=azure.100))</li><li>[チェックリスト: フェデレーション サーバー ファームを配置する](/previous-versions/azure/azure-services/dn528856(v=azure.100))</li><li>[AD FS に対してエクストラネット アクセスを構成する](/previous-versions/azure/azure-services/dn528859(v=azure.100))</li><li>[AD FS と Azure AD の間の信頼を確立する](/previous-versions/azure/azure-services/jj205461(v=azure.100))</li><li>[AD FS によるシングル サインオンを確認および管理する](/previous-versions/azure/azure-services/jj151809(v=azure.100))</li><li>[ディレクトリ同期を設定する](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>複数要素の認証

パスワードは、コンピューターまたはオンライン サービスにサインインする最も一般的な認証方法ですが、最も脆弱なパスワードです。 ユーザーは簡単なパスワードを選択し、異なるコンピューターやサービスへの複数のサインインに同じパスワードを使用できます。 

サインインにさらにレベルのセキュリティを提供するには、多要素認証 (MFA) を使用します。この場合は、パスワードと次のような追加の確認方法の両方が必要です。

- ユーザーが確認コードを入力する必要がある電話に送信されたテキスト メッセージ。
- 電話。
- Microsoft Authenticator スマート フォン アプリ。
- ハイブリッド ID とフェデレーション認証で使用できるその他の方法。

MFA は、Microsoft Teams を含む Microsoft 365 Office 365 プランでサポートされます。 管理者ロールが割り当てられているアカウント (Teams サービス管理者など)[](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)には、少なくとも MFA が必要です。

MFA をユーザーにロールアウトする必要があります。 ユーザーが MFA に登録された後、次回サインインすると、追加の認証方法のセットアップを求めるメッセージが表示されます。 

詳細については [、「Microsoft 365 の多要素認証」を参照してください](/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)。