---
title: Microsoft Teams ミーティングのアカウントを構成する
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: ''
description: このトピックでは、Exchange と Skype for Business で Microsoft Teams ミーティングのアカウントを構成する方法について説明します。
ms.openlocfilehash: 66eecbb0773f04599a0b5255cb5f83f158eb74f7
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825945"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a><span data-ttu-id="4e608-103">Microsoft Teams ミーティングのアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="4e608-103">Configure accounts for Microsoft Teams Rooms</span></span>
 
<span data-ttu-id="4e608-104">このトピックでは、Microsoft Teams ミーティングの概要と、Exchange や Skype for Business との統合方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e608-104">Read this topic to learn about Microsoft Teams Rooms and how it integrates with Exchange and Skype for Business.</span></span>
  
<span data-ttu-id="4e608-105">このトピックでは、Microsoft Exchange や Skype for Business で Microsoft Teams ミーティングに使用されるアカウントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e608-105">This topic introduces how to create accounts used by Microsoft Teams Rooms in Microsoft Exchange and Skype for Business.</span></span> <span data-ttu-id="4e608-106">Microsoft Teams ミーティング デバイスの展開手順は、「[Microsoft Teams ミーティングのコンソールを構成する](console.md)」で取り上げられてます。</span><span class="sxs-lookup"><span data-stu-id="4e608-106">Deployment instructions for Microsoft Teams Rooms devices is covered in [Configure a Microsoft Teams Rooms console](console.md).</span></span> <span data-ttu-id="4e608-107">インフラストラクチャは、次のいずれかの構成に分類されます。</span><span class="sxs-lookup"><span data-stu-id="4e608-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="4e608-108">オンライン展開: 組織の環境全体が Office 365 に展開されます。</span><span class="sxs-lookup"><span data-stu-id="4e608-108">Online deployment: Your organization's environment is deployed entirely on Office 365.</span></span> <span data-ttu-id="4e608-109">詳細については、「[Office 365 での Microsoft Teams ミーティングを展開する](with-office-365.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4e608-109">For more information, see [Deploy Microsoft Teams Rooms with Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="4e608-110">オンプレミス展開: 組織に、Active Directory、Exchange、Skype for Business Server がどこでホストされるかを制御するサーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="4e608-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted.</span></span> <span data-ttu-id="4e608-111">詳細については、「[Skype for Business Server での Microsoft Teams ミーティングを展開する](with-skype-for-business-server-2015.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4e608-111">For more information, see [Deploy Microsoft Teams Rooms with Skype for Business Server](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="4e608-112">ハイブリッド展開: 組織に、オンプレミスでホストされるサービスと、Office 365 を介してオンラインでホストされるサービスが混在しています。</span><span class="sxs-lookup"><span data-stu-id="4e608-112">Hybrid deployments: Your organization has a mix of services, with some hosted on premises and some hosted online through Office 365.</span></span> <span data-ttu-id="4e608-113">Microsoft Teams ミーティングでは、次のハイブリッド シナリオがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4e608-113">With Microsoft Teams Rooms, the following hybrid scenarios are supported:</span></span> 
    
  - <span data-ttu-id="4e608-114">Exchange Online とオンプレミスの Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="4e608-114">Exchange Online with Skype for Business Server on premises.</span></span> <span data-ttu-id="4e608-115">詳細については、「[Exchange Online を使用して Microsoft Teams ミーティングを展開 (ハイブリッド)](with-exchange-online.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4e608-115">For more information, see [Deploy Microsoft Teams Rooms with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="4e608-116">オンプレミスの Exchange と Microsoft Teams または Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="4e608-116">Exchange on premises with Microsoft Teams or Skype for Business Online.</span></span> <span data-ttu-id="4e608-117">詳細については、「[オンプレミスで Exchange を使用して Microsoft Teams ミーティングを展開 (ハイブリッド)](with-exchange-on-premises.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4e608-117">For more information, see [Deploy Microsoft Teams Rooms with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="4e608-118">どの構成かによって、デバイス セットアップの準備の方法が変わります。</span><span class="sxs-lookup"><span data-stu-id="4e608-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="4e608-119">Microsoft Teams ミーティングには、Active Directory、Exchange、Skype for Business の "デバイス アカウント" が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e608-119">Microsoft Teams Rooms needs to be assigned a "device account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="4e608-120">このアカウントは、会議の予定表にアクセスし、Microsoft Teams または Skype for Business の接続を確立するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4e608-120">The account is used to access its meeting calendar and establish Microsoft Teams or Skype for Business connectivity.</span></span> <span data-ttu-id="4e608-121">このアカウントを使用して会議をスケジュールすることで、ユーザーはこのアカウントを予約することができます。</span><span class="sxs-lookup"><span data-stu-id="4e608-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="4e608-122">Microsoft Teams ミーティングはその会議に参加して、会議の出席者にさまざまな機能を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="4e608-122">Microsoft Teams Rooms will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4e608-123">デバイス アカウントがないと、これらの機能はいずれも動作しません。</span><span class="sxs-lookup"><span data-stu-id="4e608-123">Without a device account, none of these features will work.</span></span> 
  
<span data-ttu-id="4e608-124">それぞれのデバイス アカウントは 1 つの Microsoft Teams ミーティング デバイスに固有で、設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="4e608-124">Every device account is unique to a single Microsoft Teams Rooms device, and requires some setup:</span></span>
  
- <span data-ttu-id="4e608-125">デバイス アカウントは正しく構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e608-125">The device account must be configured correctly.</span></span>
    
- <span data-ttu-id="4e608-126">Microsoft Teams ミーティングがデバイス アカウントを確認し、適切な Microsoft のサービスに到達できるように、インフラストラクチャを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e608-126">Your infrastructure must be configured to allow Microsoft Teams Rooms to validate the device account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="4e608-127">ハードウェアを実際に設置するよりも十分に前もってアカウントを作成しておくことを、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4e608-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="4e608-128">設置の 2 週間から 3 週間前にアカウントの準備を開始するのが理想的です。</span><span class="sxs-lookup"><span data-stu-id="4e608-128">Ideally, account preparation is started two to three weeks before installation.</span></span> <span data-ttu-id="4e608-129">ハイブリッド環境で Microsoft Teams ミーティングに使用するアカウントは、Microsoft Teams ミーティングの認証に Office 365 認証が求められるため、AAD Sync で有効にされたパスワードの同期が必要です。</span><span class="sxs-lookup"><span data-stu-id="4e608-129">In hybrid environments the account used for Microsoft Teams Rooms must have password sync enabled in AAD Sync because Microsoft Teams Rooms authentication requires Office 365 authentication.</span></span>
  
<span data-ttu-id="4e608-130">デバイス アカウントは、会議室やミーティング スペースのアカウントとして認識されるリソース アカウントと見なすことができます。</span><span class="sxs-lookup"><span data-stu-id="4e608-130">You can think of a device account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="4e608-131">その会議室を使って会議をスケジュールするときは、アカウントをその会議に招待します。</span><span class="sxs-lookup"><span data-stu-id="4e608-131">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="4e608-132">Microsoft Teams ミーティングを最も効果的に利用するには、各会議室に割り当てられているデバイス アカウントで同じ操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4e608-132">In order to use Microsoft Teams Rooms most effectively, you do the same with the device account that's assigned to each one.</span></span>
  
<span data-ttu-id="4e608-133">Microsoft Teams ミーティングをインストールするミーティング スペース用に設定されたリソース メールボックス アカウントが既に存在する場合は、そのリソース アカウントをデバイス アカウントに変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4e608-133">If you already have a resource mailbox account set up for the meeting space where you're installing Microsoft Teams Rooms, you can change that resource account into a device account.</span></span> <span data-ttu-id="4e608-134">その操作が完了した後に行う必要があるのは、デバイス アカウントを Microsoft Teams ミーティング デバイスに追加することだけです。</span><span class="sxs-lookup"><span data-stu-id="4e608-134">Once that's done, all you need to do is add the device account to a Microsoft Teams Rooms device.</span></span> <span data-ttu-id="4e608-135">下記のデバイス アカウントのセットアップ例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e608-135">See device account setup examples provided below.</span></span>
  
<span data-ttu-id="4e608-136">「[Azure Monitor を使用して Microsoft Teams ミーティングの管理を計画する](azure-monitor-plan.md)」、「[Azure Monitor を使用して Microsoft Teams ミーティングの管理を展開する](azure-monitor-deploy.md)」、「[Azure Monitor を使用して Microsoft Teams ミーティングのデバイスを管理する](azure-monitor-manage.md)」で説明されているように、追加の構成を行えば Microsoft Azure Monitor を使用してリモート管理を行うことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="4e608-136">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md),  and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="4e608-137">基本構成</span><span class="sxs-lookup"><span data-stu-id="4e608-137">Basic configuration</span></span>

<span data-ttu-id="4e608-138">次のプロパティは、デバイス アカウントが Microsoft Teams ミーティングで機能するための最小構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="4e608-138">These properties represent the minimum configuration for a device account to work with Microsoft Teams Rooms.</span></span> <span data-ttu-id="4e608-139">デバイス アカウントによっては、追加のセットアップが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4e608-139">Your device account may require further setup.</span></span>
  
|<span data-ttu-id="4e608-140">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="4e608-140">**Property**</span></span>|<span data-ttu-id="4e608-141">**用途**</span><span class="sxs-lookup"><span data-stu-id="4e608-141">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4e608-142">Exchange メールボックス (Exchange 2013 SP1 以降、または Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="4e608-142">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="4e608-143">アカウントを Exchange メールボックスで有効にすると、そのデバイス アカウントはメールと会議出席依頼の両方を送受信し、Microsoft Teams ミーティング デバイスで会議の予定表を表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4e608-143">Enabling the account with an Exchange mailbox gives the device account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="4e608-144">Microsoft Teams ミーティングのメールボックスは、会議室メールボックスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e608-144">The Microsoft Teams Rooms mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="4e608-145">Skype for Business が有効</span><span class="sxs-lookup"><span data-stu-id="4e608-145">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="4e608-146">ビデオ通話、IM、画面共有などのさまざまな会議機能を使用するには、Skype for Business が有効である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e608-146">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="4e608-147">Skype for Business Online と Skype for Business Server の両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4e608-147">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="4e608-148">Password が有効</span><span class="sxs-lookup"><span data-stu-id="4e608-148">Password-enabled</span></span>  <br/> |<span data-ttu-id="4e608-149">デバイス アカウントはパスワードによって有効になる必要があります。そうでない場合は、Exchange や Skype for Business Server で認証できません。</span><span class="sxs-lookup"><span data-stu-id="4e608-149">The device account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="4e608-150">詳細構成</span><span class="sxs-lookup"><span data-stu-id="4e608-150">Advanced configuration</span></span>

<span data-ttu-id="4e608-151">基本構成のプロパティではシンプルな環境でデバイス アカウントをセットアップできますが、お使いの環境でディレクトリ アカウントに対するその他の制限が存在し、Microsoft Teams ミーティングで正常にデバイス アカウントを使用するためにそれらの制限を満たす必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4e608-151">While the properties for the basic configuration will allow the device account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Microsoft Teams Rooms to successfully use the device account.</span></span>
  
|<span data-ttu-id="4e608-152">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="4e608-152">**Property**</span></span>|<span data-ttu-id="4e608-153">**用途**</span><span class="sxs-lookup"><span data-stu-id="4e608-153">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4e608-154">証明書ベースの認証</span><span class="sxs-lookup"><span data-stu-id="4e608-154">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="4e608-155">Exchange と Skype for Business Server の両方で証明書が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4e608-155">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="4e608-156">証明書を展開するには、管理者としてログインするときに証明書を読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="4e608-156">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="4e608-157">デバイス アカウントをセットアップする最も簡単な方法は、リモート Windows PowerShell を使用して構成することです。</span><span class="sxs-lookup"><span data-stu-id="4e608-157">The easiest way to set up device accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="4e608-158">Microsoft では、[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) を提供しています。これは、新しいデバイス アカウントを作成するか、既存のリソース アカウントを検証するスクリプトであり、それらのアカウントを互換性のある Microsoft Teams ミーティングのデバイス アカウントに変換する助けとなります。</span><span class="sxs-lookup"><span data-stu-id="4e608-158">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new device accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms device accounts.</span></span>
  
<span data-ttu-id="4e608-159">Windows PowerShell コマンドレットよりも Office 365 UI を使用することを望む場合は、一部の手順を手動で実行できます。</span><span class="sxs-lookup"><span data-stu-id="4e608-159">If you prefer to use the Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="4e608-160">「[Office 365 を使ったデバイス アカウントの作成](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e608-160">See [Creating a device account using Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4e608-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e608-161">See also</span></span>

[<span data-ttu-id="4e608-162">Microsoft Teams ミーティングを計画する</span><span class="sxs-lookup"><span data-stu-id="4e608-162">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="4e608-163">Microsoft Teams ミーティングのコンソールを構成する</span><span class="sxs-lookup"><span data-stu-id="4e608-163">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="4e608-164">Microsoft Teams Rooms を管理する</span><span class="sxs-lookup"><span data-stu-id="4e608-164">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

