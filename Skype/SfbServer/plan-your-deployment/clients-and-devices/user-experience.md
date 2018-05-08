---
title: ユーザー向けに Skype for Business のクライアント エクスペリエンスを計画する
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0df4fd9e-370b-4b9d-a595-f1199fbc9f81
description: '概要: は、ビジネスとビジネス サーバー 2015、Lync Server 2013 では、Lync Server 2010 のオンライン ビジネス、Skype の Skype を使用しているかどうか、更新プログラムのユーザー、お客様の環境を準備するための手順は、新しい Skype について説明します。'
ms.openlocfilehash: eaa8b7835cb3834ff9cc24a6dc941b47a2796b9f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="plan-the-skype-for-business-client-experience-for-your-users"></a><span data-ttu-id="1560f-103">ユーザー向けに Skype for Business のクライアント エクスペリエンスを計画する</span><span class="sxs-lookup"><span data-stu-id="1560f-103">Plan the Skype for Business client experience for your users</span></span>
 
<span data-ttu-id="1560f-104">**の概要:** ビジネスおよびビジネス サーバー 2015、Lync Server 2013 では、Lync Server 2010 のオンライン ビジネス、Skype の Skype を使用しているかどうか、更新プログラムのユーザー、お客様の環境を準備するための手順は、新しい Skype について説明します。</span><span class="sxs-lookup"><span data-stu-id="1560f-104">**Summary:** Learn about the new Skype for Business and the steps you can take to prepare your environment and your users for the update, whether you're using Skype for Business Online, Skype for Business Server 2015, Lync Server 2013, or Lync Server 2010.</span></span>
  
