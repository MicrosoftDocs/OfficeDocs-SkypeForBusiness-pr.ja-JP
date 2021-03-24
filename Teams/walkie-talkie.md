---
title: Microsoft Teams のトランシーバー アプリケーション
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: ITAdmin の観点から、Microsoft Teams でトランシーバー アプリを構成する方法です。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90d5135196de9ecf62085e88053d80299b6e5a58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097463"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="4a2c7-103">Microsoft Teams のトランシーバー アプリ</span><span class="sxs-lookup"><span data-stu-id="4a2c7-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="4a2c7-104">Teams のトランシーバー アプリは、Teams にインスタント プッシュツートーク (PTT) 通信を提供し、Android で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="4a2c7-105">トランシーバーを使用すると、ユーザーは、メンバーと同じ基本チャネルを使用してチームとつながることができます。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="4a2c7-106">チャネルでトランシーバーに接続するユーザーのみが参加者になり、プッシュツートークを使用して一度に 1 つずつ相互に通信できます。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="4a2c7-107">Teams の Walkie Talkie を使用すると、Frontline の作業者は、バルク ラジオを運ぶ必要なく、使い慣れた PTT エクスペリエンスで安全に通信できます。また、Walkie Talkie は WiFi または携帯電話のインターネット接続を使用してどこからでも作業できます。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-107">With Walkie Talkie in Teams, Frontline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="4a2c7-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="4a2c7-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="4a2c7-109">トランシーバーの展開</span><span class="sxs-lookup"><span data-stu-id="4a2c7-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="4a2c7-110">現在、トランシーバーはプリインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-110">Currently, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="4a2c7-111">組織内のユーザーに対してこの機能を有効にするには、[[Teams 管理センター]](https://admin.teams.microsoft.com/) からユーザーに割り当てられた [アプリ セットアップ ポリシー](teams-app-setup-policies.md) にトランシーバーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="4a2c7-112">有効にすると、トランシーバーは 48 時間以内に Android アプリで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="4a2c7-113">トランシーバーをアプリ リストに追加する</span><span class="sxs-lookup"><span data-stu-id="4a2c7-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="4a2c7-114">Microsoft Teams 管理センターの **[Teams アプリ]** > **[セットアップ ポリシー]** で、**[ユーザーのピン留めを許可]** を **[オン]** に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="4a2c7-115">次に、「ピン留めされたアプリ」セクションで、**[アプリの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="「ピン留めされたアプリ」セクションと選択する [アプリの追加] ボタンが表示されます。":::

<span data-ttu-id="4a2c7-117">右側に表示される **[ピン留めされたアプリを追加]** パネルで、**[検索]** テキストボックスを使用してトランシーバーを探します。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="4a2c7-118">検索結果として保存されている場合は、名前の右側にある[追加] ボタンを選択してリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-118">When you have it as a search result, select the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="検索ウィンドウにトランシーバーが入力された [ピン留めされたアプリを追加] サイドバーと、検索結果にトランシーバー アプリが表示され、その横に [追加] ボタンが表示されます。":::

<span data-ttu-id="4a2c7-120">トランシーバー アプリが [ピン留めされたアプリ] リストに表示され、**[保存]** ボタンをクリックすると使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="トランシーバー アプリが追加されたピン留めされたアプリのリストと、リストの下にある [保存] ボタンが表示されます。":::

### <a name="network-documentation"></a><span data-ttu-id="4a2c7-122">ネットワーク ドキュメント</span><span class="sxs-lookup"><span data-stu-id="4a2c7-122">Network documentation</span></span>

<span data-ttu-id="4a2c7-123">Teams のトランシーバーにはインターネット接続が必要であり、最適なエクスペリエンスを得るには以下のネットワーク条件が必要です。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="4a2c7-124">測定基準</span><span class="sxs-lookup"><span data-stu-id="4a2c7-124">Metric</span></span> | <span data-ttu-id="4a2c7-125">必須</span><span class="sxs-lookup"><span data-stu-id="4a2c7-125">Required</span></span> |
|---|---|
|<span data-ttu-id="4a2c7-126">遅延 (RTT)</span><span class="sxs-lookup"><span data-stu-id="4a2c7-126">Latency (RTT)</span></span> | <span data-ttu-id="4a2c7-127">< 300 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="4a2c7-127">< 300ms</span></span> |
|<span data-ttu-id="4a2c7-128">ジッター</span><span class="sxs-lookup"><span data-stu-id="4a2c7-128">Jitter</span></span> |<span data-ttu-id="4a2c7-129">< 30 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="4a2c7-129">< 30ms</span></span> |
|<span data-ttu-id="4a2c7-130">パケット損失</span><span class="sxs-lookup"><span data-stu-id="4a2c7-130">Packet Loss</span></span> |<span data-ttu-id="4a2c7-131">< 1%</span><span class="sxs-lookup"><span data-stu-id="4a2c7-131">< 1%</span></span> |

<span data-ttu-id="4a2c7-132">上記のように、IP ネットワークを介したリアルタイム メディアの品質は、ネットワーク接続の品質、特に次の量によって大きく影響されます。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="4a2c7-133">**遅延** - これは、IP パケットがネットワーク上のポイント A からポイント B に到達するまでにかかる時間です。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="4a2c7-134">このネットワーク伝達遅延は、基本的に、2 つのポイントと光の速度の間の物理的な距離に結び付き、その間にあるさまざまなルーターによって発生するオーバーヘッドが多く含まれています。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including more overhead taken by the various routers in between.</span></span> <span data-ttu-id="4a2c7-135">遅延は往復時間 (RTT) として測定されます。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="4a2c7-136">**パケット損失** - これは、指定した時間帯に失ったパケットの割合として定義されることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-136">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="4a2c7-137">パケット損失は、オーディオの品質に直接影響を与えます。ほとんど影響を及ぼすことのない小規模のパケット損失から、音声が完全に途切れる原因となる連続したバースト損失まで存在します。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-137">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="4a2c7-138">**ジッタ** - これは、連続するパケット間の遅延の平均変動です。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-138">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="4a2c7-139">トランシーバーからの予想データ使用量は、オーディオの送受信時に約 20KB/秒です。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-139">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="4a2c7-140">アイドル状態の場合、トランシーバーからの予想されるデータ使用量はごくわずかです。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="4a2c7-141">トランシーバー デバイス</span><span class="sxs-lookup"><span data-stu-id="4a2c7-141">Walkie Talkie devices</span></span>

<span data-ttu-id="4a2c7-142">最前線の従業員は、多くの場合、自分の電話がロックされている場合でも、Walkie Talkie の通話を話して受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-142">Frontline workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="4a2c7-143">この体験は、専用の PTT ボタンを備えた専用デバイスを介して可能です。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="4a2c7-144">ヘッドセット</span><span class="sxs-lookup"><span data-stu-id="4a2c7-144">Headsets</span></span>
  - <span data-ttu-id="4a2c7-145">有線ヘッドセット ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span><span class="sxs-lookup"><span data-stu-id="4a2c7-145">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span></span>
  - <span data-ttu-id="4a2c7-146">ワイヤレス ヘッドセット ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span><span class="sxs-lookup"><span data-stu-id="4a2c7-146">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span></span>
- <span data-ttu-id="4a2c7-147">頑丈な電話</span><span class="sxs-lookup"><span data-stu-id="4a2c7-147">Rugged phones</span></span>
  - <span data-ttu-id="4a2c7-148">Samsung Galaxy XCover Pro</span><span class="sxs-lookup"><span data-stu-id="4a2c7-148">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="4a2c7-149">[詳細情報](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-149">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="4a2c7-150">[セットアップ ガイド](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-150">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="4a2c7-151">これらのデバイスは Teams 認定を受けていません。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-151">These devices are not Teams certified.</span></span> <span data-ttu-id="4a2c7-152">Teams トランシーバーで動作することが検証されています。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-152">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="4a2c7-153">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="4a2c7-153">License requirements</span></span>

<span data-ttu-id="4a2c7-154">トランシーバー アプリは、[Office 365 サブスクリプション](/office365/servicedescriptions/teams-service-description)の Teams のすべての有料ライセンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-154">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](/office365/servicedescriptions/teams-service-description).</span></span> <span data-ttu-id="4a2c7-155">Teams の入手方法の詳細については、「 [Microsoft Teams へのアクセス方法](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-155">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="4a2c7-156">特定の高度な機能には、追加のライセンスが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-156">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="4a2c7-157">たとえば、Samsung Galaxy XCover Pro との統合には Knox ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-157">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="4a2c7-158">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4a2c7-158">Further information</span></span>

- <span data-ttu-id="4a2c7-159">ITAdmins は、アプリ ポリシーを通じてトランシーバーを使用しているユーザーの制御を維持できます。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-159">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="4a2c7-160">フロントライン ワーカーがモバイル データを使用して Teams 経由で通信している場合、Walkie Talkie も同じ方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-160">If your Frontline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="4a2c7-161">トランシーバーは、低帯域幅の状況、またはスマートフォンが接続されて機能している状況でうまく機能するはずです。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-161">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="4a2c7-162">接続がまったくない場合、トランシーバーは機能しません。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-162">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="4a2c7-163">エンドユーザー エクスペリエンスの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a2c7-163">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="4a2c7-164">Teams トランシーバーの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="4a2c7-164">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="4a2c7-165">トランシーバーを使用してチームと通信する</span><span class="sxs-lookup"><span data-stu-id="4a2c7-165">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)