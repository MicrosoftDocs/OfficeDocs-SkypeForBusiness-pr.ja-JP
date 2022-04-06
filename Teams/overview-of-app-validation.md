---
title: Microsoft によるアプリの検証とアプリ テストの概要
ms.reviewer: ''
description: Teams アプリの品質チェック、アプリ検証、認定プログラムについて理解します。
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9accce27ded20f8ce78d4d5b80f6aff474213675
ms.sourcegitcommit: c2a77ef9c1c9e6f00b3a4589bf02b100c37f5801
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2022
ms.locfileid: "64649026"
---
# <a name="checks-and-validation-performed-by-microsoft-on-teams-apps"></a>Teams アプリで Microsoft によって実行されるチェックと検証

Microsoft では、エンド 用途のためにストアに一覧表示される前に、すべてのアプリが必須の検証に合格する必要があります。 これは、Teams アプリ ストアで公開されたすべてのアプリ (カスタム アプリを除く) に適用されます。 さらに、Microsoft は、アプリ開発者に対して、コンプライアンス、セキュリティ、およびプライバシーの制御の強化を示すアプリのオプションの認定に参加することを強くお勧めします。

すべてのアプリは、Microsoft アプリ認定ポリシーに準拠する必要があります。 Teams ストア チームは、アプリが使用可能で、高いプライバシーとセキュリティの基準に準拠していることを確認するために、400 を超えるテストを実行します。

アプリ開発者が準拠する詳細な検証ガイドラインについては、 [開発者の検証ガイドラインに関するページを](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)参照してください。

> [!NOTE]
> Microsoft による検証とチェックは、組織内で開発され、組織のメンバーのみが使用できるため、カスタム アプリでは使用できません。

<!--- TBD: Add the link later. 
To review the certification policies of any app, see [App certification policies]().
Is the link /microsoft-365-app-certification/teams/teams-apps
--->

## <a name="app-validation-and-testing"></a>アプリの検証とテスト

Teams ストアで利用可能にする前に、すべてのアプリに対して 400 を超えるテスト ケースを実行します。 テストでは、適切な機能、ユーザー エクスペリエンス、およびセキュリティが保証され、すべてのアプリが一般公開されている CMO ポリシーに準拠していることを確認します。 発行前に、すべてのアプリに対して Microsoft App Validation チームによって実行されるテストの一部を次に示します。

* アプリによって要求されるGraphアクセス許可が、アプリの機能に必要なアクセス許可であり、追加のアクセス許可でないことを確認します。 既存のアプリのGraphアクセス許可は定期的にチェックされ、アプリで追加のアクセス許可が必要とされないようにします。
* ユーザーにログイン/サインインを要求するアプリには、ログ/サインアウト オプションが必要です。
* すべてのアプリ発行元は、Microsoft パートナー センターで詳細な検証プロセスを受けます。 確認には、電子メールの確認、ビジネスの確認などが含まれます。 アプリの発行の詳細については、「 [開発者がパートナー センター アカウントを作成する方法](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account)」、 [開発者向けの提出ガイド](/office/dev/store/add-in-submission-guide)、および [開発者がアプリを発行する方法に関するページを](https://aka.ms/PublishToTeamsStore)参照してください。
* エンド ユーザーにGraphアクセス許可を求めることができるのは、検証済みの発行元のアプリのみです。
* 実行可能ファイルをダウンロードできるアプリはありません。
* アプリに広告が含まれていないかテストされ、他のアプリのプロモーション
* アプリは、攻撃的な言語、サイバー攻撃ボット、スパム、または詐欺コンテンツなしで適切に動作することがテストされます。
* アプリ内のすべてのリンクは機能しており、アプリオファリングにのみ関連しています。
* アプリ ストアの正常性チェックの一環として、発行されたすべてのTeams アプリを定期的にテストして評価します。
* Teams アプリを対象とするプライバシー ポリシーと使用条件は、ISV によって公開されます
* ISV の連絡先の詳細は、ストアの登録情報とそれぞれの[Publisher構成証明ページで](/microsoft-365-app-certification/teams/teams-apps)入手できます。

## <a name="publisher-verification"></a>Publisher検証

Publisher検証は、管理者とエンド ユーザーがMicrosoft ID プラットフォームと統合するアプリケーション開発者の信頼性を理解するのに役立ちます。 発行元が検証済みである場合は、発行元が Microsoft パートナー ネットワーク (MPN) アカウントを使用して ID を確認し、この MPN アカウントをアプリ登録に関連付けたことを意味します。

Publisher検証には、次の利点があります。

* 顧客の透明性の向上とリスクの軽減 - この機能は、組織で使用されているアプリが信頼できる開発者によって公開されているかを顧客が理解するのに役立ちます。
* ブランドの強化 - `verified` Azure Active Directory同意プロンプト、Enterprise アプリ ページ、エンド ユーザーと管理者が使用するその他のユーザー インターフェイスにバッジが表示されます。
* よりスムーズなエンタープライズ導入 - 管理者は、パブリッシャーの検証状態をプライマリ ポリシー条件として使用して、ユーザー同意ポリシーを構成できます。

さらに、Microsoft はアプリ開発者に対し、アプリの品質、セキュリティ、コンプライアンスを確保するための厳格で 2 層のアプローチであるコンプライアンス プログラムに参加することをお勧めします。 Teams ストアには、既に詳細な検証ガイドラインを満たすだけでなく、これらのプログラムに準拠する何百ものアプリがあります。

## <a name="microsoft-365-app-compliance-program"></a>Microsoft 365 アプリ コンプライアンス プログラム

Microsoft コンプライアンス プログラムは、主要な業界標準フレームワークから派生したコントロールに対してアプリが審査され、顧客データを保護するために強力なセキュリティとコンプライアンスプラクティスが実施されていることを示しています。 このプログラムには、次の 2 つのフェーズがあります。

* 構成証明をPublisherします。
* Microsoft 365認定。

### <a name="publisher-attestation"></a>Publisher構成証明

アプリ開発者は、アプリのセキュリティとコンプライアンスを評価するときに、顧客または IT 管理者からよく寄せられる質問を含む自己評価を完了する必要があります。 その後、Microsoft は、この情報を公開して、より簡単でタイムリーな評価を行います。 この情報には、組織でアプリがアクティブ化されたときのデータ処理、セキュリティ、コンプライアンス、プライバシーに関する詳細が含まれます。

詳細については、 [発行構成証明ガイド](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide)を参照してください。

### <a name="microsoft-365-certification"></a>Microsoft 365認定

アプリ認定は、アプリのセキュリティとコンプライアンスのフレームワーク、プロセス、および手順を中心とした包括的な評価の認定アナリストによるレビューと承認を通じて達成されます。 このアプリは、業界の主要なフレームワークから派生した一連のセキュリティ制御に対して審査されます。 証明書は、アプリが組織でアクティブ化されたときに、顧客データを保護するために強力なセキュリティとコンプライアンスのプラクティスが実施されていることを示しています。

<!--- TBD: Parking some content for later review. Check if this content needs to be published.

We also have a few more quality and security checks for apps. We have launched Microsoft Cloud App Security (MCAS) program for the customer who have E5 or EMS license, where we rate risk for your cloud apps based on regulatory certification, industry standards, and best practices. We are also working on an Apps Quality Score system (launching soon) for all apps on Teams platform, and you will be able to check an app’s quality score quickly on Teams Store.

--->
