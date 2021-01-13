---
title: ユーザーの Skype for Business 2015 クライアント エクスペリエンスを計画する
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: '概要: Skype for Business Online、Skype for Business Server 2019、Skype for Business Server 2015、Lync Server 2013、または Lync Server 2010 を使用している場合に関係ない、新しい Skype for Business について、および環境とユーザーが更新プログラムを準備するために実行できる手順について説明します。'
ms.openlocfilehash: 1136bcf95a0c9ee045d9947bd7a2f7771dae16fd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813927"
---
# <a name="plan-the-skype-for-business-2015-client-experience-for-your-users"></a><span data-ttu-id="3d8a3-103">ユーザーの Skype for Business 2015 クライアント エクスペリエンスを計画する</span><span class="sxs-lookup"><span data-stu-id="3d8a3-103">Plan the Skype for Business 2015 client experience for your users</span></span>
 
<span data-ttu-id="3d8a3-104">**概要:** 新しい Skype for Business と、Skype for Business Online、Skype for Business Server 2019、Skype for Business Server 2015、Lync Server 2013、Lync Server 2010 を使用している場合に、環境とユーザーが更新プログラムを準備するために実行できる手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-104">**Summary:** Learn about the new Skype for Business and the steps you can take to prepare your environment and your users for the update, whether you're using Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015, Lync Server 2013, or Lync Server 2010.</span></span>
  
