---
title: "サードパーティを電話会議プロバイダーとして割り当てる"
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
description: 'Learn how to set up a third-party as your dial-in conferencing provider with Skype for Business. '
ms.openlocfilehash: 5ae513c754764933f08370139eeb557f0fb39211
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a><span data-ttu-id="19aaa-103">サードパーティを電話会議プロバイダーとして割り当てる</span><span class="sxs-lookup"><span data-stu-id="19aaa-103">Assign a third-party as the audio conferencing provider</span></span>

<span data-ttu-id="19aaa-104">オーディオ会議プロバイダーでは、*テレビ会議サービス*を提供します。</span><span class="sxs-lookup"><span data-stu-id="19aaa-104">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="19aaa-105">この会議ブリッジは、作成される会議のダイヤルイン電話番号、PIN、および会議 ID を提供します。</span><span class="sxs-lookup"><span data-stu-id="19aaa-105">The conference bridge provides the dial-in phone number, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="19aaa-106">必要なのは、電話会議プロバイダーを Skype for Business 会議または Microsoft Teams 会議をスケジュールまたは開催しようとしている人に割り当てることだけです。</span><span class="sxs-lookup"><span data-stu-id="19aaa-106">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="19aaa-107">Microsoft Teams の場合、ユーザーはサードパーティーの電話会議プロバイダーを使用できません。電話会議プロバイダーが Microsoft に設定される Office 365 の電話会議を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19aaa-107">For Microsoft Teams, a user can't use a third-party audio conferencing provider, they must use Audio Conferencing in Office 365, which sets the audio conferencing provider to Microsoft.</span></span> 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="19aaa-108">サードパーティーの電話会議プロバイダーを割り当てる前に実行する手順</span><span class="sxs-lookup"><span data-stu-id="19aaa-108">Steps to do BEFORE you can assign a third-party audio conferencing provider</span></span>

