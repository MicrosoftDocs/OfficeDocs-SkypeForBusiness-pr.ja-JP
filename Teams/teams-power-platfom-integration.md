---
title: Microsoft Power Platform とのチームとの統合
author: lanachin
ms.author: v-lanac
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
description: Power BI、Power apps、Power オートメーション、Power Virtual Agent などの Microsoft Power Platform ツールとのチームの統合について説明します。
ms.openlocfilehash: 81d673069e972f4627a8bfab18095e81803dd4b1
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085683"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="e9787-103">Microsoft Power Platform とのチームとの統合</span><span class="sxs-lookup"><span data-stu-id="e9787-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="e9787-104">Microsoft Power Platform を使用すると、ユーザーは低コードツールを使用して開発を加速し、power **BI** を使ってデータを分析したり、power **app** を使用してカスタムアプリを構築したり **、power online** を使ってプロセスを自動化したり、より早く **power Virtual agent** を使用してインテリジェントなボットを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="e9787-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="e9787-105">リモートとハイブリッドの作業への移行により、Microsoft Teams では、世界中のユーザーが引き続き作成、共同作業、コミュニケーションを行うことができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e9787-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="e9787-106">1人のユーザーが7500万以上のアクティブユーザーを使用している場合、Teams では作業の実行方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="e9787-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="チームと Microsoft Power Platform の概要の画像":::

<span data-ttu-id="e9787-108">Microsoft Power Platform には、Teams とのさまざまな統合機能が用意されています。このチームでは、power **BI** レポートを teams ワークスペースに埋め込むことができます。 power **apps** で作成されたアプリはタブまたは個人用アプリと **して埋め** 込むことができます。また、任意のメッセージからの **power** online フローのトリガー、または</span><span class="sxs-lookup"><span data-stu-id="e9787-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="e9787-109">2020年9月に、Microsoft Power Platform との統合により、ユーザーは *チームインターフェイスを離れることなく* 次の操作を実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e9787-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="e9787-110">**POWER BI** を使ってダッシュボード、レポート、アプリを作成して共有し、データ駆動型の決定を行います。</span><span class="sxs-lookup"><span data-stu-id="e9787-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="e9787-111">基盤となる **Power apps** studio を使って低コードの目的に特化したアプリを作成して共有します。これには、新しい基になるデータプラットフォーム (microsoft Dataverse Teams)、microsoft 365、またはコネクタを介したその他のデータソースに保存されているビジネスデータに接続します。</span><span class="sxs-lookup"><span data-stu-id="e9787-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="e9787-112">**Power オートメーション** を使って、ファイルの同期、通知の取得、データ収集などを行うために、アプリとサービスの間に自動化されたワークフローを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9787-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="e9787-113">「 **Power Virtual agent** を使って簡単にデジタルアシスタントを作成する」を参照して、ガイド付きのコードなしのグラフィカルインターフェイスを使用してボットを作成してください。</span><span class="sxs-lookup"><span data-stu-id="e9787-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="e9787-114">アプリ、ボット、ワークフローを作成するための新機能は、Teams 用の新しい低コードデータ [プラットフォーム、リレーショナル](https://go.microsoft.com/fwlink/?linkid=2143541)データストレージ、リッチデータ型、エンタープライズグレードガバナンス、1回のクリックソリューションの展開によってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e9787-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](https://go.microsoft.com/fwlink/?linkid=2143541), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="e9787-115">Teams の dataverse 定型文は、 [Microsoft dataverse 定型文](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)の上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="e9787-115">Dataverse for Teams is built on top of [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="e9787-116">Teams の Dataverse を使用すると、Teams ユーザーは、業界全体の一般的なシナリオを示す Teams app store から、使いやすいカスタムソリューションを見つけてインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9787-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="e9787-117">組織のブランドと要件に合わせて、これらのカスタムソリューションをカスタマイズして拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="e9787-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="e9787-118">ライセンス</span><span class="sxs-lookup"><span data-stu-id="e9787-118">Licensing</span></span>

<span data-ttu-id="e9787-119">新しい機能は、select Microsoft 365 サブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="e9787-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="e9787-120">Power Apps、Power オートメーション、Power Virtual Agent、および Teams の Dataverse 補足情報のライセンス要件の詳細については、「 [ライセンス](https://go.microsoft.com/fwlink/?linkid=2143647)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9787-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span></span>
- <span data-ttu-id="e9787-121">Power BI のライセンス要件の詳細については、「 [要件](https://go.microsoft.com/fwlink/?linkid=2143490)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9787-121">For more information about licensing requirements for Power BI, see [Requirements](https://go.microsoft.com/fwlink/?linkid=2143490).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="e9787-122">作業を始めるにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="e9787-122">How do I get started?</span></span>

- [<span data-ttu-id="e9787-123">Power BI とチーム</span><span class="sxs-lookup"><span data-stu-id="e9787-123">Power BI and Teams</span></span>](https://aka.ms/pbi-teams-docs)
- [<span data-ttu-id="e9787-124">Power Apps と Teams</span><span class="sxs-lookup"><span data-stu-id="e9787-124">Power Apps and Teams</span></span>](https://aka.ms/pa-teams-docs)
- [<span data-ttu-id="e9787-125">Power オートメーションと Teams</span><span class="sxs-lookup"><span data-stu-id="e9787-125">Power Automate and Teams</span></span>](https://aka.ms/pauto-teams-docs)
- [<span data-ttu-id="e9787-126">Power Virtual エージェントと Teams</span><span class="sxs-lookup"><span data-stu-id="e9787-126">Power Virtual Agents and Teams</span></span>](https://aka.ms/pva-teams-docs)
