---
title: 既知の問題
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 管理者は、更新、ユーザーインターフェイス、ハードウェア、制限事項、予期される動作など、Microsoft Teams のルームの既知の問題のリストについて知ることができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d8f7dcd6453458885a35bdcf7b39e729cc776f5a
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905419"
---
# <a name="known-issues"></a><span data-ttu-id="db6a8-103">既知の問題</span><span class="sxs-lookup"><span data-stu-id="db6a8-103">Known issues</span></span> 
 
<span data-ttu-id="db6a8-104">この記事では、Microsoft Teams Rooms の既知の問題を、機能の領域ごとにまとめています。</span><span class="sxs-lookup"><span data-stu-id="db6a8-104">This article lists the known issues for Microsoft Teams Rooms, by feature area.</span></span>
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<span data-ttu-id="db6a8-105"><a name="update"> </a></span><span class="sxs-lookup"><span data-stu-id="db6a8-105"><a name="update"> </a></span></span>  
## <a name="update"></a><span data-ttu-id="db6a8-106">更新する</span><span class="sxs-lookup"><span data-stu-id="db6a8-106">Update</span></span> 

| <span data-ttu-id="db6a8-107">問題のタイトル</span><span class="sxs-lookup"><span data-stu-id="db6a8-107">Issue title</span></span> |  <span data-ttu-id="db6a8-108">動作 \/ 症状</span><span class="sxs-lookup"><span data-stu-id="db6a8-108">Behavior \/ Symptom</span></span> | <span data-ttu-id="db6a8-109">既知の回避策</span><span class="sxs-lookup"><span data-stu-id="db6a8-109">Known workaround</span></span> | <span data-ttu-id="db6a8-110">サポート技術情報記事</span><span class="sxs-lookup"><span data-stu-id="db6a8-110">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
|  <span data-ttu-id="db6a8-111">旧版のアプリ</span><span class="sxs-lookup"><span data-stu-id="db6a8-111">App out of date</span></span>         |    <span data-ttu-id="db6a8-112">Microsoft Teams Rooms のコンソールには、「システム構成が古くなっています」というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="db6a8-112">The Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>                |   [<span data-ttu-id="db6a8-113">Microsoft Teams Rooms の回復ツールを使用する</span><span class="sxs-lookup"><span data-stu-id="db6a8-113">Use the Microsoft Teams Rooms recovery tool</span></span>](recovery-tool.md)             |  <span data-ttu-id="db6a8-114">なし</span><span class="sxs-lookup"><span data-stu-id="db6a8-114">None</span></span> |
|  <span data-ttu-id="db6a8-115">サポートされていないバージョンの Windows 10 に更新されたデバイス</span><span class="sxs-lookup"><span data-stu-id="db6a8-115">Device updated to unsupported version of Windows 10</span></span>   |    <span data-ttu-id="db6a8-116">Windows 10 デバイスがバージョン1803からバージョン1809に更新されました。これはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="db6a8-116">Windows 10 device updated from version 1803 to version 1809, which is not supported.</span></span> <span data-ttu-id="db6a8-117">サポートされているバージョンは1903です。</span><span class="sxs-lookup"><span data-stu-id="db6a8-117">The supported version is 1903.</span></span> |   <span data-ttu-id="db6a8-118">この問題は、 [DeferFeatureUpdatesPeriodinDays 設定のグループポリシーまたは MDM の設定](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb)によって、指定した日数の機能更新プログラムを延期できる場合に、最大365日間に設定されている場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="db6a8-118">This can happen if the [Group Policy or MDM setting for DeferFeatureUpdatesPeriodinDays](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) setting, which lets you defer feature updates for a specified number of days, is set to the maximum of 365 days.</span></span> <br><br> <span data-ttu-id="db6a8-119">Windows 10 バージョン1809は、Microsoft Teams のルームでサポートされていません。バージョン1903はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="db6a8-119">Windows 10 version 1809 isn't supported with Microsoft Teams Rooms, while version 1903 is supported.</span></span> <span data-ttu-id="db6a8-120">ただし、2020年3月27日より、バージョン1809は365日以上経過しています。</span><span class="sxs-lookup"><span data-stu-id="db6a8-120">However, as of March 27, 2020, version 1809 is over 365 days old.</span></span> <span data-ttu-id="db6a8-121">この設定が変更されていない場合、Windows はバージョン1809をインストールしようとします。これにより、Microsoft Teams のルームで問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="db6a8-121">If this setting isn't changed, Windows attempts to install version 1809, which may cause issues with Microsoft Teams Rooms.</span></span><br><br><span data-ttu-id="db6a8-122">この問題を回避するには、更新を延期するグループポリシーまたは MDM 設定を**削除**します。</span><span class="sxs-lookup"><span data-stu-id="db6a8-122">To avoid this situation, **remove** any Group Policy or MDM setting for deferring updates.</span></span> <span data-ttu-id="db6a8-123">これにより、Windows はサポートされている最新の OS バージョンに更新されます。</span><span class="sxs-lookup"><span data-stu-id="db6a8-123">This allows Windows to update to the latest, supported OS version.</span></span> <br><br><span data-ttu-id="db6a8-124">**重要**グループポリシーまたは MDM 設定は**削除**する必要があり (左側に構成されて**いない)、0には設定しない**でください。</span><span class="sxs-lookup"><span data-stu-id="db6a8-124">**IMPORTANT** The Group Policy or MDM setting must be **removed** (left unconfigured) and **not set to 0**.</span></span> <span data-ttu-id="db6a8-125">ポリシーが0に設定されている場合、Windows はサポートされていない最新バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="db6a8-125">If the policy is set to 0, Windows takes the latest available version which may not be supported.</span></span> |  <span data-ttu-id="db6a8-126">なし</span><span class="sxs-lookup"><span data-stu-id="db6a8-126">None</span></span> |

