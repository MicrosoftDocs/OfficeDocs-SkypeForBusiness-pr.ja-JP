---
title: "電話会議プロバイダーとしてサードパーティを割り当てる"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Skype for Business とのダイヤルイン会議プロバイダーとしてサードパーティを設定する方法について説明します。 "
ms.openlocfilehash: 5ae513c754764933f08370139eeb557f0fb39211
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a><span data-ttu-id="66dd9-103">電話会議プロバイダーとしてサードパーティを割り当てる</span><span class="sxs-lookup"><span data-stu-id="66dd9-103">Assign a third-party as the audio conferencing provider</span></span>

<span data-ttu-id="66dd9-p101">電話会議プロバイダーは*会議ブリッジ*を提供します。会議ブリッジにダイヤルイン電話番号、ピン、作成した会議の会議 Id を提供します。Skype を潜在顧客のビジネスまたは Microsoft チーム会議やスケジュールを設定する人に電話会議プロバイダーを割り当てる必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p101">An audio conferencing provider supplies the *conference bridge*. The conference bridge provides the dial-in phone number, PINs, and conference IDs for meetings that are created. You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="66dd9-107">Microsoft チームのユーザーがサードパーティ電話会議プロバイダーを使用できません、Office 365 で、電話会議プロバイダーを Microsoft に設定している電話会議を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66dd9-107">For Microsoft Teams, a user can't use a third-party audio conferencing provider, they must use Audio Conferencing in Office 365, which sets the audio conferencing provider to Microsoft.</span></span> 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="66dd9-108">サードパーティ電話会議プロバイダーを割り当てることができる前に実行する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="66dd9-108">Steps to do BEFORE you can assign a third-party audio conferencing provider</span></span>

1. <span data-ttu-id="66dd9-p102">によっては、Office 365 プランでは、スケジュールされたり、Skype for Business または Microsoft チーム会議の音声会議を使用する組織内のユーザーの**電話会議**アドオン ライセンスを購入する必要があります。詳細については、 [Skype for Business や Microsoft チーム アドオンのライセンス](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p102">Depending on your Office 365 plan, you might need to buy **Audio Conferencing** add-on licenses for the people in your organization who are going to schedule or lead Skype for Business or Microsoft Teams meetings using Audio Conferencing. To learn more, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="66dd9-p103">**電話会議**アドオン ライセンスを購入した場合は、スケジュールの設定、または電話会議を使用する会議を進行するユーザーは、組織のユーザーに割り当てます。[ビジネスや Microsoft チームのライセンスを割り当てる Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p103">If you purchased **Audio Conferencing** add-on licenses, assign them to the people in your organization who are going to schedule or lead meetings that use Audio Conferencing. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="66dd9-p104">**後**サードパーティ電話会議プロバイダーを割り当てるユーザーに**電話会議**のライセンスを割り当てる場合、代わりに、電話会議プロバイダーとして Microsoft を使用するユーザーが自動的に設定されます。このような場合は、サードパーティ電話会議プロバイダーにそれらを割り当てるには前に、電話会議プロバイダーとして Microsoft を最初に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p104">If you assign an **Audio Conferencing** license to someone **AFTER** you assign them a third-party audio conferencing provider, that person will automatically be set to use Microsoft as their audio conferencing provider instead! If this happens, you will need to first remove Microsoft as the audio conferencing provider before you can assign a third-party audio conferencing provider to them.</span></span>
  
3. <span data-ttu-id="66dd9-p105">[Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530)では、サードパーティ電話会議プロバイダーを検索します。連絡を取るし、それらのファイルを設定する項目を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p105">Find a third-party audio conferencing provider at [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530). Contact them and find out how to get things set up with them.</span></span>
    
    <span data-ttu-id="66dd9-117">されます。</span><span class="sxs-lookup"><span data-stu-id="66dd9-117">They will give you:</span></span>
    
  - <span data-ttu-id="66dd9-118">**ダイヤルイン番号 (有料)**と利用可能な場合はフリー ダイヤルの番号。</span><span class="sxs-lookup"><span data-stu-id="66dd9-118">**Dial-in numbers (toll)** and toll-free numbers if they are available.</span></span>
    
  - <span data-ttu-id="66dd9-p106">会議をスケジュールするユーザーごとの使用されている**会議 Id** 。一部の Acp では、これらの会議パスコードを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p106">**Conference IDs** that are used for each person who schedules meetings. Some ACPs call these conference passcodes.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="66dd9-121">場合は、サードパーティ ACP 用を設定する最初のようになりましたする必要しますが、あります**ここをクリックすると、サードパーティ電話会議プロバイダーを構成する** **Microsoft ブリッジ**ページの下部にある、変更を行います。</span><span class="sxs-lookup"><span data-stu-id="66dd9-121">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="66dd9-122">音声会議に人を有効にし、サードパーティ電話会議プロバイダーを割り当てると、会議 Id (パスコード) と音声番号は、**新しい**Skype for Business Online の会議を作成するに自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="66dd9-122">When you enable a person for audio conferencing, and assign them a third-party audio conferencing provider, the audio numbers and conference IDs (passcodes) are automatically added to any **new** Skype for Business Online meetings that they create.</span></span>
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a><span data-ttu-id="66dd9-123">サードパーティ電話会議プロバイダーをユーザーに割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="66dd9-123">How to assign a third-party audio conferencing provider to a user</span></span>

1. <span data-ttu-id="66dd9-p107">**Skype for Business 管理センター**で、[**ユーザー**] を選びます。リストからユーザーを選択し、操作ウィンドウで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p107">In the **Skype for Business admin center**, choose **Users**. Select the user from the list and click **Edit** in the action pane.</span></span>
    
2. <span data-ttu-id="66dd9-126">ユーザーのプロパティ] ページは、**電話会議**をクリックし、この情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="66dd9-126">On the user's properties page, click **Audio conferencing** and enter this information:</span></span>
    
  - <span data-ttu-id="66dd9-127">**プロバイダー名**リストからサードパーティ プロバイダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="66dd9-127">**Provider name** Select the third-party provider from the list.</span></span>
    
  - <span data-ttu-id="66dd9-128">**既定の電話番号**これが必要です。</span><span class="sxs-lookup"><span data-stu-id="66dd9-128">**Default toll number** This is required.</span></span>
    
  - <span data-ttu-id="66dd9-129">**既定のフリー ダイヤル番号**これは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="66dd9-129">**Default toll-free number** This not required.</span></span>
    
  - <span data-ttu-id="66dd9-130">**電話会議 ID**これは、電話会議プロバイダーによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="66dd9-130">**Conference ID** This is provided by your audio conferencing provider.</span></span>
    
