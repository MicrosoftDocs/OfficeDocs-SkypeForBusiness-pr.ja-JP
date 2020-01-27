---
title: Business Voice のインターネット接続を確認する
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 17eca42d01bcfb8a6b440c16408f31f6301b0338
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268713"
---
# <a name="check-your-internet-connection-for-business-voice"></a><span data-ttu-id="b9999-102">Business Voice のインターネット接続を確認する</span><span class="sxs-lookup"><span data-stu-id="b9999-102">Check your Internet connection for Business Voice</span></span>

<span data-ttu-id="b9999-103">Business Voice は、Microsoft 365 のクラウドにあります。</span><span class="sxs-lookup"><span data-stu-id="b9999-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="b9999-104">Microsoft Teams および Business Voice を使用するすべてのデバイスで、インターネット接続が必要になります。</span><span class="sxs-lookup"><span data-stu-id="b9999-104">Every computer and device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span>

<span data-ttu-id="b9999-105">最高の Business Voice エクスペリエンスを達成するには、組織が一度に行う最大通話数をサポートできるブロードバンド インターネット接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="b9999-105">To get the best experience with Business Voice, you need a broadband Internet connection that can support the expected number of phone calls that will be made at any one time.</span></span> <span data-ttu-id="b9999-106">また、ネットワーク上のコンピューターが Microsoft 365 サーバーに到達できることを確認する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="b9999-106">You also need to make sure that computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="b9999-107">これらの手順を実行するには、次のいずれかのサブスクリプションを持つテナントが必要です。</span><span class="sxs-lookup"><span data-stu-id="b9999-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="b9999-108">Office 365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="b9999-108">Office 365 Business Essentials</span></span>
* <span data-ttu-id="b9999-109">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="b9999-109">Office 365 Business Premium</span></span>
* <span data-ttu-id="b9999-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="b9999-110">Office 365 E1</span></span>
* <span data-ttu-id="b9999-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="b9999-111">Office 365 E3</span></span>
* <span data-ttu-id="b9999-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="b9999-112">Office 365 F1</span></span>
* <span data-ttu-id="b9999-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="b9999-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="b9999-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="b9999-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="b9999-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="b9999-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="b9999-116">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="b9999-116">Microsoft 365 Business</span></span>

<span data-ttu-id="b9999-117">これらの手順を実行するのに Business Voice ライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b9999-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="b9999-118">インターネット接続の速度を確認する</span><span class="sxs-lookup"><span data-stu-id="b9999-118">Check your Internet connection speed</span></span>

<span data-ttu-id="b9999-119">この記事は、電話をかける必要のある人数、ビデオ会議のホストに対応するのにインターネット接続が十分な速度であるかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b9999-119">This article helps you determine whether your Internet connection is fast enough for the number of people who need to make phone calls, host video conferences, and so on.</span></span> <span data-ttu-id="b9999-120">組織に関する情報を入力すると、Teams や Business Voice で使用されるインターネット接続の量が記載されたレポートが返されます。</span><span class="sxs-lookup"><span data-stu-id="b9999-120">You'll enter some information about your organization and get back a report with how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="gather-information-about-your-internet-connection-and-users"></a><span data-ttu-id="b9999-121">インターネット接続とユーザーに関する情報を収集する</span><span class="sxs-lookup"><span data-stu-id="b9999-121">Get information about your Internet connection and users</span></span>

<span data-ttu-id="b9999-122">始める前に、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="b9999-122">Before you start, you need to know the following information:</span></span>

* <span data-ttu-id="b9999-123">インターネット接続の速度</span><span class="sxs-lookup"><span data-stu-id="b9999-123">The speed of your Internet connection.</span></span>
* <span data-ttu-id="b9999-124">主にオフィス内で Business Voice を使用する人数</span><span class="sxs-lookup"><span data-stu-id="b9999-124">How many people will use Business Voice mainly from your office.</span></span>
* <span data-ttu-id="b9999-125">ホーム オフィスなど、主にリモートの場所で Business Voice を使用する人数</span><span class="sxs-lookup"><span data-stu-id="b9999-125">How many people will use Business Voice mainly from a remote location, such as a home office.</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="b9999-126">ネットワーク プランナーに情報を入力する</span><span class="sxs-lookup"><span data-stu-id="b9999-126">Enter your information into the network planner</span></span>

<span data-ttu-id="b9999-127">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b9999-127">Follow these steps.</span></span>

