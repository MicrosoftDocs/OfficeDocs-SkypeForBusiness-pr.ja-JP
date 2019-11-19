---
title: インターネット接続を確認する
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
ms.openlocfilehash: 19f26c0bd7ab4fe89770909d81d60abc97aaa8b0
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653553"
---
# <a name="check-your-internet-connection"></a><span data-ttu-id="5f5f3-102">インターネット接続を確認する</span><span class="sxs-lookup"><span data-stu-id="5f5f3-102">Check your Internet connection</span></span>

<span data-ttu-id="5f5f3-103">Business Voice は、Microsoft 365 のクラウドにあります。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="5f5f3-104">Microsoft Teams および Business Voice を使用するすべてのコンピューターとデバイスで、インターネット接続が必要になります。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-104">Every computer and device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span> <span data-ttu-id="5f5f3-105">Business Voice を最大限に活用するには、予想される電話の数を一度にサポートできるブロードバンド インターネット接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-105">To get the best experience with Business Voice, you need a broadband Internet connection that can support the expected number of phone calls that will be made at any one time.</span></span> <span data-ttu-id="5f5f3-106">また、ネットワーク上のコンピューターが Microsoft 365 サーバーに到達できることを確認する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-106">You also need to make sure that computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="5f5f3-107">これらの手順を実行するには、次のいずれかのサブスクリプションを持つテナントが必要です。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="5f5f3-108">Office 365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="5f5f3-108">Office 365 Business Essentials</span></span>
* <span data-ttu-id="5f5f3-109">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="5f5f3-109">Office 365 Business Premium</span></span>
* <span data-ttu-id="5f5f3-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="5f5f3-110">Office 365 E1</span></span>
* <span data-ttu-id="5f5f3-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="5f5f3-111">Office 365 E3</span></span>
* <span data-ttu-id="5f5f3-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="5f5f3-112">Office 365 F1</span></span>
* <span data-ttu-id="5f5f3-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="5f5f3-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="5f5f3-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="5f5f3-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="5f5f3-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="5f5f3-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="5f5f3-116">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="5f5f3-116">Microsoft 365 Business</span></span>

<span data-ttu-id="5f5f3-117">これらの手順を実行するのに Business Voice ライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="5f5f3-118">インターネット接続の速度を確認する</span><span class="sxs-lookup"><span data-stu-id="5f5f3-118">Check your Internet connection speed</span></span>

<span data-ttu-id="5f5f3-119">この記事は、電話をかける必要のある人数、ビデオ会議のホストなどに対応するのにインターネット接続が十分な速度であるかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-119">This article helps you determine whether your Internet connection is fast enough for the number of people who need to make phone calls, host video conferences, and so on.</span></span> <span data-ttu-id="5f5f3-120">組織に関する情報を入力すると、Teams や Business Voice で使用されるインターネット接続の量が記載されたレポートが返されます。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-120">You'll enter some information about your organization and get back a report with how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="get-information-about-your-internet-connection-and-users"></a><span data-ttu-id="5f5f3-121">インターネット接続とユーザーに関する情報を入手する</span><span class="sxs-lookup"><span data-stu-id="5f5f3-121">Get information about your Internet connection and users</span></span>

<span data-ttu-id="5f5f3-122">始める前に、次の情報を知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-122">Before you start, you need to know the following information:</span></span>

* <span data-ttu-id="5f5f3-123">インターネット接続の速度。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-123">The speed of your Internet connection.</span></span>
* <span data-ttu-id="5f5f3-124">主にオフィス内で Business Voice を使用する人数。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-124">How many people will use Business Voice mainly from your office.</span></span>
* <span data-ttu-id="5f5f3-125">ホーム オフィスなど、主にリモートの場所で Business Voice を使用する人数。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-125">How many people will use Business Voice mainly from a remote location, such as a home office.</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="5f5f3-126">ネットワーク プランナーに情報を入力する</span><span class="sxs-lookup"><span data-stu-id="5f5f3-126">Enter your information into the network planner</span></span>

<span data-ttu-id="5f5f3-127">必要な操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-127">Here's what you need to do:</span></span>