1. <span data-ttu-id="19aaa-109">ご利用の Office 365 プランに応じて、組織内で電話会議を使用する Skype for Business 会議または Microsoft Teams 会議をスケジュールまたは開催しようとしているユーザーのために **電話会議**アドオンライセンスを購入する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="19aaa-109">Depending on your Office 365 plan, you might need to buy **Audio Conferencing** add-on licenses for the people in your organization who are going to schedule or lead Skype for Business or Microsoft Teams meetings using Audio Conferencing.</span></span> <span data-ttu-id="19aaa-110">詳細については、 [Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19aaa-110">To learn more, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="19aaa-111">**電話会議**アドオン ライセンスを購入した場合、それらのライセンスを組織内で電話会議を使用する会議をスケジュールまたは開催しようとしている人に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="19aaa-111">If you purchased **Audio Conferencing** add-on licenses, assign them to the people in your organization who are going to schedule or lead meetings that use Audio Conferencing.</span></span> <span data-ttu-id="19aaa-112">「[Skype for Business と Microsoft Teams のライセンスを割り当てる](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="19aaa-112">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="19aaa-p104">**電話会議**ライセンスをサードパーティーの電話会議プロバイダーに割り当てた **後に** 、任意のユーザーに割り当てる場合、そのユーザーは自動的に Microsoft を電話会議プロバイダーとして使用するように設定されます。このような場合は、サードパーティーの電話会議プロバイダーを割り当てる前に、Microsoft を電話会議プロバイダーとして削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19aaa-p104">If you assign an **Audio Conferencing** license to someone **AFTER** you assign them a third-party audio conferencing provider, that person will automatically be set to use Microsoft as their audio conferencing provider instead! If this happens, you will need to first remove Microsoft as the audio conferencing provider before you can assign a third-party audio conferencing provider to them.</span></span>
  
3. <span data-ttu-id="19aaa-p105">サードパーティーの電話会議プロバイダーは、[Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530) で見つけてください。セットアップ方法については、これらのプロバイダーに連絡して確認してください。</span><span class="sxs-lookup"><span data-stu-id="19aaa-p105">Find a third-party audio conferencing provider at [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530). Contact them and find out how to get things set up with them.</span></span>
    
    <span data-ttu-id="19aaa-117">サードパーティーのダイヤルイン会議プロバイダーから以下の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="19aaa-117">They will give you:</span></span>
    
  - <span data-ttu-id="19aaa-118">**ダイヤルイン番号 (有料)** とフリーダイヤルの番号 (提供されている場合)。</span><span class="sxs-lookup"><span data-stu-id="19aaa-118">**Dial-in numbers (toll)** and toll-free numbers if they are available.</span></span>
    
  - <span data-ttu-id="19aaa-p106">**会議 Id。これは会議をスケジュールする各ユーザーが使用します。一部の** 。これは会議をスケジュールする各ユーザーで使用されます。一部の ACP では、これらのパスコードが要求されます。</span><span class="sxs-lookup"><span data-stu-id="19aaa-p106">**Conference IDs** that are used for each person who schedules meetings. Some ACPs call these conference passcodes.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="19aaa-121">サードパーティー ACP の初回のセットアップを完了したが変更する必要が生じた場合には、[ **Microsoft Bridge**] ページの下部で **ここをクリックしてサードパーティーの音声会議プロバイダーを構成してください**。</span><span class="sxs-lookup"><span data-stu-id="19aaa-121">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="19aaa-122">ある人を電話会議に対して有効にして、サードパーティーの電話会議プロバイダーを割り当てると、音声会議と会議の ID (パスコード) が、これらにより作成される **新しい** Skype for Business Online会議に自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="19aaa-122">When you enable a person for audio conferencing, and assign them a third-party audio conferencing provider, the audio numbers and conference IDs (passcodes) are automatically added to any **new** Skype for Business Online meetings that they create.</span></span>
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a><span data-ttu-id="19aaa-123">サードパーティー電話会議プロバイダーをユーザーに割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="19aaa-123">How to assign a third-party audio conferencing provider to a user</span></span>

1. <span data-ttu-id="19aaa-p107">[ **Skype for Business 管理センター**] で、[ **ユーザー**] を選択します。リストからユーザーを選び、操作ウィンドウで [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19aaa-p107">In the **Skype for Business admin center**, choose **Users**. Select the user from the list and click **Edit** in the action pane.</span></span>
    
2. <span data-ttu-id="19aaa-126">ユーザーのプロパティ ページで [ **電話会議**] をクリックして次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="19aaa-126">On the user's properties page, click **Audio conferencing** and enter this information:</span></span>
    
  - <span data-ttu-id="19aaa-127">**プロバイダー名**サードパーティのプロバイダーを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="19aaa-127">**Provider name** Select the third-party provider from the list.</span></span>
    
  - <span data-ttu-id="19aaa-128">[ **既定の有料電話番号**] これは必須です。</span><span class="sxs-lookup"><span data-stu-id="19aaa-128">**Default toll number** This is required.</span></span>
    
  - <span data-ttu-id="19aaa-129">[ **既定のフリー ダイヤル番号**] これは必須です。</span><span class="sxs-lookup"><span data-stu-id="19aaa-129">**Default toll-free number** This not required.</span></span>
    
  - <span data-ttu-id="19aaa-130">[ **会議 ID**] ご利用の音声会議プロバイダーから提供されます。</span><span class="sxs-lookup"><span data-stu-id="19aaa-130">**Conference ID** This is provided by your audio conferencing provider.</span></span>
    
3. <span data-ttu-id="19aaa-131">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19aaa-131">Click **Save**.</span></span>
    
4. <span data-ttu-id="19aaa-p108">各ユーザーに電話会議プロバイダーから受け取った PIN を送信します。この PIN は電話会議の開催者またはリーダーとしてコールインするために必要です。</span><span class="sxs-lookup"><span data-stu-id="19aaa-p108">Send each person the PIN you received from the audio conferencing provider. The PIN may be required to call in as the conference call organizer or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="19aaa-134">サードパーティーの電話会議プロバイダーを使用している場合、会議の開催者の代わりに PIN を表示 / 設定する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="19aaa-134">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a><span data-ttu-id="19aaa-135">サードパーティーの電話会議プロバイダーを多数の人に同時に割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="19aaa-135">How to assign a third-party audio conferencing provider to many people at the same time</span></span>

1. <span data-ttu-id="19aaa-p109">In the **Skype for Business admin center**, choose **Audio conferencing** > **Microsoft bridge**. At the bottom of the page, click the link in **If you would like to configure a third-party audio conferencing provider instead, click here**.</span><span class="sxs-lookup"><span data-stu-id="19aaa-p109">In the **Skype for Business admin center**, choose **Audio conferencing** > **Microsoft bridge**. At the bottom of the page, click the link in **If you would like to configure a third-party audio conferencing provider instead, click here**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="19aaa-138">行う場合、サード パーティ製の ACP の最初のセットアップが、今すぐ**ここをクリックすると、サード ・ パーティ製のオーディオ会議プロバイダーを構成するのには**、**マイクロソフトのブリッジ**のページの下部にある変更を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="19aaa-138">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page, **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
2. <span data-ttu-id="19aaa-p110">[ **サードパーティーの音声会議プロバイダーを構成する**] ページで、[ **ユーザーのインポートおよびエクスポート**] の [ **エクスポート ウィザード**] をクリックして [ **ユーザーのエクスポート ウィザード**] の手順を実行します。完了すると、電話会議に設定する人を一覧表示するファイルを入手します。</span><span class="sxs-lookup"><span data-stu-id="19aaa-p110">On the **Configure a third party audio conferencing provider** page, under **Import and export users**, click **Export wizard**, and then follow the steps in the **Export Users wizard**. When you finish, you'll have a file that lists the people you want to set up for audio conferencing.</span></span>
    
3. <span data-ttu-id="19aaa-p111">作成したファイルをサードパーティーの電話会議プロバイダーに送信します。プロバイダーはファイルに一覧表示された人の電話会議情報を追加して、ファイルを返送します。</span><span class="sxs-lookup"><span data-stu-id="19aaa-p111">Send the file you created to your third-party audio conferencing provider. They will add audio conferencing information for the people listed in the file, and then return the file to you.</span></span>
    
4. <span data-ttu-id="19aaa-p112">返送されたファイルに正しい情報が含まれていることを慎重に確認してください。ファイルに一覧表示された人が正しい情報を取得していない場合があることがわかっています。</span><span class="sxs-lookup"><span data-stu-id="19aaa-p112">Double-check that the returned file has the right information in it. We've heard of instances where not everyone listed in the file got the right information.</span></span>
    
5. <span data-ttu-id="19aaa-145">[ **サードパーティーの音声会議プロバイダーを構成する**] で、[ **ユーザーのインポートおよびエクスポート**] の [ **インポート ウィザード**] をクリックして、[ **ユーザーのインポート ウィザード**] の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="19aaa-145">On the **Configure a third-party audio conferencing provider page**, under **Import and export users**, click **Import wizard**, and then follow the steps in the **Import Users wizard**</span></span>
    
6. <span data-ttu-id="19aaa-p113">各ユーザーに電話会議プロバイダーから受け取った PIN を送信します。この PIN は電話会議の開催者またはリーダーとしてコールインするために必要です。</span><span class="sxs-lookup"><span data-stu-id="19aaa-p113">Send each person the PIN you received from the audio conferencing provider. The PIN may be required to call in as the conference call organizer, or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="19aaa-148">サードパーティーの電話会議プロバイダーを使用している場合、会議の開催者の代わりに PIN を表示 / 設定する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="19aaa-148">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="19aaa-149">サードパーティーの電話会議プロバイダーを使用する場合</span><span class="sxs-lookup"><span data-stu-id="19aaa-149">When to use a third-party audio conferencing provider</span></span>

<span data-ttu-id="19aaa-p114">Office 365 の電話会議を利用できない国または地域にお住まいの場合は、場所が原因でサービス品質が低下します。サードパーティーの電話会議プロバイダーとの既存の契約がある場合は、サードパーティーの電話会議プロバイダーを使用することをお勧めしますが、それ以外の場合は、マイクロソフトを電話会議プロバイダーとして使用してください。</span><span class="sxs-lookup"><span data-stu-id="19aaa-p114">If you are in a country or region where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract with a third-party audio conferencing provider, we recommend using a third-party audio conferencing provider. Otherwise, we recommend using Microsoft as your audio conferencing provider.</span></span>
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a><span data-ttu-id="19aaa-152">Windows PowerShell を使用して、サードパーティーの音声会議プロバイダーとしての割り当てを自動化する</span><span class="sxs-lookup"><span data-stu-id="19aaa-152">Automate assigning the third-party audio conferencing provider by using Windows PowerShell</span></span>

- <span data-ttu-id="19aaa-153">時間を節約したり、自動化したりするために、[Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="19aaa-153">To save time or automate this, you can use the [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) cmdlet.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="19aaa-p115">プロバイダーを Microsoft からサードパーティーの電話会議プロバイダーに変更するには、Microsoft を電話会議プロバイダーから削除する必要があります。これを行うには、[Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="19aaa-p115">To change the audio provider from Microsoft to a third-party audio conferencing provider, you must remove Microsoft as the audio conferencing provider. To do this, use the [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) cmdlet.</span></span>
  
- <span data-ttu-id="19aaa-156">Windows PowerShell の使い方の詳細については、「[Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="19aaa-156">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
    
## <a name="what-else-do-i-need-to-know"></a><span data-ttu-id="19aaa-157">他に必要な情報について</span><span class="sxs-lookup"><span data-stu-id="19aaa-157">What else do I need to know?</span></span>

<span data-ttu-id="19aaa-158">組織内のユーザーは 1 つの電話会議プロバイダーのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="19aaa-158">A person in your organization can only use one audio conferencing provider.</span></span> <span data-ttu-id="19aaa-159">マイクロソフトに個人の電話会議プロバイダーを変更するには、[マイクロソフトのユーザーのオーディオ会議プロバイダーを移動](moving-a-user-s-audio-conferencing-provider-to-microsoft.md)または[オーディオ会議プロバイダーとしてのマイクロソフトの割り当て](assign-microsoft-as-the-audio-conferencing-provider.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19aaa-159">To change a person's audio conferencing provider to Microsoft, see [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="19aaa-160">関連トピック</span><span class="sxs-lookup"><span data-stu-id="19aaa-160">Related Topics</span></span>

[<span data-ttu-id="19aaa-161">Skype for Business および Microsoft Teams の電話会議のセットアップ</span><span class="sxs-lookup"><span data-stu-id="19aaa-161">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="19aaa-162">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="19aaa-162">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

