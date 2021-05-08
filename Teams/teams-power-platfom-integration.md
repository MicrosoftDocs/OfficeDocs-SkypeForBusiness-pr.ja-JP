---
title: Teams Microsoft Power Platform との統合
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: kvivek
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Microsoft Power Platform Teams、Power Apps、Power Automate、Power BI などの Microsoft Power Platform ツールとの統合について説明Power Virtual Agents。
ms.openlocfilehash: c6442cd654dd8da6e26de048d50b7c80ef95cf26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111043"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="7c6fb-103">Teams Microsoft Power Platform との統合</span><span class="sxs-lookup"><span data-stu-id="7c6fb-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="7c6fb-104">Microsoft Power Platform は、Power BI を使用してデータを分析し **、Power Apps** を使用してカスタム アプリを構築し、Power Automate を使用してプロセスを自動化し、Power Virtual Agents を使用してインテリジェントなボットをこれまで以上に迅速に作成する低コード ツールを使用して開発を加速するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7c6fb-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="7c6fb-105">リモート作業とハイブリッド作業への移行によりMicrosoft Teams世界中のユーザーが作成、共同作業、コミュニケーションを継続できます。</span><span class="sxs-lookup"><span data-stu-id="7c6fb-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="7c6fb-106">1 日に 7,500 万人を超えるアクティブ ユーザーがTeamsが作業を完了する方法です。</span><span class="sxs-lookup"><span data-stu-id="7c6fb-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Microsoft Power Platform Teams概要を示す画像":::

<span data-ttu-id="7c6fb-108">Microsoft Power Platform は Teams との多くの統合機能を提供します。Teams ワークスペースに **Power BI** レポートを埋め込み、Power Appsを使用して作成されたアプリをタブまたは個人用アプリとして埋め込み、任意のメッセージから **Power Automate** フローをトリガーしたり、アダプティブカードを使用したり、Power Virtual Agents を使用して作成されたボットを Teams に追加して、組織の他のメンバーとやり取りすることができます。</span><span class="sxs-lookup"><span data-stu-id="7c6fb-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="7c6fb-109">2020 年 9 月から、Microsoft Power Platform との統合が改善され、ユーザーは次の操作を行い、Teams *になりました*。</span><span class="sxs-lookup"><span data-stu-id="7c6fb-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="7c6fb-110">ダッシュボード、レポート、アプリを作成および共有するには、Power BIを使用してデータ駆動型の決定を行います。</span><span class="sxs-lookup"><span data-stu-id="7c6fb-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="7c6fb-111">統合された **Power Apps** Studio を使用して、新しい基になるデータ プラットフォーム (microsoft Dataverse for Teams)、Microsoft 365、またはコネクタを介して他のデータ ソースに格納されているビジネス データに接続することで、低コードの専用アプリを作成して共有します。</span><span class="sxs-lookup"><span data-stu-id="7c6fb-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="7c6fb-112">アプリとサービスの間に自動化されたワークフローを作成して、ファイルの同期、通知の取得、データの収集など、 を使用 **Power Automate。**</span><span class="sxs-lookup"><span data-stu-id="7c6fb-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="7c6fb-113">**Power Virtual Agents** を使用して、ガイド付きのコードなしグラフィカル インターフェイスを使用してボットを構築し、Teams 内でデジタル アシスタントを簡単に作成し、同僚がチャットを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7c6fb-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="7c6fb-114">アプリ、ボット、ワークフローを作成する新しい機能は[、Teams、Dataverse for Teams](/powerapps/teams/overview-data-platform)用の新しい組み込みの低コード データ プラットフォームによって支え、リレーショナル データ ストレージ、リッチ データ型、エンタープライズ レベルのガバナンス、およびワンクリック ソリューションデプロイを提供します。</span><span class="sxs-lookup"><span data-stu-id="7c6fb-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](/powerapps/teams/overview-data-platform), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="7c6fb-115">Dataverse for Teams は[、Microsoft Dataverse の上に構築されます](/powerapps/maker/common-data-service/data-platform-intro)。</span><span class="sxs-lookup"><span data-stu-id="7c6fb-115">Dataverse for Teams is built on top of [Microsoft Dataverse](/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="7c6fb-116">Teams 用 Dataverse を使用すると、Teams ユーザーは、Teams アプリ ストアから、業界全体の一般的なシナリオを紹介するカスタムのすぐに使用できるソリューションを見つけてインストールできます。</span><span class="sxs-lookup"><span data-stu-id="7c6fb-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="7c6fb-117">これらのカスタム ソリューションをカスタマイズして拡張し、組織のブランドと要件に合わせて調整できます。</span><span class="sxs-lookup"><span data-stu-id="7c6fb-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="7c6fb-118">ライセンス</span><span class="sxs-lookup"><span data-stu-id="7c6fb-118">Licensing</span></span>

<span data-ttu-id="7c6fb-119">新しい機能は、サブスクリプションを選択してMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="7c6fb-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="7c6fb-120">Power Apps、Power Automate、Power Virtual Agents、Dataverse のライセンス要件の詳細については、「Teams」を[参照してください](/power-platform/admin/about-teams-environment)。</span><span class="sxs-lookup"><span data-stu-id="7c6fb-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](/power-platform/admin/about-teams-environment).</span></span>
- <span data-ttu-id="7c6fb-121">アプリケーションのライセンス要件の詳細については、「要件」Power BI[を参照してください](/power-bi/collaborate-share/service-collaborate-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="7c6fb-121">For more information about licensing requirements for Power BI, see [Requirements](/power-bi/collaborate-share/service-collaborate-microsoft-teams).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="7c6fb-122">使用を開始する方法</span><span class="sxs-lookup"><span data-stu-id="7c6fb-122">How do I get started?</span></span>

- [<span data-ttu-id="7c6fb-123">Power BIとTeams</span><span class="sxs-lookup"><span data-stu-id="7c6fb-123">Power BI and Teams</span></span>](/power-bi/collaborate-share/service-collaborate-microsoft-teams)
- [<span data-ttu-id="7c6fb-124">Power AppsとTeams</span><span class="sxs-lookup"><span data-stu-id="7c6fb-124">Power Apps and Teams</span></span>](/powerapps/teams/overview)
- [<span data-ttu-id="7c6fb-125">Power AutomateとTeams</span><span class="sxs-lookup"><span data-stu-id="7c6fb-125">Power Automate and Teams</span></span>](/power-automate/teams/overview)
- [<span data-ttu-id="7c6fb-126">Power Virtual AgentsとTeams</span><span class="sxs-lookup"><span data-stu-id="7c6fb-126">Power Virtual Agents and Teams</span></span>](/power-virtual-agents/teams/fundamentals-what-is-power-virtual-agents-teams)