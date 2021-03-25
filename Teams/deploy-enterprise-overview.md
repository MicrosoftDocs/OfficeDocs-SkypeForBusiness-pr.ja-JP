---
title: Microsoft Teams エンタープライズ展開の概要
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Microsoft Teams のエンタープライズ機能を展開する方法を学びます。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd3e60fafecd3cf025187935a9dc28b492c39d1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121415"
---
# <a name="teams-enterprise-deployment-overview"></a>Teams エンタープライズ展開の概要

中規模または大規模のビジネスの場合、ユーザーにサービスを展開する方法、Microsoft Teams クライアントをユーザーに展開する方法、ネットワーク設計がユーザーにどのように影響するか、リアルタイム通信の品質などについて考える必要があります。  組織内のチームの計画に役立つ記事へのポインターについては、次のセクションを確認してください。

> [!NOTE]
> まだ行っていない場合は、パイロットから Teams の展開を開始することを強くお勧めします。 パイロットにより、計画と最終的な展開の前に、あなたや早期採用者が Teams とその機能に精通することができます。 パイロットを開始する方法の詳細については、「[Microsoft Teams を開始する](get-started-with-teams-quick-start.md)」を参照してください。

以下のセクションを読み、組織での Teams の展開を開始する準備ができたら、「[企業で Microsoft Teams を設定する](deploy-enterprise-setup.md)」を参照してください。

## <a name="architecture"></a>アーキテクチャ

Teams は Microsoft 365 に緊密に統合されており、チャット、ファイル共有、会議、テレフォニー、ビデオ ストリーミングなどを強化するために多くの機能を使用しています。 Teams を展開する前に、[Microsoft Teams IT アーキテクチャとテレフォニー ソリューション ポスター](teams-architecture-solutions-posters.md)を確認して、Teams が Microsoft 365 の他の部分とどのように連携して、ユーザーに完全なコラボレーション エクスペリエンスを提供するかを理解してください。

## <a name="workloads"></a>ワークロード

Teams には、互いに独立して展開できる次の 3 つのワークロードがあります: **チャット、チーム、チャネル**; **ミーティングと会議**; および **電話システムと PSTN (公衆交換電話網) 接続** です。 各ワークロードには、そのワークロードに関する情報を簡単に見つけられるように、ドキュメントに独自のセクションがあります。 これには、展開計画についての情報が含まれます。

展開するワークロードの展開計画情報を確認するには、次の記事を参照してください。

