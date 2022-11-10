---
title: Microsoft Teams のアプリについて知っておくべきこと
ms.reviewer: ''
description: アプリについて学習し、組織のプロファイルとビジネス要件に基づいて、Teams で使用できるアプリを決定します。
ms.topic: conceptual
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.date: 10/01/2022
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: 9b8d4ca3140b6bd8907938b5c2ac86aeabb39e37
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912626"
---
# <a name="understand-microsoft-teams-apps-and-their-capabilities"></a>Microsoft Teams アプリとその機能について

Teams のアプリは、ユーザーが職場のツールやサービスをまとめ、他のユーザーと共同作業するのに役立ちます。 たとえば、エンド ユーザーは、他のユーザーとすばやく共同で作業するために Teams にピン留めされた予定表アプリ、Teams チャネルで Web サービスの品質をユーザーに通知するボット機能を備えたアプリ、チャネル内のさまざまなエンド ユーザーとタスクを共有して割り当てるアプリなどを使用します。 Microsoft Teams アプリは、ローカルに展開する必要のない Web ベースの SaaS アプリです。

管理者は、エンド ユーザーの幅広い要件と組織の IT ポリシー、標準、リスク プロファイルのバランスを取るアプリ ガバナンス プロセスを設定します。

検証およびセキュリティで保護された Teams アプリの広範な [カタログ](https://appsource.microsoft.com/marketplace/apps?product=office%3Bteams&page=1) により、エンド ユーザーは、組織が毎日必要とするツールとサービスにアクセスできます。 Teams 管理センターには、アプリを管理するためのエンタープライズ レベルのコントロールと構成が管理者に用意されています。 会議、チャット、チャネルなどのさまざまなコンテキストで、各ユーザーのアプリの可用性を制御します。

この記事は、アプリの種類と、ユーザーがそれらのアプリにアクセスする場所を理解することに役立ちます。 アプリの使用方法の詳細については、「[エンドユーザー向けアプリの概要](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)」を参照してください。

エンド ユーザーが Teams で使用できるアプリの種類は次のとおりです。

* [Teams の一部であるコア アプリ](#core-apps)。
* [Microsoft によって作成されたその他のアプリ](#apps-created-by-microsoft)。
* パートナーによって作成された[サード パーティ製アプリ](#third-party-apps-created-by-independent-app-developers) (Microsoft によって検証)。
* 独自の組織によって作成された[カスタム アプリ](#custom-apps-created-within-an-organization-for-internal-use)。

## <a name="core-apps"></a>コア アプリ

アクティビティ フィード、チーム、チャット、予定表、通話、ファイル、割り当て (教育テナント) などの一部の Teams 機能は既定で使用でき、エンド ユーザーが簡単にアクセスできるように既定でピン留めされています。 現場担当者の場合は、アクティビティ、シフト、チャット、通話のみが使用でき、ピン留めされます。 管理者は、[セットアップ ポリシー](/microsoftteams/teams-app-setup-policies)を使用してこの既定の動作を変更できます。

:::image type="content" source="media/core-apps-pinned1.png" alt-text="コア アプリは、既定で Teams にピン留めされたアプリです。" lightbox="media/core-apps-pinned2.png":::

## <a name="apps-created-by-microsoft"></a>Microsoft によって作成されたアプリ

Microsoft には、生産性と共同作業を向上させるための多くのアプリがあります。 ユーザーとエンド ユーザーは、Teams 管理センターでパブリッシャーとして表示されている Microsoft を探すか、Teams ストアでプロバイダーとして一覧表示することで、これらのアプリを見つけることができます。

Teams には、リスト、Tasks、称賛、承認などを含む一連の組み込みアプリが付属しています。 Teams の初期展開時に、おすすめのアプリ (Planner など) を含めることをお勧めします。

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Teams 管理センターの Microsoft アプリの一覧を示すスクリーンショット。" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-created-by-independent-app-developers"></a>独立したアプリ開発者によって作成されたサード パーティ製アプリ

Microsoft が提供するアプリに加えて、サード パーティ製アプリを使用できます。 Microsoft では、これらすべてのアプリの機能とセキュリティを厳格に検証しています。 これらのアプリを Teams ストアで使用できるようにする前に、詳細な手動テストと自動テストが実行され、アプリが公開された後でも多くのテストが定期的に継続されます。 アプリ検証の利点を理解するには、[サード パーティ製アプリの検証](overview-of-app-validation.md)を参照してください。 一部のアプリでは [、Microsoft コンプライアンス プログラム](overview-of-app-certification.md) をサブスクライブして、検証を超えて複数のレベルのさらなるチェックを受けます。

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Teams ストアにあるサード パーティ製アプリの例のスクリーンショット。":::

## <a name="custom-apps-created-within-an-organization-for-internal-use"></a>組織内で内部で使用するために作成されたカスタム アプリ

組織内の開発者によって作成されたアプリは、カスタム アプリ (または基幹業務アプリ) と呼ばれます。 組織は、組織固有の要件に応じてカスタム アプリの作成を委託する場合があります。 あなたは組織全体または特定のユーザーに対して、このようなアプリを許可またはブロックする管理能力を保持しています。 組織内の開発者は、Teams と [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) の統合を使用して、カスタムのローコード ソリューションを構築できます。

管理者がカスタム アプリの使用を許可した後、エンド ユーザーは Teams ストアの左側のナビゲーションで **[組織のビルド** ] を選択することで、このようなアプリを見つけることができます。

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams デスクトップ アプリの Teams ストアにあるカスタム アプリのスクリーンショット。" lightbox="media/built-for-your-org2.png":::

詳細については、「 [カスタムアプリとサイドロードされたアプリの理解と管理](custom-app-overview.md)」を参照してください。

## <a name="about-app-templates"></a>アプリ テンプレートについて

Microsoft は、アプリ開発方法を使用して、機能的で運用環境に対応したサンプル アプリを作成して提供します。 総称して、これらのアプリは Teams のアプリ テンプレートと呼ばれ、次の目的で提供されます。

* Teams でのコラボレーションのユース ケースをいくつか示します。
* アプリ開発のベスト プラクティスと方法を紹介します。
* 開発者が独自のアプリを作成するために拡張できるオープン ソース アプリを提供します。

組織の開発者は、提供されたソース コードを簡単に変更してアプリ テンプレートをカスタマイズします。 これらのアプリをエンド ユーザー向けのカスタム アプリとして提供して、組織のニーズを満たします。

詳細については、「[Microsoft Teams アプリ テンプレート](https://adoption.microsoft.com/microsoft-teams/app-templates/)」を参照してください。

## <a name="understand-app-capabilities"></a>アプリの機能を理解する

Teams アプリの機能は、統合と対話を可能にするためにアプリに組み込み可能なコア機能です。

:::row:::
    :::column span="":::
    :::column-end:::
    :::column span="3":::
        :::image type="content" source="media/teams-app-capabilities-group.png" alt-text="Microsoft Teams アプリのアプリ機能を示す図。" border="false":::
    :::column-end:::
    :::column:::
    :::column-end:::
:::row-end:::

エンド ユーザーが Teams 内で作業できる豊富なエクスペリエンスを提供するために、アプリ開発者は次の機能を使用してアプリを作成します。

* **ボット**: ボットは、チャットボットまたは会話ボットとも呼ばれます。 ボットは、単純な反復タスクを実行するアプリです。 ボットの操作には、簡単な質問と回答や、サービスやサポートへのアクセスを提供する複雑な会話などがあります。 ユーザーは、個人用チャット、チャネル、またはグループ チャットでボットとの会話を行うことができます。 詳細については、「 [Microsoft Teams のボット](/microsoftteams/platform/bots/what-are-bots)」を参照してください。

  Teams は、プライベートのチャットおよびチャネルでボットをサポートしています。 管理者は、Microsoft 365 組織または Office 365 組織でのボットの使用を許可するかどうかを制御できます。 カスタム ボットのオンとオフの切り替えについては、「 [Teams 管理センターでのアプリ管理とガバナンスの概要](manage-apps.md)」を参照してください。

* **タブ**: タブは、チャネルまたはチャットの上部にピン留めされた Teams 対応 Web ページです。 タブを使用すると、Web に似たエクスペリエンスでコンテンツやサービスを操作できます。 これは、アプリ マニフェストで宣言されたドメインを指す単純な HTML <iframe\> タグであり、個々のユーザーのチーム、グループ チャット、または個人用アプリ内のチャネルの一部として追加できます。 詳細については、「 [Microsoft Teams のタブ](/microsoftteams/platform/tabs/what-are-tabs)」を参照してください。

  すべてのプライベート チャットには、[会話]、[ファイル]、[組織]、および [アクティビティ] のタブが既定で作成されます。 これらの組み込みタブに加えて、開発者はカスタム タブを設計および追加できます。 詳細については、「[Teams の組み込みタブとカスタム タブを使用する](/microsoftteams/platform/tabs/what-are-tabs)」を参照してください。

* **Webhook とコネクタ**: Webhook とコネクタは、Microsoft Teams のチャネルとチームに Web サービスを接続するのに役立ちます。 Webhook は、Teams チャネルで行われたアクションについてユーザーに通知するユーザー定義 HTTP コールバックです。 これは、アプリがリアルタイム データを取得する方法です。 コネクタを使用すると、ユーザーは Web サービスからの通知とメッセージの受信をサブスクライブできます。 詳細については、「 [Webhook とコネクタ](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)」を参照してください。

  ユーザーが Teams でカスタム コネクタを使用できるようにするには、「Teams で [カスタム コネクタを使用する](office-365-custom-connectors.md)」を参照してください。

* **メッセージング拡張機能**: メッセージング拡張機能は、アプリ コンテンツを挿入したり、エンド ユーザーが会話から離れることなくメッセージに対応したりするためのショートカットです。 ユーザーは、メッセージの作成領域、コマンド ボックス、またはメッセージから直接、外部システムでアクションを検索または開始できます。 詳細については、「 [メッセージ拡張機能](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions?tabs=dotnet)」を参照してください。

* **会議拡張機能**: ユーザーは、会議内にタブ、ボット、メッセージ拡張機能を統合し、会議の生産性を高めることで、会議エクスペリエンスを強化できます。 さまざまな参加者ロールとユーザーの種類を識別し、会議イベントを取得し、会議内ダイアログを生成できます。 詳細については、「 [Teams 会議用アプリ](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings)」を参照してください。

* **カードとタスク モジュール**: カードは、さまざまな視覚的、オーディオ、選択可能なメッセージと会話フローのヘルプをユーザーに提供します。 タスク モジュールは、Microsoft Teams でモーダル ポップアップ エクスペリエンスを作成するのに役立ちます。 これらは、タスクの開始と完了、ビデオや Power Business Intelligence (BI) ダッシュボードなどの豊富な情報の表示に役立ちます。 詳細については、「 [カードとタスク モジュール](/microsoftteams/platform/task-modules-and-cards/cards-and-task-modules)」を参照してください。

Teams 機能にマップされている一般的なユース ケースを表示するには、「 [ユース ケースを Teams アプリの機能にマップする](/microsoftteams/platform/concepts/design/map-use-cases)」を参照してください。

## <a name="related-articles"></a>関連記事

* [Teams 用アプリ テンプレートの詳細](/microsoftteams/platform/samples/app-templates)
* [Teams 管理センターでのアプリ管理とガバナンスの概要](manage-apps.md)
