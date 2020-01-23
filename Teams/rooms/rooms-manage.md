---
title: Microsoft Teams のルームの管理の概要
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Microsoft Teams のルームの管理の概要。
ms.openlocfilehash: 6b42f9aa34acf14749a3674e975d15292f363cf0
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269054"
---
# <a name="management-overview"></a><span data-ttu-id="ac8f1-103">管理の概要</span><span class="sxs-lookup"><span data-stu-id="ac8f1-103">Management overview</span></span>

<span data-ttu-id="ac8f1-104">Microsoft Teams の部屋システムがユーザーに提供され、優れたユーザーエクスペリエンスを提供できるように、継続的なメンテナンスと運用を開発して実施することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="ac8f1-105">監視</span><span class="sxs-lookup"><span data-stu-id="ac8f1-105">Monitoring</span></span> 

<span data-ttu-id="ac8f1-106">Microsoft Teams のルームシステムの監視は、次の2つの主要なアクティビティで構成されます。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

- <span data-ttu-id="ac8f1-107">デバイス、アプリケーション、周辺機器の監視</span><span class="sxs-lookup"><span data-stu-id="ac8f1-107">Device, application, and peripheral device monitoring</span></span>
- <span data-ttu-id="ac8f1-108">品質と信頼性の監視 (CQD)</span><span class="sxs-lookup"><span data-stu-id="ac8f1-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="ac8f1-109">Microsoft Teams の会議室デバイス、アプリケーション、周辺機器の監視</span><span class="sxs-lookup"><span data-stu-id="ac8f1-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="ac8f1-110">ユーザーが Microsoft Teams のルームユニットを使用できるようにするには、単位をオンにして、Microsoft Teams のルームアプリケーションで正しく構成されたネットワークに接続して、機能している周辺デバイスに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 

