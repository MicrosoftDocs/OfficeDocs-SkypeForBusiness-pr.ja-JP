---
title: Skype ルーム システム v2 の管理の概要
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
description: Skype ルーム システム v2 の管理の概要です。
ms.openlocfilehash: d79c04c69e320f404c8ce245120e9b01bd8de1ca
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965657"
---
# <a name="management-overview"></a><span data-ttu-id="e9341-103">管理の概要</span><span class="sxs-lookup"><span data-stu-id="e9341-103">Management overview</span></span> 

<span data-ttu-id="e9341-104">確認して、Skype ルーム システム v2 システム、ユーザーの利用可能な優れた操作を提供する操作が発生しを開発し、継続的なメンテナンスを実行することが重要です。</span><span class="sxs-lookup"><span data-stu-id="e9341-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Skype Room Systems v2 systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="e9341-105">監視</span><span class="sxs-lookup"><span data-stu-id="e9341-105">Monitoring</span></span> 

<span data-ttu-id="e9341-106">Skype ルーム システム v2 のシステムの監視は、2 つの主要な活動で構成されます。</span><span class="sxs-lookup"><span data-stu-id="e9341-106">Monitoring Skype Room Systems v2 systems consists of two key activities:</span></span>

-  <span data-ttu-id="e9341-107">デバイス、アプリケーション、および周辺機器の監視</span><span class="sxs-lookup"><span data-stu-id="e9341-107">Device, application, and peripheral device monitoring</span></span>

-  <span data-ttu-id="e9341-108">品質と信頼性の監視 (救難)</span><span class="sxs-lookup"><span data-stu-id="e9341-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="skype-room-systems-v2-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="e9341-109">Skype ルーム システム v2 のデバイス、アプリケーション、および周辺機器の監視</span><span class="sxs-lookup"><span data-stu-id="e9341-109">Skype Room Systems v2 device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="e9341-110">ユーザーが Skype ルーム システム v2 の単位を使用できることを確認するには、単位は、Skype ルーム システム v2 アプリケーションが正しく構成されてネットワークに接続されている、および、機能している周辺機器に接続するのにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9341-110">To ensure that users are able to use the Skype Room Systems v2 units, the units must be on, connected to the network with the Skype Room Systems v2 application correctly configured, and be connected to functioning peripheral devices.</span></span> 


