---
title: Surface Hub の Microsoft Teams を展開する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: サーフェスのハブのマイクロソフトのチームの管理の設定を構成します。
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: add4b7ece81fd2c4184453b03c889a27982c830b
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460117"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="b341f-103">Surface Hub の Microsoft Teams を展開する</span><span class="sxs-lookup"><span data-stu-id="b341f-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="b341f-104">サーフェスのハブのチームをインストールする前に、次の操作をすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b341f-104">Before you install Teams for Surface Hub, be sure to do the following:</span></span>

 <span data-ttu-id="b341f-105">□ 作成ことを確認してハードウェア、オペレーティング システム、およびその他の要件が満たされています。</span><span class="sxs-lookup"><span data-stu-id="b341f-105">□ Make sure hardware, operating system, and other requirements are met.</span></span> <span data-ttu-id="b341f-106">詳細については、 [Microsoft Surface ハブ管理者ガイド](https://docs.microsoft.com/surface-hub/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b341f-106">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span><br>
 <span data-ttu-id="b341f-107">□ がチームに必要な最低限のオペレーティング システムの更新プログラムがインストールされているを確認してください。 [KB4343889](https://support.microsoft.com/help/4343889)。</span><span class="sxs-lookup"><span data-stu-id="b341f-107">□ Make sure the minimum operating system update required for Teams is installed - [KB4343889](https://support.microsoft.com/help/4343889).</span></span><br>
 <span data-ttu-id="b341f-108">□ ハブ デバイスのアカウントをチームのライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b341f-108">□ Assign a Teams license to the Hub device account.</span></span><br>
 <span data-ttu-id="b341f-109">□ は、Skype からのビジネス オンラインでは、処理中の場合に、チームのライセンスがユーザーに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b341f-109">□ If you are transitioning from Skype for Business Online, confirm that a Teams license is assigned to the user.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="b341f-110">Microsoft ストアからのサーフェスのハブのチームをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b341f-110">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="b341f-111">これらは、Microsoft ストアからのサーフェスのハブのチームをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b341f-111">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="b341f-112">マイクロソフトのストアを開始します。</span><span class="sxs-lookup"><span data-stu-id="b341f-112">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="b341f-113">a.</span><span class="sxs-lookup"><span data-stu-id="b341f-113">a.</span></span> <span data-ttu-id="b341f-114">**スタート**をタップして > **すべてのアプリケーション** > **の設定**です。</span><span class="sxs-lookup"><span data-stu-id="b341f-114">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="b341f-115">b.</span><span class="sxs-lookup"><span data-stu-id="b341f-115">b.</span></span> <span data-ttu-id="b341f-116">**サーフェス ハブ デバイスのアカウント、管理**をタップします。</span><span class="sxs-lookup"><span data-stu-id="b341f-116">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="b341f-117">c.</span><span class="sxs-lookup"><span data-stu-id="b341f-117">c.</span></span> <span data-ttu-id="b341f-118">左側の [**アプリケーションの & の機能**] タブをタップします。</span><span class="sxs-lookup"><span data-stu-id="b341f-118">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="b341f-119">d.</span><span class="sxs-lookup"><span data-stu-id="b341f-119">d.</span></span> <span data-ttu-id="b341f-120">、右側には、**ストアを開く**] ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="b341f-120">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="b341f-121">マイクロソフト ストアからには、*マイクロソフトのチーム*を検索します。</span><span class="sxs-lookup"><span data-stu-id="b341f-121">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="b341f-122">**サーフェスのハブのマイクロソフトのチーム**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b341f-122">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="b341f-123">インストールする**アプリケーションを取得する**ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="b341f-123">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="b341f-124">インストールが完了すると、サーフェスのハブを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b341f-124">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="b341f-125">ページを一覧表示するストアからの**起動**をタップしないようにします。</span><span class="sxs-lookup"><span data-stu-id="b341f-125">Do not tap **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="b341f-126">デフォルトの通話や会議アプリケーションは、チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="b341f-126">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="b341f-127">通話や会議アプリケーションの既定ポリシーを構成するための 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b341f-127">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="b341f-128">**オプション 1**: USB キーを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="b341f-128">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="b341f-129">**オプション 2**: Intune などの MDM を使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="b341f-129">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="b341f-130">オプション 1: は、USB キーを使用して構成します。</span><span class="sxs-lookup"><span data-stu-id="b341f-130">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="b341f-131">この[ダウンロード ページ](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)で、パッケージをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b341f-131">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="b341f-132">適切なパッケージをインストールし、USB キーにコピーする予定しているを選択します。</span><span class="sxs-lookup"><span data-stu-id="b341f-132">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="b341f-133">正しい .ppkg ファイルを使用するのには、次のように適用するにはアプリケーションの既定のポリシーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b341f-133">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="b341f-134">数値</span><span class="sxs-lookup"><span data-stu-id="b341f-134">Number</span></span>  |<span data-ttu-id="b341f-135">説明</span><span class="sxs-lookup"><span data-stu-id="b341f-135">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b341f-136">0</span><span class="sxs-lookup"><span data-stu-id="b341f-136">0</span></span>     | <span data-ttu-id="b341f-137">[開始] 画面で [チームの会議が利用可能な Skype 優先のアプリケーション</span><span class="sxs-lookup"><span data-stu-id="b341f-137">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="b341f-138">1</span><span class="sxs-lookup"><span data-stu-id="b341f-138">1</span></span>     | <span data-ttu-id="b341f-139">チーム優先のアプリケーション起動画面で、利用可能な Skype の会議</span><span class="sxs-lookup"><span data-stu-id="b341f-139">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="b341f-140">2</span><span class="sxs-lookup"><span data-stu-id="b341f-140">2</span></span>     | <span data-ttu-id="b341f-141">チームの排他的なアプリケーション (Skype アプリが利用できない) の開始画面</span><span class="sxs-lookup"><span data-stu-id="b341f-141">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="b341f-142">サーフェス ハブ デバイスに USB キーを接続します。</span><span class="sxs-lookup"><span data-stu-id="b341f-142">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="b341f-143">サーフェス ハブ デバイスの**設定**アプリを開きます。</span><span class="sxs-lookup"><span data-stu-id="b341f-143">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="b341f-144">**表面ハブ デバイスのアカウントの管理**を開きます。</span><span class="sxs-lookup"><span data-stu-id="b341f-144">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="b341f-145">**デバイスの管理**を開きます。</span><span class="sxs-lookup"><span data-stu-id="b341f-145">Open **Device Management**.</span></span> 
5. <span data-ttu-id="b341f-146">**追加またはプロビジョニング ・ パッケージを削除する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b341f-146">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="b341f-147">**パッケージの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b341f-147">Click **Add Package**.</span></span>
7. <span data-ttu-id="b341f-148">ドロップ ダウン メニューから、[**リムーバブル メディア**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b341f-148">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="b341f-149">以前、USB キーにコピーされた適切な<strong>TeamsRTMMode\*.ppkg</strong>パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="b341f-149">Add the appropriate <strong>TeamsRTMMode\*.ppkg</strong> package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="b341f-150">サーフェス ハブ デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b341f-150">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="b341f-151">デバイスを再起動した後は、開始画面から、チームのアプリケーションを起動し、カレンダーから会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="b341f-151">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="b341f-152">Intune などの MDM を使用してオプション 2: を構成します。</span><span class="sxs-lookup"><span data-stu-id="b341f-152">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="b341f-153">Intune を使用して既定の通話や会議のアプリケーション ポリシーを構成するのにには、次を使用します。</span><span class="sxs-lookup"><span data-stu-id="b341f-153">Use the following to configure the default calling and meetings application policy via Intune.</span></span> <span data-ttu-id="b341f-154">[展開 Intune を使用してサーフェスのハブのアプリケーションのマイクロソフトのチーム](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/)のブログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b341f-154">Also see the blog, [Deploy the Microsoft Teams for Surface Hub app using Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span></span>

|<span data-ttu-id="b341f-155">設定</span><span class="sxs-lookup"><span data-stu-id="b341f-155">Setting</span></span>   |<span data-ttu-id="b341f-156">値</span><span class="sxs-lookup"><span data-stu-id="b341f-156">Value</span></span>    |<span data-ttu-id="b341f-157">説明</span><span class="sxs-lookup"><span data-stu-id="b341f-157">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="b341f-158"> Path</span><span class="sxs-lookup"><span data-stu-id="b341f-158">Path</span></span>      | <span data-ttu-id="b341f-159">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="b341f-159">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="b341f-160">データ型</span><span class="sxs-lookup"><span data-stu-id="b341f-160">Data Type</span></span> | <span data-ttu-id="b341f-161">整数 (0-2)</span><span class="sxs-lookup"><span data-stu-id="b341f-161">integer (0-2)</span></span>   |<span data-ttu-id="b341f-162">0 - [開始] 画面で [チームの会議が利用可能な Skype 優先のアプリケーション</span><span class="sxs-lookup"><span data-stu-id="b341f-162">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="b341f-163">1 のチーム開始画面で、Skype の会議が利用可能なアプリケーションを優先します。</span><span class="sxs-lookup"><span data-stu-id="b341f-163">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="b341f-164">2-チームは、開始画面 (Skype アプリケーションではありません排他的なアプリケーション</span><span class="sxs-lookup"><span data-stu-id="b341f-164">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="b341f-165">運用</span><span class="sxs-lookup"><span data-stu-id="b341f-165">Operations</span></span>| <span data-ttu-id="b341f-166">取得、設定</span><span class="sxs-lookup"><span data-stu-id="b341f-166">Get, Set</span></span>        |

|<span data-ttu-id="b341f-167">設定</span><span class="sxs-lookup"><span data-stu-id="b341f-167">Setting</span></span>   |<span data-ttu-id="b341f-168">値</span><span class="sxs-lookup"><span data-stu-id="b341f-168">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="b341f-169"> Path</span><span class="sxs-lookup"><span data-stu-id="b341f-169">Path</span></span>      | <span data-ttu-id="b341f-170">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="b341f-170">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="b341f-171">データ型</span><span class="sxs-lookup"><span data-stu-id="b341f-171">Data Type</span></span> | <span data-ttu-id="b341f-172">文字列 - **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe としてチームのアプリケーション パッケージ ID に文字列を設定します。チーム**</span><span class="sxs-lookup"><span data-stu-id="b341f-172">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="b341f-173">運用</span><span class="sxs-lookup"><span data-stu-id="b341f-173">Operations</span></span>| <span data-ttu-id="b341f-174">取得、設定</span><span class="sxs-lookup"><span data-stu-id="b341f-174">Get, Set</span></span>        |

<span data-ttu-id="b341f-175">サーフェス ハブ デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b341f-175">Restart the Surface Hub device.</span></span> <span data-ttu-id="b341f-176">デバイスを再起動した後は、開始画面から、チームのアプリケーションを起動し、カレンダーから会議に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="b341f-176">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