3. <span data-ttu-id="66dd9-131">{[**保存**] をクリックします。}</span><span class="sxs-lookup"><span data-stu-id="66dd9-131">Click **Save**.</span></span>
    
4. <span data-ttu-id="66dd9-p108">電話会議プロバイダーから受け取った暗証番号 (pin) を各ユーザーに送信します。PIN は、電話会議の開催者またはリーダーとしてコールインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p108">Send each person the PIN you received from the audio conferencing provider. The PIN may be required to call in as the conference call organizer or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="66dd9-134">サードパーティ電話会議プロバイダーを使っているときに参照するか、会議の開催者の代わりに Pin を設定する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="66dd9-134">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a><span data-ttu-id="66dd9-135">サードパーティ電話会議プロバイダーを多数のユーザーに同時に割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="66dd9-135">How to assign a third-party audio conferencing provider to many people at the same time</span></span>

1. <span data-ttu-id="66dd9-p109">**Skype for Business 管理センター**で、[**音声会議**] を選びます > **Microsoft ブリッジ**します。ページの下部にあるには、**代わりに、サードパーティ電話会議プロバイダーを構成したい場合は、ここをクリックして**リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p109">In the **Skype for Business admin center**, choose **Audio conferencing** > **Microsoft bridge**. At the bottom of the page, click the link in **If you would like to configure a third-party audio conferencing provider instead, click here**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="66dd9-138">場合は、サードパーティ ACP 用を設定する最初のようになりましたする必要しますが、あります**ここをクリックすると、サードパーティ電話会議プロバイダーを構成するのには**、 **Microsoft ブリッジ**ページの下部にある、変更を行います。</span><span class="sxs-lookup"><span data-stu-id="66dd9-138">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page, **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
2. <span data-ttu-id="66dd9-p110">**電話会議プロバイダーをサードパーティの構成**] ページの [**インポートとエクスポートのユーザー**] の下で、**エクスポート ウィザード**] をクリックし、[**ユーザーのエクスポート ウィザード**の手順に従います。完了したら、電話会議を設定する人の一覧が表示されているファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p110">On the **Configure a third party audio conferencing provider** page, under **Import and export users**, click **Export wizard**, and then follow the steps in the **Export Users wizard**. When you finish, you'll have a file that lists the people you want to set up for audio conferencing.</span></span>
    
3. <span data-ttu-id="66dd9-p111">サードパーティ電話会議プロバイダーを作成したファイルを送信します。ファイルに記載されているユーザーの電話会議の情報を追加に戻って、ファイル、されます。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p111">Send the file you created to your third-party audio conferencing provider. They will add audio conferencing information for the people listed in the file, and then return the file to you.</span></span>
    
4. <span data-ttu-id="66dd9-p112">返されたファイルが含まれている正しい情報にはことを確認してください。適切な情報を持っていないファイルに記載されているすべてのインスタンスのことができます。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p112">Double-check that the returned file has the right information in it. We've heard of instances where not everyone listed in the file got the right information.</span></span>
    
5. <span data-ttu-id="66dd9-145">**サードパーティ電話会議プロバイダーのページの構成**] の [**インポートとエクスポートのユーザー**の場合は、[**インポート ウィザード**] をクリックし、[**ユーザーのインポート ウィザード**の手順を実行</span><span class="sxs-lookup"><span data-stu-id="66dd9-145">On the **Configure a third-party audio conferencing provider page**, under **Import and export users**, click **Import wizard**, and then follow the steps in the **Import Users wizard**</span></span>
    
6. <span data-ttu-id="66dd9-p113">電話会議プロバイダーから受け取った暗証番号 (pin) を各ユーザーに送信します。PIN は、電話会議の開催者、またはリーダーとしてコールインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p113">Send each person the PIN you received from the audio conferencing provider. The PIN may be required to call in as the conference call organizer, or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="66dd9-148">サードパーティ電話会議プロバイダーを使っているときに参照するか、会議の開催者の代わりに Pin を設定する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="66dd9-148">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="66dd9-149">サードパーティ電話会議プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="66dd9-149">When to use a third-party audio conferencing provider</span></span>

<span data-ttu-id="66dd9-p114">サード パーティの音声を使用してをお勧めの国または地域を Office 365 で音声会議は使用できません、サービスの品質がない理由により、その場所では、とても便利なまたはサードパーティ電話会議プロバイダーを既存の契約がある場合は、会議のプロバイダーします。それ以外の場合、電話会議プロバイダーとしての Microsoft の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p114">If you are in a country or region where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract with a third-party audio conferencing provider, we recommend using a third-party audio conferencing provider. Otherwise, we recommend using Microsoft as your audio conferencing provider.</span></span>
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a><span data-ttu-id="66dd9-152">Windows PowerShell を使用して、サードパーティ電話会議プロバイダーを割り当てるを自動化します。</span><span class="sxs-lookup"><span data-stu-id="66dd9-152">Automate assigning the third-party audio conferencing provider by using Windows PowerShell</span></span>

- <span data-ttu-id="66dd9-153">時間を節約し、自動化したりには、[セット CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851)コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="66dd9-153">To save time or automate this, you can use the [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) cmdlet.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="66dd9-p115">Microsoft からサードパーティ電話会議プロバイダーに、オーディオ プロバイダーを変更するには、電話会議プロバイダーとして Microsoft を削除する必要があります。これを行うには、[無効にする CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 )コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p115">To change the audio provider from Microsoft to a third-party audio conferencing provider, you must remove Microsoft as the audio conferencing provider. To do this, use the [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) cmdlet.</span></span>
  
- <span data-ttu-id="66dd9-156">詳細については、Windows PowerShell を使用して、[共通の Skype for Business Online の管理タスクを実行する Windows PowerShell を使用する](https://go.microsoft.com/fwlink/?LinkId=525038)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66dd9-156">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
    
## <a name="what-else-do-i-need-to-know"></a><span data-ttu-id="66dd9-157">他に必要な情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="66dd9-157">What else do I need to know?</span></span>

<span data-ttu-id="66dd9-p116">組織内のユーザーは、1 つの電話会議プロバイダーにのみ使用できます。Microsoft には、その人の電話会議プロバイダーを変更するには、 [Microsoft にユーザーの電話会議プロバイダーを移動](moving-a-user-s-audio-conferencing-provider-to-microsoft.md)または[電話会議プロバイダーとして Microsoft を割り当てる](assign-microsoft-as-the-audio-conferencing-provider.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66dd9-p116">A person in your organization can only use one audio conferencing provider. To change a person's audio conferencing provider to Microsoft, see [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="66dd9-160">関連トピック</span><span class="sxs-lookup"><span data-stu-id="66dd9-160">Related Topics</span></span>

[<span data-ttu-id="66dd9-161">Skype for Business とチームの Microsoft の音声会議をセットアップする設定します。</span><span class="sxs-lookup"><span data-stu-id="66dd9-161">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="66dd9-162">Skype for Business Online をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="66dd9-162">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

