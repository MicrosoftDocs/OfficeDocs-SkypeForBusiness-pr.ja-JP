---
title: Teams と Microsoft Power Platform の統合
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
description: Power BI、Power アプリ、Power Automate、Power Virtual Agents などの Microsoft Power Platform ツールとの Teams の統合について説明します。
ms.openlocfilehash: c6442cd654dd8da6e26de048d50b7c80ef95cf26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111043"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="f65c4-103">Teams と Microsoft Power Platform の統合</span><span class="sxs-lookup"><span data-stu-id="f65c4-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="f65c4-104">Microsoft Power Platform は、ユーザーが Power BI を使用してデータを分析し **、Power** Apps を使用してカスタム アプリを構築し **、Power** Automate を使用してプロセスを自動化し **、Power Virtual** **Agents** を使用してインテリジェントなボットを作成する低コード ツールを使用して、これまで以上に迅速に開発を加速するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f65c4-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="f65c4-105">リモート作業とハイブリッド作業への移行により、Microsoft Teams は世界中のユーザーが引き続き作成、共同作業、コミュニケーションを行える機能を提供しています。</span><span class="sxs-lookup"><span data-stu-id="f65c4-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="f65c4-106">1 日に 7,500 万人を超えるアクティブ ユーザーを持つ Teams は、ユーザーが作業を行う方法です。</span><span class="sxs-lookup"><span data-stu-id="f65c4-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Teams と Microsoft Power Platform の概要を示す画像":::

<span data-ttu-id="f65c4-108">Microsoft Power Platform は Teams と多くの統合機能を提供し、Teams ワークスペースに **Power BI** レポートを埋め込み、タブまたは個人用アプリとして **Power Apps** を使用して作成されたアプリを埋め込み、任意のメッセージから Power **Automate** フローをトリガーしたり、アダプティブ カードを使用したり **、Power Virtual Agents** を使用して作成したボットを Teams に追加して、組織の他のメンバーとやり取りすることができます。</span><span class="sxs-lookup"><span data-stu-id="f65c4-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="f65c4-109">2020 年 9 月から、Microsoft Power Platform との統合が改善され、ユーザーは Teams のインターフェイスから離れることなく次の操作を *行えるすすめになりました*。</span><span class="sxs-lookup"><span data-stu-id="f65c4-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="f65c4-110">**Power BI** を使用してダッシュボード、レポート、アプリを作成して共有し、データを基にした意思決定を行います。</span><span class="sxs-lookup"><span data-stu-id="f65c4-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="f65c4-111">統合 **された Power Apps** スタジオを使用して、新しい基になるデータ プラットフォーム (Microsoft Dataverse for Teams)、Microsoft 365、またはコネクタを介して他のデータ ソースに保存されているビジネス データに接続して、低コードで専用のアプリを作成して共有します。</span><span class="sxs-lookup"><span data-stu-id="f65c4-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="f65c4-112">Power Automate を使用して、アプリとサービスの間で自動ワークフローを作成して、ファイルの同期、通知の取得、データ収集、その他 **の操作を行います**。</span><span class="sxs-lookup"><span data-stu-id="f65c4-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="f65c4-113">**Power Virtual Agents** を使用して、ガイド付きコードなしグラフィカル インターフェイスを使用してボットを構築し、Teams 内でデジタル アシスタントを簡単に作成し、同僚がチャットを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f65c4-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="f65c4-114">アプリ、ボット、ワークフローを作成する新しい機能は [、Teams、Dataverse for Teams](/powerapps/teams/overview-data-platform)用の新しい組み込みの低コード データ プラットフォームに支え、リレーショナル データ ストレージ、豊富なデータ型、エンタープライズ レベルのガバナンス、および 1 回クリックでソリューションを展開できます。</span><span class="sxs-lookup"><span data-stu-id="f65c4-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](/powerapps/teams/overview-data-platform), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="f65c4-115">Dataverse for Teams は [、Microsoft Dataverse の上に構築されています](/powerapps/maker/common-data-service/data-platform-intro)。</span><span class="sxs-lookup"><span data-stu-id="f65c4-115">Dataverse for Teams is built on top of [Microsoft Dataverse](/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="f65c4-116">Teams 用 Dataverse を使用すると、Teams ユーザーは、業界全体の一般的なシナリオを紹介する Teams アプリ ストアから、すぐに使用できるカスタム ソリューションを見つけてインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f65c4-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="f65c4-117">これらのカスタム ソリューションをカスタマイズして拡張し、組織のブランドと要件に合わせて調整できます。</span><span class="sxs-lookup"><span data-stu-id="f65c4-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="f65c4-118">ライセンス</span><span class="sxs-lookup"><span data-stu-id="f65c4-118">Licensing</span></span>

<span data-ttu-id="f65c4-119">新しい機能は、一部の Microsoft 365 サブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="f65c4-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="f65c4-120">Power Apps、Power Automate、Power Virtual Agents、Dataverse for Teams のライセンス要件の詳細については、「ライセンス」を [参照してください](/power-platform/admin/about-teams-environment)。</span><span class="sxs-lookup"><span data-stu-id="f65c4-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](/power-platform/admin/about-teams-environment).</span></span>
- <span data-ttu-id="f65c4-121">Power BI のライセンス要件の詳細については、「要件」を [参照してください](/power-bi/collaborate-share/service-collaborate-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="f65c4-121">For more information about licensing requirements for Power BI, see [Requirements](/power-bi/collaborate-share/service-collaborate-microsoft-teams).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="f65c4-122">使い始めるには、方法を知る方法を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="f65c4-122">How do I get started?</span></span>

- [<span data-ttu-id="f65c4-123">Power BI と Teams</span><span class="sxs-lookup"><span data-stu-id="f65c4-123">Power BI and Teams</span></span>](/power-bi/collaborate-share/service-collaborate-microsoft-teams)
- [<span data-ttu-id="f65c4-124">Power Apps と Teams</span><span class="sxs-lookup"><span data-stu-id="f65c4-124">Power Apps and Teams</span></span>](/powerapps/teams/overview)
- [<span data-ttu-id="f65c4-125">Power Automate と Teams</span><span class="sxs-lookup"><span data-stu-id="f65c4-125">Power Automate and Teams</span></span>](/power-automate/teams/overview)
- [<span data-ttu-id="f65c4-126">Power Virtual Agents と Teams</span><span class="sxs-lookup"><span data-stu-id="f65c4-126">Power Virtual Agents and Teams</span></span>](/power-virtual-agents/teams/fundamentals-what-is-power-virtual-agents-teams)