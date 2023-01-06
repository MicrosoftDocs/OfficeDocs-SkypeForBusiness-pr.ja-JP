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
- tier2
- highpri
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: a41393f763c9d8ebb328d586f6ae12636e87b0b4
ms.sourcegitcommit: eb0e754d7e2877f686021d3ab75b6d8d44db3a95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2023
ms.locfileid: "69727739"
---
# <a name="understand-microsoft-teams-apps-and-their-capabilities"></a>Microsoft Teams アプリとその機能について

Teams のアプリは、ユーザーが職場のツールやサービスをまとめ、他のユーザーと共同作業するのに役立ちます。 たとえば、エンド ユーザーは、他のユーザーとすばやく共同で作業するために Teams にピン留めされた予定表アプリ、Teams チャネルで Web サービスの品質をユーザーに通知するボット機能を備えたアプリ、チャネル内のさまざまなエンド ユーザーとタスクを共有して割り当てるアプリなどを使用します。 Microsoft Teams アプリは、ローカルに展開する必要のない Web ベースの SaaS アプリに似ています。 エンド ユーザーが Teams クライアントにアプリを追加しても、 のインストールは必要ありません(バイナリ ファイルなど)。

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

## <a name="discover-and-use-apps-in-teams"></a>Teams でアプリを検出して使用する

ユーザーは、Teams デスクトップまたは Web クライアントの Teams アプリ ストアから Teams で利用可能なすべてのアプリを表示できます。 ユーザーは、名前で検索したり、カテゴリで参照したり、組織用に構築され、Power Platform を使用してビルドされたアプリで参照して、Teams でアプリを検出してインストールしたりできます。

