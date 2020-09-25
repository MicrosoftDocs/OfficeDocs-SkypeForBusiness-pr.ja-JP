---
title: Microsoft Teams での internet explorer のトランシーバーアプリケーション
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: ITAdmin の観点から、Microsoft Teams でトランシーバー Ie のアプリを構成する方法について説明します。
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
ms.openlocfilehash: 605ba58582210c71561cd60442aa66f97be0be0d
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262504"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="e0635-103">Microsoft Teams での ie トランシーバーアプリの解説</span><span class="sxs-lookup"><span data-stu-id="e0635-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="e0635-104">Teams のトランシーバー Ie のアプリでは、チームのインスタントプッシュツートーク (PTT) コミュニケーションが提供され、Android で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e0635-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="e0635-105">トランシーバー ie では、ユーザーは、メンバーである基になるチャネルを使ってチームと接続できます。</span><span class="sxs-lookup"><span data-stu-id="e0635-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="e0635-106">チャネルで、トランシーバーに接続しているユーザーのみが、チャネルで参加者になり、プッシュツートークを使って互いに通信できます。</span><span class="sxs-lookup"><span data-stu-id="e0635-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="e0635-107">Teams でトランシーバー Ie の機能を使用することで、firstline worker は、非常に強い無線を伝送することなく、使い慣れた PTT エクスペリエンスと安全に通信できるようになりました。また、WiFi または携帯電話のインターネット接続があればどこでも Ie トランシーバーが動作します。</span><span class="sxs-lookup"><span data-stu-id="e0635-107">With Walkie Talkie in Teams, firstline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="e0635-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="e0635-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="e0635-109">解説した Ie トランシーバーの展開</span><span class="sxs-lookup"><span data-stu-id="e0635-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="e0635-110">現在、トランシーバー Ie のお勧めのインストールはプリインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="e0635-110">Currently, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="e0635-111">組織内のユーザーに対してこの機能を有効にするには、 [App Setup Policy](teams-app-setup-policies.md)   [Teams 管理センター](https://admin.teams.microsoft.com/)のユーザーに割り当てられているアプリセットアップポリシーに、トランシーバーした ie のを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0635-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="e0635-112">有効にすると、48時間以内に Android アプリで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e0635-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="e0635-113">登録した Ie トランシーバーをアプリの一覧に追加する</span><span class="sxs-lookup"><span data-stu-id="e0635-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="e0635-114">Microsoft teams 管理センターの [ **Teams アプリ**  >  **セットアップポリシー**] で、**ユーザーの固定**を **[オン**] に設定しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0635-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="e0635-115">次に、[固定されたアプリ] セクションで、[ **+ アプリの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0635-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="[固定されたアプリ] セクションと [アプリの追加] ボタンを選んで表示します。":::

<span data-ttu-id="e0635-117">右側に表示される [固定された **アプリの追加** ] パネルで、[ **検索** ] ボックスを使用して、「トランシーバー」という ie の説明を探します。</span><span class="sxs-lookup"><span data-stu-id="e0635-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="e0635-118">検索結果として表示されたら、名前の右側にある [ **追加** ] ボタンをクリックして、リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="e0635-118">When you have it as a search result, click the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="検索ウィンドウと検索した Ie トランシーバーアプリの横にある [追加] ボタンをクリックして、[ピン留めされたアプリの追加] サイドバーを表示します。":::

<span data-ttu-id="e0635-120">これで、このアプリを [ピン留めされたアプリ] の一覧に表示されるようになり、[ **保存** ] ボタンをクリックすると使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e0635-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="[挿入済みの Ie トランシーバーアプリが追加され、リストの下に [保存] ボタンが追加された、ピンされたアプリの一覧を示します。":::

### <a name="network-documentation"></a><span data-ttu-id="e0635-122">ネットワークドキュメント</span><span class="sxs-lookup"><span data-stu-id="e0635-122">Network documentation</span></span>

<span data-ttu-id="e0635-123">トランシーバー Teams での ie の紹介は、インターネット接続が必要です。また、最適なエクスペリエンスを実現するには、ネットワークの条件が必要です。</span><span class="sxs-lookup"><span data-stu-id="e0635-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="e0635-124">指標</span><span class="sxs-lookup"><span data-stu-id="e0635-124">Metric</span></span> | <span data-ttu-id="e0635-125">必須</span><span class="sxs-lookup"><span data-stu-id="e0635-125">Required</span></span> |
|---|---|
|<span data-ttu-id="e0635-126">待機時間 (RTT)</span><span class="sxs-lookup"><span data-stu-id="e0635-126">Latency (RTT)</span></span> | <span data-ttu-id="e0635-127">300ms <</span><span class="sxs-lookup"><span data-stu-id="e0635-127">< 300ms</span></span> |
|<span data-ttu-id="e0635-128">ジッター</span><span class="sxs-lookup"><span data-stu-id="e0635-128">Jitter</span></span> |<span data-ttu-id="e0635-129">< 30 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="e0635-129">< 30ms</span></span> |
|<span data-ttu-id="e0635-130">パケット損失</span><span class="sxs-lookup"><span data-stu-id="e0635-130">Packet Loss</span></span> |<span data-ttu-id="e0635-131">< 1%</span><span class="sxs-lookup"><span data-stu-id="e0635-131">< 1%</span></span> |

<span data-ttu-id="e0635-132">上で説明したように、IP ネットワーク上のリアルタイムメディアの品質は、ネットワーク接続の品質に大きな影響を与えますが、特に次の量によって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="e0635-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="e0635-133">**待機** 時間-この時刻は、IP パケットがネットワーク上のポイント B からポイント B に到達するまでの時間です。</span><span class="sxs-lookup"><span data-stu-id="e0635-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="e0635-134">このネットワーク伝達遅延は、さまざまなルーターの間の追加のオーバーヘッドを含めて、2 つのポイントの間の物理的な距離と光速度に関連しています。</span><span class="sxs-lookup"><span data-stu-id="e0635-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span> <span data-ttu-id="e0635-135">待ち時間はラウンドトリップ時間 (RTT) として測定されます。</span><span class="sxs-lookup"><span data-stu-id="e0635-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="e0635-136">[**パケット損失**]: 特定の時間帯に失われるパケットのパーセンテージとして定義されることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="e0635-136">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="e0635-137">パケット損失は、オーディオの品質に直接影響を与えます。これは、完全に失われた小さいパケットによって、完全なオーディオのカットアウトを引き起こすバックツーバックのバースト損失になります。</span><span class="sxs-lookup"><span data-stu-id="e0635-137">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="e0635-138">**ジッタ** -連続したパケット間の遅延の平均変化を示します。</span><span class="sxs-lookup"><span data-stu-id="e0635-138">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="e0635-139">データ使用量は、「音楽を送信または受信するときに 20KB/s」からトランシーバーます。</span><span class="sxs-lookup"><span data-stu-id="e0635-139">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="e0635-140">アイドル状態の場合、トランシーバー Ie のデータ使用量はごくわずかです。</span><span class="sxs-lookup"><span data-stu-id="e0635-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="e0635-141">お互いの ie トランシーバーデバイス</span><span class="sxs-lookup"><span data-stu-id="e0635-141">Walkie Talkie devices</span></span>

<span data-ttu-id="e0635-142">FirstLine worker は、多くの場合、電話がロックされているときでも、聞く Ie トランシーバーの通話を発信したり、受信したりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0635-142">FirstLine workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="e0635-143">この操作は、専用の PTT ボタンを持つ専用デバイスから実行できます。</span><span class="sxs-lookup"><span data-stu-id="e0635-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="e0635-144">ヘッドホン</span><span class="sxs-lookup"><span data-stu-id="e0635-144">Headsets</span></span>
  - <span data-ttu-id="e0635-145">有線ヘッドセット ([Klein エレクトロニクス](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span><span class="sxs-lookup"><span data-stu-id="e0635-145">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span></span>
  - <span data-ttu-id="e0635-146">ワイヤレスヘッドセット ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span><span class="sxs-lookup"><span data-stu-id="e0635-146">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span></span>
- <span data-ttu-id="e0635-147">丈夫の携帯電話</span><span class="sxs-lookup"><span data-stu-id="e0635-147">Rugged phones</span></span>
  - <span data-ttu-id="e0635-148">Samsung Galaxy XCover Pro</span><span class="sxs-lookup"><span data-stu-id="e0635-148">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="e0635-149">[さらに詳しい情報](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)があります。</span><span class="sxs-lookup"><span data-stu-id="e0635-149">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="e0635-150">[セットアップガイド](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)。</span><span class="sxs-lookup"><span data-stu-id="e0635-150">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="e0635-151">これらのデバイスは Teams で認定されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="e0635-151">These devices are not Teams certified.</span></span> <span data-ttu-id="e0635-152">チームの内容を確認した Ie トランシーバーで動作することが検証されました。</span><span class="sxs-lookup"><span data-stu-id="e0635-152">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="e0635-153">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="e0635-153">License requirements</span></span>

<span data-ttu-id="e0635-154">このアプリは、 [Office 365 サブスクリプション](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)のすべての有料ライセンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="e0635-154">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span></span> <span data-ttu-id="e0635-155">Teams の入手方法について詳しくは、「 [Microsoft teams にアクセスする方法](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e0635-155">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="e0635-156">一部の高度な機能には追加のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="e0635-156">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="e0635-157">たとえば、Samsung Galaxy XCover Pro との統合には、Knox ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="e0635-157">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="e0635-158">さらに詳しい情報</span><span class="sxs-lookup"><span data-stu-id="e0635-158">Further information</span></span>

- <span data-ttu-id="e0635-159">ITAdmins は、アプリのポリシーを通じて、トランシーバーの Ie を使用しているユーザーを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="e0635-159">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="e0635-160">最初のラインワーカーがモバイルデータを使って Teams で通信している場合、トランシーバーは同じメソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="e0635-160">If your firstline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="e0635-161">トランシーバー ie は、低帯域幅の状況でも適切に動作する必要があります。または、スマートフォンが接続され、動作している場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="e0635-161">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="e0635-162">トランシーバーは、接続されていない場合は機能しません。</span><span class="sxs-lookup"><span data-stu-id="e0635-162">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="e0635-163">エンドユーザーエクスペリエンスの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0635-163">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="e0635-164">チームを活用する Ie トランシーバーの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="e0635-164">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="e0635-165">トランシーバー Ie のお客様のチームとコミュニケーションする</span><span class="sxs-lookup"><span data-stu-id="e0635-165">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
