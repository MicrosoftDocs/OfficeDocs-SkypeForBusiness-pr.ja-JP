---
title: Microsoft Teams ミーティングの管理の概要
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Microsoft Teams のルームシステムがユーザーに対して利用可能になるように、継続的なメンテナンスと運用を開発して実行する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd1b552e9a59ee36856d23478a7e414637976889
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085953"
---
# <a name="management-overview"></a><span data-ttu-id="0d36c-103">管理の概要</span><span class="sxs-lookup"><span data-stu-id="0d36c-103">Management overview</span></span>

<span data-ttu-id="0d36c-104">Microsoft Teams の部屋システムがユーザーに提供され、優れたユーザーエクスペリエンスを提供できるように、継続的なメンテナンスと運用を開発して実施することが重要です。</span><span class="sxs-lookup"><span data-stu-id="0d36c-104">It's essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="0d36c-105">監視</span><span class="sxs-lookup"><span data-stu-id="0d36c-105">Monitoring</span></span> 

<span data-ttu-id="0d36c-106">Microsoft Teams ミーティング システムの監視は、次の 2 つの主要なアクティビティで構成されます。</span><span class="sxs-lookup"><span data-stu-id="0d36c-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

- <span data-ttu-id="0d36c-107">デバイス、アプリケーション、周辺機器の監視</span><span class="sxs-lookup"><span data-stu-id="0d36c-107">Device, application, and peripheral device monitoring</span></span>
- <span data-ttu-id="0d36c-108">品質と信頼性の監視 (CQD)</span><span class="sxs-lookup"><span data-stu-id="0d36c-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="0d36c-109">Microsoft Teams ミーティング デバイス、アプリケーション、周辺機器の監視</span><span class="sxs-lookup"><span data-stu-id="0d36c-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="0d36c-110">Microsoft Teams ミーティングのユニットをユーザーが使えるようにするには、ユニットの電源を入れ、Microsoft Teams ミーティング アプリケーションを正しく構成したうえでネットワークに接続し、正常に機能している周辺機器に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d36c-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 