簡単にアクセスできるように、アプリを Teams にピン留めできます。 セットアップ ポリシーで許可されている場合と、アプリが Teams 管理者によって許可されている場合、ユーザーは [アプリを自分でピン留め](https://support.microsoft.com/office/pin-an-app-for-easy-access-3045fd44-6604-4ba7-8ecc-1c0d525e89ec) できます。管理者は、アプリをピン留めし、ピン留めされたアプリの動作を制御できます。詳細については、「 [アプリのセットアップ ポリシー](/microsoftteams/teams-app-setup-policies)」を参照してください。

:::image type="content" source="media/user-app-experience-find-apps.png" alt-text="ユーザーが Microsoft Teams でアプリを閲覧できるすべての場所を示すスクリーンショット。" lightbox="media/user-app-experience-find-apps-full.png":::

ユーザーは、Teams アプリ ストアからアプリを見つけて Teams に追加できます。 また、チャットまたはチャネル タブ、Teams 会議、メッセージング領域など、作業中のコンテキストからアプリを直接追加することもできます。 詳細については、「 [Microsoft Teams にアプリを追加する」を](https://support.microsoft.com/office/add-an-app-to-microsoft-teams-b2217706-f7ed-4e64-8e96-c413afd02f77)参照してください。

ユーザーは、管理者がアプリを許可し、アクセス [許可ポリシー](teams-app-permission-policies.md)を使用してアプリをユーザーが利用できる場合にのみ、アプリを追加して使用できます。 組織の IT 管理者は、どのアプリをどのコンテキストにインストールできるかを完全に制御できます。 ユーザーはブロックされているアプリを追加できません。Teams ストアのロック アイコンを持つアプリは、ユーザーに対してブロックされます。 ただし、 [ユーザーは組織の IT 管理者に承認を要求できます](https://support.microsoft.com/office/request-apps-that-require-approval-by-your-org-924e3a9e-33f0-44c2-9e81-e875214c05ae)。 アプリが承認されると、ユーザーは Teams ストアからアプリを追加できます。

> [!NOTE]
> Teams にアプリを追加するための承認を要求できるのは個人だけです。

## <a name="understand-app-capabilities"></a>アプリの機能を理解する

Teams アプリの機能は、開発者が Teams アプリのさまざまなユース ケースを満たすためにアプリで構築するコア機能です。 アプリには、次の 1 つ以上の機能が含まれています。 これらはすべて、一般的なアプリ [ガバナンス メソッド](manage-apps.md)を使用して、これらのアプリを管理する Teams アプリと管理者のさまざまな機能です。

<!---
        :::image type="content" source="media/teams-app-capabilities-group.png" alt-text="Graphic that shows the app capabilities of a Microsoft Teams app." border="false":::
--->

* **ボット**: ボットは、チャットボットまたは会話ボットとも呼ばれます。 ボットは、単純な反復タスクを実行するアプリです。 ボットの操作には、簡単な質問と回答や、サービスやサポートへのアクセスを提供する複雑な会話などがあります。 ユーザーは、個人用チャット、チャネル、またはグループ チャットでボットとの会話を行うことができます。 詳細については、「 [Microsoft Teams のボット](/microsoftteams/platform/bots/what-are-bots)」を参照してください。

* **タブ**: タブは、チャネルまたはチャットの上部にピン留めされた Teams 対応 Web ページです。 タブを使用すると、Web に似たエクスペリエンスでコンテンツやサービスを操作できます。 これは、個々のユーザーのチーム、グループ チャット、または個人用アプリ内のチャネルの一部として追加できる単純な HTML `iframe` タグです。 詳細については、「 [Microsoft Teams のタブ](/microsoftteams/platform/tabs/what-are-tabs)」を参照してください。

* **Webhook とコネクタ**: Webhook とコネクタは、さまざまな Web サービスを Microsoft Teams のチャネルやチームに接続するのに役立ちます。 Webhook は、Teams チャネルで行われたアクションについてユーザーに通知するユーザー定義の HTTP コールバックです。 これは、アプリがリアルタイム データを取得する方法です。 コネクタを使用すると、ユーザーは Web サービスからの通知とメッセージの受信をサブスクライブできます。 詳細については、「 [Webhook とコネクタ](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)」を参照してください。

  ユーザーが Teams でカスタム コネクタを使用できるようにするには、「Teams で [カスタム コネクタを使用する](office-365-custom-connectors.md)」を参照してください。

* **メッセージング拡張機能**: メッセージング拡張機能は、アプリ コンテンツを挿入したり、エンド ユーザーが会話から離れることなくメッセージに対応したりするためのショートカットです。 ユーザーは、メッセージの作成領域、コマンド ボックス、またはメッセージから直接、外部システムでアクションを検索または開始できます。 詳細については、「 [メッセージ拡張機能](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions?tabs=dotnet)」を参照してください。

* **会議拡張機能**: ユーザーは、会議内にメッセージ拡張機能を統合し、会議の生産性を高めることで、会議エクスペリエンスを向上させることができます。 さまざまな参加者ロールとユーザーの種類を識別し、会議イベントを取得し、会議内ダイアログを生成できます。 詳細については、「 [Teams 会議用アプリ](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings)」を参照してください。

<!---
* **Cards and task modules**: Cards provide users with various visual, audio, and selectable messages and help in conversation flow. Task modules help you create modal pop-up experiences in Microsoft Teams. They're useful for starting and completing the tasks, or displaying rich information like videos or Power business intelligence (BI) dashboards. For more information, see [Cards and task modules](/microsoftteams/platform/task-modules-and-cards/cards-and-task-modules).
--->

* **アクティビティ フィード**: Teams のアクティビティ フィードには、チャネルやチャットなどのさまざまなスコープ内のすべてのアクティビティの通知が含まれています。 アプリは、すべてのメンバーにメッセージをブロードキャストして、更新プログラムを通知することができます。 ユーザーは、表示する通知をカスタマイズできます。

Teams 機能にマップされている一般的なユース ケースを表示するには、「 [ユース ケースを Teams アプリの機能にマップする](/microsoftteams/platform/concepts/design/map-use-cases)」を参照してください。

## <a name="related-articles"></a>関連記事

* [Teams 用アプリ テンプレートの詳細については、こちらをご覧ください](/microsoftteams/platform/samples/app-templates)。
* [Teams アプリの更新と管理者ロール](apps-update-experience.md)
* [Teams 管理センターでのアプリ管理とガバナンスの概要](manage-apps.md)
