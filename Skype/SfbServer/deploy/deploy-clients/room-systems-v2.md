---
title: Skype Room System バージョン 2 を展開する
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: Skype ルーム システム v2 と統合する方法と交換し、Skype ビジネス サーバー 2015 の詳細については、このトピックを参照してください。
ms.openlocfilehash: 54dc3d42d406fea2bdefcac5eb726dd77fde078f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2"></a><span data-ttu-id="1dcde-103">Skype Room System バージョン 2 を展開する</span><span class="sxs-lookup"><span data-stu-id="1dcde-103">Deploy Skype Room Systems v2</span></span>
 
<span data-ttu-id="1dcde-104">Skype ルーム システム v2 と統合する方法と交換し、Skype ビジネス サーバー 2015 の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dcde-104">Read this topic to learn about Skype Room Systems v2 and how it integrates with Exchange and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1dcde-105">このトピックでは、ビジネス サーバー 2015 の Microsoft Exchange と Skype の Skype ルーム システム v2 を使用するアカウントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1dcde-105">This topic introduces how to create accounts used by Skype Room Systems v2 in Microsoft Exchange and Skype for Business Server 2015.</span></span> <span data-ttu-id="1dcde-106">Skype ルーム システム v2 デバイスの展開の手順については、 [Skype ルーム システム v2 のコンソールを構成](console.md)してください。</span><span class="sxs-lookup"><span data-stu-id="1dcde-106">Deployment instructions for Skype Room Systems v2 devices is covered in [Configure a Skype Room Systems v2 console](console.md).</span></span> <span data-ttu-id="1dcde-107">通常、インフラストラクチャは次のいずれかの構成に該当します。</span><span class="sxs-lookup"><span data-stu-id="1dcde-107">Your infrastructure will likely fall into one of the following configurations:</span></span>
  
- <span data-ttu-id="1dcde-108">オンラインの展開: 組織の環境を Office 365 の完全に展開します。</span><span class="sxs-lookup"><span data-stu-id="1dcde-108">Online deployment: Your organization's environment is deployed entirely on Office 365.</span></span> <span data-ttu-id="1dcde-109">詳細については、 [Office 365 で v2 を Skype ルーム システムの展開](with-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dcde-109">For more information, see [Deploy Skype Room Systems v2 with Office 365](with-office-365.md).</span></span>
    