1. <span data-ttu-id="5f5f3-128">ブラウザーを開き、https://admin.teams.microsoft.com に移動して、グローバル管理者のアクセス許可を持つアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-128">Open a browser and go to https://admin.teams.microsoft.com and sign in with an account that has Global Administrator permissions.</span></span> <span data-ttu-id="5f5f3-129">Office 365 へのサインアップに使用したアカウントには、これらのアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-129">The account you used to sign up for Office 365 has these permissions.</span></span>
1. <span data-ttu-id="5f5f3-130">**[計画]** を開いて **[ネットワーク プランナー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-130">Open **Org-wide settings** and then select **Network planner**.</span></span>
1. <span data-ttu-id="5f5f3-131">**[ネットワーク プラン]** で、**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-131">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="5f5f3-132">プランの名前を指定して、**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-132">Give your plan a name, and then select **Apply**.</span></span> <span data-ttu-id="5f5f3-133">ネットワーク プランは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-133">Your network plan should look like this:</span></span>

    ![ネットワーク プランナーのメイン画面](../media/network-planner-main.png)
1. <span data-ttu-id="5f5f3-135">ネットワーク プランの名前をクリックします (上の図の**本社**)。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-135">Click on your network plan's name (**Main office** in the picture above).</span></span>
1. <span data-ttu-id="5f5f3-136">次のページで、**[ネットワーク サイト]** タブの **[ネットワーク サイトを追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-136">On the next page, select **Add a network site** under the **Network sites** tab.</span></span>
1. <span data-ttu-id="5f5f3-137">以下のスクリーンショットに示されているフィールドにのみ入力し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-137">Fill in only the fields indicated in the screenshot below and then select **Save**.</span></span> <span data-ttu-id="5f5f3-138">この画面上の他のフィールドを空白のままにしておき、**[ExpressRoute]** も **[WAN に接続済み]** のオプションも選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-138">Leave the other fields on this screen blank, and don't select either the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![ネットワーク プランナー サイトに関する情報](../media/network-planner-site-info.png)
1. <span data-ttu-id="5f5f3-140">**[レポート]** タブで、**[レポートの開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-140">Under the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="5f5f3-141">次の情報を入力してから **[レポートの生成]** を選択し、Teams の帯域幅要件を示すレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-141">Fill out the following information and then select **Generate report** to create a report showing the bandwidth requirements for Teams.</span></span> <span data-ttu-id="5f5f3-142">次のセクションでは、レポートを読み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-142">We'll show you how to read the report in the next section.</span></span>

    ![ネットワーク プランナー レポートに関する情報](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="5f5f3-144">インターネット接続の最低速度を確認する</span><span class="sxs-lookup"><span data-stu-id="5f5f3-144">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="5f5f3-145">**[レポートの生成]** を選択すると、Office 365 で次のようなレポートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-145">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![ネットワーク プランナー レポートの詳細](../media/network-planner-report.png)

<span data-ttu-id="5f5f3-147">強調表示された数値は、Teams と Business Voice で使用するインターネット接続の量を示しています。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-147">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="5f5f3-148">この数値が、インターネット接続の合計速度の 30% を超えないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-148">We recommend that this number be no more than 30% of your total Internet connection speed.</span></span> <span data-ttu-id="5f5f3-149">たとえば、インターネット接続が 60 Mbps の場合、Teams や Business Voice は 18 Mbps を超えないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-149">For example, if your Internet connection is 60Mbps, Teams and Business Voice should take up no more than 18Mbps.</span></span>

<span data-ttu-id="5f5f3-150">インターネット接続の最低速度を確認するには、次の計算を行います。`<highlighted number> / .3`。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-150">You can find your minimum Internet connection speed by doing this calculation: `<highlighted number> / .3`.</span></span> <span data-ttu-id="5f5f3-151">上の図で強調表示された数値を使用すると、`4.6875 / .3 = 15.6` になります。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-151">Using the highlighted number in the picture above, the calculation would be `4.6875 / .3 = 15.6`.</span></span> <span data-ttu-id="5f5f3-152">つまり、インターネット接続の最低速度は、少なくとも 15.6 Mbps である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-152">This means your minimum Internet connection speed needs to be at least 15.6Mbps.</span></span>

<span data-ttu-id="5f5f3-153">Teams と Business Voice での使用量がインターネット接続の合計速度の 30% を超える場合、強調表示された数値が赤色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-153">If Teams and Business Voice will use more than 30% of your total Internet connection speed, the highlighted number will show up as red.</span></span> <span data-ttu-id="5f5f3-154">この場合、インターネット接続をアップグレードする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-154">If this happens, you might need to upgrade your Internet connection.</span></span>

![接続速度の警告](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="5f5f3-156">ネットワーク上のコンピューターとデバイスが Microsoft 365 に到達できることを確認する</span><span class="sxs-lookup"><span data-stu-id="5f5f3-156">Make sure computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="5f5f3-157">正常に動作させるには、Business Voice で使用するコンピューターとデバイスが特定のネットワーク ポートを使用して Microsoft 365 サーバーと通信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-157">To work correctly, computers and devices you want to use with Business Voice need to communicate with Microsoft 365 servers using specific network ports.</span></span> <span data-ttu-id="5f5f3-158">ネットワーク ポートは実質的に、ネットワークやインターネット経由でコンピューターとデバイスが相互に通信するための出入口です。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-158">Network ports are essentially doors through which computers and devices can talk to each other over a network or the Internet.</span></span> <span data-ttu-id="5f5f3-159">ファイアウォールでは、次の送信ネットワーク ポートを使用して、ネットワーク上のコンピューターとデバイスが Microsoft 365 に到達できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-159">Your firewall needs to allow computers and devices on your network to reach Microsoft 365 using the following outbound network ports:</span></span>

* <span data-ttu-id="5f5f3-160">**TCP ポート** 80 と 443</span><span class="sxs-lookup"><span data-stu-id="5f5f3-160">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="5f5f3-161">**UDP ポート** 3478、3479、3480、3481</span><span class="sxs-lookup"><span data-stu-id="5f5f3-161">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="5f5f3-162">お使いのファイアウォールでこれらのネットワーク ポート上の通信が許可されているかどうかを確認する一番簡単な方法は、Teams を使用してテスト通話を行うことです。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-162">The easiest way to check whether your firewall allows communication on these network ports is to make a test call using Teams.</span></span> <span data-ttu-id="5f5f3-163">テスト通話を行うには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-163">To make a test call, do the following:</span></span>

1. <span data-ttu-id="5f5f3-164">ネットワーク上のコンピューターで https://aka.ms/getteams に移動して、Teams をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-164">Go to https://aka.ms/getteams on a computer on your network to install Teams.</span></span> <span data-ttu-id="5f5f3-165">スピーカーとマイクがこのコンピューターに接続されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-165">Make sure speakers and a microphone are connected to this computer.</span></span>
2. <span data-ttu-id="5f5f3-166">Teams を開いて、Microsoft 365 アカウントを使用してサインインします</span><span class="sxs-lookup"><span data-stu-id="5f5f3-166">Open Teams and sign in using a Microsoft 365 account</span></span>
3. <span data-ttu-id="5f5f3-167">Teams で、プロファイルの画像を選択してから、**[設定]**  >  **[デバイス]** の順に選択します</span><span class="sxs-lookup"><span data-stu-id="5f5f3-167">In Teams, select your profile picture, then **Settings** > **Devices**</span></span>
4. <span data-ttu-id="5f5f3-168">**[オーディオ デバイス]** の **[テスト通話]** を選択します</span><span class="sxs-lookup"><span data-stu-id="5f5f3-168">Choose **Make a test call** under **Audio devices**</span></span>
5. <span data-ttu-id="5f5f3-169">プロンプトに従ってメッセージを残し、メッセージを再生します</span><span class="sxs-lookup"><span data-stu-id="5f5f3-169">Follow the prompts to leave a message and have it played back to you</span></span>

* <span data-ttu-id="5f5f3-170">電話が繋がり、メッセージを再生できたら、ファイアウォールは正しく設定されています。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-170">If the call connects and you can hear your message played back to you, your firewall is set up correctly.</span></span>
* <span data-ttu-id="5f5f3-171">電話は繋がるものの、プロンプトが聞こえない場合またはメッセージが再生されない場合は、コンピューターによってスピーカーとマイクが正しく設定され、検出されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-171">If the call connects but you can't hear the prompts or your message played back to you, make sure your speakers and microphone are set up correctly and detected by the computer.</span></span> <span data-ttu-id="5f5f3-172">もう一度お試しください。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-172">Try again.</span></span>
* <span data-ttu-id="5f5f3-173">電話が繋がらない場合、または繋がるもののメッセージが聞こえない場合は、ファイアウォールを更新して、上のリストに表示されているネットワーク ポートを許可する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-173">If the call doesn't connect or if it does but you can't hear your message played back to you, you might need to update your firewall to allow the network ports listed above.</span></span> <span data-ttu-id="5f5f3-174">ネットワーク ポートがインターネットに到達できるようにする方法については、ファイアウォールのドキュメントを確認するか、IT スペシャリストにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-174">Check your firewall's documentation on how to allow network ports to reach the Internet, or contact an IT specialist to help you.</span></span>

<span data-ttu-id="5f5f3-175">IT プロフェッショナルで、Business Voice をサポートするためにより大きくて複雑なネットワークを準備する方法の詳細が必要な場合は、「[環境を評価する](../3-envision-evaluate-my-environment.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, take a look at [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="5f5f3-176">記事「[環境を評価する](../3-envision-evaluate-my-environment.md)」では、帯域幅、プロキシ、ファイアウォールの要件に関する詳細と、[Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network) を使用してネットワークをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f5f3-176">The [Evaluate my environment](../3-envision-evaluate-my-environment.md) article gives additional information about bandwidth, proxy, and firewall requirements and also how to test your network using the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network).</span></span>