1. <span data-ttu-id="b9999-128">ブラウザーで、https://admin.teams.microsoft.com に移動します。</span><span class="sxs-lookup"><span data-stu-id="b9999-128">In a browser, go to https://admin.teams.microsoft.com.</span></span> <span data-ttu-id="b9999-129">グローバル管理者権限を持つアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="b9999-129">Sign in by using an account that has Global Administrator permissions.</span></span> <span data-ttu-id="b9999-130">Office 365 へのサインアップに使用したアカウントには、これらのアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="b9999-130">The account you used to sign up for Office 365 has these permissions.</span></span>
2. <span data-ttu-id="b9999-131">**[計画]** を開いて **[ネットワーク プランナー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9999-131">Open **Planning** and then select **Network planner**.</span></span>
3. <span data-ttu-id="b9999-132">**[ネットワーク プラン]** で、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9999-132">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="b9999-133">プランの名前を入力して、**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9999-133">Enter a name for your plan, and then select **Apply**.</span></span> <span data-ttu-id="b9999-134">ネットワーク プランは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b9999-134">Your network plan should look like this:</span></span>

    ![ネットワーク プランナーのメイン画面](../media/network-planner-main.png)
1. <span data-ttu-id="b9999-136">ネットワーク プランの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9999-136">Select the name of your network plan.</span></span> <span data-ttu-id="b9999-137">(これは、前の図では **[メイン オフィス]** です。)</span><span class="sxs-lookup"><span data-stu-id="b9999-137">(It's **Main office** in the preceding picture.)</span></span>
2. <span data-ttu-id="b9999-138">次のページで、**[ネットワーク サイト]** タブで **[ネットワーク サイトを追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9999-138">On the next page, select **Add a network site** under the **Network sites** tab.</span></span>
3. <span data-ttu-id="b9999-139">次のスクリーンショットに示されているフィールドにのみ入力し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9999-139">Fill in only the fields indicated in the screenshot below and then select **Save**.</span></span> <span data-ttu-id="b9999-140">この画面上の他のフィールドを空白のままにしておき、**[ExpressRoute]** も **[WAN に接続済み]** のオプションも選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="b9999-140">Leave the other fields on this screen blank, and don't select either the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![ネットワーク プランナー サイトに関する情報](../media/network-planner-site-info.png)
1. <span data-ttu-id="b9999-142">**[レポート]** タブで、**[レポートの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9999-142">Under the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="b9999-143">次の情報を入力してから **[レポートの生成]** を選択し、Teams の帯域幅要件を示すレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b9999-143">Fill out the following information and then select **Generate report** to create a report showing the bandwidth requirements for Teams.</span></span> <span data-ttu-id="b9999-144">次のセクションでは、レポートを読み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9999-144">We'll show you how to read the report in the next section.</span></span>

    ![ネットワーク プランナー レポートに関する情報](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="b9999-146">インターネット接続の最低速度を確認する</span><span class="sxs-lookup"><span data-stu-id="b9999-146">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="b9999-147">**[レポートの生成]** を選択すると、Office 365 で次のようなレポートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b9999-147">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![ネットワーク プランナー レポートの詳細](../media/network-planner-report.png)

<span data-ttu-id="b9999-149">強調表示された数値は、Teams と Business Voice で使用するインターネット接続の量を示しています。</span><span class="sxs-lookup"><span data-stu-id="b9999-149">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="b9999-150">この数値が、インターネット接続の合計速度の 30% を超えないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b9999-150">We recommend that this number be no more than 30% of your total Internet connection speed.</span></span> <span data-ttu-id="b9999-151">たとえば、インターネット接続が 60 Mbps の場合、Teams や Business Voice は 18 Mbps 未満を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9999-151">For example, if your Internet connection is 60Mbps, Teams and Business Voice should take up no more than 18Mbps.</span></span>

<span data-ttu-id="b9999-152">この式を使用して、インターネット接続の最小速度を決定します: *\< 強調表示された数字 > / 0.3*。</span><span class="sxs-lookup"><span data-stu-id="b9999-152">Use this equation to determine your minimum Internet connection speed: *\<highlighted number> / 0.3*.</span></span> <span data-ttu-id="b9999-153">前の図で強調表示されている数値を使用すると計算は、*4.6875 / 0.3 = 15.6* になります。</span><span class="sxs-lookup"><span data-stu-id="b9999-153">With the number that's highlighted in the preceding image, the calculation is *4.6875 / 0.3 = 15.6*.</span></span> <span data-ttu-id="b9999-154">この場合、インターネット接続速度は、15.6 Mbps 以上にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9999-154">In this case, the Internet connection speed should be at least 15.6 Mbps.</span></span>

<span data-ttu-id="b9999-155">Teams と Business Voice での使用量がインターネット接続の合計速度の 30% を超える場合、強調表示された数値が赤色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9999-155">If Teams and Business Voice will use more than 30% of your total Internet connection speed, the highlighted number will show up as red.</span></span> <span data-ttu-id="b9999-156">この場合、インターネット接続をアップグレードする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9999-156">In that case, you may need to upgrade your Internet connection.</span></span>

![接続速度の警告](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="b9999-158">ネットワーク上のコンピューターとデバイスが Microsoft 365 に到達できることを確認する</span><span class="sxs-lookup"><span data-stu-id="b9999-158">Make sure computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="b9999-159">Business Voice を使用するコンピューターやデバイスは、特定のネットワーク ポートを使用して Microsoft 365 サーバーと通信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9999-159">Computers and devices that use Business Voice must use specific network ports to communicate with Microsoft 365 servers.</span></span> <span data-ttu-id="b9999-160">これらのポートは実質的に、ネットワークやインターネット経由でデバイスが相互に通信するための出入口です。</span><span class="sxs-lookup"><span data-stu-id="b9999-160">Network ports are essentially doors through which computers and devices can talk to each other over a network or the Internet.</span></span> <span data-ttu-id="b9999-161">ファイアウォールでは、次の*送信*ネットワーク ポートを使用して、ネットワーク上のデバイスが Microsoft 365 に到達できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9999-161">Your firewall needs to allow computers and devices on your network to reach Microsoft 365 using the following outbound network ports:</span></span>

* <span data-ttu-id="b9999-162">**TCP ポート** 80 と 443</span><span class="sxs-lookup"><span data-stu-id="b9999-162">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="b9999-163">**UDP ポート** 3478、3479、3480、3481</span><span class="sxs-lookup"><span data-stu-id="b9999-163">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="b9999-164">お使いのファイアウォールでこれらのネットワーク ポート上の通信が許可されているかどうかを確認する一番簡単な方法は、Teams でテスト通話を行うことです。</span><span class="sxs-lookup"><span data-stu-id="b9999-164">The easiest way to check whether your firewall allows communication on these network ports is to make a test call using Teams.</span></span>

1. <span data-ttu-id="b9999-165">ネットワーク上のコンピューターで https://aka.ms/getteams に移動して、Teams をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b9999-165">Go to https://aka.ms/getteams on a computer on your network to install Teams.</span></span> <span data-ttu-id="b9999-166">コンピューターにスピーカーとマイクがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b9999-166">Make sure that the computer has speakers and a microphone.</span></span>
2. <span data-ttu-id="b9999-167">Teams を開いて、Microsoft 365 アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="b9999-167">Open Teams and sign in using a Microsoft 365 account</span></span>
3. <span data-ttu-id="b9999-168">Teams で、プロファイルの画像を選択してから、**[設定]**  >  **[デバイス]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="b9999-168">In Teams, select your profile picture, then **Settings** > **Devices**</span></span>
4. <span data-ttu-id="b9999-169">**[オーディオ デバイス]** で、**[テスト通話]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9999-169">Under **Audio devices**, select **Make a test call**.</span></span>
5. <span data-ttu-id="b9999-170">手順に従ってメッセージを残し、メッセージを再生します。</span><span class="sxs-lookup"><span data-stu-id="b9999-170">Follow the prompts to leave a message and have it played back to you</span></span>

   * <span data-ttu-id="b9999-171">電話が繋がり、メッセージが聞こえたら、ファイアウォールは正しく設定されています。</span><span class="sxs-lookup"><span data-stu-id="b9999-171">If the call connects and you can hear your message played back to you, your firewall is set up correctly.</span></span>
   * <span data-ttu-id="b9999-172">電話は繋がるものの、指示が聞こえない場合またはメッセージが再生されない場合は、コンピューターによってスピーカーとマイクが正しく設定されていることを確認し、もう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="b9999-172">If the call connects but you can't hear the prompts or your message played back to you, make sure your speakers and microphone are set up correctly and detected by the computer.</span></span>
   * <span data-ttu-id="b9999-173">電話が繋がらない場合、または繋がるもののメッセージが聞こえない場合は、ファイアウォールを更新して、必要なネットワーク ポートへのアクセスを許可する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9999-173">If the call doesn't connect or if it does but you can't hear your message played back to you, you might need to update your firewall to allow the network ports listed above.</span></span> <span data-ttu-id="b9999-174">ファイアウォールのドキュメントを確認するか、IT 専門家にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="b9999-174">Check your firewall's documentation, or contact an IT specialist for help.</span></span>

 <span data-ttu-id="b9999-175">IT プロフェッショナルで、Business Voice をサポートするためにより大きくて複雑なネットワークを準備する方法の詳細が必要な場合は、「[環境を評価する](../3-envision-evaluate-my-environment.md)」をご参照ください。</span><span class="sxs-lookup"><span data-stu-id="b9999-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, take a look at [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="b9999-176">この記事では、帯域幅、プロキシ、ファイアウォールの要件に関する詳細と、[Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network) を使用してネットワークをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9999-176">This article provides information about bandwidth, proxy and firewall requirements, and how to use the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network) to test your network.</span></span>