- <span data-ttu-id="1dcde-110">設置型展開: 組織が、制御しているサーバーは、Active Directory、Exchange、およびビジネス サーバー 2015 の Skype がホストされています。</span><span class="sxs-lookup"><span data-stu-id="1dcde-110">On-premises deployment: Your organization has servers that it controls, where Active Directory, Exchange, and Skype for Business Server 2015 are hosted.</span></span> <span data-ttu-id="1dcde-111">詳細については、[ビジネス サーバー 2015 の Skype で v2 を Skype ルーム システムの展開](with-skype-for-business-server-2015.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dcde-111">For more information, see [Deploy Skype Room Systems v2 with Skype for Business Server 2015](with-skype-for-business-server-2015.md)</span></span>
    
- <span data-ttu-id="1dcde-112">ハイブリッド展開: 設置型およびいくつかの Office 365 を通じてオンラインでホストでホストされているいくつかのサービスを組み合わせています。</span><span class="sxs-lookup"><span data-stu-id="1dcde-112">Hybrid deployment: Your organization has a mix of services, with some hosted on premises and some hosted online through Office 365.</span></span> <span data-ttu-id="1dcde-113">Skype ルーム システム v2 では、ハイブリッドの次のシナリオがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1dcde-113">With Skype Room Systems v2, the following hybrid scenarios are supported:</span></span> 
    
  - <span data-ttu-id="1dcde-114">Exchange Online の社内のビジネス サーバー 2015 の Skype で。</span><span class="sxs-lookup"><span data-stu-id="1dcde-114">Exchange Online with Skype for Business Server 2015 on premises.</span></span> <span data-ttu-id="1dcde-115">詳細については、 [Exchange オンライン (ハイブリッド) と v2 を Skype ルーム システムの展開](with-exchange-online.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dcde-115">For more information, see [Deploy Skype Room Systems v2 with Exchange Online (Hybrid)](with-exchange-online.md).</span></span>
    
  - <span data-ttu-id="1dcde-116">ビジネス オンラインの Skype では、社内設置型に交換します。</span><span class="sxs-lookup"><span data-stu-id="1dcde-116">Exchange on premises with Skype for Business Online.</span></span> <span data-ttu-id="1dcde-117">詳細については、[設置型 (ハイブリッド) 上での交換と v2 を Skype ルーム システムの展開](with-exchange-on-premises.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dcde-117">For more information, see [Deploy Skype Room Systems v2 with Exchange on premises (Hybrid)](with-exchange-on-premises.md).</span></span>
    
<span data-ttu-id="1dcde-118">使用する構成は、デバイスのセットアップの準備方法に影響します。</span><span class="sxs-lookup"><span data-stu-id="1dcde-118">Which configuration you have will affect how you prepare for device setup.</span></span>
  
<span data-ttu-id="1dcde-119">Skype ルーム システム v2 では、Active Directory、Exchange、およびビジネスのための Skype は、[ユーザー アカウント] を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dcde-119">Skype Room Systems v2 needs to be assigned a "User account" in Active Directory, Exchange, and Skype for Business.</span></span> <span data-ttu-id="1dcde-120">アカウントを使用して、その会議の予定表にアクセスし、Skype をビジネスの接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="1dcde-120">The account is used to access its meeting calendar and establish Skype for Business connectivity.</span></span> <span data-ttu-id="1dcde-121">ユーザーは、このアカウントで会議をスケジュール設定することで、このアカウントを予約できます。</span><span class="sxs-lookup"><span data-stu-id="1dcde-121">People can book this account by scheduling a meeting with it.</span></span> <span data-ttu-id="1dcde-122">Skype ルーム システム v2 はその会議に参加し、会議の出席者にさまざまな機能を提供することになります。</span><span class="sxs-lookup"><span data-stu-id="1dcde-122">Skype Room Systems v2 will be able to join that meeting and provide various features to the meeting attendees.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1dcde-123">ユーザー アカウントがないと、これらの機能はいずれも動作しません。</span><span class="sxs-lookup"><span data-stu-id="1dcde-123">Without a user account, none of these features will work.</span></span> 
  
<span data-ttu-id="1dcde-124">すべてのユーザー アカウントは 1 つの Skype ルーム システム v2 デバイスに一意であり、いくつかの設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="1dcde-124">Every user account is unique to a single Skype Room Systems v2 device, and requires some setup:</span></span>
  
- <span data-ttu-id="1dcde-125">ユーザー アカウントは正しく構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dcde-125">The user account must be configured correctly.</span></span>
    
- <span data-ttu-id="1dcde-126">Skype ルーム システム v2 のユーザー アカウントを検証し、適切な Microsoft サービスに到達できるようにするのには、お客様のインフラストラクチャを構成しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="1dcde-126">Your infrastructure must be configured to allow Skype Room Systems v2 to validate the user account, and to reach the appropriate Microsoft services.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="1dcde-127">ハードウェアを実際に設置するよりも十分に前もってアカウントを作成しておくことを、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1dcde-127">It is highly recommended that account creation be done well in advance of actual hardware installation.</span></span> <span data-ttu-id="1dcde-128">設置の 2 週間から 3 週間前にアカウントの準備を開始するのが理想的です。</span><span class="sxs-lookup"><span data-stu-id="1dcde-128">Ideally, account preparation is started two to three weeks before installation.</span></span> 
  
<span data-ttu-id="1dcde-129">ユーザー アカウントは、リソース アカウントのユーザーが、会議室の会議の空き容量またはのアカウントとして認識されると考えることができます。</span><span class="sxs-lookup"><span data-stu-id="1dcde-129">You can think of a user account as the resource account that people recognize as a conference room's or meeting space's account.</span></span> <span data-ttu-id="1dcde-130">こうした会議室を使用する会議を予約する場合は、そのアカウントを会議に招待します。</span><span class="sxs-lookup"><span data-stu-id="1dcde-130">When you want to schedule a meeting using that conference room, you invite the account to that meeting.</span></span> <span data-ttu-id="1dcde-131">Skype ルーム システム v2 を最も効果的に使用するには、それぞれに割り当てられているユーザー アカウントを使用して同じを行います。</span><span class="sxs-lookup"><span data-stu-id="1dcde-131">In order to use Skype Room Systems v2 most effectively, you do the same with the user account that's assigned to each one.</span></span>
  
<span data-ttu-id="1dcde-132">設定リソース メールボックスのアカウントが既に存在する場合に Skype ルーム システム v2 をインストールしている会議の場所に、ユーザー アカウントにそのリソースのアカウントを変更できます。</span><span class="sxs-lookup"><span data-stu-id="1dcde-132">If you already have a resource mailbox account set up for the meeting space where you're installing Skype Room Systems v2, you can change that resource account into a user account.</span></span> <span data-ttu-id="1dcde-133">完了すると、実行する必要があります、Skype ルーム システム v2 デバイスへのユーザー アカウントの追加です。</span><span class="sxs-lookup"><span data-stu-id="1dcde-133">Once that's done, all you need to do is add the user account to a Skype Room Systems v2 device.</span></span> <span data-ttu-id="1dcde-134">下記のユーザー アカウントのセットアップ例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dcde-134">See user account setup examples provided below.</span></span>
  
<span data-ttu-id="1dcde-135">リモート管理は、 [Skype ルーム システムの計画 v2 管理 OMS を使用して](../../plan-your-deployment/clients-and-devices/oms-management.md)、 [OMS を使用して Skype ルーム システムの展開 v2 の管理](with-oms.md)、および管理の[で説明したように運用管理スイート (OMS) を使用して、追加の構成OMS を使用して Skype ルーム システム v2 のデバイス](../../manage/skype-room-systems-v2/oms.md)。</span><span class="sxs-lookup"><span data-stu-id="1dcde-135">With additional configuration, remote management is possible using Microsoft Operations Management Suite (OMS) as described in [Plan Skype Room Systems v2 management with OMS](../../plan-your-deployment/clients-and-devices/oms-management.md), [Deploy Skype Room Systems v2 management with OMS](with-oms.md), and [Manage Skype Room Systems v2 devices with OMS](../../manage/skype-room-systems-v2/oms.md).</span></span> 
  
## <a name="basic-configuration"></a><span data-ttu-id="1dcde-136">基本構成</span><span class="sxs-lookup"><span data-stu-id="1dcde-136">Basic Configuration</span></span>

<span data-ttu-id="1dcde-137">これらのプロパティでは、Skype ルーム システム v2 を使用するユーザー アカウントの最小構成を表します。</span><span class="sxs-lookup"><span data-stu-id="1dcde-137">These properties represent the minimum configuration for a user account to work with Skype Room Systems v2.</span></span> <span data-ttu-id="1dcde-138">ユーザー アカウントによっては、追加のセットアップが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="1dcde-138">Your user account may require further setup.</span></span>
  
|<span data-ttu-id="1dcde-139">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="1dcde-139">**Property**</span></span>|<span data-ttu-id="1dcde-140">**目的**</span><span class="sxs-lookup"><span data-stu-id="1dcde-140">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1dcde-141">Exchange メールボックス (Exchange 2013 SP1 以降、または Exchange のオンライン)</span><span class="sxs-lookup"><span data-stu-id="1dcde-141">Exchange mailbox (Exchange 2013 SP1 or later, or Exchange Online)</span></span>  <br/> |<span data-ttu-id="1dcde-142">Exchange メールボックスを持つアカウントを有効にすると、受信し、会議出席依頼、およびメールの両方を送信し、Skype ルーム システム v2 デバイス上の会議の予定表を表示する機能、ユーザー アカウントが与えられます。</span><span class="sxs-lookup"><span data-stu-id="1dcde-142">Enabling the account with an Exchange mailbox gives the user account the capability to receive and send both mail and meeting requests, and to display a meetings calendar on the Skype Room Systems v2 device.</span></span> <span data-ttu-id="1dcde-143">Skype ルーム システム v2 のメールボックスは、会議室メールボックスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dcde-143">The Skype Room Systems v2 mailbox must be a room mailbox.</span></span>  <br/> |
|<span data-ttu-id="1dcde-144">ビジネス用の Skype が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="1dcde-144">Skype for Business is enabled</span></span>  <br/> |<span data-ttu-id="1dcde-145">ビデオ通話、IM、および画面共有など、さまざまな会議機能を使用するためには、ビジネス用の Skype を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1dcde-145">Skype for Business must be enabled in order to use various conferencing features, like video calls, IM, and screen-sharing.</span></span> <span data-ttu-id="1dcde-146">ビジネス オンラインの Skype と Skype のビジネス サーバーの両方がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1dcde-146">Both Skype for Business Online and Skype for Business Server are supported.</span></span>  <br/> |
|<span data-ttu-id="1dcde-147">パスワードが有効になっている</span><span class="sxs-lookup"><span data-stu-id="1dcde-147">Password-enabled</span></span>  <br/> |<span data-ttu-id="1dcde-148">パスワードを使ってユーザー アカウントを有効にする必要がありますか、ビジネスのサーバーの Exchange または Skype のいずれかで認証することはできません。</span><span class="sxs-lookup"><span data-stu-id="1dcde-148">The user account must be enabled with a password, or it cannot authenticate with either Exchange or Skype for Business Server.</span></span>  <br/> |
   
## <a name="advanced-configuration"></a><span data-ttu-id="1dcde-149">詳細構成</span><span class="sxs-lookup"><span data-stu-id="1dcde-149">Advanced Configuration</span></span>

<span data-ttu-id="1dcde-150">プロパティの中に基本的な構成が単純な環境で設定するユーザー アカウントを許可するには環境は、Skype ルーム システム v2 を正常に使用するために満たす必要のあるディレクトリのアカウントにその他の制限を持っている可能性のある、ユーザー アカウントです。</span><span class="sxs-lookup"><span data-stu-id="1dcde-150">While the properties for the basic configuration will allow the user account to be set up in a simple environment, it is possible your environment has other restrictions on directory accounts that must be met in order for Skype Room Systems v2 to successfully use the user account.</span></span>
  
|<span data-ttu-id="1dcde-151">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="1dcde-151">**Property**</span></span>|<span data-ttu-id="1dcde-152">**目的**</span><span class="sxs-lookup"><span data-stu-id="1dcde-152">**Purpose**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1dcde-153">証明書ベースの認証</span><span class="sxs-lookup"><span data-stu-id="1dcde-153">Certificate-based authentication</span></span>  <br/> |<span data-ttu-id="1dcde-154">証明書は、Exchange と Skype のビジネス サーバーの両方に必要な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1dcde-154">Certificates may be required for both Exchange and Skype for Business Server.</span></span> <span data-ttu-id="1dcde-155">証明書を展開するには、管理者としてログインしたときに証明書をロードできます。</span><span class="sxs-lookup"><span data-stu-id="1dcde-155">To deploy certificates, you can load them when logged in as Admin.</span></span>  <br/> |
   
<span data-ttu-id="1dcde-156">ユーザー アカウントを設定する最善の方法では、リモートの Windows PowerShell を使用してそれらを構成します。</span><span class="sxs-lookup"><span data-stu-id="1dcde-156">The best way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="1dcde-157">[マイクロソフトのスクリプトを提供する](https://go.microsoft.com/fwlink/?linkid=870105)ことで、新しいユーザー アカウントを作成または、Skype ルーム システム v2 の互換性のあるユーザー アカウントにそれらを有効にするためにある既存のリソース アカウントを検証します。</span><span class="sxs-lookup"><span data-stu-id="1dcde-157">[Microsoft provides scripts](https://go.microsoft.com/fwlink/?linkid=870105) that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span>
  
<span data-ttu-id="1dcde-158">Windows PowerShell コマンドレット経由で Office 365 の UI を使用する場合は、いくつかの手順を手動で実行することができます。</span><span class="sxs-lookup"><span data-stu-id="1dcde-158">If you prefer to use the Office 365 UI over Windows PowerShell cmdlets, some steps can be performed manually.</span></span> <span data-ttu-id="1dcde-159">[Office 365 を使用してデバイスのアカウントを作成する](https://technet.microsoft.com/en-us/itpro/surface-hub/create-a-device-account-using-office-365)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dcde-159">See [Creating a device account using Office 365](https://technet.microsoft.com/en-us/itpro/surface-hub/create-a-device-account-using-office-365).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1dcde-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dcde-160">See also</span></span>

#### 

[<span data-ttu-id="1dcde-161">Skype ルームの計画システム v2</span><span class="sxs-lookup"><span data-stu-id="1dcde-161">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="1dcde-162">Skype ルーム システム v2 のコンソールを構成します。</span><span class="sxs-lookup"><span data-stu-id="1dcde-162">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="1dcde-163">Skype ルームの管理システム v2</span><span class="sxs-lookup"><span data-stu-id="1dcde-163">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

