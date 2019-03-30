---
title: マイクロソフト チームの会議室の管理の概要
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: マイクロソフト チームの会議室の管理の概要です。
ms.openlocfilehash: a06ffc6bb0aa69b493c95a516946c322034913f8
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012494"
---
# <a name="management-overview"></a><span data-ttu-id="e3bac-103">管理の概要</span><span class="sxs-lookup"><span data-stu-id="e3bac-103">Management overview</span></span> 

<span data-ttu-id="e3bac-104">確認して、マイクロソフト チームの会議室のシステム、ユーザーの利用可能な優れた操作を提供する操作が発生しを開発し、継続的なメンテナンスを実行することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e3bac-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="e3bac-105">監視</span><span class="sxs-lookup"><span data-stu-id="e3bac-105">Monitoring</span></span> 

<span data-ttu-id="e3bac-106">マイクロソフト チームの会議室のシステムの監視は、2 つの主要な活動で構成されます。</span><span class="sxs-lookup"><span data-stu-id="e3bac-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

-  <span data-ttu-id="e3bac-107">デバイス、アプリケーション、および周辺機器の監視</span><span class="sxs-lookup"><span data-stu-id="e3bac-107">Device, application, and peripheral device monitoring</span></span>

-  <span data-ttu-id="e3bac-108">品質と信頼性の監視 (救難)</span><span class="sxs-lookup"><span data-stu-id="e3bac-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="e3bac-109">マイクロソフト チームの会議室のデバイス、アプリケーション、および周辺機器の監視</span><span class="sxs-lookup"><span data-stu-id="e3bac-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="e3bac-110">ユーザーがマイクロソフト チームの会議室の単位を使用できることを確認するには、単位は、マイクロソフト チームの会議室アプリケーションが正しく構成されてネットワークに接続されている、および、機能の周辺機器に接続するのにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3bac-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 


