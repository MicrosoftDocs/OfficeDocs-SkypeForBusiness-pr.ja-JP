---
title: マイクロソフト チームの会議室のアカウントを構成します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: ''
description: マイクロソフト チームの会議室のアカウントを設定すると、Exchange とビジネス用の Skype については、このトピックを参照してください。
ms.openlocfilehash: cbff055a80a156deab0446e5da08fa4fe9bb3808
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012892"
---
# <a name="configure-accounts-for-microsoft-teams-rooms"></a><span data-ttu-id="6a4e7-103">マイクロソフト チームの会議室のアカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-103">Configure accounts for Microsoft Teams Rooms</span></span>
 
<span data-ttu-id="6a4e7-104">マイクロソフト チームの会議室と交換し、ビジネスの Skype を統合する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-104">Read this topic to learn about Microsoft Teams Rooms and how it integrates with Exchange and Skype for Business.</span></span>
  
<span data-ttu-id="6a4e7-105">このトピックでは、ビジネスのための Microsoft Exchange と Skype でマイクロソフト チームの会議室で使用するアカウントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-105">This topic introduces how to create accounts used by Microsoft Teams Rooms in Microsoft Exchange and Skype for Business.</span></span> <span data-ttu-id="6a4e7-106">マイクロソフト チーム ルーム デバイスの展開手順については、[マイクロソフト チームの会議室のコンソールの構成](console.md)で説明します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-106">Deployment instructions for Microsoft Teams Rooms devices is covered in [Configure a Microsoft Teams Rooms console](console.md).</span></span> <span data-ttu-id="6a4e7-107">通常、インフラストラクチャは次のいずれかの構成に該当します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="6a4e7-108">オンラインの展開: 組織の環境を Office 365 の完全に展開します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-108">Online deployment: Your organization's environment is deployed entirely on Office 365.</span></span> <span data-ttu-id="6a4e7-109">詳細については、 [Office 365 でのマイクロソフト チーム ルームの展開](with-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-109">For more information, see [Deploy Microsoft Teams Rooms with Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="6a4e7-110">設置型展開: 組織が、制御しているサーバーは、Active Directory、Exchange、および Skype のビジネス サーバーがホストされています。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server are hosted.</span></span> <span data-ttu-id="6a4e7-111">詳細については、 [Skype のビジネス サーバーでの Microsoft チーム ルームの展開](with-skype-for-business-server-2015.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-111">For more information, see [Deploy Microsoft Teams Rooms with Skype for Business Server](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="6a4e7-112">ハイブリッド展開: 設置型およびいくつかの Office 365 を通じてオンラインでホストでホストされているいくつかのサービスを組み合わせています。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-112">Hybrid deployments: Your organization has a mix of services, with some hosted on premises and some hosted online through Office 365.</span></span> <span data-ttu-id="6a4e7-113">マイクロソフト チーム ルームでは、ハイブリッドの次のシナリオがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-113">With Microsoft Teams Rooms, the following hybrid scenarios are supported:</span></span> 
    
  - <span data-ttu-id="6a4e7-114">Exchange オンライン ビジネス上のサーバー設置型の Skype で。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-114">Exchange Online with Skype for Business Server on premises.</span></span> <span data-ttu-id="6a4e7-115">詳細については、 [Exchange online (ハイブリッド) のマイクロソフト チーム室の配置](with-exchange-online.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-115">For more information, see [Deploy Microsoft Teams Rooms with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="6a4e7-116">ビジネス オンラインの Skype では、社内設置型に交換します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-116">Exchange on premises with Skype for Business Online.</span></span> <span data-ttu-id="6a4e7-117">詳細については、[設置型 (ハイブリッド) の交換をマイクロソフト チームの会議室を展開](with-exchange-on-premises.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-117">For more information, see [Deploy Microsoft Teams Rooms with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="6a4e7-118">使用する構成は、デバイスのセットアップの準備方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="6a4e7-119">マイクロソフト チームの会議室では、Active Directory、Exchange、およびビジネスのための Skype は、[デバイスのアカウント] を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-119">Microsoft Teams Rooms needs to be assigned a "device account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="6a4e7-120">アカウントを使用して、その会議の予定表にアクセスし、Skype をビジネスの接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-120">The account is used to access its meeting calendar and establish Skype for Business connectivity.</span></span> <span data-ttu-id="6a4e7-121">ユーザーは、このアカウントで会議をスケジュール設定することで、このアカウントを予約できます。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="6a4e7-122">マイクロソフト チームの会議室はその会議に参加し、会議の出席者にさまざまな機能を提供することになります。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-122">Microsoft Teams Rooms will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6a4e7-123">なしデバイスのアカウントでは、これらの機能のいずれも動作します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-123">Without a device account, none of these features will work.</span></span> 
  
<span data-ttu-id="6a4e7-124">デバイスのすべてのアカウントは、1 つのマイクロソフト チーム室デバイスに一意であり、いくつかの設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-124">Every device account is unique to a single Microsoft Teams Rooms device, and requires some setup:</span></span>
  
- <span data-ttu-id="6a4e7-125">デバイスのアカウントを正しく構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-125">The device account must be configured correctly.</span></span>
    
- <span data-ttu-id="6a4e7-126">デバイスのアカウントを検証し、適切な Microsoft サービスに到達するためにマイクロソフト チームの部屋を許可するには、お客様のインフラストラクチャを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-126">Your infrastructure must be configured to allow Microsoft Teams Rooms to validate the device account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="6a4e7-127">ハードウェアを実際に設置するよりも十分に前もってアカウントを作成しておくことを、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="6a4e7-128">設置の 2 週間から 3 週間前にアカウントの準備を開始するのが理想的です。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-128">Ideally, account preparation is started two to three weeks before installation.</span></span> 
  
<span data-ttu-id="6a4e7-129">デバイスのアカウントは、リソース アカウントのユーザーが、会議室の会議の空き容量またはのアカウントとして認識されると考えることができます。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-129">You can think of a device account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="6a4e7-130">こうした会議室を使用する会議を予約する場合は、そのアカウントを会議に招待します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-130">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="6a4e7-131">マイクロソフト チームの会議室を最も効果的に使用するには、それぞれに割り当てられているデバイスのアカウントを使用して同じを行います。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-131">In order to use Microsoft Teams Rooms most effectively, you do the same with the device account that's assigned to each one.</span></span>
  
<span data-ttu-id="6a4e7-132">設定リソース メールボックスのアカウントが既に存在する場合に、マイクロソフト チームの会議室をインストールしているミーティング スペース、デバイスのアカウントにリソース アカウントを変更できます。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-132">If you already have a resource mailbox account set up for the meeting space where you're installing Microsoft Teams Rooms, you can change that resource account into a device account.</span></span> <span data-ttu-id="6a4e7-133">完了するを実行する必要がありますは、マイクロソフト チームの会議室のデバイスにデバイスのアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-133">Once that's done, all you need to do is add the device account to a Microsoft Teams Rooms device.</span></span> <span data-ttu-id="6a4e7-134">デバイス アカウント セットアップ以降の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-134">See device account setup examples provided below.</span></span>
  
<span data-ttu-id="6a4e7-135">追加の構成をリモート管理は、 [Azure のモニターを使用して Microsoft チームの部屋の計画の管理](../../plan-your-deployment/clients-and-devices/azure-monitor.md)、 [Azure のモニターを使用してマイクロソフト チーム ルームの展開の管理](azure-monitor.md)、および[で説明したように、Microsoft Azure のモニターを使用してAzure のモニターを使用して Microsoft チームの会議室のデバイスを管理する](../../manage/skype-room-systems-v2/azure-monitor.md)。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-135">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor.md),  and [Manage Microsoft Teams Rooms devices with Azure Monitor](../../manage/skype-room-systems-v2/azure-monitor.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="6a4e7-136">基本的な構成</span><span class="sxs-lookup"><span data-stu-id="6a4e7-136">Basic configuration</span></span>

<span data-ttu-id="6a4e7-137">これらのプロパティでは、マイクロソフト チームの会議室を使用するデバイスのアカウントの最小構成を表します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-137">These properties represent the minimum configuration for a device account to work with Microsoft Teams Rooms.</span></span> <span data-ttu-id="6a4e7-138">お使いのデバイスのアカウントは、さらにセットアップで必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-138">Your device account may require further setup.</span></span>
  
|<span data-ttu-id="6a4e7-139">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="6a4e7-139">**Property**</span></span>|<span data-ttu-id="6a4e7-140">**用途**</span><span class="sxs-lookup"><span data-stu-id="6a4e7-140">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6a4e7-141">Exchange メールボックス (Exchange 2013 SP1 以降、または Exchange のオンライン)</span><span class="sxs-lookup"><span data-stu-id="6a4e7-141">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="6a4e7-142">Exchange メールボックスを持つアカウントを有効にすると、メールや会議出席依頼の両方を送受信するため、マイクロソフト チームの会議室のデバイス上の会議の予定表を表示する機能、デバイスのアカウントが与えられます。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-142">Enabling the account with an Exchange mailbox gives the device account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="6a4e7-143">マイクロソフト チームの会議室メールボックスは会議室メールボックスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-143">The Microsoft Teams Rooms mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="6a4e7-144">ビジネス用の Skype が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-144">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="6a4e7-145">ビデオ通話、IM、および画面共有など、さまざまな会議機能を使用するためには、ビジネス用の Skype を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-145">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="6a4e7-146">ビジネス オンラインの Skype と Skype のビジネス サーバーの両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-146">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="6a4e7-147">パスワードが有効になっている</span><span class="sxs-lookup"><span data-stu-id="6a4e7-147">Password-enabled</span></span>  <br/> |<span data-ttu-id="6a4e7-148">デバイスのアカウントは、パスワードを使用して有効にする必要がありますか、ビジネスのサーバーの Exchange または Skype のいずれかで認証することはできません。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-148">The device account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="6a4e7-149">[詳細設定の構成</span><span class="sxs-lookup"><span data-stu-id="6a4e7-149">Advanced configuration</span></span>

<span data-ttu-id="6a4e7-150">プロパティの中に基本的な構成が単純な環境で設定するデバイスのアカウントを許可するには環境は、マイクロソフト チームの会議室を使用するために満たす必要のあるディレクトリのアカウントにその他の制限を持っている可能性のある、デバイスのアカウントです。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-150">While the properties for the basic configuration will allow the device account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Microsoft Teams Rooms to successfully use the device account.</span></span>
  
|<span data-ttu-id="6a4e7-151">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="6a4e7-151">**Property**</span></span>|<span data-ttu-id="6a4e7-152">**用途**</span><span class="sxs-lookup"><span data-stu-id="6a4e7-152">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6a4e7-153">証明書ベースの認証</span><span class="sxs-lookup"><span data-stu-id="6a4e7-153">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="6a4e7-154">証明書は、Exchange と Skype のビジネス サーバーの両方に必要な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-154">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="6a4e7-155">証明書を展開するには、管理者としてログインしたときに証明書をロードできます。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-155">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="6a4e7-156">デバイスのアカウントを設定する最も簡単な方法では、リモートの Windows PowerShell を使用してそれらを構成します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-156">The easiest way to set up device accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="6a4e7-157">マイクロソフトでは、 [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)デバイスの新しいアカウントを作成または互換性のあるマイクロソフト チーム ルーム デバイスのアカウントにそれらを有効にするためにある既存のリソース アカウントの検証を支援するスクリプトを提供します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-157">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new device accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms device accounts.</span></span>
  
<span data-ttu-id="6a4e7-158">Windows PowerShell コマンドレット経由で Office 365 の UI を使用する場合は、いくつかの手順を手動で実行することができます。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-158">If you prefer to use the Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="6a4e7-159">[Office 365 を使用してデバイスのアカウントを作成する](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-159">See [Creating a device account using Office 365](https://docs.microsoft.com/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6a4e7-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a4e7-160">See also</span></span>

[<span data-ttu-id="6a4e7-161">マイクロソフト チームの会議室のプラン</span><span class="sxs-lookup"><span data-stu-id="6a4e7-161">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="6a4e7-162">マイクロソフト チームの会議室のコンソールを構成します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-162">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="6a4e7-163">マイクロソフト チームの会議室を管理します。</span><span class="sxs-lookup"><span data-stu-id="6a4e7-163">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