<span data-ttu-id="0d36c-111">Microsoft Teams ミーティング アプリケーションと接続している周辺機器の状態についての情報は、Microsoft Teams ミーティング アプリケーションによって Windows イベント ログに書き込まれ、[ログ エントリーを理解する](azure-monitor-manage.md#understand-the-log-entries)ために文書化されています。</span><span class="sxs-lookup"><span data-stu-id="0d36c-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="0d36c-112">**設定**</span><span class="sxs-lookup"><span data-stu-id="0d36c-112">**Setting**</span></span>|<span data-ttu-id="0d36c-113">**許可**</span><span class="sxs-lookup"><span data-stu-id="0d36c-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0d36c-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="0d36c-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="0d36c-115">Microsoft Teams ミーティングの起動を有効にする</span><span class="sxs-lookup"><span data-stu-id="0d36c-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="0d36c-116">電源管理 -\> AC で、10 分後に画面をオフにする</span><span class="sxs-lookup"><span data-stu-id="0d36c-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="0d36c-117">電源管理 -\> AC で、システムをスリープさせない</span><span class="sxs-lookup"><span data-stu-id="0d36c-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="0d36c-118">接続されているディスプレイをオフにし、自動的にウェイク アップさせるように Microsoft Teams ミーティングを有効化する</span><span class="sxs-lookup"><span data-stu-id="0d36c-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="0d36c-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="0d36c-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="0d36c-120">これは、ローカル アカウントでパスワードの有効期限を無効にすることに相当します。</span><span class="sxs-lookup"><span data-stu-id="0d36c-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="0d36c-121">この操作を行わないと、最終的に Skype アカウントがログオンできなくなり、パスワードの有効期限が切れているという通知が発生します。</span><span class="sxs-lookup"><span data-stu-id="0d36c-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="0d36c-122">これは、コンピューター上のすべてのローカル アカウントに影響を与えるため、設定に失敗すると、ボックスの管理者アカウントも最終的に有効期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="0d36c-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="0d36c-123">常にログインするように Skype アカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="0d36c-123">Enables Skype account to always log in</span></span>  <br/> |

<span data-ttu-id="0d36c-124">グループ ポリシーを使用してファイルを転送する方法については、「[ファイルの項目を構成する](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)」で説明しています。</span><span class="sxs-lookup"><span data-stu-id="0d36c-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="0d36c-125">PowerShell を使ったリモート管理</span><span class="sxs-lookup"><span data-stu-id="0d36c-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="0d36c-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="0d36c-126"><a name="RemotePS"> </a></span></span>

<span data-ttu-id="0d36c-127">Microsoft Operations Manager Suite を使用して、Microsoft Teams ミーティング システムを監視することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d36c-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="0d36c-128">監視と基本的な通知を設定する方法についてのガイダンスは、「[Azure Monitor で Microsoft Teams ミーティングの管理を展開する](azure-monitor-deploy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d36c-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md).</span></span> 

<span data-ttu-id="0d36c-129">このガイダンスを使って、簡単に使えるダッシュボードを作り、展開における Microsoft Teams ミーティングのユニットに関する問題点を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="0d36c-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="0d36c-130">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="0d36c-130">Decision points</span></span>|<ul><li><span data-ttu-id="0d36c-131">Operations Management Suite を使って Microsoft Teams ミーティングの展開を監視することを確認します。</span><span class="sxs-lookup"><span data-stu-id="0d36c-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="0d36c-132">メール通知に使用するターゲット配布リストを決定します。</span><span class="sxs-lookup"><span data-stu-id="0d36c-132">Decide the target distribution list you'll use for email alerts.</span></span></li></ul>|
|![](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="0d36c-133">次の手順</span><span class="sxs-lookup"><span data-stu-id="0d36c-133">Next steps</span></span>|<ul><li><span data-ttu-id="0d36c-134">品質と信頼性の監視アプローチを定義します。</span><span class="sxs-lookup"><span data-stu-id="0d36c-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="0d36c-135">品質と信頼性の監視 (CQD)</span><span class="sxs-lookup"><span data-stu-id="0d36c-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="0d36c-136">通話と会議の品質および信頼性の傾向を監視する展開の一環として、運用上の品質および信頼性に対する継続的な監視の手順を実行することにより、懸念のある部分を特定し、解決に向けて取り組むようにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d36c-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="0d36c-137">CQD に建物の情報をアップロードすると、建物の階ごとに通話の品質と信頼性の傾向を調査することができ、これにより建物間で比較したり、特定の問題に注目したりしやすくなります。</span><span class="sxs-lookup"><span data-stu-id="0d36c-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span>

<span data-ttu-id="0d36c-138">品質と信頼性の傾向を特定するために、[チームの通話品質](../monitor-call-quality-qos.md)を確認して追跡し、それを解決するためのアクションプランを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d36c-138">We recommend that you review and follow [Improve and monitor call quality for Teams](../monitor-call-quality-qos.md) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="0d36c-139">Microsoft Teams ミーティング OS と Microsoft Teams ミーティング アプリケーションの更新</span><span class="sxs-lookup"><span data-stu-id="0d36c-139">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="0d36c-140">Microsoft Teams ミーティング OS と Microsoft Teams ミーティング アプリケーションを更新して、製品の更新プログラムや機能強化を活用するようお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d36c-140">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="0d36c-141">詳細なガイダンスについては、「[Microsoft Teams ミーティングを管理する](rooms-operations.md#software-updates)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d36c-141">For detailed guidance, see [Manage Microsoft Teams Rooms](rooms-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="0d36c-142">Windows の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="0d36c-142">Windows Updates</span></span>

<span data-ttu-id="0d36c-143">Microsoft Teams ミーティングは Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で動作し、同じ Windows の更新プログラムと OS ビルドを標準デスクトップとして受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0d36c-143">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="0d36c-144">詳細については、「[Windows 更新プログラムを管理する](updates.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d36c-144">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="0d36c-145">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0d36c-145">Troubleshooting</span></span>

<span data-ttu-id="0d36c-146">上記のセクションで前述したように、Operations Management Suite の通知を設定し、Microsoft Teams ミーティングの問題についての通知をお客様の運用チームやヘルプデスクが受け取れるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d36c-146">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="0d36c-147">PowerShell リモート管理用のオプションについては、「[PowerShell を使ったリモート管理](rooms-operations.md#remote-management-using-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d36c-147">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="0d36c-148">周辺機器が切断されている場合は、ローカルの "スマートハンド" または IT サポートに依存して、デバイスを調査し、再接続することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d36c-148">In the event that a peripheral device is disconnected, you might need to rely on local "smart hands" or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="0d36c-149">トラブルシューティングと管理モードについての詳細は、「[管理者モードとデバイス管理](rooms-operations.md#admin-mode-and-device-management)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d36c-149">For more information about troubleshooting and admin mode, see [Admin mode and device management](rooms-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="0d36c-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d36c-150">See also</span></span>

[<span data-ttu-id="0d36c-151">Microsoft Teams Rooms ヘルプ</span><span class="sxs-lookup"><span data-stu-id="0d36c-151">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="0d36c-152">Microsoft Teams ミーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="0d36c-152">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="0d36c-153">Microsoft Teams ミーティングを展開する</span><span class="sxs-lookup"><span data-stu-id="0d36c-153">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="0d36c-154">Microsoft Teams ミーティングのコンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="0d36c-154">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="0d36c-155">Microsoft Teams ミーティング のコンソールの設定を、XML 構成ファイルを使用してリモートで管理する</span><span class="sxs-lookup"><span data-stu-id="0d36c-155">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
