---
title: "Microsoft のチームで認証との id モデル"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection: Strat_MT_TeamsAdmin
description: "クラウド、同期、フェデレーションなどの Microsoft チームで別のユーザーのモデルの概要について説明します。多要素認証についても説明します。"
ms.openlocfilehash: 706d1d0cddb9b2e7cb992b8825b18ac9661660dc
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Microsoft のチームで認証との id モデル
==========================================

Microsoft チームは、Office 365 で利用できるすべてのユーザー モデルをサポートします。サポートされる id モデルは次のとおりです。

-   **クラウドの Id**: このモデルでユーザーを作成し、Office 365 で管理し、Azure Active Directory に格納されている、Azure Active Directory でパスワードを確認します。

-   **同期の Id**: このモデルでユーザーをオンプレミス サーバーで管理して、アカウントとパスワード ハッシュが、クラウドに同期されます。クラウドで操作し、Azure Active Directory でのサインインにパスワードを確認、ユーザーは、同じパスワード内部設置型を入力します。このモデルでは、Microsoft Azure Active Directory 接続ツールを使用します。

-   **フェデレーション Id**: ユーザーのパスワードの同期の id が内部設置型の id プロバイダーによって検証が必要です。このモデルでは、パスワード ハッシュが Azure AD、同期する必要はありませんし、Active Directory フェデレーション サービス (ADFS) またはサード パーティの id プロバイダーを使用すると、に対して、オンプレミスの Active Directory のユーザーを認証します。

<a name="configurations"></a>構成
--------------

実装して使用するには、どのユーザー モデルの組織の意思決定によって実装要件が異なる場合があります。配置が、これらの前提条件を満たしていることを確認するのには、次の要件の表を参照してください。既に Office 365 を展開して、id と認証方法済みである場合は、次の手順をスキップできます。


|ユーザーのモデル |展開チェックリストを作成します。  |追加情報  |
|---------|---------|---------|
|すべて     |<ol type="1"><li>Office 365 プランのオプションを比較してサブスクリプションを取得するには.</li><li>Office 365 テナントを作成します。</li><li>テナントに Office 365 のライセンスを割り当てる</li><li>ドメインとユーザーの管理を構成します。</li><li>ユーザーのモデルの手順を続ける</li></ol>          |<ul style="list-style-type:none"><li>[Office 365 プランのオプション](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Office 365 ビジネス プランを比較します。](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Office 365 for business サブスクリプションのライセンスを購入します。](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[サブスクリプションにライセンスを追加します。](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[向けの Office 365 をセットアップします。](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[セットアップ ウィザードを使用してユーザーとドメインを追加します。](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>メモ: サポートが必要な場合は、 [Office 365 チーム用 Microsoft FastTrack](https://go.microsoft.com/fwlink/?linkid=854618)は支援するために使用します。</li></ul>          |
|クラウドの Id     |<ol type="1"><li>Office 365 管理ポータルを使用しているユーザーを作成します。</li></ol>           |<ul style="list-style-type:none"><li>[Office 365 にユーザーを個別に、またはまとめてに追加します。](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|同期の Id     |<ol type="1"><li>インストール Azure AD 接続します。</li><li>ディレクトリ同期を構成します。</li><li>オンプレミスの Active Directory の管理ツールを使用しているユーザーを作成します。</li></ol>         |<ul style="list-style-type:none"><li>[Office 365 のディレクトリ同期を設定します。](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>注意: 認証を実行する Office 365 のパスワード ハッシュを同期する必要があります。</li></ul>         |
|フェデレーション Id    |<ol type="1"><li>インストール Azure AD 接続します。</li><li>ディレクトリ同期を構成します。</li><li>インストールおよびフェデレーションの Id プロバイダーを (ADFS 推奨) を構成します。</li><li>オンプレミスの Active Directory の管理ツールを使用しているユーザーを作成します。</li></ol>           |<ul style="list-style-type:none"><li>[Office 365 のディレクトリ同期を設定します。](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[AD FS 展開を計画します。](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[展開する、フェデレーション サーバー ファームのチェックリストを作成します。](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[AD FS 向けエクストラネットのアクセスを構成します。](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[AD FS と Azure AD の信頼関係を設定します。](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[確認し、ADFS を使用したシングル サインオンを管理します。](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Azure AD フェデレーション互換性リスト](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>メモ: パスワード ハッシュは Azure Active Directory に同期する必要はありません。</li></ul>         |

詳細については、 [Office 365 のサインイン モデルを選択して](https://go.microsoft.com/fwlink/?linkid=854626)、[について Office 365 id と Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9)のガイドを参照してください。

<a name="multi-factor-authentication"></a>多要素認証 
----------------------------

Office 365 プランでは、多要素認証 (MFA) Office 365 サービスのユーザーのログインのセキュリティが強化されるをサポートします。For Office 365 MFA] では、ユーザーは、電話をかけ、テキスト メッセージ、またはユーザーのパスワードが正しく入力した後に、スマート フォン上のアプリ通知を確認する必要があります。この 2 つ目の認証要素が満たされると後でのみユーザーのサインインできます。

多要素認証 Microsoft チームを含むすべての Office 365 プランがサポートされます。Microsoft チームを含む Office 365 サブスクリプション プランについては、後述の「ライセンスの後で説明します。

Mfa は、ユーザーが登録されているとユーザーがサインインすると、次回メッセージが表示されるメッセージが表示されたら、2 番目の認証要素を設定するようにします。サポートされている認証の方法があります。


|テナントの種類  |MFA の 2 番目の要素の利用可能なオプション  |注記  |
|---------|---------|---------|
|**クラウドのみ**     |Office 365 用の MFA <ul><li>電話をかける</li><li>テキスト メッセージ</li><li>モバイル アプリの通知</li><li>モバイル アプリの検証コード</li></ul>        |[多要素認証を Office 365 の展開の計画](https://support.office.com/article/Plan-for-multi-factor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)         |
|**ハイブリッド セットアップ (同期済み] または [Id のフェデレーション モデル)**     |<ul><li>Office 365 用の MFA</li><li>Azure MFA モジュール (ADFS 統合)</li><li>物理または仮想スマート カード (ADFS 統合)</li></ul>         |注: その他の MFA ソリューションで利用できません[Azure AD フェデレーションと互換性のある Id プロバイダー](http://go.microsoft.com/fwlink/p/?LinkId=510953)         |
