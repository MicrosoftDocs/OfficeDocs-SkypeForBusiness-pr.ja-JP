---
title: Microsoft Teams での ID モデルと認証
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: クラウド、同期済み、フェデレーションなど、Microsoft Teams のさまざまな ID モデルを紹介します。また、多要素認証についても紹介します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34e70313d83bfa7873e990a2d77bc165dfd8dfbe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234939"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Microsoft Teams での ID モデルと認証
==========================================

Microsoft Teams は、Office 365 で利用できるすべての ID モデルをサポートしています。サポート対象の ID モデルには次のものがあります。

-   **クラウド ID**: このモデルでは、ユーザーは Office 365 で作成、管理され、Azure Active Directory に保存されます。パスワードは Azure Active Directory によって確認されます。

-   **同期された ID**: このモデルでは、ユーザー ID はオンプレミス サーバーで管理され、アカウントとパスワードのハッシュはクラウドに同期されます。ユーザーは、クラウドの場合と同様にオンプレミスで同じパスワードを入力し、サインイン時にパスワードが Azure Active Directory によって確認されます。このモデルでは、Microsoft Azure Active Directory Connect ツールが使用されます。

-   **フェデレーション ID**: このモデルでは、ユーザー パスワードと同期済みの ID がオンプレミスの ID プロバイダーにより確認されることが要求されます。このモデルを使用する場合、パスワードのハッシュは Azure AD に同期される必要はなく、Active Directory フェデレーション サービス (ADFS) またはサードパーティの ID プロバイダーを使用してオンプレミスの Active Directory に対するユーザー認証が行われます。

<a name="configurations"></a>設定
--------------

組織がどの ID モデルを実装および使用するかに応じて、実装の要件は変わります。以下の要件を参照して、目的の展開が前提条件を満たしていることを確認してください。展開済みの Office 365 があり、ID および認証方法を実装・実行済みの場合は、以下の手順を省略できます。


|ID モデル |展開チェックリスト  |その他の情報  |
|---------|---------|---------|
|すべて     |<ol type="1"><li>Office 365 プランのオプションの比較、サブスクリプションの入手</li><li>Office 365 テナントの作成</li><li>テナントへの Office 365 ライセンスの割り当て</li><li>ドメインおよび管理者ユーザーの設定</li><li>引き続き ID モデル固有の手順の実施</li></ol>          |<ul style="list-style-type:none"><li>[Office 365 プランのオプション](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Office 365 ビジネス プランの比較](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[一般法人向け Office 365 サブスクリプションのライセンスを購入する](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[サブスクリプションにライセンスを追加する](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[一般法人向け Office 365 のセットアップ](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[セットアップ ウィザードでユーザーとドメインを追加する](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>注意: サポートが必要な場合は、[Microsoft FastTrack for Office 365 team](https://go.microsoft.com/fwlink/?linkid=854618)を参照してください。</li></ul>          |
|クラウド ID     |<ol type="1"><li>Office 365 管理ポータルを使用したユーザーの作成</li></ol>           |<ul style="list-style-type:none"><li>[Office 365 にユーザーを個別に、またはまとめて追加する](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|同期された ID     |<ol type="1"><li>Azure AD Connect のインストール</li><li>ディレクトリ同期の設定</li><li>オンプレミスの Active Directory 管理ツールを使用したユーザーの作成</li></ol>         |<ul style="list-style-type:none"><li>[Office 365 のディレクトリ同期をセットアップする](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>注意: 認証を実行する場合、パスワードのハッシュを Office 365 に同期させる必要があります。</li></ul>         |
|フェデレーション ID    |<ol type="1"><li>Azure AD Connect のインストール</li><li>ディレクトリ同期の設定</li><li>フェデレーション ID プロバイダーのインストールと設定 (ADFS 推奨)</li><li>オンプレミスの Active Directory 管理ツールを使用したユーザーの作成</li></ol>           |<ul style="list-style-type:none"><li>[Office 365 のディレクトリ同期をセットアップする](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[AD FS の配置を計画する](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[チェックリスト: フェデレーション サーバー ファームを配置する](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[AD FS に対してエクストラネット アクセスを構成する](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[AD FS と Azure AD の間の信頼を確立する](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[AD FS によるシングル サインオンを確認および管理する](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Azure AD のフェデレーション互換性リスト](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>注意: パスワードのハッシュは Azure Active Directory に同期させる必要はありません。</li></ul>         |

詳細については、[Choosing a sign-in model for Office 365 (Office 365 のサインイン モデルを選ぶ)](https://go.microsoft.com/fwlink/?linkid=854626)および[Office 365 ID と Azure Active Directory について](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9)を参照してください。

<a name="multi-factor-authentication"></a>複数要素の認証
----------------------------

Office 365 プランでは、Office 365 サービスへのユーザー ログインのセキュリティを高める多要素認証 (MFA) をサポートしています。Office 365 の MFA では、ユーザーはパスワードを正しく入力した後に、自分のスマートフォンで電話、テキスト メッセージ、またはアプリの通知を承認します。この 2 番目の認証要素が満たされた後に、ユーザーはサイン インできるようになります。

多要素認証は、Microsoft Teams が含まれている任意の Office 365 プランでサポートされています。 Microsoft Teams を含む Office 365 サブスクリプションプランについては、後の「ライセンス」セクションで説明します。

MFA に登録したユーザーは、次回のサインイン時に、2 番目の認証要素を設定するよう求めるメッセージが表示されます。サポートされる認証方法は次のとおりです。


|テナント タイプ  |MFA の 2 番目の要素に関する利用可能なオプション  |メモ  |
|---------|---------|---------|
|**クラウドのみ**     |Office 365 の MFA <ul><li>電話</li><li>テキスト メッセージ</li><li>モバイル アプリへの通知</li><li>モバイル アプリの確認コード</li></ul>        |[Office 365 展開用の多要素認証の計画](https://support.office.com/article/Plan-for-multi-factor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)         |
|**ハイブリッド セットアップ (同期済みまたはフェデレーション ID モデル)**     |<ul><li>Office 365 の MFA</li><li>Azure MFA モジュール (ADFS 統合)</li><li>物理または仮想スマート カード (ADFS 統合)</li></ul>         |注意: その他の MFA ソリューションは、[Identity providers that are compatible with Azure AD federation (Azure AD との互換性がある ID プロバイダー)](https://go.microsoft.com/fwlink/p/?LinkId=510953) で確認できます。         |