<span data-ttu-id="ac8f1-111">Microsoft Teams のルームアプリケーションと接続されている周辺機器の状態に関する情報は、Microsoft Teams のルームアプリケーションによって Windows イベントログに書き込まれ、[ログエントリを理解](azure-monitor-manage.md#understand-the-log-entries)するために文書化されています。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="ac8f1-112">**]**</span><span class="sxs-lookup"><span data-stu-id="ac8f1-112">**Setting**</span></span>|<span data-ttu-id="ac8f1-113">**よう**</span><span class="sxs-lookup"><span data-stu-id="ac8f1-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ac8f1-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="ac8f1-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="ac8f1-115">Microsoft Teams のルームを起動できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="ac8f1-116">電源管理-\> AC 電源、10分後に画面をオフにする</span><span class="sxs-lookup"><span data-stu-id="ac8f1-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="ac8f1-117">電源管理-\> AC で、システムをスリープ状態にしない</span><span class="sxs-lookup"><span data-stu-id="ac8f1-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="ac8f1-118">Microsoft Teams の会議機能を有効にして、添付されたディスプレイをオフにし、自動的にスリープ状態を解除する</span><span class="sxs-lookup"><span data-stu-id="ac8f1-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="ac8f1-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="ac8f1-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="ac8f1-120">または、ローカルアカウントのパスワードの有効期限を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="ac8f1-121">そうしないと、有効期限が切れたパスワードについて、Skype アカウントがログオンに失敗することになります。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="ac8f1-122">これは、マシン上のすべてのローカルアカウントに影響を与えるため、これを設定しないと、そのボックスの管理者アカウントも最終的に有効期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="ac8f1-123">常にログインするように Skype アカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="ac8f1-123">Enables Skype account to always log in</span></span>  <br/> |

<span data-ttu-id="ac8f1-124">グループポリシーを使用してファイルを転送する方法については[、「ファイルを構成](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)する」をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="ac8f1-125">PowerShell を使用したリモート管理</span><span class="sxs-lookup"><span data-stu-id="ac8f1-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="ac8f1-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="ac8f1-126"></span></span>

<span data-ttu-id="ac8f1-127">Microsoft Operations Manager スイートを使用して、Microsoft Teams のルームシステムを監視することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="ac8f1-128">監視と基本的な通知の設定方法のガイダンスについては、「 [Azure モニターを使用して Microsoft Teams のルーム管理を展開](azure-monitor-deploy.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md).</span></span> 

<span data-ttu-id="ac8f1-129">このガイダンスを使用すると、簡単に使用できるダッシュボードを作成して、Microsoft Teams のルーム単位での展開の問題を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="ac8f1-130">判断のポイント</span><span class="sxs-lookup"><span data-stu-id="ac8f1-130">Decision points</span></span>|<ul><li><span data-ttu-id="ac8f1-131">Operations Management Suite を使用して、Microsoft Teams ルームの展開を監視することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="ac8f1-132">メール通知に使用するターゲット配布リストを決定します。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="ac8f1-133">次の手順</span><span class="sxs-lookup"><span data-stu-id="ac8f1-133">Next steps</span></span>|<ul><li><span data-ttu-id="ac8f1-134">品質と信頼性の監視方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="ac8f1-135">品質と信頼性の監視 (CQD)</span><span class="sxs-lookup"><span data-stu-id="ac8f1-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="ac8f1-136">現在の運用品質と信頼性の監視手順は展開の一部として実装することをお勧めします。通話と品質と信頼性のトレンドを監視し、問題の領域を特定し、解決に向けて作業することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="ac8f1-137">CQD に建物情報をアップロードする場合は、建物レベルで通話品質と信頼性の傾向を調べることができます。これにより、建物を比較したり、特定の問題に注意を向けることが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span>

<span data-ttu-id="ac8f1-138">品質と信頼性の傾向を特定し、問題を解決するためのアクション[プランを作成](https://aka.ms/qerguide)することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-138">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="ac8f1-139">Microsoft Teams のルーム OS および Microsoft Teams のルームアプリケーションを更新する</span><span class="sxs-lookup"><span data-stu-id="ac8f1-139">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="ac8f1-140">Microsoft Teams 室の OS および Microsoft Teams のルームアプリケーションを更新して、製品の更新や改善を活用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-140">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="ac8f1-141">詳細なガイドについては、「 [Microsoft Teams のルームを管理](rooms-operations.md#software-updates)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-141">For detailed guidance, see [Manage Microsoft Teams Rooms](rooms-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="ac8f1-142">Windows の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="ac8f1-142">Windows Updates</span></span>

<span data-ttu-id="ac8f1-143">Microsoft Teams の会議は、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップと同じ Windows 更新プログラムと OS ビルドを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-143">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="ac8f1-144">詳細については、「 [Windows 更新プログラムを管理](updates.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-144">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="ac8f1-145">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ac8f1-145">Troubleshooting</span></span>

<span data-ttu-id="ac8f1-146">上のセクションで説明されているように、operations Management Suite 通知を設定することをお勧めします。これにより、運用チームとヘルプデスクは Microsoft Teams の会議の問題について通知されます。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-146">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="ac8f1-147">PowerShell リモート管理のオプションについては、「 [powershell を使用したリモート管理](rooms-operations.md#remote-management-using-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-147">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="ac8f1-148">周辺機器が切断されている場合は、ローカルの "スマートハンド" または IT サポートに依存して、デバイスを調査し、再接続することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-148">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="ac8f1-149">トラブルシューティングと管理モードの詳細については、「[管理者モードとデバイス管理](rooms-operations.md#admin-mode-and-device-management)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac8f1-149">For more information about troubleshooting and admin mode, see [Admin mode and device management](rooms-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="ac8f1-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac8f1-150">See also</span></span>

[<span data-ttu-id="ac8f1-151">Microsoft Teams Rooms ヘルプ</span><span class="sxs-lookup"><span data-stu-id="ac8f1-151">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="ac8f1-152">Microsoft Teams のルームを計画する</span><span class="sxs-lookup"><span data-stu-id="ac8f1-152">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="ac8f1-153">Microsoft Teams ルームの展開</span><span class="sxs-lookup"><span data-stu-id="ac8f1-153">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="ac8f1-154">Microsoft Teams 室コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="ac8f1-154">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="ac8f1-155">XML 構成ファイルを使用して、Microsoft Teams ルームコンソールの設定をリモートで管理する</span><span class="sxs-lookup"><span data-stu-id="ac8f1-155">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
