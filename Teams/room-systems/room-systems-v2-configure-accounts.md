---
title: Microsoft Teams 室のアカウントを構成する
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: ''
description: このトピックでは、Exchange および Skype for Business で Microsoft Teams ルームのアカウントを構成する方法について説明します。
ms.openlocfilehash: 2c826be24ab9051c3dd206e2f4bbc7bdc832e250
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305402"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a><span data-ttu-id="79468-103">Microsoft Teams 室のアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="79468-103">Configure accounts for Microsoft Teams Rooms</span></span>
 
<span data-ttu-id="79468-104">このトピックでは、Microsoft Teams のルームの概要と Exchange と Skype for Business との統合について説明します。</span><span class="sxs-lookup"><span data-stu-id="79468-104">Read this topic to learn about Microsoft Teams Rooms and how it integrates with Exchange and Skype for Business.</span></span>
  
<span data-ttu-id="79468-105">このトピックでは、microsoft Teams のルームで使用されるアカウントを Microsoft Exchange および Skype for Business で作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="79468-105">This topic introduces how to create accounts used by Microsoft Teams Rooms in Microsoft Exchange and Skype for Business.</span></span> <span data-ttu-id="79468-106">Microsoft Teams の会議室デバイスの展開手順については[、「Microsoft Teams 室コンソールを構成する](console.md)」をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="79468-106">Deployment instructions for Microsoft Teams Rooms devices is covered in [Configure a Microsoft Teams Rooms console](console.md).</span></span> <span data-ttu-id="79468-107">通常、インフラストラクチャは次のいずれかの構成に該当します。</span><span class="sxs-lookup"><span data-stu-id="79468-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="79468-108">オンライン展開: 組織の環境は、完全に Office 365 に展開されます。</span><span class="sxs-lookup"><span data-stu-id="79468-108">Online deployment: Your organization's environment is deployed entirely on Office 365.</span></span> <span data-ttu-id="79468-109">詳細については、「 [Office 365 で Microsoft Teams ルームを展開](with-office-365.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79468-109">For more information, see [Deploy Microsoft Teams Rooms with Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="79468-110">オンプレミスの展開: 組織には、Active Directory、Exchange、および Skype for Business Server がホストされていることを制御するサーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="79468-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted.</span></span> <span data-ttu-id="79468-111">詳細については、「 [Skype For Business Server で Microsoft Teams のルームを展開](with-skype-for-business-server-2015.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79468-111">For more information, see [Deploy Microsoft Teams Rooms with Skype for Business Server](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="79468-112">ハイブリッド展開: 組織には、オンプレミスのホストと、Office 365 を介してオンラインでホストされているサービスが混在しています。</span><span class="sxs-lookup"><span data-stu-id="79468-112">Hybrid deployments: Your organization has a mix of services, with some hosted on premises and some hosted online through Office 365.</span></span> <span data-ttu-id="79468-113">Microsoft Teams のルームでは、次のハイブリッドシナリオがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="79468-113">With Microsoft Teams Rooms, the following hybrid scenarios are supported:</span></span> 
    
  - <span data-ttu-id="79468-114">オンプレミスの Skype for Business Server での Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="79468-114">Exchange Online with Skype for Business Server on premises.</span></span> <span data-ttu-id="79468-115">詳細については、「 [Microsoft Teams のルームを Exchange Online (ハイブリッド) と連携](with-exchange-online.md)させる」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79468-115">For more information, see [Deploy Microsoft Teams Rooms with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="79468-116">Microsoft Teams または Skype for Business Online でオンプレミスの Exchange に接続します。</span><span class="sxs-lookup"><span data-stu-id="79468-116">Exchange on premises with Microsoft Teams or Skype for Business Online.</span></span> <span data-ttu-id="79468-117">詳細については、「 [Exchange on プレミス (ハイブリッド) で Microsoft Teams のルームを展開](with-exchange-on-premises.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79468-117">For more information, see [Deploy Microsoft Teams Rooms with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="79468-118">使用する構成は、デバイスのセットアップの準備方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="79468-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="79468-119">Microsoft Teams の会議室には、Active Directory、Exchange、Skype for Business に "デバイスアカウント" が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="79468-119">Microsoft Teams Rooms needs to be assigned a "device account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="79468-120">アカウントは、会議の予定表にアクセスし、Microsoft Teams または Skype for Business の接続を確立するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="79468-120">The account is used to access its meeting calendar and establish Microsoft Teams or Skype for Business connectivity.</span></span> <span data-ttu-id="79468-121">ユーザーは、このアカウントで会議をスケジュール設定することで、このアカウントを予約できます。</span><span class="sxs-lookup"><span data-stu-id="79468-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="79468-122">Microsoft Teams のルームは、会議に参加し、会議の出席者にさまざまな機能を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="79468-122">Microsoft Teams Rooms will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="79468-123">デバイスアカウントがない場合は、これらの機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="79468-123">Without a device account, none of these features will work.</span></span> 
  
<span data-ttu-id="79468-124">すべてのデバイスアカウントは、1つの Microsoft Teams のルームデバイスに固有のものであり、いくつかのセットアップが必要です。</span><span class="sxs-lookup"><span data-stu-id="79468-124">Every device account is unique to a single Microsoft Teams Rooms device, and requires some setup:</span></span>
  
- <span data-ttu-id="79468-125">デバイスアカウントが正しく構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="79468-125">The device account must be configured correctly.</span></span>
    
- <span data-ttu-id="79468-126">Microsoft Teams の会議でデバイスアカウントを検証し、適切な Microsoft サービスにアクセスできるように、インフラストラクチャを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79468-126">Your infrastructure must be configured to allow Microsoft Teams Rooms to validate the device account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="79468-127">ハードウェアを実際に設置するよりも十分に前もってアカウントを作成しておくことを、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="79468-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="79468-128">設置の 2 週間から 3 週間前にアカウントの準備を開始するのが理想的です。</span><span class="sxs-lookup"><span data-stu-id="79468-128">Ideally, account preparation is started two to three weeks before installation.</span></span> <span data-ttu-id="79468-129">ハイブリッド環境では、microsoft Teams 会議室で使用されるアカウントでは、Microsoft Teams の会議室認証には 0ffice 365 認証が必要であるため、AAD 同期でパスワード同期が有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="79468-129">In hybrid environments the account used for Microsoft Teams Rooms must have password sync enabled in AAD Sync because Microsoft Teams Rooms authentication requires 0ffice 365 authentication.</span></span>
  
<span data-ttu-id="79468-130">デバイスアカウントは、会議室または会議スペースのアカウントとして認識されるリソースアカウントと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="79468-130">You can think of a device account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="79468-131">こうした会議室を使用する会議を予約する場合は、そのアカウントを会議に招待します。</span><span class="sxs-lookup"><span data-stu-id="79468-131">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="79468-132">Microsoft Teams の会議室を最も効果的に使用するために、各ユーザーに割り当てられているデバイスアカウントと同じ操作を行います。</span><span class="sxs-lookup"><span data-stu-id="79468-132">In order to use Microsoft Teams Rooms most effectively, you do the same with the device account that's assigned to each one.</span></span>
  
<span data-ttu-id="79468-133">Microsoft Teams のルームをインストールしている会議スペースにリソースメールボックスアカウントが既に設定されている場合は、そのリソースアカウントをデバイスアカウントに変更することができます。</span><span class="sxs-lookup"><span data-stu-id="79468-133">If you already have a resource mailbox account set up for the meeting space where you're installing Microsoft Teams Rooms, you can change that resource account into a device account.</span></span> <span data-ttu-id="79468-134">この作業が完了したら、デバイスアカウントを Microsoft Teams 室のデバイスに追加するだけです。</span><span class="sxs-lookup"><span data-stu-id="79468-134">Once that's done, all you need to do is add the device account to a Microsoft Teams Rooms device.</span></span> <span data-ttu-id="79468-135">以下の「デバイスアカウントのセットアップ例」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79468-135">See device account setup examples provided below.</span></span>
  
<span data-ttu-id="79468-136">追加の構成では、「 [Microsoft teams のルーム管理を Azure monitor で計画](azure-monitor-plan.md)する」、「 [Microsoft teams のルーム管理を azure monitor で展開](azure-monitor-deploy.md)する」の説明に従って、microsoft azure モニターを使用してリモート管理を行う[ことができます。Azure モニターを使用して、Microsoft Teams のルームデバイスを管理](azure-monitor-manage.md)します。</span><span class="sxs-lookup"><span data-stu-id="79468-136">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md),  and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="79468-137">基本構成</span><span class="sxs-lookup"><span data-stu-id="79468-137">Basic configuration</span></span>

<span data-ttu-id="79468-138">これらのプロパティは、Microsoft Teams のルームで動作するデバイスアカウントの最小構成を表します。</span><span class="sxs-lookup"><span data-stu-id="79468-138">These properties represent the minimum configuration for a device account to work with Microsoft Teams Rooms.</span></span> <span data-ttu-id="79468-139">デバイスアカウントに追加のセットアップが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="79468-139">Your device account may require further setup.</span></span>
  
|<span data-ttu-id="79468-140">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="79468-140">**Property**</span></span>|<span data-ttu-id="79468-141">**用途**</span><span class="sxs-lookup"><span data-stu-id="79468-141">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="79468-142">Exchange メールボックス (Exchange 2013 SP1 以降、または Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="79468-142">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="79468-143">Exchange メールボックスを使用してアカウントを有効にすると、デバイスアカウントは、メールおよび会議の出席依頼の受信と送信を行うことができます。また、Microsoft Teams のルームデバイスで会議の予定表を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="79468-143">Enabling the account with an Exchange mailbox gives the device account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="79468-144">Microsoft Teams 会議のメールボックスは、会議室メールボックスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="79468-144">The Microsoft Teams Rooms mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="79468-145">Skype for Business が有効になっています</span><span class="sxs-lookup"><span data-stu-id="79468-145">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="79468-146">Skype for Business は、ビデオ通話、IM、画面共有などのさまざまな会議機能を使用するために有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79468-146">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="79468-147">Skype for Business Online と Skype for business Server の両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="79468-147">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="79468-148">パスワードが有効になっている</span><span class="sxs-lookup"><span data-stu-id="79468-148">Password-enabled</span></span>  <br/> |<span data-ttu-id="79468-149">デバイスアカウントは、パスワードを使用して有効にする必要があります。または、Exchange または Skype for Business Server で認証することはできません。</span><span class="sxs-lookup"><span data-stu-id="79468-149">The device account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="79468-150">詳細構成</span><span class="sxs-lookup"><span data-stu-id="79468-150">Advanced configuration</span></span>

<span data-ttu-id="79468-151">基本構成のプロパティによってデバイスアカウントを簡単な環境で設定することはできますが、Microsoft Teams のルームで正常に使用できるようにするために満たす必要があるディレクトリアカウントについては、環境にその他の制限がある可能性があります。デバイスアカウント。</span><span class="sxs-lookup"><span data-stu-id="79468-151">While the properties for the basic configuration will allow the device account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Microsoft Teams Rooms to successfully use the device account.</span></span>
  
|<span data-ttu-id="79468-152">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="79468-152">**Property**</span></span>|<span data-ttu-id="79468-153">**用途**</span><span class="sxs-lookup"><span data-stu-id="79468-153">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="79468-154">証明書ベースの認証</span><span class="sxs-lookup"><span data-stu-id="79468-154">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="79468-155">Exchange と Skype for Business Server の両方で証明書が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="79468-155">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="79468-156">証明書を展開するには、管理者としてログインしたときに証明書をロードできます。</span><span class="sxs-lookup"><span data-stu-id="79468-156">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="79468-157">デバイスアカウントを設定する最も簡単な方法は、リモートの Windows PowerShell を使って構成することです。</span><span class="sxs-lookup"><span data-stu-id="79468-157">The easiest way to set up device accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="79468-158">Microsoft は[SkypeRoomProvisioningScript](https://go.microsoft.com/fwlink/?linkid=870105)を提供します。これは、新しいデバイスアカウントを作成するのに役立ちます。また、既存のリソースアカウントを、互換性のある Microsoft Teams のルームデバイスアカウントに変換するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="79468-158">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new device accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms device accounts.</span></span>
  
<span data-ttu-id="79468-159">Windows PowerShell コマンドレットで Office 365 UI を使用する場合は、いくつかの手順を手動で実行できます。</span><span class="sxs-lookup"><span data-stu-id="79468-159">If you prefer to use the Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="79468-160">「 [Office 365 を使ってデバイスアカウントを作成](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79468-160">See [Creating a device account using Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="79468-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="79468-161">See also</span></span>

[<span data-ttu-id="79468-162">Microsoft Teams のルームを計画する</span><span class="sxs-lookup"><span data-stu-id="79468-162">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="79468-163">Microsoft Teams 室コンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="79468-163">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="79468-164">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="79468-164">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)