<span data-ttu-id="db6a8-127"><a name="OS-conflicts"> </a></span><span class="sxs-lookup"><span data-stu-id="db6a8-127"><a name="OS-conflicts"> </a></span></span>  
## <a name="user-interface"></a><span data-ttu-id="db6a8-128">ユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="db6a8-128">User interface</span></span> 

| <span data-ttu-id="db6a8-129">問題のタイトル</span><span class="sxs-lookup"><span data-stu-id="db6a8-129">Issue title</span></span> |  <span data-ttu-id="db6a8-130">動作 \/ 症状</span><span class="sxs-lookup"><span data-stu-id="db6a8-130">Behavior \/ Symptom</span></span> | <span data-ttu-id="db6a8-131">既知の回避策</span><span class="sxs-lookup"><span data-stu-id="db6a8-131">Known workaround</span></span> | <span data-ttu-id="db6a8-132">サポート技術情報記事</span><span class="sxs-lookup"><span data-stu-id="db6a8-132">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
|<span data-ttu-id="db6a8-133">仮想キーボードが見つかりません</span><span class="sxs-lookup"><span data-stu-id="db6a8-133">Virtual keyboard missing</span></span>   | <span data-ttu-id="db6a8-134">Microsoft Teams Rooms に情報を入力する必要がある場合に、仮想キーボードが表示されません。</span><span class="sxs-lookup"><span data-stu-id="db6a8-134">The virtual keyboard doesn't appear when you need to enter information in Microsoft Teams Rooms.</span></span> <span data-ttu-id="db6a8-135">この問題は、Windows 10 バージョン1903で発生します。</span><span class="sxs-lookup"><span data-stu-id="db6a8-135">This issue occurs in Windows 10, version 1903.</span></span> | <span data-ttu-id="db6a8-136">Windows の更新プログラムを使用して、x64 ベースのシステム用の Windows 10 バージョン1903の2020-04 累積更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="db6a8-136">Install 2020-04 Cumulative Update for Windows 10, version 1903 for x64-based Systems through Windows Updates.</span></span>  | <span data-ttu-id="db6a8-137">なし</span><span class="sxs-lookup"><span data-stu-id="db6a8-137">None</span></span> | 

