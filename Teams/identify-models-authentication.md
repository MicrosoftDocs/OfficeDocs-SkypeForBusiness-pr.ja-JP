---
title: Id モデルと認証
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: クラウド、同期済み、フェデレーションなど、Microsoft Teams のさまざまな ID モデルを紹介します。また、多要素認証についても紹介します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ccddd3bacdd495fb6febb11871d6d501f0a666b
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637206"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Microsoft Teams での ID モデルと認証
==========================================

Microsoft Teams では、Microsoft 365 および Office 365 で利用できるすべての id モデルをサポートしています。 サポートされている id モデルは次のとおりです。

-   **クラウド id**: このモデルでは、ユーザーが Microsoft 365 または Office 365 で作成および管理され、Azure active directory に保存されて、パスワードが Azure active directory によって確認されます。

-   **同期された ID**: このモデルでは、ユーザー ID はオンプレミス サーバーで管理され、アカウントとパスワードのハッシュはクラウドに同期されます。ユーザーは、クラウドの場合と同様にオンプレミスで同じパスワードを入力し、サインイン時にパスワードが Azure Active Directory によって確認されます。このモデルでは、Microsoft Azure Active Directory Connect ツールが使用されます。

-   **フェデレーション ID**: このモデルでは、ユーザー パスワードと同期済みの ID がオンプレミスの ID プロバイダーにより確認されることが要求されます。このモデルを使用する場合、パスワードのハッシュは Azure AD に同期される必要はなく、Active Directory フェデレーション サービス (ADFS) またはサードパーティの ID プロバイダーを使用してオンプレミスの Active Directory に対するユーザー認証が行われます。

<a name="configurations"></a>設定
--------------

実装および使用する id モデルに関する組織の決定に応じて、実装の要件は異なる場合があります。 以下の要件の表を参照して、展開がこれらの前提条件を満たしていることを確認します。 既に Microsoft 365 または Office 365 を展開していて、id と認証の方法を既に実装している場合は、次の手順をスキップできます。


|ID モデル |展開チェックリスト  |その他の情報  |
|---------|---------|---------|
|すべて     |<ol type="1"><li>Microsoft 365 と Office 365 プランのオプションを比較してサブスクリプションを取得する</li><li>Microsoft 365 または Office 365 組織を作成する</li><li>テナントに Microsoft 365 または Office 365 ライセンスを割り当てる</li><li>ドメインおよび管理者ユーザーの設定</li><li>引き続き ID モデル固有の手順の実施</li></ol>          |<ul style="list-style-type:none"><li>[Microsoft 365 および Office 365 プランのオプション](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[一般法人向け Microsoft 365 アプリの比較](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[サブスクリプションライセンスを管理する](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[サブスクリプションにライセンスを追加する](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[一般法人向け Microsoft 365 のセットアップ](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[セットアップ ウィザードでユーザーとドメインを追加する](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>注: サポートが必要な場合は、 [Microsoft FastTrack](https://go.microsoft.com/fwlink/?linkid=854618)を使用してサポートを受けることができます。</li></ul>          |
|クラウド ID     |<ol type="1"><li>Microsoft 365 管理センターを使用してユーザーを作成する</li></ol>           |<ul style="list-style-type:none"><li>[ユーザーを個別に、またはまとめて追加する](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|同期された ID     |<ol type="1"><li>Azure AD Connect のインストール</li><li>ディレクトリ同期の設定</li><li>オンプレミスの Active Directory 管理ツールを使用したユーザーの作成</li></ol>         |<ul style="list-style-type:none"><li>[ディレクトリ同期をセットアップする](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>注: 認証を実行するには、パスワードハッシュが Microsoft 365 および Office 365 で同期されている必要があります。</li></ul>         |
|フェデレーション ID    |<ol type="1"><li>Azure AD Connect のインストール</li><li>ディレクトリ同期の設定</li><li>フェデレーション ID プロバイダーのインストールと設定 (ADFS 推奨)</li><li>オンプレミスの Active Directory 管理ツールを使用したユーザーの作成</li></ol>           |<ul style="list-style-type:none"><li>[ディレクトリ同期をセットアップする](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[AD FS の配置を計画する](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[チェックリスト: フェデレーション サーバー ファームを配置する](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[AD FS に対してエクストラネット アクセスを構成する](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[AD FS と Azure AD の間の信頼を確立する](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[AD FS によるシングル サインオンを確認および管理する](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Azure AD のフェデレーション互換性リスト](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>注意: パスワードのハッシュは Azure Active Directory に同期させる必要はありません。</li></ul>         |

追加情報については、 [「サインインモデルを選択](https://go.microsoft.com/fwlink/?linkid=854626)する」と「 [Id モデルと Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9)ガイドについて」を参照してください。

<a name="multi-factor-authentication"></a>複数要素の認証
----------------------------

Microsoft 365 および Office 365 プランは、ユーザーログインのセキュリティを強化する多要素認証 (MFA) をサポートしています。 MFA を使用して、ユーザーは、パスワードを正しく入力した後に、スマートフォンでの電話、テキストメッセージ、またはアプリの通知について同意する必要があります。 この2番目の認証ファクターが満たされた後にのみ、ユーザーはサインインできます。

多要素認証は、microsoft Teams を含む Microsoft 365 または Office 365 プランでサポートされています。 Microsoft Teams を含むサブスクリプションプランについては、後の「ライセンス」セクションで説明します。

ユーザーが MFA に登録されると、次回ユーザーがサインインしたときに、第2の認証要素を設定するように求めるメッセージが表示されます。 サポートされている認証方法は次のとおりです。


|テナント タイプ  |MFA の 2 番目の要素に関する利用可能なオプション  |メモ  |
|---------|---------|---------|
|**クラウドのみ**     |Microsoft 365 および Office 365 の MFA <ul><li>電話</li><li>テキスト メッセージ</li><li>モバイル アプリへの通知</li><li>モバイル アプリの確認コード</li></ul>        |[Microsoft 365 展開用の多要素認証の計画](https://support.office.com/article/Plan-for-multi-factor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)         |
|**ハイブリッド セットアップ (同期済みまたはフェデレーション ID モデル)**     |<ul><li>Microsoft 365 および Office 365 の MFA</li><li>Azure MFA モジュール (ADFS 統合)</li><li>物理または仮想スマート カード (ADFS 統合)</li></ul>         |注: 追加の MFA ソリューションは、 [AZURE AD Id プロバイダーの互換性](https://www.microsoft.com/download/details.aspx?id=56843)に関するドキュメントで利用できます。         |