<span data-ttu-id="1560f-105">2015 年 4 月 14 日 Lync 2013 用の Office の更新プログラムには、ビジネス ユーザー ・ インタ フェースの新しい Skype が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1560f-105">The April 14th, 2015 Office Update for Lync 2013 includes the new Skype for Business user interface.</span></span> <span data-ttu-id="1560f-106">この更新プログラムでは、クライアントの外観と動作を制御し、Lync 2013 クライアント エクスペリエンスを保持またはビジネス クライアント エクスペリエンスの向上の Skype を使用するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1560f-106">This update enables administrators to control the look and feel of the client and choose whether to retain the Lync 2013 client experience or use the improved Skype for Business client experience.</span></span> <span data-ttu-id="1560f-107">ビジネス クライアント用の Skype は効果的に、Lync 2013 クライアントは置き換えられ、管理者は既存の Lync クライアントの経験とビジネス クライアント エクスペリエンスの新しい Skype との間を選択するための機能を追加しました。</span><span class="sxs-lookup"><span data-stu-id="1560f-107">The Skype for Business client effectively replaced the Lync 2013 client, and added the ability for administrators to choose between the existing Lync client experience and the new Skype for Business client experience.</span></span> <span data-ttu-id="1560f-108">この更新プログラムについてを参照してください[2015 年 4 月 14 日は、Lync 2013 (ビジネス用の Skype) の更新 (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/)。</span><span class="sxs-lookup"><span data-stu-id="1560f-108">For information about this update, see [April 14, 2015 update for Lync 2013 (Skype for Business) (KB2889923)](https://support.microsoft.com/en-us/kb/2889923/).</span></span>
  
<span data-ttu-id="1560f-109">2015 5 月 12 日のビジネス クライアント用の更新された Skype を含む Office から別の毎月更新されます。</span><span class="sxs-lookup"><span data-stu-id="1560f-109">On May 12th, 2015 there will be another monthly update from Office that includes the updated Skype for Business client.</span></span> <span data-ttu-id="1560f-110">4 月の更新は、5 月 12日の選択を適用していない多くのお客様は、Office 2013 の更新します。</span><span class="sxs-lookup"><span data-stu-id="1560f-110">Many customers that did not apply the April update will pick up the May 12th update for Office 2013.</span></span> <span data-ttu-id="1560f-111">このトピックの情報は、クライアントの更新に対する組織、環境、ユーザーの準備に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1560f-111">The information in this topic will help you prepare your organization, your environment, and your users for the client update.</span></span> <span data-ttu-id="1560f-112">ユーザーおよびサポート チームが容易に移行できるように、このトピックの情報を使用して、ユーザーに対してどちらのクライアント エクスペリエンスを使用するかを決定し、組織でクライアント更新プログラムを展開する前に環境に変更を加えてください。</span><span class="sxs-lookup"><span data-stu-id="1560f-112">To make the transition easy for your users and support teams, use the information in this topic to help you decide which client experience you want for your users and then make the changes to your environment before deploying the client update in your organization.</span></span>
  
- [<span data-ttu-id="1560f-113">What client experience do you want for your users?</span><span class="sxs-lookup"><span data-stu-id="1560f-113">What client experience do you want for your users?</span></span>](user-experience.md#clientexperience)
    
- [<span data-ttu-id="1560f-114">ビジネス クライアント用の Skype の環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="1560f-114">Prepare your environment for the Skype for Business client</span></span>](user-experience.md#usinglync)
    
- [<span data-ttu-id="1560f-115">Resources to help you prepare your support teams and your end users for the update</span><span class="sxs-lookup"><span data-stu-id="1560f-115">Resources to help you prepare your support teams and your end users for the update</span></span>](user-experience.md#support)
    
> [!NOTE]
> <span data-ttu-id="1560f-116">Lync 2013 クライアント エクスペリエンスは、ビジネス 2016年のクライアント バージョン用には、Skype のオプションではありません。</span><span class="sxs-lookup"><span data-stu-id="1560f-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="1560f-117">Lync 2013 クライアントを使用するようにクライアント環境を構成する前に、クライアント バージョンを調べて、バージョンの先頭が 16 ではない (16.x.x.x などではない) ことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1560f-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="what-client-experience-do-you-want-for-your-users"></a><span data-ttu-id="1560f-118">ユーザーに対して必要なクライアント エクスペリエンスは何ですか?</span><span class="sxs-lookup"><span data-stu-id="1560f-118">What client experience do you want for your users?</span></span>
<span data-ttu-id="1560f-119"><a name="clientexperience"> </a></span><span class="sxs-lookup"><span data-stu-id="1560f-119"></span></span>

<span data-ttu-id="1560f-120">ビジネス クライアント用の新しい Skype、どのクライアントの機能をユーザーが取得すると、Lync またはビジネス用の Skype のいずれかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="1560f-120">With the new Skype for Business client, you can control which client experience your users get, either Lync or Skype for Business.</span></span> <span data-ttu-id="1560f-121">既定のクライアントの動作は、かどうか、またはを使用して Lync Skype ビジネス設置型またはオンラインによって異なります。</span><span class="sxs-lookup"><span data-stu-id="1560f-121">The default client experience depends on whether you are using Lync or Skype for Business on-premises or online.</span></span> <span data-ttu-id="1560f-122">ビジネス クライアント用の更新された Skype が発生するビジネス オンライン (Lync オンライン) に、現在、Office 365 用リソース、Office 365 のビジネス プレミアムまたは Office 2013 の Skype を使用する場合、Skype の外観に触発されたもの-既定のユーザー エクスペリエンスになります。</span><span class="sxs-lookup"><span data-stu-id="1560f-122">If you are using Skype for Business Online (Lync Online) today with Office 365 ProPlus, Office 365 Business Premium or Office 2013, the updated Skype for Business client experience—inspired by the look and feel of Skype—will be the default user experience.</span></span> <span data-ttu-id="1560f-123">今日、Lync Server の設置型を使用している、Lync クライアント エクスペリエンスが既定値になります。</span><span class="sxs-lookup"><span data-stu-id="1560f-123">If you are using Lync Server on-premises today, the Lync client experience will be the default.</span></span>
  
<span data-ttu-id="1560f-124">クライアント ポリシーを使用することにより、ユーザーにどちらのクライアント エクスペリエンスを提供するか設定できます。</span><span class="sxs-lookup"><span data-stu-id="1560f-124">You can configure which client experience your users get by using client policies.</span></span> <span data-ttu-id="1560f-125">クライアント ポリシーは、Lync またはビジネス用の Skype にログインするとユーザーに適用される構成設定のセットです。</span><span class="sxs-lookup"><span data-stu-id="1560f-125">A client policy is a set of configuration settings that are applied to users when they login to Lync or Skype for Business.</span></span>
  
### <a name="skype-for-business-client-experience"></a><span data-ttu-id="1560f-126">Skype for Business クライアント エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="1560f-126">Skype for Business client experience</span></span>

<span data-ttu-id="1560f-127">Lync のすべての機能、に加えては、ビジネス用の Skype は、Skype から簡略化されたコントロールと一般的なアイコンでの新機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1560f-127">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons from Skype.</span></span> <span data-ttu-id="1560f-128">ビジネス用の Skype の新機能は、クライアントの機能をビジネスの新しい Skype のみ用意されています。</span><span class="sxs-lookup"><span data-stu-id="1560f-128">Some new features in Skype for Business are available only with the new Skype for Business client experience.</span></span> <span data-ttu-id="1560f-129">ビジネス用の Skype の新機能に関する詳細については、[ビジネス用の Skype の検出](https://go.microsoft.com/fwlink/p/?LinkId=528686)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1560f-129">To learn more about the new features in Skype for Business, see [Discover Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=528686).</span></span>
  
### <a name="lync-client-experience"></a><span data-ttu-id="1560f-130">Lync クライアント エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="1560f-130">Lync client experience</span></span>

<span data-ttu-id="1560f-131">Lync クライアント エクスペリエンスは、多くのユーザーが既に使いなれている Lync 2013 のクライアント エクスペリエンスによく似ていますが、いくつかの変更点についてユーザーに知らせておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="1560f-131">The Lync client experience is very similar to the Lync 2013 client experience that your users are already familiar with, but there are a few changes that you'll want to let your users know about.</span></span> <span data-ttu-id="1560f-132">Lync 2013 クライアントと Lync クライアント エクスペリエンスの間の違いを参照してください[が表示されます Skype ビジネスの Lync を使用している場合ですか?](https://go.microsoft.com/fwlink/p/?LinkId=544712)とこのトピックの後半の他のリンクです。</span><span class="sxs-lookup"><span data-stu-id="1560f-132">To see what's different between the Lync client experience and the Lync 2013 client, see [Why do I see Skype for Business when I'm using Lync?](https://go.microsoft.com/fwlink/p/?LinkId=544712) and the additional links later in this topic.</span></span>
  
## <a name="prepare-your-environment-for-the-skype-for-business-client"></a><span data-ttu-id="1560f-133">Skype for Business クライアント用に環境を準備する</span><span class="sxs-lookup"><span data-stu-id="1560f-133">Prepare your environment for the Skype for Business client</span></span>
<span data-ttu-id="1560f-134"><a name="usinglync"> </a></span><span class="sxs-lookup"><span data-stu-id="1560f-134"></span></span>

<span data-ttu-id="1560f-135">クライアントの更新に向けて環境を準備するのに必要な作業はそれほど多くありません。</span><span class="sxs-lookup"><span data-stu-id="1560f-135">There are a few things you'll need to do to get your environment ready for the client update.</span></span> <span data-ttu-id="1560f-136">クライアント エクスペリエンスを構成するのには何も変更を開始する前にビジネスのサーバーまたはクライアントのポリシー設定をサポートしている Lync Server のバージョンの Skype を使用しているかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1560f-136">Before you start making any changes to configure the client experience, you first need to make sure that you are using a version of Skype for Business Server or Lync Server that supports the client policy settings.</span></span>
  
<span data-ttu-id="1560f-137">ビジネス サーバーまたはクライアント エクスペリエンスを制御するポリシーの設定をサポートしている Lync Server のバージョンの Skype を使っていることを確認して、環境内でポリシー設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1560f-137">Once you've confirmed that you're using a version of Skype for Business Server or Lync Server that supports the policy settings to control the client experience, you'll need to configure the policy settings in your environment.</span></span> <span data-ttu-id="1560f-138">ビジネス サーバー、または使用する場合は、Lync Server の Skype のバージョンで、特定の手順を実行する必要に依存しているし、ユーザーは、設置するかどうかまたはオンラインです。</span><span class="sxs-lookup"><span data-stu-id="1560f-138">The specific steps you need to follow depend on the version of Skype for Business Server or Lync Server that you are using, and whether your users are on-premises or online.</span></span> 
  
<span data-ttu-id="1560f-139">ビジネス クライアント用の Skype を起動する最初の時間からのクライアント エクスペリエンスを制御することができますように、ユーザーにクライアント用更新プログラムが配信される前に、これらの変更を実行します。</span><span class="sxs-lookup"><span data-stu-id="1560f-139">You'll want to make these changes before the client update is delivered to your users so that you can control the client experience from the first time they start the Skype for Business client.</span></span> <span data-ttu-id="1560f-140">次の表には、ユーザーのために必要なクライアント操作の環境を構成するために必要な手順へのリンクがあります。</span><span class="sxs-lookup"><span data-stu-id="1560f-140">The following tables points you to the steps you need to take to configure your environment for the desired client experience for your users.</span></span>
  
|<span data-ttu-id="1560f-141">**展開**</span><span class="sxs-lookup"><span data-stu-id="1560f-141">**Deployment**</span></span>|<span data-ttu-id="1560f-142">**ビジネス クライアント エクスペリエンスの Skype**</span><span class="sxs-lookup"><span data-stu-id="1560f-142">**Skype for Business client experience**</span></span>|<span data-ttu-id="1560f-143">**Lync クライアント エクスペリエンス**</span><span class="sxs-lookup"><span data-stu-id="1560f-143">**Lync client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1560f-144">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1560f-144">Skype for Business Online</span></span>  <br/> |<span data-ttu-id="1560f-145">クライアント ビルド 4711.1002 (2015 年 4 月) 以降を展開する以外、特別な手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1560f-145">There are no additional steps other than to deploy client build 4711.1002 (April, 2015) or later.</span></span>  <br/> |[<span data-ttu-id="1560f-146">Skype での Lync クライアント エクスペリエンスを使用して、オンライン ビジネスの</span><span class="sxs-lookup"><span data-stu-id="1560f-146">Use the Lync client experience with Skype for Business Online</span></span>](user-experience.md#LyncwithSfBO) <br/> |
|<span data-ttu-id="1560f-147">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1560f-147">Skype for Business Server 2015</span></span>  <br/> |<span data-ttu-id="1560f-148">クライアント ビルド 4711.1002 (2015 年 4 月) 以降を展開する以外、特別な手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1560f-148">There are no additional steps other than to deploy client build 4711.1002 (April, 2015) or later.</span></span>  <br/> |[<span data-ttu-id="1560f-149">Skype での Lync クライアント エクスペリエンスを使用して、ビジネス サーバー設置型の</span><span class="sxs-lookup"><span data-stu-id="1560f-149">Use the Lync client experience with Skype for Business Server on-premises</span></span>](user-experience.md#LyncwithSfBServer) <br/> |
|<span data-ttu-id="1560f-150">Lync Server 2013 および Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1560f-150">Lync Server 2013 and Lync Server 2010</span></span>  <br/> |[<span data-ttu-id="1560f-151">Skype クライアント エクスペリエンスを使用して、Lync Server 2013 または Lync Server 2010 の設置型の</span><span class="sxs-lookup"><span data-stu-id="1560f-151">Use the Skype client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>](user-experience.md#SkypewithLynconprem) <br/> |[<span data-ttu-id="1560f-152">Lync クライアント エクスペリエンスを使用して、Lync Server 2013 または Lync Server 2010 の設置型の</span><span class="sxs-lookup"><span data-stu-id="1560f-152">Use the Lync client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>](user-experience.md#LyncwithLynconprem) <br/> |
   
## <a name="use-the-skype-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a><span data-ttu-id="1560f-153">Skype クライアント エクスペリエンスを使用して、Lync Server 2013 または Lync Server 2010 の設置型の</span><span class="sxs-lookup"><span data-stu-id="1560f-153">Use the Skype client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>
<span data-ttu-id="1560f-154"><a name="SkypewithLynconprem"> </a></span><span class="sxs-lookup"><span data-stu-id="1560f-154"></span></span>

<span data-ttu-id="1560f-p111">このセクションの手順は、オンプレミス環境で Skype クライアント エクスペリエンスを構成したい場合に実行します。これは、オンプレミスの既定のエクスペリエンスです。</span><span class="sxs-lookup"><span data-stu-id="1560f-p111">Follow the steps in this section if you want to configure the Skype client experience in an on-premises deployment. The default experience for on-premises</span></span>
  
 <span data-ttu-id="1560f-157">**手順 1:** まず、クライアントのポリシー設定をサポートしている Lync Server のバージョンを実行していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1560f-157">**Step 1:** First, make sure you are running a version of Lync Server that supports the client policy settings.</span></span>
  
- <span data-ttu-id="1560f-158">**Lync Server 2013** - を実行する必要があります 2014年 12 月の Lync Server 2013 またはそれ以降の更新プログラムの累積的な更新 (5.0.8308.857)。</span><span class="sxs-lookup"><span data-stu-id="1560f-158">**Lync Server 2013** - You must be running the December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013 or a later update.</span></span> <span data-ttu-id="1560f-159">については、 [Lync Server 2013 の更新プログラム](https://go.microsoft.com/fwlink/p/?LinkId=532772)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1560f-159">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
- <span data-ttu-id="1560f-160">**Lync Server 2010** - を実行する必要があります 2015年 2 月の Lync Server 2010 またはそれ以降の更新プログラムの累積的な更新 (4.0.7577.710)。</span><span class="sxs-lookup"><span data-stu-id="1560f-160">**Lync Server 2010** - You must be running the February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010 or a later update.</span></span> <span data-ttu-id="1560f-161">については、 [Lync Server 2010 用の更新プログラム](https://go.microsoft.com/fwlink/p/?LinkId=532771)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1560f-161">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771).</span></span>
    
 <span data-ttu-id="1560f-162">**手順 2:** 次に、ビジネス クライアント用の Skype と Skype クライアント エクスペリエンスを設定するのには、クライアント ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="1560f-162">**Step 2:** Next, use a client policy to set the Skype client experience with the Skype for Business client.</span></span> <span data-ttu-id="1560f-163">クライアント ポリシーを使用して、クライアント エクスペリエンスを設定する場合、**3 つのオプション**があります。</span><span class="sxs-lookup"><span data-stu-id="1560f-163">There are **3 options** for using a client policy to set the client experience.</span></span>
  
 <span data-ttu-id="1560f-p115">**オプション 1:** グローバル ポリシーを使用して、Skype クライアント エクスペリエンスを設定します。グローバル ポリシーは、展開に含まれるすべてのユーザーに適用されますが、ユーザー レベルおよびサイト レベルのポリシーの方がグローバル ポリシーよりも優先される点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="1560f-p115">**Option 1:** Set the Skype client experience by using a Global policy. Note that the Global policy applies to all of the users in your deployment, but user and site level policies take precedence over the Global policy:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $True
```

 <span data-ttu-id="1560f-p116">**オプション 2:** 現在環境で使用している既存のクライアント ポリシーを変更し、Skype クライアント エクスペリエンスを有効にする設定が含まれるようにします。この場合、既存のポリシーが割り当てられているユーザーのみに Skype クライアント エクスペリエンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1560f-p116">**Option 2:** Modify an existing client policy that you are using in your environment to include the setting to enable the Skype client experience. This lets you assign the Skype client experience only to those users that have the existing policy assigned:</span></span>
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $True
```

 <span data-ttu-id="1560f-p117">**オプション 3:** Skype クライアント エクスペリエンスの設定を含む新しいポリシーを作成して、ユーザーに割り当てます。最初に新しいクライアント ポリシーを作成してから、ポリシーの名前を **Identity** パラメーターの値として指定します。</span><span class="sxs-lookup"><span data-stu-id="1560f-p117">**Option 3:** Create a new policy to assign to users that includes the setting for the Skype client experience. First, create the new client policy and provide the name of the policy as the value of the **Identity** parameter:</span></span>
  
```
New-CsClientPolicy -Identity UseSkypeUI -EnableSkypeUI $True
```

<span data-ttu-id="1560f-170">次にポリシーの名前 (**Identity** パラメーターに使用した値) を **PolicyName** パラメーターの値として使用し、ユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1560f-170">Then assign the policy to users, using the name of the policy (the value you used for the **Identity** parameter) as the value of the **PolicyName** parameter:</span></span>
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseSkypeUI
```

 <span data-ttu-id="1560f-171">**手順 3:** ビジネス クライアントでは、ビルド 4711.1002 (2015 年 4 月に) Skype を導入、クライアントのポリシーを構成した後またはそれ以降です。</span><span class="sxs-lookup"><span data-stu-id="1560f-171">**Step 3:** After you've configured your client policies, deploy the Skype for Business client, build 4711.1002 (April, 2015) or later.</span></span>
  
## <a name="use-the-lync-client-experience-with-lync-server-2013-or-lync-server-2010-on-premises"></a><span data-ttu-id="1560f-172">Lync クライアント エクスペリエンスを使用して、Lync Server 2013 または Lync Server 2010 の設置型の</span><span class="sxs-lookup"><span data-stu-id="1560f-172">Use the Lync client experience with Lync Server 2013 or Lync Server 2010 on-premises</span></span>
<span data-ttu-id="1560f-173"><a name="LyncwithLynconprem"> </a></span><span class="sxs-lookup"><span data-stu-id="1560f-173"></span></span>

<span data-ttu-id="1560f-174">これは、オンプレミスの Lync Server 展開のビジネス クライアント用の Skype を配置するときの既定の動作です。</span><span class="sxs-lookup"><span data-stu-id="1560f-174">This is the default experience when the Skype for Business client is deployed in an on-premises Lync Server deployment.</span></span> <span data-ttu-id="1560f-175">Lync クライアントの操作性を使用するすべてのクライアント ポリシーを構成する必要はありませんが、クライアントの最初の実行動作を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="1560f-175">You don't need to configure any client policies to use the Lync client experience, but you may want to control the first run behavior for the client.</span></span> <span data-ttu-id="1560f-176">既定では、ユーザーが初めてビジネス クライアント用の Skype を起動する、Skype クライアント エクスペリエンスが使用され、Lync クライアント エクスペリエンスを取得するクライアントを再起動することを要求するユーザーに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1560f-176">By default, the first time users start the Skype for Business client, the Skype client experience is used and a notification is displayed to users that requests that they restart the client to get the Lync client experience.</span></span> <span data-ttu-id="1560f-177">お客様の環境を構成するには、Lync クライアント エクスペリエンスには、最初にクライアントを起動するだけでなくユーザーのクライアント コンピューター上のシステム レジストリを変更することによってクライアントのチュートリアルをオフが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="1560f-177">You can configure your environment so that the Lync client experience is displayed the first time users start the client, as well as turn off the client tutorial by modifying the system registry on client computers.</span></span> <span data-ttu-id="1560f-178">手順については、ビジネス クライアントは、次のトピックのいずれかを参照してください Skype を導入する前に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1560f-178">For the steps you need to perform before you deploy the Skype for Business client, see one of the following topics:</span></span>
  
- <span data-ttu-id="1560f-179">**Lync Server 2013**では、 [Lync Server 2013 でビジネス用の Skype で発生するクライアントの構成](https://go.microsoft.com/fwlink/p/?LinkId=532732)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1560f-179">**Lync Server 2013**, see [Configure the client experience with Skype for Business in Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532732)</span></span>
    
- <span data-ttu-id="1560f-180">**Lync Server 2010**は、 [Lync Server 2010 のビジネス用の Skype で発生するクライアントの構成](https://go.microsoft.com/fwlink/p/?LinkId=532733)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1560f-180">**Lync Server 2010** see [Configure the client experience with Skype for Business in Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532733)</span></span>
    
## <a name="use-the-lync-client-experience-with-skype-for-business-server-on-premises"></a><span data-ttu-id="1560f-181">オンプレミスの Skype for Business Server で Lync クライアント エクスペリエンスを使用する</span><span class="sxs-lookup"><span data-stu-id="1560f-181">Use the Lync client experience with Skype for Business Server on-premises</span></span>
<span data-ttu-id="1560f-182"><a name="LyncwithSfBServer"> </a></span><span class="sxs-lookup"><span data-stu-id="1560f-182"></span></span>

<span data-ttu-id="1560f-183">サーバー 2015 のビジネス展開に、オンプレミス Skype の Lync クライアント エクスペリエンスを構成する場合は、このセクションの手順を従います。</span><span class="sxs-lookup"><span data-stu-id="1560f-183">Follow the steps in this section if you want to configure the Lync client experience in an on-premises Skype for Business Server 2015 deployment.</span></span>
  
<span data-ttu-id="1560f-p119">このセクションの手順は、オンプレミス環境で Skype クライアント エクスペリエンスを構成したい場合に実行します。これは、オンプレミスの既定のエクスペリエンスです。</span><span class="sxs-lookup"><span data-stu-id="1560f-p119">Follow the steps in this section if you want to configure the Skype client experience in an on-premises deployment. The default experience for on-premises</span></span>
  
 <span data-ttu-id="1560f-186">**手順 1:** ビジネス サーバー 2015 の Skype を最初に配置します。</span><span class="sxs-lookup"><span data-stu-id="1560f-186">**Step 1:** First, deploy Skype for Business Server 2015.</span></span>
  
 <span data-ttu-id="1560f-187">**手順 2:** 次に、クライアントのビジネスの Skype での Lync クライアント エクスペリエンスを設定するのには、クライアント ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="1560f-187">**Step 2:** Next, use a client policy to set the Lync client experience with the Skype for Business client.</span></span> <span data-ttu-id="1560f-188">クライアント ポリシーを使用して、クライアント エクスペリエンスを設定する場合、**3 つのオプション**があります。</span><span class="sxs-lookup"><span data-stu-id="1560f-188">There are **3 options** for using a client policy to set the client experience.</span></span>
  
 <span data-ttu-id="1560f-p121">**オプション 1:** グローバル ポリシーを使用して、Lync クライアント エクスペリエンスを設定します。グローバル ポリシーは、展開に含まれるすべてのユーザーに適用されますが、ユーザー レベルおよびサイト レベルのポリシーの方がグローバル ポリシーよりも優先される点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="1560f-p121">**Option 1:** Set the Lync client experience by using a Global policy. Note that the Global policy applies to all of the users in your deployment, but user and site level policies take precedence over the Global policy:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $False
```

 <span data-ttu-id="1560f-p122">**オプション 2:** 現在環境で使用している既存のクライアント ポリシーを変更し、Lync クライアント エクスペリエンスを有効にする設定が含まれるようにします。この場合、既存のポリシーが割り当てられているユーザーのみに Lync クライアント エクスペリエンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1560f-p122">**Option 2:** Modify an existing client policy that you are using in your environment to include the setting to enable the Lync client experience. This lets you assign the Lync client experience only to those users that have the existing policy assigned:</span></span>
  
```
Set-CsClientPolicy -Identity ExistingClientPolicyName -EnableSkypeUI $False
```

 <span data-ttu-id="1560f-p123">**オプション 3:** Lync クライアント エクスペリエンスの設定を含む新しいポリシーを作成して、ユーザーに割り当てます。最初に新しいクライアント ポリシーを作成してから、ポリシーの名前を **Identity** パラメーターの値として指定します。</span><span class="sxs-lookup"><span data-stu-id="1560f-p123">**Option 3:** Create a new policy to assign to users that includes the setting for the Lync client experience. First, create the new client policy and provide the name of the policy as the value of the **Identity** parameter:</span></span>
  
```
New-CsClientPolicy -Identity UseLyncUI -EnableSkypeUI $False
```

<span data-ttu-id="1560f-195">次にポリシーの名前 (**Identity** パラメーターに使用した値) を **PolicyName** パラメーターの値として使用し、ユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1560f-195">Then assign the policy to users, using the name of the policy (the value you used for the **Identity** parameter) as the value of the **PolicyName** parameter:</span></span>
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName UseLyncUI
```

 <span data-ttu-id="1560f-196">**手順 3: 省略可能な**時の最初のユーザーがビジネス クライアント用の Skype を起動する既定では、-、Skype クライアント エクスペリエンスを使用し、Lync クライアント エクスペリエンスを取得するクライアントを再起動を要求することをユーザーに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1560f-196">**Step 3: Optional** - By default, the first time users start the Skype for Business client, the Skype client experience is used and a notification is displayed to users asking them to restart the client to get the Lync client experience.</span></span> <span data-ttu-id="1560f-197">お客様の環境を構成するには、Lync クライアント エクスペリエンスには、ユーザー、クライアントを起動すると、クライアント コンピューター上のシステム レジストリを変更することにより、クライアントのチュートリアルでは、オフには、最初が表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="1560f-197">You can configure your environment so that the Lync client experience is displayed the first time users start the client, as well as turn off the client tutorial, by modifying the system registry on client computers.</span></span> <span data-ttu-id="1560f-198">ビジネス クライアント用の Skype を導入する前に実行する必要がある手順は、 [Skype のビジネスで発生するクライアントの構成](../../deploy/deploy-clients/configure-the-client-experience.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1560f-198">For the steps you need to perform before you deploy the Skype for Business client see [Configure the client experience with Skype for Business](../../deploy/deploy-clients/configure-the-client-experience.md).</span></span>
  
 <span data-ttu-id="1560f-199">**手順 4:** ビジネス クライアントでは、ビルド 4711.1002 (2015 年 4 月に) Skype を導入、クライアントのポリシーを構成した後またはそれ以降です。</span><span class="sxs-lookup"><span data-stu-id="1560f-199">**Step 4:** After you've configured your client policies, deploy the Skype for Business client, build 4711.1002 (April, 2015) or later.</span></span>
  
## <a name="use-the-lync-client-experience-with-skype-for-business-online"></a><span data-ttu-id="1560f-200">Skype for Business Online で Lync クライアント エクスペリエンスを使用する</span><span class="sxs-lookup"><span data-stu-id="1560f-200">Use the Lync client experience with Skype for Business Online</span></span>
<span data-ttu-id="1560f-201"><a name="LyncwithSfBO"> </a></span><span class="sxs-lookup"><span data-stu-id="1560f-201"></span></span>

<span data-ttu-id="1560f-202">Lync クライアントの操作性とビジネス オンラインの Skype を使用するを構成する場合は、このセクションの手順を従います。</span><span class="sxs-lookup"><span data-stu-id="1560f-202">Follow the steps in this section if you want to configure the Lync client experience and you using Skype for Business Online.</span></span>
  
<span data-ttu-id="1560f-203">ビジネス オンラインの Skype を使用する場合も使用できます Lync クライアント エクスペリエンス、Skype でビジネスのクライアントの組織のクライアントのポリシーを構成するリモート PowerShell を使用しています。</span><span class="sxs-lookup"><span data-stu-id="1560f-203">If you are using Skype for Business Online, you can still use the Lync client experience with the Skype for Business client in your organization by using Remote PowerShell to configure client policies.</span></span> <span data-ttu-id="1560f-204">クライアント ポリシーを使用して、クライアント エクスペリエンスを設定する場合、**3 つのオプション**があります。</span><span class="sxs-lookup"><span data-stu-id="1560f-204">There are **3 options** for using a client policy to set the client experience.</span></span> <span data-ttu-id="1560f-205">ポリシーとパラメーターの名前とは異なるビジネスまたは Lync Server の Skype を使用している場合は、クライアント エクスペリエンスを構成するのにを使用する設定を設置します。</span><span class="sxs-lookup"><span data-stu-id="1560f-205">Note that the policy and parameter names are different than the settings you use to configure the client experience when you are using Skype for Business or Lync Server on-premises.</span></span>
  
 <span data-ttu-id="1560f-206">**オプション 1:** グローバル ポリシーを使用して Lync クライアント エクスペリエンスを設定します。</span><span class="sxs-lookup"><span data-stu-id="1560f-206">**Option 1:** Set the Lync client experience by using a Global policy.</span></span> <span data-ttu-id="1560f-207">ユーザーに適用されるクライアントとサイトのポリシーはグローバル ポリシーより優先されることを注意してください。</span><span class="sxs-lookup"><span data-stu-id="1560f-207">Note that client and site policies applied to users will take precedence over a Global policy.</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 <span data-ttu-id="1560f-p127">**オプション 2:** 現在環境で使用している既存のクライアント ポリシーを変更し、Lync クライアント エクスペリエンスを有効にする設定が含まれるようにします。この場合、既存のポリシーが割り当てられているユーザーのみに Lync クライアント エクスペリエンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1560f-p127">**Option 2:** Modify an existing client policy that you are using in your environment to include the setting to enable the Lync client experience. This lets you assign the Lync client experience only to those users that have the existing policy assigned:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

 <span data-ttu-id="1560f-210">**オプション 3:** Lync クライアント エクスペリエンスの設定を含むカスタム ポリシーのインスタンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="1560f-210">**Option 3:** Use a custom policy instance that includes the setting for the Lync client experience.</span></span>
  
```
Grant-CsClientPolicy username@contoso.com -PolicyName ClientPolicyNoIMURLDisableSkypeUI
```

<span data-ttu-id="1560f-211">ビジネス クライアントでは、ビルド 4711.1002 (2015 年 4 月に) Skype を導入、クライアントのポリシーを構成した後またはそれ以降です。</span><span class="sxs-lookup"><span data-stu-id="1560f-211">After you've configured your client policies, deploy the Skype for Business client, build 4711.1002 (April, 2015) or later.</span></span>
  
<span data-ttu-id="1560f-212">クライアントを構成する方法についての詳細な発生 Skype で、最初の実行経験とお客様の環境を構成するのにを使用することができます PowerShell スクリプトを制御する方法について手順を含むビジネス オンライン、[を参照するくださいとの間の切り替え、Skype ビジネスおよび Lync クライアントのユーザー インターフェイスの](https://aka.ms/SfBOUI)です。</span><span class="sxs-lookup"><span data-stu-id="1560f-212">For detailed information about how to configure the client experience with Skype for Business Online, including steps about how to control the first run experience and PowerShell scripts you can use to configure your environment, see [Switching between the Skype for Business and the Lync client user interfaces](https://aka.ms/SfBOUI).</span></span>
  
## <a name="resources-to-help-you-prepare-your-support-teams-and-your-end-users-for-the-update"></a><span data-ttu-id="1560f-213">サポート チームとエンド ユーザーの更新の準備に役立つリソース</span><span class="sxs-lookup"><span data-stu-id="1560f-213">Resources to help you prepare your support teams and your end users for the update</span></span>
<span data-ttu-id="1560f-214"><a name="support"> </a></span><span class="sxs-lookup"><span data-stu-id="1560f-214"></span></span>

<span data-ttu-id="1560f-215">簡単にしてを組織の移行の準備、計画、教育、およびエンド ・ ユーザーに協力するため、その他多くのリソースがあります。</span><span class="sxs-lookup"><span data-stu-id="1560f-215">To make it easier for you and your organization prepare for the transition, we have many additional resources available to help you plan, educate and engage end-users.</span></span>
  
- [<span data-ttu-id="1560f-216">ビデオ: ビジネス用の Skype の導入</span><span class="sxs-lookup"><span data-stu-id="1560f-216">Video: Introducing Skype for Business</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=544819)
    
- [<span data-ttu-id="1560f-217">Skype のビジネス ・ クイック ・ スタート ・ ガイド (ダウンロード)</span><span class="sxs-lookup"><span data-stu-id="1560f-217">Skype for Business Quick Start Guides (Download)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=544818)
    
- [<span data-ttu-id="1560f-218">Lync はビジネス用の Skype では今すぐ、新機能を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1560f-218">Lync is now Skype for Business — see what's new</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=529224)
    
- [<span data-ttu-id="1560f-219">ビジネス用の Skype: 新規ユーザーのためのステップ バイ ステップ ガイド</span><span class="sxs-lookup"><span data-stu-id="1560f-219">Skype for Business: Step-by-step guide for new users</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=544815)
    
- [<span data-ttu-id="1560f-220">なぜ表示 Skype ビジネスの Lync を使用している場合ですか。</span><span class="sxs-lookup"><span data-stu-id="1560f-220">Why do I see Skype for Business when I'm using Lync?</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=544712)
    

