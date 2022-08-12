---
title: Microsoft によるアプリの検証とアプリのテストの概要
description: マーケットプレイス認定ポリシーに基づく Teams アプリの検証ガイドラインについて説明します。 Teams アプリが高水準のプライバシーとセキュリティに準拠していることを Microsoft がどのように保証しているかを理解します。
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
ms.openlocfilehash: c6ca0590f254a0567eec8946ae3c4323bf541f05
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299236"
---
# <a name="validation-performed-by-microsoft-for-all-teams-apps"></a>Microsoft がすべての Teams アプリに対して実行する検証

Microsoft では、最終用途のためにストアに登録される前に、すべてのアプリが必須の検証に合格する必要があります。 これは、Teams アプリ ストアで公開されるすべてのアプリ (カスタム アプリを除く) に適用されます。 さらに、Microsoft は、アプリ開発者がコンプライアンス、セキュリティ、およびプライバシー制御の強化を示すアプリのオプションの認定に参加することを強くお勧めします。

すべてのアプリは、Microsoft アプリ認定ポリシーに準拠する必要があります。 Teams ストア チームは、アプリが使用可能で、プライバシーとセキュリティの高い基準に準拠していることを確認するために、400 を超えるテストを実行します。

アプリ開発者が準拠する検証ガイドライの詳細については、「[開発者のための検証ガイドライン](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines)」を参照してください。 このガイダンスは、[Teams アプリの認定ポリシー](/legal/marketplace/certification-policies#1140-teams)に基づいています。

> [!NOTE]
> カスタム アプリの場合、組織内で開発され、組織のメンバーだけが使用できるため、Microsoft による検証とチェックは利用できません。

## <a name="app-validation-and-testing"></a>アプリの検証とテスト

すべてのアプリには、Teams ストアで利用可能になる前に 400 を超えるテスト ケースが実行されます。 テストは、適切な機能、ユーザー エクスペリエンス、およびセキュリティを保証し、すべてのアプリが一般公開されている CMO ポリシーに準拠していることを確認します。 すべてのアプリに対して発行前に Microsoft アプリ検証チームによって実行されるテストの一部を次に示します。

* アプリによって要求される Graph のアクセス許可が、アプリの機能に必要なアクセス許可であり、余分なアクセス許可ではないことを確認します。 既存のアプリの Graph のアクセス許可は、アプリが余分なアクセス許可を要求しないように定期的にチェックされます。
* ユーザーにサインインを要求するアプリには、サインアウトするオプションがあります。
* すべてのアプリ開発者は、Microsoft パートナー センターで詳細な検証プロセスを受けます。 検証には、メールの確認、ビジネスの確認などが含まれます。 アプリの発行の詳細については、「[開発者がパートナー センターのアカウントを作成する方法](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account)」、「[開発者向けの送信ガイド](/office/dev/store/add-in-submission-guide)」、「[開発者がアプリを発行する方法](https://aka.ms/PublishToTeamsStore)」を参照してください。
* 検証済みの開発者からのアプリのみが、エンド ユーザーから Graph のアクセス許可を求めることができます。
* アプリは実行可能ファイルをダウンロードできません。
* アプリは、広告や他のアプリのプロモーションを含まないようにテストされています。
* アプリは、不快な言葉、サイバー攻撃ボット、スパム、または詐欺のコンテンツが含まれず、適切に動作するかどうかをテストされます。
* アプリ内のすべてのリンクは機能し、アプリのサービスにのみ関係しています。
* アプリ ストアの正常性チェックの一環として、発行されたすべての Teams アプリが定期的にテストおよび評価されます。
* Teams アプリを対象とするプライバシー ポリシーと利用規約は、アプリの開発者によって公開されています。
* アプリ開発者の連絡先の詳細は、ストアの掲載情報と、それぞれの [[発行者の証明書ページ]](/microsoft-365-app-certification/teams/teams-apps) で確認できます。

さらに、Microsoft はアプリ開発者に対し、アプリの品質、セキュリティ、コンプライアンスを確保するための厳格な 2 層のアプローチであるコンプライアンス プログラムに参加することをお勧めします。 Teams ストアは、既に詳細な検証ガイドラインを満たし、これらのプログラムに準拠する以上の数百ものアプリを提供しています。

## <a name="related-article"></a>関連記事

* [Microsoft 365 アプリ コンプライアンス プログラムの管理者向けの概要](overview-of-app-certification.md)
