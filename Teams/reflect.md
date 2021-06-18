---
title: Microsoft Teams の Reflect への IT 管理者ガイド
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams for Education の Reflect への IT 管理者ガイドです。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 981061e4892f679dac2a4e4f47fdcc929e6a02fb
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997706"
---
# <a name="it-admin-guide-to-reflect-in-microsoft-teams"></a><span data-ttu-id="91e51-103">Microsoft Teams の Reflect への IT 管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="91e51-103">IT Admin Guide to Reflect in Microsoft Teams</span></span>

<span data-ttu-id="91e51-104">このドキュメントでは、[Microsoft Teams の Education Insights](class-insights.md) に不可欠な要素である [Reflect](https://aka.ms/reflect) に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="91e51-104">This document provides information concerning [Reflect](https://aka.ms/reflect) – an integral part of [Education Insights in Microsoft Teams](class-insights.md).</span></span> <span data-ttu-id="91e51-105">Reflect は、学生が自分の感情を認識し、コントロールできるようにするために、共有や傾聴の機会を定期的に提供するためのサポートをします。</span><span class="sxs-lookup"><span data-stu-id="91e51-105">Reflect helps students recognize and navigate their emotions by providing regular opportunities to share and be heard.</span></span> <span data-ttu-id="91e51-106">Reflect は、学習者の感情表現に必要な語彙を増やし、仲間に対する共感を深めると同時に、教室の健全なコミュニティを維持するために教師に貴重なフィードバックを提供します。</span><span class="sxs-lookup"><span data-stu-id="91e51-106">Reflect can help broaden learners' emotional vocabulary and deepen empathy for their peers while also providing valuable feedback to educators for a healthy classroom community.</span></span>

<span data-ttu-id="91e51-107">このチェックイン アプリは、絵文字や研究に裏付けられた感情についての精度を用いて、教師の忙しい日常業務への社会性や感情に関する学びの場の追加をサポートします。</span><span class="sxs-lookup"><span data-stu-id="91e51-107">This check-in app uses emojis and research-backed emotional granularity to support educators in adding social and emotional learning into their already busy routine.</span></span>


## <a name="privacy-and-security"></a><span data-ttu-id="91e51-108">プライバシーとセキュリティ</span><span class="sxs-lookup"><span data-stu-id="91e51-108">Privacy and Security</span></span>
<span data-ttu-id="91e51-109">Reflect は、Education Insights と同じプライバシーとセキュリティ標準に従って学生の機密情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="91e51-109">Reflect follows the same privacy and security standards as Education Insights to protect students' sensitive information.</span></span>

<span data-ttu-id="91e51-110">Reflect で収集、表示される情報は、学生、子供、その他同様のプライバシーに関する規定に対して、[GDPR](/compliance/regulatory/gdpr)、家庭教育の[権利とプライバシーに関する法律 (FERPA)](/compliance/regulatory/offering-ferpa) などを含む [90 以上の規制および業界標準](/compliance/regulatory/offering-home)を満たしています。</span><span class="sxs-lookup"><span data-stu-id="91e51-110">The information collected and shown through Reflect meets [more than 90 regulatory and industry standards](/compliance/regulatory/offering-home), including [GDPR](/compliance/regulatory/gdpr) and the Family [Education Rights and Privacy Act (FERPA)](/compliance/regulatory/offering-ferpa) for students and children's security and other, similar, privacy-oriented regulations.</span></span>

<span data-ttu-id="91e51-111">学生が他の学生の名前を閲覧することは *なく*、反応の内容のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="91e51-111">Students *never* see the names of other students, only how they responded.</span></span> <span data-ttu-id="91e51-112">回答の分布を確認することはできますが、それぞれの反応に関連付けられている名前を表示することは *できません*。</span><span class="sxs-lookup"><span data-stu-id="91e51-112">While they can see the distribution of responses, they *cannot* see names associated with each reflection.</span></span> 

> [!NOTE]
> <span data-ttu-id="91e51-113">学生による回答が 5 人に満たない場合には、学生にデータは表示されません。</span><span class="sxs-lookup"><span data-stu-id="91e51-113">If less than five students respond, no data is shown to the students.</span></span> <span data-ttu-id="91e51-114">これは、学生同士がお互いの回答を識別してしまう可能性を最小限にするための措置です。</span><span class="sxs-lookup"><span data-stu-id="91e51-114">This is to minimize the possibility of students identifying each other's responses.</span></span>

## <a name="data-collection-and-storage"></a><span data-ttu-id="91e51-115">データの収集と記憶域</span><span class="sxs-lookup"><span data-stu-id="91e51-115">Data collection and storage</span></span>
<span data-ttu-id="91e51-116">データは教育機関に属しており、Microsoft が行うのはデータの収集と保存のみです。</span><span class="sxs-lookup"><span data-stu-id="91e51-116">The data belongs to the educational institution, and Microsoft only collects the data and stores it.</span></span> <span data-ttu-id="91e51-117">Microsoft の担当者は、データ リカバリなど、サービスを維持するための監査された方法でコンプライアンスによって許可されている場合を除き、データにアクセスしたり、データを表示したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="91e51-117">Microsoft personnel cannot access the data or see it, except as allowed by compliance in an audited way to maintain the service, such as data recovery.</span></span>

<span data-ttu-id="91e51-118">データは Education Insights に保存されます。</span><span class="sxs-lookup"><span data-stu-id="91e51-118">The data is stored in Education Insights.</span></span> <span data-ttu-id="91e51-119">既定では、Education Insights はオンになっています。</span><span class="sxs-lookup"><span data-stu-id="91e51-119">By default, Education Insights is turned on.</span></span> <span data-ttu-id="91e51-120">オプトアウトすると、Reflect 用に収集された **すべてのデータが削除されます**。</span><span class="sxs-lookup"><span data-stu-id="91e51-120">When you opt-out, we **delete all the data collected for Reflect**.</span></span> <span data-ttu-id="91e51-121">Education Insights をオンに戻すと、データが再度有効になった時点からデータの収集が開始されます。</span><span class="sxs-lookup"><span data-stu-id="91e51-121">Turn Education Insights back on, and we start collecting data from the time it's re-enabled.</span></span>

<span data-ttu-id="91e51-122">「[Education Insights への IT 管理者ガイド](class-insights.md)」では、Education Insights の仕組み (保存場所など) や、データを削除したり、サービスを有効にしたりする際に [Education Insights をオフまたはオンにする方法](class-insights.md#turn-insights-on-or-off)について説明しています。</span><span class="sxs-lookup"><span data-stu-id="91e51-122">In the [IT Admin Guide to Education Insights](class-insights.md), you can read how Education Insights works (including storage locations) and [how to turn Education Insights off or on](class-insights.md#turn-insights-on-or-off) when you want to delete the data or enable the service.</span></span>

<span data-ttu-id="91e51-123">Reflect では学生からデータを収集しますが、ゲスト データは収集されません。</span><span class="sxs-lookup"><span data-stu-id="91e51-123">Data is collected from student in Reflect, though guest data is not collected.</span></span> <span data-ttu-id="91e51-124">**学生がゲストとして定義されている場合には、そのユーザーのデータは収集されません。**</span><span class="sxs-lookup"><span data-stu-id="91e51-124">**If a student is defined as a guest, their data is not collected.**</span></span> 

## <a name="enable-reflect"></a><span data-ttu-id="91e51-125">Reflect を有効にする</span><span class="sxs-lookup"><span data-stu-id="91e51-125">Enable Reflect</span></span>
<span data-ttu-id="91e51-126">教育機関のアプリ設定ポリシーを管理する場合は、Reflect がテナントで *許可* されていることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="91e51-126">If you manage the app setup policy for your institution, ensure that Reflect is *allowed* in your tenant.</span></span> <span data-ttu-id="91e51-127">また、Teams 管理センターから Reflect を関連するクラスのチームに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="91e51-127">You can also add Reflect to the relevant class teams from the Teams admin center.</span></span>

<span data-ttu-id="91e51-128">ユーザーが任意のアプリをインストールして操作できるようにするには、**[アプリの管理]** ページからアプリを組織レベルで許可し、ユーザーに割り当てられている **アプリのアクセス許可ポリシー** を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91e51-128">To enable a user to install and interact with any app, you must allow the app at the org level on the **Manage apps** page and the **app permission policy** assigned to the user.</span></span>

<span data-ttu-id="91e51-129">各アプリに許可が必要となるように事前に定義している場合には、[アプリの管理] ページから Reflect を "許可" してください。</span><span class="sxs-lookup"><span data-stu-id="91e51-129">If you have previously defined that each app needs to be allowed, please go to the Manage apps page and 'allow' Reflect.</span></span> <span data-ttu-id="91e51-130">**アプリをブロックすると、組織内のすべてユーザーに対してそのアプリが Teams に表示されなくなります。**</span><span class="sxs-lookup"><span data-stu-id="91e51-130">**When you block an app, the app doesn't appear in Teams for any users in your organization.**</span></span>

> [!NOTE]
> <span data-ttu-id="91e51-131">Reflect アプリにアクセスするには、Microsoft 365 の A1、A3、A5 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="91e51-131">To have access to the Reflect app, you will need an A1, A3, or A5 license for Microsoft 365.</span></span>

> [!TIP]
> <span data-ttu-id="91e51-132">詳細については、「[How to allow an app or to add it to a class team (アプリを許可するか、クラスのチームに追加する方法)](manage-apps.md#allow-and-block-apps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91e51-132">For more details, read [how to allow an app or to add it to a class team](manage-apps.md#allow-and-block-apps).</span></span>

## <a name="where-do-educators-find-reflect"></a><span data-ttu-id="91e51-133">Reflect はどこから利用できますか?</span><span class="sxs-lookup"><span data-stu-id="91e51-133">Where do educators find Reflect?</span></span>
<span data-ttu-id="91e51-134">Reflect を有効にしたら教師はクラスに移動し、**[新しい会話]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="91e51-134">Once you have enabled Reflect, educators go to the class and select **New Conversation**.</span></span> <span data-ttu-id="91e51-135">そして、**[...]** を選択してメッセージング拡張機能を表示し、検索バーに 「**Reflect**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="91e51-135">They then select '**…**' to bring up messaging extensions and enter **Reflect** in the search bar.</span></span> <span data-ttu-id="91e51-136">ダイアログ ボックスでは、質問や、誰が何を表示できるかに関する定義をガイドします。</span><span class="sxs-lookup"><span data-stu-id="91e51-136">The dialog box guides them through defining the question and who can see what.</span></span>

:::image type="content" source="media/reflect-add-app.png" alt-text="クラス チームに Reflect を追加する":::

<span data-ttu-id="91e51-138">[Reflect] アイコンを右クリックして **[固定]** を選択することにより、アクセスが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="91e51-138">They can right-click on the Reflect icon and select **Pin** for easy access.</span></span>

:::image type="content" source="media/reflect-pin-app.png" alt-text="Reflect アプリを固定する":::

> [!TIP]
> <span data-ttu-id="91e51-140">このリンクから Reflect アプリを見つけることもできます。[https://aka.ms/getReflect](https://aka.ms/getReflect)</span><span class="sxs-lookup"><span data-stu-id="91e51-140">You can also locate the Reflect app through this link: [https://aka.ms/getReflect](https://aka.ms/getReflect)</span></span>

> [!TIP]
> <span data-ttu-id="91e51-141">詳細については、「[Reflect support page (Reflect のサポート ページ)](https://support.microsoft.com/topic/e9198f62-7860-4532-821f-53ef14afa79a)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91e51-141">For more details, visit [Reflect support page](https://support.microsoft.com/topic/e9198f62-7860-4532-821f-53ef14afa79a).</span></span> <span data-ttu-id="91e51-142">このページでは、教師と学生の両方にガイドラインを提供し、初めての Reflect チェックインを作成する方法について説明しています。</span><span class="sxs-lookup"><span data-stu-id="91e51-142">This page provides guidelines for both educators and students and helps with how to create their first Reflect check-in.</span></span>