<span data-ttu-id="e3bac-111">マイクロソフト チームの会議室のアプリケーションと接続されている周辺機器の状態についての情報は、Windows イベント ログにマイクロソフト チーム ルーム アプリケーションによって書かれた、[ログ エントリを理解するの](azure-monitor.md#understand-the-log-entries)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="e3bac-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="e3bac-112">**設定**</span><span class="sxs-lookup"><span data-stu-id="e3bac-112">**Setting**</span></span>|<span data-ttu-id="e3bac-113">**により、**</span><span class="sxs-lookup"><span data-stu-id="e3bac-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e3bac-114">HKLM\SOFTWARE\Microsoft\Windows 探して AutoAdminLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="e3bac-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="e3bac-115">起動するように、マイクロソフト チームの会議室を使用します。</span><span class="sxs-lookup"><span data-stu-id="e3bac-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="e3bac-116">電源管理 -\> AC、画面をオフに 10 分後</span><span class="sxs-lookup"><span data-stu-id="e3bac-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="e3bac-117">電源管理 -\> Ac システムをスリープ状態を配置しません。</span><span class="sxs-lookup"><span data-stu-id="e3bac-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="e3bac-118">マイクロソフト チームの部屋に接続されている表示をオフにして、自動的にスリープを有効に</span><span class="sxs-lookup"><span data-stu-id="e3bac-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="e3bac-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="e3bac-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="e3bac-120">またはローカル アカウントのパスワードの有効期限を無効にするのと同等のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e3bac-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="e3bac-121">これを行うには、障害が発生する Skype アカウントの期限切れのパスワードについて苦情を言ってログオンが失敗すると、最終的に。</span><span class="sxs-lookup"><span data-stu-id="e3bac-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="e3bac-122">したがってこれを設定して必要があります管理者アカウント、最終的にも期限切れにする] ボックスに、コンピューター上のすべてのローカル アカウントに影響を与えるこのこと注意してください。</span><span class="sxs-lookup"><span data-stu-id="e3bac-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="e3bac-123">常にログインするように Skype アカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="e3bac-123">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="e3bac-124">グループ ポリシーを使用してファイルを転送するは、[構成ファイルの項目](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)で説明します。</span><span class="sxs-lookup"><span data-stu-id="e3bac-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="e3bac-125">PowerShell を使用したリモート管理</span><span class="sxs-lookup"><span data-stu-id="e3bac-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="e3bac-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="e3bac-126"></span></span>

<span data-ttu-id="e3bac-127">マイクロソフト チームの会議室のシステムを監視する Microsoft オペレーション マネージャーのスイートを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e3bac-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="e3bac-128">監視と警告の基本的なセットアップ方法については、 [Azure のモニターを使用してマイクロソフト チーム ルームの展開の管理](../../deploy/deploy-clients/azure-monitor.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3bac-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](../../deploy/deploy-clients/azure-monitor.md).</span></span> 

<span data-ttu-id="e3bac-129">このガイドを使用すると、マイクロソフト チームの部屋にいるユニットを配置ですべての問題を識別する簡単に使用できるダッシュ ボードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e3bac-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/><span data-ttu-id="e3bac-130">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="e3bac-130">Decision points</span></span>|<ul><li><span data-ttu-id="e3bac-131">マイクロソフト チームの会議室の展開を監視する操作の管理スイートを使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e3bac-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="e3bac-132">メール ・ アラートを使用するターゲットの配布リストを決定します。</span><span class="sxs-lookup"><span data-stu-id="e3bac-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/><span data-ttu-id="e3bac-133">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e3bac-133">Next steps</span></span>|<ul><li><span data-ttu-id="e3bac-134">品質と信頼性の監視方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e3bac-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="e3bac-135">品質と信頼性の監視 (救難)</span><span class="sxs-lookup"><span data-stu-id="e3bac-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="e3bac-136">懸念される領域を識別し、解決に向けて、継続的なオペレーションの品質と信頼性の呼び出し、会議の品質と信頼性、トレンドを監視するのには、展開の一部としてプロシージャを監視を実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e3bac-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="e3bac-137">救難に、建物の情報をアップロードするとき簡単に建物を比較し、特定の問題を絞り込んで、建物ごとのレベルでの呼び出しの品質と信頼性の傾向を調査できます。</span><span class="sxs-lookup"><span data-stu-id="e3bac-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span> <span data-ttu-id="e3bac-138">詳細については、 [Skype のオンライン配信のビジネスおよび運用ガイド 』 のモニター ・救難](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e3bac-138">For more information, download the [Monitor-CQD for Skype for Business Online-Delivery and Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span></span> 

<span data-ttu-id="e3bac-139">確認し、することと[品質の経験をレビュー ガイド](https://aka.ms/qerguide)の品質と信頼性の傾向を把握するのには、次の解決するためのアクション ・ プランの作成をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e3bac-139">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="e3bac-140">チーム ルーム OS のマイクロソフトおよびマイクロソフト チームの会議室のアプリケーションを更新</span><span class="sxs-lookup"><span data-stu-id="e3bac-140">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="e3bac-141">製品の更新プログラムと機能強化によるメリットを得るチーム ルーム OS のマイクロソフトおよびマイクロソフト チームの会議室のアプリケーションを更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e3bac-141">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="e3bac-142">詳細については、[マイクロソフト チームのルームの管理](room-systems-v2-operations.md#software-updates)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3bac-142">For detailed guidance, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="e3bac-143">Windows の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="e3bac-143">Windows Updates</span></span>

<span data-ttu-id="e3bac-144">マイクロソフト チームの会議室では、10 企業「IoT の Windows または Windows 10 エンタープライズ (VL) 上で実行し標準のデスクトップと同じ Windows の更新プログラムおよびオペレーティング システムのビルドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e3bac-144">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="e3bac-145">詳細については、 [Windows の更新プログラムの管理](updates.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3bac-145">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="e3bac-146">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e3bac-146">Troubleshooting</span></span>

<span data-ttu-id="e3bac-147">管理スイートの操作、運用チームとヘルプデスク警告が表示されます、マイクロソフト チームの会議室の問題にするために上記のセクションで説明したようのアラートを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e3bac-147">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="e3bac-148">[PowerShell を使用してリモート管理](room-systems-v2-operations.md#remote-management-using-powershell)では、PowerShell のリモート管理に使用できるオプションが説明されています。</span><span class="sxs-lookup"><span data-stu-id="e3bac-148">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="e3bac-149">周辺機器が切断されているローカルの「スマート手」かを調査し、デバイスを再接続する IT サポートに依存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3bac-149">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="e3bac-150">トラブルシューティングと管理モードの詳細については、[マイクロソフト チームのルームの管理](room-systems-v2-operations.md#admin-mode-and-device-management)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3bac-150">For more information about troubleshooting and admin mode, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="e3bac-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3bac-151">See also</span></span>

[<span data-ttu-id="e3bac-152">マイクロソフト チームの会議室のヘルプ</span><span class="sxs-lookup"><span data-stu-id="e3bac-152">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="e3bac-153">マイクロソフト チームの会議室のプラン</span><span class="sxs-lookup"><span data-stu-id="e3bac-153">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="e3bac-154">マイクロソフト チームの会議室を配置します。</span><span class="sxs-lookup"><span data-stu-id="e3bac-154">Deploy Microsoft Teams Rooms</span></span>](../../deploy/deploy-clients/room-systems-v2.md)

[<span data-ttu-id="e3bac-155">マイクロソフト チームの会議室のコンソールを構成します。</span><span class="sxs-lookup"><span data-stu-id="e3bac-155">Configure a Microsoft Teams Rooms console</span></span>](../../deploy/deploy-clients/console.md)

[<span data-ttu-id="e3bac-156">マイクロソフト チームの会議室のコンソールの設定を XML 構成ファイルを使用してリモートで管理します。</span><span class="sxs-lookup"><span data-stu-id="e3bac-156">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