<span data-ttu-id="3d8a3-105">Lync 2013 Office 2015 年 4 月 14 日には、新しい Skype for Business ユーザー インターフェイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-105">The April 14th, 2015 Office Update for Lync 2013 includes the new Skype for Business user interface.</span></span> <span data-ttu-id="3d8a3-106">この更新プログラムを使用すると、管理者はクライアントの外観を制御し、Lync 2013 クライアント エクスペリエンスを維持するか、改善された Skype for Business クライアント エクスペリエンスを使用するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-106">This update enables administrators to control the look and feel of the client and choose whether to retain the Lync 2013 client experience or use the improved Skype for Business client experience.</span></span> <span data-ttu-id="3d8a3-107">Skype for Business クライアントは、Lync 2013 クライアントを効果的に置き換え、管理者が既存の Lync クライアント エクスペリエンスと新しい Skype for Business クライアント エクスペリエンスの中から選択する機能を追加しました。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-107">The Skype for Business client effectively replaced the Lync 2013 client, and added the ability for administrators to choose between the existing Lync client experience and the new Skype for Business client experience.</span></span> <span data-ttu-id="3d8a3-108">この更新プログラムの詳細については [、Lync 2013 (Skype for Business) (KB2889923) 用の 2015](https://support.microsoft.com/kb/2889923/)年 4 月 14 日の更新プログラムを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-108">For information about this update, see [April 14, 2015 update for Lync 2013 (Skype for Business) (KB2889923)](https://support.microsoft.com/kb/2889923/).</span></span>
  
<span data-ttu-id="3d8a3-109">2015 年 5 月 12 日には、更新された Skype for Business クライアントを含む Office月次更新プログラムが追加されます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-109">On May 12th, 2015 there will be another monthly update from Office that includes the updated Skype for Business client.</span></span> <span data-ttu-id="3d8a3-110">4 月の更新プログラムを適用しなかった多くのお客様は、5 月 12 日の更新プログラムをOffice 2013。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-110">Many customers that did not apply the April update will pick up the May 12th update for Office 2013.</span></span> <span data-ttu-id="3d8a3-111">このトピックの情報は、組織、環境、およびユーザーのクライアント更新の準備に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-111">The information in this topic will help you prepare your organization, your environment, and your users for the client update.</span></span> <span data-ttu-id="3d8a3-112">ユーザーとサポート チームが簡単に移行するには、このトピックの情報を使用して、ユーザーに必要なクライアント エクスペリエンスを決定し、組織にクライアント更新プログラムを展開する前に環境に変更を加えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-112">To make the transition easy for your users and support teams, use the information in this topic to help you decide which client experience you want for your users and then make the changes to your environment before deploying the client update in your organization.</span></span>
  
- [<span data-ttu-id="3d8a3-113">ユーザーに対してどのようなクライアント エクスペリエンスが必要か。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-113">What client experience do you want for your users?</span></span>](user-experience.md#clientexperience)
    
- [<span data-ttu-id="3d8a3-114">Skype for Business クライアント用の環境を準備する</span><span class="sxs-lookup"><span data-stu-id="3d8a3-114">Prepare your environment for the Skype for Business client</span></span>](user-experience.md#usinglync)
    
- [<span data-ttu-id="3d8a3-115">サポート チームとエンド ユーザーの更新準備に役立つリソース</span><span class="sxs-lookup"><span data-stu-id="3d8a3-115">Resources to help you prepare your support teams and your end users for the update</span></span>](user-experience.md#support)
    
> [!NOTE]
> <span data-ttu-id="3d8a3-116">Lync 2013 クライアント エクスペリエンスは、Skype for Business 2016 クライアント バージョンのオプションではありません。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="3d8a3-117">Lync 2013 クライアントを使用するためのクライアント環境の構成を試みる前に、クライアントのバージョンを確認して、番号 16 で始まるのではないか確認してください。例: 16.x.x.x。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a><span data-ttu-id="3d8a3-118">ユーザーに対してどのようなクライアント エクスペリエンスが必要か。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-118">What client experience do you want for your users?</span></span>
<span data-ttu-id="3d8a3-119"><a name="clientexperience"> </a></span><span class="sxs-lookup"><span data-stu-id="3d8a3-119"><a name="clientexperience"> </a></span></span>

<span data-ttu-id="3d8a3-120">新しい Skype for Business クライアントを使用すると、ユーザーが取得するクライアント エクスペリエンス (Lync または Skype for Business) を制御できます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-120">With the new Skype for Business client, you can control which client experience your users get, either Lync or Skype for Business.</span></span> <span data-ttu-id="3d8a3-121">既定のクライアント エクスペリエンスは、Lync または Skype for Business オンプレミスを使用しているかオンラインを使用しているかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-121">The default client experience depends on whether you are using Lync or Skype for Business on-premises or online.</span></span> <span data-ttu-id="3d8a3-122">現在、Microsoft 365 Apps for enterprise、Microsoft 365 Business Standard、または Office 2013 で Skype for Business Online (Lync Online) を使用している場合、更新された Skype for Business クライアント エクスペリエンス (Skype の外観から着たもの) が既定のユーザー エクスペリエンスになります。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-122">If you are using Skype for Business Online (Lync Online) today with Microsoft 365 Apps for enterprise, Microsoft 365 Business Standard or Office 2013, the updated Skype for Business client experience—inspired by the look and feel of Skype—will be the default user experience.</span></span> <span data-ttu-id="3d8a3-123">現在、オンプレミスの Lync Server を使用している場合、Lync クライアント エクスペリエンスが既定になります。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-123">If you are using Lync Server on-premises today, the Lync client experience will be the default.</span></span>
  
<span data-ttu-id="3d8a3-124">クライアント ポリシーを使用して、ユーザーが取得するクライアント エクスペリエンスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-124">You can configure which client experience your users get by using client policies.</span></span> <span data-ttu-id="3d8a3-125">クライアント ポリシーは、ユーザーが Lync または Skype for Business にログインするときに適用される一連の構成設定です。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-125">A client policy is a set of configuration settings that are applied to users when they login to Lync or Skype for Business.</span></span>
  
### <a name="skype-for-business-client-experience"></a><span data-ttu-id="3d8a3-126">Skype for Business クライアント エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="3d8a3-126">Skype for Business client experience</span></span>

<span data-ttu-id="3d8a3-127">Skype for Business は、Lync のすべての機能に加えて、簡素化されたコントロールと Skype の使い慣れたアイコンを備え、新機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-127">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons from Skype.</span></span> <span data-ttu-id="3d8a3-128">Skype for Business の一部の新機能は、新しい Skype for Business クライアント エクスペリエンスでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-128">Some new features in Skype for Business are available only with the new Skype for Business client experience.</span></span> <span data-ttu-id="3d8a3-129">Skype for Business の新機能の詳細については、「Skype for Business の検出」を [参照してください](https://go.microsoft.com/fwlink/p/?LinkId=528686)。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-129">To learn more about the new features in Skype for Business, see [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686).</span></span>
  
### <a name="lync-client-experience"></a><span data-ttu-id="3d8a3-130">Lync クライアント エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="3d8a3-130">Lync client experience</span></span>

<span data-ttu-id="3d8a3-131">Lync クライアント エクスペリエンスは、ユーザーが既に理解している Lync 2013 クライアント エクスペリエンスと非常に似ていますが、ユーザーに知らせたい変更がいくつか存在します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-131">The Lync client experience is very similar to the Lync 2013 client experience that your users are already familiar with, but there are a few changes that you'll want to let your users know about.</span></span> <span data-ttu-id="3d8a3-132">Lync クライアント エクスペリエンスと Lync 2013 クライアントの違いを確認するには [、Lync](https://go.microsoft.com/fwlink/p/?LinkId=544712) を使用している場合に Skype for Business が表示される理由と、このトピックの後半にあるその他のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-132">To see what's different between the Lync client experience and the Lync 2013 client, see [Why do I see Skype for Business when I'm using Lync?](https://go.microsoft.com/fwlink/p/?LinkId=544712) and the additional links later in this topic.</span></span>
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a><span data-ttu-id="3d8a3-133">Skype for Business クライアント用の環境を準備する</span><span class="sxs-lookup"><span data-stu-id="3d8a3-133">Prepare your environment for the Skype for Business client</span></span>
<span data-ttu-id="3d8a3-134"><a name="usinglync"> </a></span><span class="sxs-lookup"><span data-stu-id="3d8a3-134"><a name="usinglync"> </a></span></span>

<span data-ttu-id="3d8a3-135">クライアントの更新に備え、環境を整えるには、いくつかの操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-135">There are a few things you'll need to do to get your environment ready for the client update.</span></span> <span data-ttu-id="3d8a3-136">クライアント エクスペリエンスを構成する変更を開始する前に、クライアント ポリシー設定をサポートするバージョンの Skype for Business Server または Lync Server を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-136">Before you start making any changes to configure the client experience, you first need to make sure that you are using a version of Skype for Business Server or Lync Server that supports the client policy settings.</span></span>
  
<span data-ttu-id="3d8a3-137">クライアント エクスペリエンスを制御するポリシー設定をサポートするバージョンの Skype for Business Server または Lync Server を使用しているのを確認したら、環境内でポリシー設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-137">Once you've confirmed that you're using a version of Skype for Business Server or Lync Server that supports the policy settings to control the client experience, you'll need to configure the policy settings in your environment.</span></span> <span data-ttu-id="3d8a3-138">従う必要がある具体的な手順は、使用している Skype for Business Server または Lync Server のバージョン、およびユーザーがオンプレミスかオンラインかによって異なっています。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-138">The specific steps you need to follow depend on the version of Skype for Business Server or Lync Server that you are using, and whether your users are on-premises or online.</span></span> 
  
<span data-ttu-id="3d8a3-139">クライアント更新プログラムがユーザーに配信される前にこれらの変更を行い、ユーザーが初めて Skype for Business クライアントを起動してからクライアント エクスペリエンスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-139">You'll want to make these changes before the client update is delivered to your users so that you can control the client experience from the first time they start the Skype for Business client.</span></span> <span data-ttu-id="3d8a3-140">次の表は、ユーザーに必要なクライアント エクスペリエンスを提供するために環境を構成するために必要な手順を示しています。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-140">The following tables points you to the steps you need to take to configure your environment for the desired client experience for your users.</span></span>
  
|<span data-ttu-id="3d8a3-141">**展開**</span><span class="sxs-lookup"><span data-stu-id="3d8a3-141">**Deployment**</span></span>|<span data-ttu-id="3d8a3-142">**Skype for Business クライアント エクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="3d8a3-142">**Skype for Business client experience**</span></span>|<span data-ttu-id="3d8a3-143">**Lync クライアント エクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="3d8a3-143">**Lync client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3d8a3-144">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3d8a3-144">Skype for Business Online</span></span>  <br/> |<span data-ttu-id="3d8a3-145">クライアント ビルド 4711.1002 (2015 年 4 月) 以降を展開する以外に、追加の手順はありません。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-145">There are no additional steps other than to deploy client build 4711.1002 (April, 2015) or later.</span></span>  <br/> |[<span data-ttu-id="3d8a3-146">Skype for Business Online で Lync クライアント エクスペリエンスを使用する</span><span class="sxs-lookup"><span data-stu-id="3d8a3-146">Use the Lync client experience with Skype for Business Online</span></span>](user-experience.md#LyncwithSfBO) <br/> |
|<span data-ttu-id="3d8a3-147">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3d8a3-147">Skype for Business Server 2015</span></span>  <br/> |<span data-ttu-id="3d8a3-148">クライアント ビルド 4711.1002 (2015 年 4 月) 以降を展開する以外に、追加の手順はありません。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-148">There are no additional steps other than to deploy client build 4711.1002 (April, 2015) or later.</span></span>  <br/> |[<span data-ttu-id="3d8a3-149">オンプレミスの Skype for Business Server で Lync クライアント エクスペリエンスを使用する</span><span class="sxs-lookup"><span data-stu-id="3d8a3-149">Use the Lync client experience with Skype for Business Server on-premises</span></span>](user-experience.md#LyncwithSfBServer) <br/> |
|<span data-ttu-id="3d8a3-150">Lync Server 2013 および Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3d8a3-150">Lync Server 2013 and Lync Server 2010</span></span>  <br/> |[<span data-ttu-id="3d8a3-151">Lync Server 2013 または Lync Server 2010 オンプレミスで Skype クライアント エクスペリエンスを使用する</span><span class="sxs-lookup"><span data-stu-id="3d8a3-151">Use the Skype client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>](user-experience.md#SkypewithLynconprem) <br/> |[<span data-ttu-id="3d8a3-152">Lync Server 2013 または Lync Server 2010 オンプレミスで Lync クライアント エクスペリエンスを使用する</span><span class="sxs-lookup"><span data-stu-id="3d8a3-152">Use the Lync client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a><span data-ttu-id="3d8a3-153">Lync Server 2013 または Lync Server 2010 オンプレミスで Skype クライアント エクスペリエンスを使用する</span><span class="sxs-lookup"><span data-stu-id="3d8a3-153">Use the Skype client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>
<span data-ttu-id="3d8a3-154"><a name="SkypewithLynconprem"> </a></span><span class="sxs-lookup"><span data-stu-id="3d8a3-154"><a name="SkypewithLynconprem"> </a></span></span>

<span data-ttu-id="3d8a3-155">オンプレミス展開で Skype クライアント エクスペリエンスを構成する場合は、このセクションの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-155">Follow the steps in this section if you want to configure the Skype client experience in an on-premises deployment.</span></span> <span data-ttu-id="3d8a3-156">オンプレミスの既定のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="3d8a3-156">The default experience for on-premises</span></span>
  
 <span data-ttu-id="3d8a3-157">**手順 1:** 最初に、クライアント ポリシー設定をサポートするバージョンの Lync Server が実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-157">**Step 1:** First, make sure you are running a version of Lync Server that supports the client policy settings.</span></span>
  
- <span data-ttu-id="3d8a3-158">**Lync Server 2013** - Lync Server 2013 以降の更新プログラムの 2014 年 12 月の累積的な更新プログラム (5.0.8308.857) を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-158">**Lync Server 2013** - You must be running the December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013 or a later update.</span></span> <span data-ttu-id="3d8a3-159">詳細については [、「Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772)の更新プログラム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-159">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
- <span data-ttu-id="3d8a3-160">**Lync Server 2010** - Lync Server 2010 以降の更新プログラムの 2015 年 2 月の累積的な更新プログラム (4.0.7577.710) を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-160">**Lync Server 2010** - You must be running the February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010 or a later update.</span></span> <span data-ttu-id="3d8a3-161">詳細については [、「Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)の更新プログラム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-161">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).</span></span>
    
  <span data-ttu-id="3d8a3-162">**手順 2:** 次に、クライアント ポリシーを使用して、Skype for Business クライアントで Skype クライアント エクスペリエンスを設定します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-162">**Step 2:** Next, use a client policy to set the Skype client experience with the Skype for Business client.</span></span> <span data-ttu-id="3d8a3-163">クライアント ポリシー **を使用してクライアント** エクスペリエンスを設定するには、3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-163">There are **3 options** for using a client policy to set the client experience.</span></span>
  
  <span data-ttu-id="3d8a3-164">**オプション 1:** グローバル ポリシーを使用して Skype クライアント エクスペリエンスを設定します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-164">**Option 1:** Set the Skype client experience by using a Global policy.</span></span> <span data-ttu-id="3d8a3-165">グローバル ポリシーは展開内のすべてのユーザーに適用されますが、ユーザー レベルおよびサイト レベルのポリシーはグローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-165">Note that the Global policy applies to all of the users in your deployment, but user and site level policies take precedence over the Global policy:</span></span>
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 <span data-ttu-id="3d8a3-166">**オプション 2:** 環境で使用している既存のクライアント ポリシーを変更して、Skype クライアント エクスペリエンスを有効にする設定を含めます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-166">**Option 2:** Modify an existing client policy that you are using in your environment to include the setting to enable the Skype client experience.</span></span> <span data-ttu-id="3d8a3-167">これにより、既存のポリシーが割り当てられているユーザーにのみ Skype クライアント エクスペリエンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-167">This lets you assign the Skype client experience only to those users that have the existing policy assigned:</span></span>
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 <span data-ttu-id="3d8a3-168">**オプション 3:** Skype クライアント エクスペリエンスの設定を含むユーザーに割り当てる新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-168">**Option 3:** Create a new policy to assign to users that includes the setting for the Skype client experience.</span></span> <span data-ttu-id="3d8a3-169">まず、新しいクライアント ポリシーを作成し、Identity パラメーターの値としてポリシーの名前を **指定** します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-169">First, create the new client policy and provide the name of the policy as the value of the **Identity** parameter:</span></span>
  
```PowerShell
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

<span data-ttu-id="3d8a3-170">次に、PolicyName パラメーターの値としてポリシーの名前 **(Identity** パラメーターに使用した値) を使用して、ポリシーをユーザーに **割り当** てる。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-170">Then assign the policy to users, using the name of the policy (the value you used for the **Identity** parameter) as the value of the **PolicyName** parameter:</span></span>
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 <span data-ttu-id="3d8a3-171">**手順 3:** クライアント ポリシーを構成した後、Skype for Business クライアントビルド 4711.1002 (2015 年 4 月) 以降を展開します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-171">**Step 3:** After you've configured your client policies, deploy the Skype for Business client, build 4711.1002 (April, 2015) or later.</span></span>
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a><span data-ttu-id="3d8a3-172">Lync Server 2013 または Lync Server 2010 オンプレミスで Lync クライアント エクスペリエンスを使用する</span><span class="sxs-lookup"><span data-stu-id="3d8a3-172">Use the Lync client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>
<span data-ttu-id="3d8a3-173"><a name="LyncwithLynconprem"> </a></span><span class="sxs-lookup"><span data-stu-id="3d8a3-173"><a name="LyncwithLynconprem"> </a></span></span>

<span data-ttu-id="3d8a3-174">これは、Skype for Business クライアントをオンプレミスの Lync Server 展開に展開する場合の既定のエクスペリエンスです。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-174">This is the default experience when the Skype for Business client is deployed in an on-premises Lync Server deployment.</span></span> <span data-ttu-id="3d8a3-175">Lync クライアント エクスペリエンスを使用するためにクライアント ポリシーを構成する必要はありません。ただし、クライアントの最初の実行動作を制御する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-175">You don't need to configure any client policies to use the Lync client experience, but you may want to control the first run behavior for the client.</span></span> <span data-ttu-id="3d8a3-176">既定では、ユーザーが初めて Skype for Business クライアントを起動すると、Skype クライアント エクスペリエンスが使用され、Lync クライアント エクスペリエンスを取得するためにクライアントの再起動を要求する通知がユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-176">By default, the first time users start the Skype for Business client, the Skype client experience is used and a notification is displayed to users that requests that they restart the client to get the Lync client experience.</span></span> <span data-ttu-id="3d8a3-177">ユーザーが初めてクライアントを起動すると Lync クライアント エクスペリエンスが表示される環境を構成できます。また、クライアント コンピューターのシステム レジストリを変更してクライアント チュートリアルをオフにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-177">You can configure your environment so that the Lync client experience is displayed the first time users start the client, as well as turn off the client tutorial by modifying the system registry on client computers.</span></span> <span data-ttu-id="3d8a3-178">Skype for Business クライアントを展開する前に実行する必要がある手順については、次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-178">For the steps you need to perform before you deploy the Skype for Business client, see one of the following topics:</span></span>
  
- <span data-ttu-id="3d8a3-179">**Lync Server 2013、Lync** [Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)での Skype for Business でのクライアント エクスペリエンスの構成を参照</span><span class="sxs-lookup"><span data-stu-id="3d8a3-179">**Lync Server 2013**, see [Configure the client experience with Skype for Business in Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)</span></span>
    
- <span data-ttu-id="3d8a3-180">**Lync Server 2010「Lync** [Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)での Skype for Business でのクライアント エクスペリエンスの構成」を参照</span><span class="sxs-lookup"><span data-stu-id="3d8a3-180">**Lync Server 2010** see [Configure the client experience with Skype for Business in Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)</span></span>
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a><span data-ttu-id="3d8a3-181">オンプレミスの Skype for Business Server で Lync クライアント エクスペリエンスを使用する</span><span class="sxs-lookup"><span data-stu-id="3d8a3-181">Use the Lync client experience with Skype for Business Server on-premises</span></span>
<span data-ttu-id="3d8a3-182"><a name="LyncwithSfBServer"> </a></span><span class="sxs-lookup"><span data-stu-id="3d8a3-182"><a name="LyncwithSfBServer"> </a></span></span>

<span data-ttu-id="3d8a3-183">オンプレミスの Skype for Business Server 展開で Lync クライアント エクスペリエンスを構成する場合は、このセクションの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-183">Follow the steps in this section if you want to configure the Lync client experience in an on-premises Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="3d8a3-184">オンプレミス展開で Skype クライアント エクスペリエンスを構成する場合は、このセクションの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-184">Follow the steps in this section if you want to configure the Skype client experience in an on-premises deployment.</span></span> <span data-ttu-id="3d8a3-185">オンプレミスの既定のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="3d8a3-185">The default experience for on-premises</span></span>
  
 <span data-ttu-id="3d8a3-186">**手順 1:** まず、Skype for Business Server を展開します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-186">**Step 1:** First, deploy Skype for Business Server.</span></span>
  
 <span data-ttu-id="3d8a3-187">**手順 2:** 次に、クライアント ポリシーを使用して、Skype for Business クライアントで Lync クライアント エクスペリエンスを設定します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-187">**Step 2:** Next, use a client policy to set the Lync client experience with the Skype for Business client.</span></span> <span data-ttu-id="3d8a3-188">クライアント ポリシー **を使用してクライアント** エクスペリエンスを設定するには、3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-188">There are **3 options** for using a client policy to set the client experience.</span></span>
  
 <span data-ttu-id="3d8a3-189">**オプション 1:** グローバル ポリシーを使用して Lync クライアント エクスペリエンスを設定します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-189">**Option 1:** Set the Lync client experience by using a Global policy.</span></span> <span data-ttu-id="3d8a3-190">グローバル ポリシーは展開内のすべてのユーザーに適用されますが、ユーザー レベルおよびサイト レベルのポリシーはグローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-190">Note that the Global policy applies to all of the users in your deployment, but user and site level policies take precedence over the Global policy:</span></span>
  
```PowerShell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 <span data-ttu-id="3d8a3-191">**オプション 2:** 環境で使用している既存のクライアント ポリシーを変更して、Lync クライアント エクスペリエンスを有効にする設定を含めます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-191">**Option 2:** Modify an existing client policy that you are using in your environment to include the setting to enable the Lync client experience.</span></span> <span data-ttu-id="3d8a3-192">これにより、既存のポリシーが割り当てられているユーザーにのみ Lync クライアント エクスペリエンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-192">This lets you assign the Lync client experience only to those users that have the existing policy assigned:</span></span>
  
```PowerShell
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 <span data-ttu-id="3d8a3-193">**オプション 3:** Lync クライアント エクスペリエンスの設定を含むユーザーに割り当てる新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-193">**Option 3:** Create a new policy to assign to users that includes the setting for the Lync client experience.</span></span> <span data-ttu-id="3d8a3-194">まず、新しいクライアント ポリシーを作成し、Identity パラメーターの値としてポリシーの名前を **指定** します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-194">First, create the new client policy and provide the name of the policy as the value of the **Identity** parameter:</span></span>
  
```PowerShell
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

<span data-ttu-id="3d8a3-195">次に、PolicyName パラメーターの値としてポリシーの名前 **(Identity** パラメーターに使用した値) を使用して、ポリシーをユーザーに **割り当** てる。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-195">Then assign the policy to users, using the name of the policy (the value you used for the **Identity** parameter) as the value of the **PolicyName** parameter:</span></span>
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 <span data-ttu-id="3d8a3-196">**手順 3:** 省略可能 - 既定では、ユーザーが初めて Skype for Business クライアントを起動すると、Skype クライアント エクスペリエンスが使用され、Lync クライアント エクスペリエンスを取得するためにクライアントを再起動することを求める通知がユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-196">**Step 3: Optional** - By default, the first time users start the Skype for Business client, the Skype client experience is used and a notification is displayed to users asking them to restart the client to get the Lync client experience.</span></span> <span data-ttu-id="3d8a3-197">ユーザーが初めてクライアントを起動すると Lync クライアント エクスペリエンスが表示され、クライアント コンピューターのシステム レジストリを変更してクライアント チュートリアルをオフにできるよう環境を構成できます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-197">You can configure your environment so that the Lync client experience is displayed the first time users start the client, as well as turn off the client tutorial, by modifying the system registry on client computers.</span></span> <span data-ttu-id="3d8a3-198">Skype for Business クライアントを展開する前に実行する必要がある手順については、「Skype for Business でクライアント エクスペリエンスを構成する」を [参照してください](../../deploy/deploy-clients/configure-the-client-experience.md)。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-198">For the steps you need to perform before you deploy the Skype for Business client see [Configure the client experience with Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md).</span></span>
  
 <span data-ttu-id="3d8a3-199">**手順 4:** クライアント ポリシーを構成した後、Skype for Business クライアントビルド 4711.1002 (2015 年 4 月) 以降を展開します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-199">**Step 4:** After you've configured your client policies, deploy the Skype for Business client, build 4711.1002 (April, 2015) or later.</span></span>
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a><span data-ttu-id="3d8a3-200">Skype for Business Online で Lync クライアント エクスペリエンスを使用する</span><span class="sxs-lookup"><span data-stu-id="3d8a3-200">Use the Lync client experience with Skype for Business Online</span></span>
<span data-ttu-id="3d8a3-201"><a name="LyncwithSfBO"> </a></span><span class="sxs-lookup"><span data-stu-id="3d8a3-201"><a name="LyncwithSfBO"> </a></span></span>

<span data-ttu-id="3d8a3-202">Lync クライアント エクスペリエンスを構成し、Skype for Business Online を使用する場合は、このセクションの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-202">Follow the steps in this section if you want to configure the Lync client experience and you using Skype for Business Online.</span></span>
  
<span data-ttu-id="3d8a3-203">Skype for Business Online を使用している場合でも、リモート PowerShell を使用してクライアント ポリシーを構成することで、組織内の Skype for Business クライアントで Lync クライアント エクスペリエンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-203">If you are using Skype for Business Online, you can still use the Lync client experience with the Skype for Business client in your organization by using Remote PowerShell to configure client policies.</span></span> <span data-ttu-id="3d8a3-204">クライアント ポリシー **を使用してクライアント** エクスペリエンスを設定するには、3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-204">There are **3 options** for using a client policy to set the client experience.</span></span> <span data-ttu-id="3d8a3-205">ポリシー名とパラメーター名は、Skype for Business または Lync Server オンプレミスを使用している場合のクライアント エクスペリエンスの構成に使用する設定とは異なります。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-205">Note that the policy and parameter names are different than the settings you use to configure the client experience when you are using Skype for Business or Lync Server on-premises.</span></span>
  
 <span data-ttu-id="3d8a3-206">**オプション 1:** グローバル ポリシーを使用して Lync クライアント エクスペリエンスを設定します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-206">**Option 1:** Set the Lync client experience by using a Global policy.</span></span> <span data-ttu-id="3d8a3-207">ユーザーに適用されるクライアント ポリシーとサイト ポリシーは、グローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-207">Note that client and site policies applied to users will take precedence over a Global policy.</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 <span data-ttu-id="3d8a3-208">**オプション 2:** 環境で使用している既存のクライアント ポリシーを変更して、Lync クライアント エクスペリエンスを有効にする設定を含めます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-208">**Option 2:** Modify an existing client policy that you are using in your environment to include the setting to enable the Lync client experience.</span></span> <span data-ttu-id="3d8a3-209">これにより、既存のポリシーが割り当てられているユーザーにのみ Lync クライアント エクスペリエンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-209">This lets you assign the Lync client experience only to those users that have the existing policy assigned:</span></span>
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 <span data-ttu-id="3d8a3-210">**オプション 3:** Lync クライアント エクスペリエンスの設定を含むカスタム ポリシー インスタンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-210">**Option 3:** Use a custom policy instance that includes the setting for the Lync client experience.</span></span>
  
```PowerShell
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

<span data-ttu-id="3d8a3-211">クライアント ポリシーを構成した後、Skype for Business クライアントビルド 4711.1002 (2015 年 4 月) 以降を展開します。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-211">After you've configured your client policies, deploy the Skype for Business client, build 4711.1002 (April, 2015) or later.</span></span>
  
<span data-ttu-id="3d8a3-212">Skype for Business Online でクライアント エクスペリエンスを構成する方法の詳細については、「最初の実行エクスペリエンスを制御する方法に関する手順、環境の構成に使用できる PowerShell スクリプト」を含む [、「Skype for Business](https://aka.ms/SfBOUI)と Lync クライアントのユーザー インターフェイスを切り替える」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-212">For detailed information about how to configure the client experience with Skype for Business Online, including steps about how to control the first run experience and PowerShell scripts you can use to configure your environment, see [Switching between the Skype for Business and the Lync client user interfaces](https://aka.ms/SfBOUI).</span></span>
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a><span data-ttu-id="3d8a3-213">サポート チームとエンド ユーザーの更新準備に役立つリソース</span><span class="sxs-lookup"><span data-stu-id="3d8a3-213">Resources to help you prepare your support teams and your end users for the update</span></span>
<span data-ttu-id="3d8a3-214"><a name="support"> </a></span><span class="sxs-lookup"><span data-stu-id="3d8a3-214"><a name="support"> </a></span></span>

<span data-ttu-id="3d8a3-215">お客様と組織が移行に備えやすくするために、エンド ユーザーの計画、教育、関与に役立つその他のリソースが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="3d8a3-215">To make it easier for you and your organization prepare for the transition, we have many additional resources available to help you plan, educate and engage end-users.</span></span>
  
- [<span data-ttu-id="3d8a3-216">ビデオ: Skype for Business の概要</span><span class="sxs-lookup"><span data-stu-id="3d8a3-216">Video: Introducing Skype for Business</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [<span data-ttu-id="3d8a3-217">Skype for Business クイック スタート ガイド (ダウンロード)</span><span class="sxs-lookup"><span data-stu-id="3d8a3-217">Skype for Business Quick Start Guides (Download)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [<span data-ttu-id="3d8a3-218">Lync が Skype for Business に変更 — 新機能を確認する</span><span class="sxs-lookup"><span data-stu-id="3d8a3-218">Lync is now Skype for Business — see what's new</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [<span data-ttu-id="3d8a3-219">Skype for Business: 新しいユーザー向けステップ バイ ステップ ガイド</span><span class="sxs-lookup"><span data-stu-id="3d8a3-219">Skype for Business: Step-by-step guide for new users</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [<span data-ttu-id="3d8a3-220">Lync を使用している場合に Skype for Business が表示される理由</span><span class="sxs-lookup"><span data-stu-id="3d8a3-220">Why do I see Skype for Business when I'm using Lync?</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