<span data-ttu-id="e9341-111">Skype ルーム システム v2 のアプリケーションと接続されている周辺機器の状態についての情報は、Skype ルーム システム v2 のアプリケーションによって Windows イベント ログに書き込まれ、[この資料に](oms.md#understand-the-log-entries)記載されています。</span><span class="sxs-lookup"><span data-stu-id="e9341-111">Information about the state of the Skype Room Systems v2 application and connected peripheral devices is written by the Skype Room Systems v2 application to the Windows event log and documented [in this article](oms.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="e9341-112">**設定**</span><span class="sxs-lookup"><span data-stu-id="e9341-112">**Setting**</span></span>|<span data-ttu-id="e9341-113">**により、**</span><span class="sxs-lookup"><span data-stu-id="e9341-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e9341-114">HKLM\SOFTWARE\Microsoft\Windows 探して AutoAdminLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="e9341-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="e9341-115">起動するように Skype ルーム システム v2 を有効に</span><span class="sxs-lookup"><span data-stu-id="e9341-115">Enables Skype Room Systems v2 to boot up</span></span>  <br/> |
|<span data-ttu-id="e9341-116">電源管理 -\> AC、画面をオフに 10 分後</span><span class="sxs-lookup"><span data-stu-id="e9341-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="e9341-117">電源管理 -\> Ac システムをスリープ状態を配置しません。</span><span class="sxs-lookup"><span data-stu-id="e9341-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="e9341-118">により、接続されている表示をオフにして、自動的に復帰する Skype ルーム システム v2</span><span class="sxs-lookup"><span data-stu-id="e9341-118">Enables Skype Room Systems v2 to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="e9341-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="e9341-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="e9341-p101">または、ローカル アカウントでパスワードの期限切れを無効にする同等の手段。この設定に失敗すると、パスワードの期限が切れていることが通知され、Skype アカウントのログオンが失敗する原因になります。この影響はマシン上のすべてのローカル アカウントに及びます。したがって、この設定に失敗すると、ボックスの管理アカウントも最終的には期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="e9341-p101">Or equivalent means of disabling password expiration on the local account. Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password. Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="e9341-123">常にログインするように Skype アカウントを有効にする</span><span class="sxs-lookup"><span data-stu-id="e9341-123">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="e9341-124">グループ ポリシーを使用してファイルを転送するは、[構成ファイルの項目](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx)で説明します。</span><span class="sxs-lookup"><span data-stu-id="e9341-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="e9341-125">PowerShell を使用したリモート管理</span><span class="sxs-lookup"><span data-stu-id="e9341-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="e9341-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="e9341-126"></span></span>


<span data-ttu-id="e9341-127">Skype ルーム システム v2 システムを監視する Microsoft オペレーション マネージャーのスイートを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e9341-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Skype Room Systems v2 systems.</span></span> <span data-ttu-id="e9341-128">監視と警告の基本的なセットアップ方法については、 [OMS を使用して Skype ルーム システムの展開 v2 の管理](../../deploy/deploy-clients/with-oms.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9341-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Skype Room Systems v2 management with OMS](../../deploy/deploy-clients/with-oms.md).</span></span> 

<span data-ttu-id="e9341-129">このガイドを使用すると、Skype ルーム システム v2 の単位数と、配置での問題を識別する簡単に使用できるダッシュ ボードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e9341-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Skype Room Systems v2 units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/><span data-ttu-id="e9341-130">意思決定ポイント</span><span class="sxs-lookup"><span data-stu-id="e9341-130">Decision points</span></span>|<ul><li><span data-ttu-id="e9341-131">Skype ルーム システム v2 の展開を監視する操作の管理スイートを使用することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e9341-131">Confirm that you'll use Operations Management Suite to monitor your Skype Room Systems v2 deployment.</span></span></li><li><span data-ttu-id="e9341-132">メール ・ アラートを使用するターゲットの配布リストを決定します。</span><span class="sxs-lookup"><span data-stu-id="e9341-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/><span data-ttu-id="e9341-133">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e9341-133">Next steps</span></span>|<ul><li><span data-ttu-id="e9341-134">品質と信頼性の監視方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="e9341-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="e9341-135">品質と信頼性の監視 (救難)</span><span class="sxs-lookup"><span data-stu-id="e9341-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="e9341-136">懸念される領域を識別し、解決に向けて、継続的なオペレーションの品質と信頼性の呼び出し、会議の品質と信頼性、トレンドを監視するのには、展開の一部としてプロシージャを監視を実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e9341-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="e9341-137">救難に、建物の情報をアップロードするとき簡単に建物を比較し、特定の問題を絞り込んで、建物ごとのレベルでの呼び出しの品質と信頼性の傾向を調査できます。</span><span class="sxs-lookup"><span data-stu-id="e9341-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span> <span data-ttu-id="e9341-138">詳細については、 [Skype のオンライン配信のビジネスおよび運用ガイド 』 のモニター ・救難](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e9341-138">For more information, download the [Monitor-CQD for Skype for Business Online-Delivery and Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span></span> 

<span data-ttu-id="e9341-139">確認し、することと[品質の経験をレビュー ガイド](https://aka.ms/qerguide)の品質と信頼性の傾向を把握するのには、次の解決するためのアクション ・ プランの作成をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e9341-139">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-skype-room-systems-v2-os-and-skype-room-systems-application"></a><span data-ttu-id="e9341-140">Skype ルーム システム v2 の OS と Skype ルーム システムのアプリケーションを更新</span><span class="sxs-lookup"><span data-stu-id="e9341-140">Updating the Skype Room Systems v2 OS and Skype Room Systems application</span></span> 

<span data-ttu-id="e9341-141">Skype ルーム システム v2 OS と Skype ルーム システム v2 アプリケーション製品の更新プログラムと機能強化の恩恵を更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e9341-141">We recommend that you update the Skype Room Systems v2 OS and Skype Room Systems v2 application to benefit from product updates and improvements.</span></span> <span data-ttu-id="e9341-142">詳細については、 [Skype ルームの管理のシステムのバージョン 2](room-systems-v2-operations.md#software-updates)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9341-142">For detailed guidance, see [Manage Skype Room Systems v2](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="troubleshooting"></a><span data-ttu-id="e9341-143">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e9341-143">Troubleshooting</span></span>

<span data-ttu-id="e9341-144">オペレーション管理スイートが、運用チームとヘルプデスク警告が表示されます、Skype ルーム システム v2 の問題にするために、上記のセクションで説明したように警告を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e9341-144">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Skype Room Systems v2 issues.</span></span> <span data-ttu-id="e9341-145">[PowerShell を使用してリモート管理](room-systems-v2-operations.md#remote-management-using-powershell)では、PowerShell のリモート管理に使用できるオプションが説明されています。</span><span class="sxs-lookup"><span data-stu-id="e9341-145">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="e9341-146">周辺機器が切断されているローカルの「スマート手」かを調査し、デバイスを再接続する IT サポートに依存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9341-146">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="e9341-147">トラブルシューティングと管理モードの詳細については、 [Skype ルームの管理のシステムのバージョン 2](room-systems-v2-operations.md#admin-mode-and-device-management)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9341-147">For more information about troubleshooting and admin mode, see [Manage Skype Room Systems v2](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 

## <a name="see-also"></a><span data-ttu-id="e9341-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9341-148">See also</span></span>

[<span data-ttu-id="e9341-149">Skype ルーム システムのバージョン 2 のヘルプ</span><span class="sxs-lookup"><span data-stu-id="e9341-149">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="e9341-150">Skype Room Systems バージョン 2 の計画</span><span class="sxs-lookup"><span data-stu-id="e9341-150">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="e9341-151">Skype Room System バージョン 2 を展開する</span><span class="sxs-lookup"><span data-stu-id="e9341-151">Deploy Skype Room Systems v2</span></span>](../../deploy/deploy-clients/room-systems-v2.md)

[<span data-ttu-id="e9341-152">Skype Room Systems バージョン 2 コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="e9341-152">Configure a Skype Room Systems v2 console</span></span>](../../deploy/deploy-clients/console.md)

[<span data-ttu-id="e9341-153">Skype Room Systems バージョン 2 のコンソールの設定を、XML 構成ファイルを使用してリモートで管理する</span><span class="sxs-lookup"><span data-stu-id="e9341-153">Manage a Skype Room Systems v2 console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