<span data-ttu-id="db6a8-138"><a name="Hardware"> </a></span><span class="sxs-lookup"><span data-stu-id="db6a8-138"><a name="Hardware"> </a></span></span>  
## <a name="hardware"></a><span data-ttu-id="db6a8-139">ハードウェア</span><span class="sxs-lookup"><span data-stu-id="db6a8-139">Hardware</span></span>

| <span data-ttu-id="db6a8-140">問題のタイトル</span><span class="sxs-lookup"><span data-stu-id="db6a8-140">Issue title</span></span> |  <span data-ttu-id="db6a8-141">動作 \/ 症状</span><span class="sxs-lookup"><span data-stu-id="db6a8-141">Behavior \/ Symptom</span></span> | <span data-ttu-id="db6a8-142">既知の回避策</span><span class="sxs-lookup"><span data-stu-id="db6a8-142">Known workaround</span></span> | <span data-ttu-id="db6a8-143">サポート技術情報記事</span><span class="sxs-lookup"><span data-stu-id="db6a8-143">KB Article</span></span> |
|  ---        |      ---             |   ---            |   --- |
| <span data-ttu-id="db6a8-144">モニターが検出されません</span><span class="sxs-lookup"><span data-stu-id="db6a8-144">Monitors not detected</span></span> | <span data-ttu-id="db6a8-145">Surface Pro (2017 年版モデル) のデバイスで Microsoft Teams Rooms を実行すると、モニターは検出されません。</span><span class="sxs-lookup"><span data-stu-id="db6a8-145">When you run Microsoft Teams Rooms on a Surface Pro (Model 2017) device, monitors are not detected.</span></span> |  <span data-ttu-id="db6a8-146">20 秒以上 Surface Pro の電源ボタンを長押しします。</span><span class="sxs-lookup"><span data-stu-id="db6a8-146">Hold down the Surface Pro power button for 20 or more seconds.</span></span> <span data-ttu-id="db6a8-147">長押しすると、デバイスが再起動し、グラフィックのキャッシュをクリアします。</span><span class="sxs-lookup"><span data-stu-id="db6a8-147">When you do this, the device restarts and clears the graphics cache.</span></span> |[<span data-ttu-id="db6a8-148">KB4055681</span><span class="sxs-lookup"><span data-stu-id="db6a8-148">KB4055681</span></span>](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<span data-ttu-id="db6a8-149"><a name="Limits"> </a></span><span class="sxs-lookup"><span data-stu-id="db6a8-149"><a name="Limits"> </a></span></span>
## <a name="limitations-and-expected-behaviors"></a><span data-ttu-id="db6a8-150">制限事項と予想される動作</span><span class="sxs-lookup"><span data-stu-id="db6a8-150">Limitations and expected behaviors</span></span>

***

<span data-ttu-id="db6a8-151">Microsoft Teams Rooms は、HDMI インジェストの機能 (ビデオ、オーディオ) に関する問題を引き起こすことが確認されている、HDCP 入力をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="db6a8-151">Microsoft Teams Rooms does not support HDCP input, which has been observed to cause issues with HDMI ingest functionality (video, audio).</span></span> <span data-ttu-id="db6a8-152">Microsoft Teams Rooms に接続されたスイッチの HDCP オプションがオフになっていることを必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="db6a8-152">Take care to ensure that switches connected to Microsoft Teams Rooms have HDCP options turned off.</span></span> 

***

<span data-ttu-id="db6a8-153">ルームの前方ディスプレイを、ソースがスタンバイ モードから復帰したときにアクティブなビデオ ソース (MTR コンソールなど) に自動的に切り替える場合は、特定の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="db6a8-153">If you desire a front of room display to automatically switch to an active video source (such as an MTR console) when the source wakes from standby mode, certain conditions must be met.</span></span> <span data-ttu-id="db6a8-154">この機能はオプションですが、基盤となるハードウェアで機能がサポートされている場合は、Microsoft Teams ミーティング ソフトウェアによってサポートされます。</span><span class="sxs-lookup"><span data-stu-id="db6a8-154">This feature is optional but supported by Microsoft Teams Rooms software, provided underlying hardware supports the feature.</span></span> <span data-ttu-id="db6a8-155">ルームの前方ディスプレイとして使用される一般向けテレビは、HDMI の CEC (Consumer Electronics Control) 機能をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="db6a8-155">A consumer TV used as a front of room display needs to support the Consumer Electronics Control (CEC) feature of HDMI.</span></span>  <span data-ttu-id="db6a8-156">選択されているドックまたはコンソール (CEC をサポートしていない可能性があるため、製造元のサポート ドキュメントを参照してください) に応じて、適切な動作を実現するには、[Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) などのワークスペース コントローラーが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="db6a8-156">Depending on the dock or console selected (which might not support CEC, refer to manufacturer support documentation), a workspace controller such as an [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) may be needed to enable the desired behavior.</span></span> 

***

<span data-ttu-id="db6a8-157">常に有線の 1-Gbps ネットワーク接続を使用して、必要な帯域幅を確保してください。</span><span class="sxs-lookup"><span data-stu-id="db6a8-157">Always use a wired 1-Gbps network connection to assure you have the needed bandwidth.</span></span> 

***

<span data-ttu-id="db6a8-158">Microsoft Teams ミーティング デバイスとドメインとの信頼が途絶えている場合は、デバイスに認証して [設定] を開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="db6a8-158">If your Microsoft Teams Rooms device loses trust with the domain, you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="db6a8-159">たとえば、ドメインに参加した後に、そのドメインから Microsoft Teams ミーティングを削除した場合、信頼関係が失われます。</span><span class="sxs-lookup"><span data-stu-id="db6a8-159">For example, if you remove the Microsoft Teams Rooms from the domain after it is domain joined, trust is lost.</span></span> <span data-ttu-id="db6a8-160">回避策では、ローカルの管理者アカウントでログインします。</span><span class="sxs-lookup"><span data-stu-id="db6a8-160">The workaround is to log in with the local Admin account.</span></span> 
***
<span data-ttu-id="db6a8-161">Windows 10 Enterprise Anniversary エディション (英語版、バージョン 1607) の 64 ビット バージョンは Microsoft Teams Rooms リリース 3.0.12.0 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="db6a8-161">The 64-bit version of Windows 10 Enterprise Anniversary edition (English language, version 1607) is no longer supported as of Microsoft Teams Rooms release 3.0.12.0.</span></span> 
***
<span data-ttu-id="db6a8-162">Microsoft Teams ミーティングは、マルチウィンドウ アプリケーションであり、アプリが正常に機能するために、ルームの前方ディスプレイをデバイスの HDMI ポートに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db6a8-162">Microsoft Teams Rooms is a multi-window application and requires a front of room display to be connected to the HDMI port of the device, for the app to function correctly.</span></span> <span data-ttu-id="db6a8-163">テスト中で、まだディスプレイを購入していない場合は、HDMI ディスプレイを接続するか、ダミーの HDMI プラグを使用するかのいずれかを必ず実行してください。</span><span class="sxs-lookup"><span data-stu-id="db6a8-163">Make sure that you either have an HDMI display connected or use a dummy HDMI plug if you are testing and do not have a display purchased yet.</span></span>
***
<span data-ttu-id="db6a8-164"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="db6a8-164"><a name="See"> </a></span></span>  
## <a name="see-also"></a><span data-ttu-id="db6a8-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="db6a8-165">See also</span></span>

[<span data-ttu-id="db6a8-166">Microsoft Teams Rooms ヘルプ</span><span class="sxs-lookup"><span data-stu-id="db6a8-166">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="db6a8-167">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="db6a8-167">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