- [チームとチャネルについて理解する](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [ミーティングと会議](deploy-meetings-microsoft-teams-landing-page.md)
- [音声 - 電話システムと PSTN 接続](cloud-voice-landing-page.md)

## <a name="network-planner"></a>ネットワーク プランナー

Teams のネットワーク計画は、多数のユーザー、複雑なネットワーク、またはその両方がある場合に非常に重要です。 Teams は、音声通話とビデオ会議をサポートしています。どちらもリアルタイム通信に依存して、ユーザーに可能な限り最高のエクスペリエンスを提供します。 ネットワークは、次の条件を満たしている必要があります。

- 同時音声通話、ビデオ会議、会議、画面共有などの数に対応するのに十分な帯域幅容量があること。
- リアルタイム通信プロトコルをサポートするネットワーク ハードウェアを用意済みであること。
- ネットワーク上のデバイス、Microsoft 365 サービス、および外部ユーザー間で必要なネットワーク ポートを許可済みであること。

Teams ネットワークの要件を理解するには、次の記事を参照してください。

- [Microsoft Teams 用に組織のネットワークを準備する](prepare-network.md)
- [Teams または Skype for Business Online 向けのプロキシ サーバー](proxy-servers-for-skype-for-business-online.md)

計画を支援するために、Teams にはネットワーク プランナーが含まれています。 ネットワーク プランナーは、ユーザーの数と種類、組織にあるサイトの数、ネットワーク リンクの帯域幅容量などについて質問します。 この情報を使用して、ネットワーク プランナーは、各アクティビティの帯域幅要件と推奨事項を示すレポートを作成します。

 > [!div class="nextstepaction"]
> [ネットワーク プランナーに移動する](https://admin.teams.microsoft.com/networkplanner/organization)

(ネットワーク プランナーを開くには、[Microsoft 365 グローバル管理者](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles)である必要があります。)

ネットワーク プランナーの動作の詳細については、「[Microsoft Teams で ネットワーク プランナー を使用する](network-planner.md)」を参照してください。

ネットワーク プランナーがネットワークを計画する方法の例を確認するには、「[ネットワーク プランナーの使用 - 例のシナリオ](tutorial-network-planner-example.yml)」を参照してください。

## <a name="teams-advisor"></a>Teams アドバイザー

Teams アドバイザーは、チーム、チャネル、ファイル共有、および Planner を統合して、組織の展開プロジェクトを作成する Teams 内のソリューションです。 Teams Advisor は、選択したワークロード (チャット、チーム、チャネルなど) に固有のプロジェクト計画を作成します。これには、展開中に実行する必要のある推奨タスクが含まれます。 各タスクには、プロセスをガイドするための指示、提案、および関連記事へのリンクが含まれています。 1 人以上の個人にタスクを簡単に割り当て、各タスクの開始日と終了日を指定できます。

> [!TIP]
> Microsoft Learn の [Teams Advisor モジュールを使用してロールアウトを完了する](/learn/modules/m365-teams-rollout-using-advisor/)ことにより、Teams Advisor を使用して Teams の展開を計画する方法を確認してください。

> [!div class="nextstepaction"]
> [Teams アドバイザーに移動する](https://admin.teams.microsoft.com/teams-deployment)

(Teams アドバイザーを開くには、[Microsoft 365 グローバル管理者](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles)である必要があります。)

Teams アドバイザーの機能の詳細については、「[Teams のアドバイザーを使用して、Microsoft Teams の展開を支援する](use-advisor-teams-roll-out.md)」を参照してください。

## <a name="lifecycle-and-governance-planning"></a>ライフサイクルとガバナンスの計画

Teams の展開を計画するときは、組織内のチーム、チャネル、ファイルなどのライフサイクルを考慮する必要があります。 また、どのような種類の情報がそれらに格納されるかについても考慮する必要があります。 Teams は、特定のプロジェクトや部門用に作成することも、組織全体の中心的なリソースとして使用することもできます。 これらの用途にはそれぞれ異なる要件があり、次のような質問が発生します。

- チームはどのくらいアクティブな状態のままですか?
- チームとそのチャネルを誰が所有および管理する必要がありますか?
- 一部のチームに適用する必要があるものの、他のチームには適用しない、特定のコンプライアンス要件がありますか?
- ユーザーが適切なチームを特定するのに役立つ命名ポリシーが必要ですか?

初期展開の一部としてポリシーとガイドラインを作成すると、ユーザーが必要な情報を確実に見つけられるようになります。 ただし、同様に重要なこととして、適切なポリシーは、情報漏えいから組織を保護し、規制要件に準拠し、アーカイブを目的として必要に応じて情報を保持するのに役立ちます。

Teams のライフサイクル管理とガバナンスの詳細については、以下を参照してください。

- [Teams でのライフサイクル管理を計画する](plan-teams-lifecycle.md)
- [Teams でのガバナンスを計画する](plan-teams-governance.md)

## <a name="adoption"></a>導入

組織とユーザーが Teams を最大限に活用できるようにするには、導入プログラムが必要です。 効果的な導入プログラムは、次のことができる早期導入者を動員することができます。

- Teams のメリットを同僚やビジネス リーダーまたはグループ リーダーに明確に伝える。
- Teams がコラボレーションを改善し、相互の接続を容易にする方法を理解している他の人の関心を呼び起こす。
- 既存のビジネスプロセスを評価し、Teams をそれらに統合する方法についての推奨事項を作成するのを助ける。
- 導入プロセスの改善に役立てるために、成功と困難の両方を展開チームに報告します。

導入プログラムの設定の詳細については、「[Microsoft Teams を導入する](adopt-microsoft-teams-landing-page.md)」を参照してください。