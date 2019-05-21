---
title: Microsoft Teams で休日を設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
description: Microsoft Teams で休日を設定し、自動応答に接続する方法について説明します。
ms.openlocfilehash: bf11fbed270d930ece29cdd89af053c34bc606da
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298703"
---
# <a name="set-up-holidays-in-microsoft-teams"></a><span data-ttu-id="26bd0-103">Microsoft Teams で休日を設定する</span><span class="sxs-lookup"><span data-stu-id="26bd0-103">Set up holidays in Microsoft Teams</span></span>

<span data-ttu-id="26bd0-104">Microsoft Teams の祝日機能を使用すると、組織内のユーザーが業務から休暇を取り、通常の営業時間内には利用できないようにする場合に、特定の日付と時刻をスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="26bd0-104">You can use the Microsoft Teams Holidays feature to schedule specific dates and times when people in your organization will be taking time off from work and won’t be available during regular business hours.</span></span> 

<span data-ttu-id="26bd0-105">組織内で作成した自動応答に休日をリンクすることができます。</span><span class="sxs-lookup"><span data-stu-id="26bd0-105">You can link the holidays to auto attendants that you create within your organization.</span></span> <span data-ttu-id="26bd0-106">自動応答を使うと、呼び出し元はメニューシステムを移動して適切な部門にアクセスしたり、必要な情報を取得したりできます。</span><span class="sxs-lookup"><span data-stu-id="26bd0-106">Auto attendants let callers navigate a menu system to get to the right department or get to information that they need.</span></span> <span data-ttu-id="26bd0-107">自動応答の休日通話の設定を構成する場合、リストから休日を選択し、あいさつ文を追加して、休暇中に自動応答によって応答されたときの通話の処理を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="26bd0-107">When you configure holiday call settings for an auto attendant, you can select the holiday from a list, add a greeting, and specify what to do with the call when it’s answered by the auto attendant during the holiday.</span></span>

<span data-ttu-id="26bd0-108">良い例としては、従業員の人数が多すぎてクリスマスの休日を作ることができます。</span><span class="sxs-lookup"><span data-stu-id="26bd0-108">A good example is creating a holiday for Christmas for when many of your employees aren’t at work.</span></span> <span data-ttu-id="26bd0-109">休日を作成し、時刻を設定した後は、休日をメインの自動応答に追加することで、ユーザーが電話をかけたときに、作成した音声メッセージが聞こえます。</span><span class="sxs-lookup"><span data-stu-id="26bd0-109">After you create the holiday and set times, then you would add the holiday to your main auto attendant so when people call in, they will hear an audio message you created.</span></span> <span data-ttu-id="26bd0-110">「お客様は、"クリスマス・年12月22日から12月27日までに終了しました。</span><span class="sxs-lookup"><span data-stu-id="26bd0-110">Something like, “We are closed for Christmas from December 22nd through December 27th.</span></span> <span data-ttu-id="26bd0-111">お客さまの勤務先に戻ってきた場合は、音声メッセージをお送りください。</span><span class="sxs-lookup"><span data-stu-id="26bd0-111">Please leave us a voice message so we can return your call when we are back in the office.”</span></span>

<span data-ttu-id="26bd0-112">自動応答の詳細については、「[クラウド自動応答とは何](what-are-phone-system-auto-attendants.md)ですか?」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26bd0-112">For more information about auto attendants, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md)?</span></span>  

## <a name="create-a-holiday"></a><span data-ttu-id="26bd0-113">休日を作成する</span><span class="sxs-lookup"><span data-stu-id="26bd0-113">Create a holiday</span></span>

1. <span data-ttu-id="26bd0-114">Microsoft Teams 管理センターで、[**組織全体の設定** > **休日**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-114">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="26bd0-115">[**新しい休日**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-115">Select **New holiday**.</span></span>

3. <span data-ttu-id="26bd0-116">休日の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-116">Enter a name for the holiday.</span></span>

4. <span data-ttu-id="26bd0-117">[ **Add new date**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="26bd0-117">Select **Add new date**.</span></span>

5. <span data-ttu-id="26bd0-118">[**開始時刻**] で、予定表アイコンを選択し、休日の開始日を選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-118">Under **Start time**, select the calendar icon and choose the date when you’d like the holiday to begin.</span></span>

6. <span data-ttu-id="26bd0-119">ドロップダウンリストを使用して、休日の開始時刻を選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-119">Use the drop-down list to select a start time for the holiday.</span></span>

7. <span data-ttu-id="26bd0-120">[**終了時刻**] で、予定表アイコンを選択し、休日の終了日を選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-120">Under **End time**, select the calendar icon and choose the date when you’d like the holiday to end.</span></span> <span data-ttu-id="26bd0-121">休日が1日のみの場合は、[**開始時刻**] で選択した日付と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="26bd0-121">If the holiday is one day only, this should be the same date as the one you chose under **Start time**.</span></span>

8. <span data-ttu-id="26bd0-122">ドロップダウンリストを使用して、休日の終了時刻を選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-122">Use the drop-down list to select an end time for the holiday.</span></span>

9. <span data-ttu-id="26bd0-123">[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="26bd0-123">Select **Save**.</span></span>

## <a name="change-a-holiday"></a><span data-ttu-id="26bd0-124">休日を変更する</span><span class="sxs-lookup"><span data-stu-id="26bd0-124">Change a holiday</span></span>

1. <span data-ttu-id="26bd0-125">Microsoft Teams 管理センターで、[**組織全体の設定** > **休日**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-125">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="26bd0-126">リストから休日を選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-126">Select the holiday from the list.</span></span>

3. <span data-ttu-id="26bd0-127">[**開始時刻**] で、予定表アイコンを選択し、休日の開始日を選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-127">Under **Start time**, select the calendar icon and choose the date when you’d like the holiday to begin.</span></span>

4. <span data-ttu-id="26bd0-128">ドロップダウンリストを使用して、休日の開始時刻を選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-128">Use the drop-down list to select a start time for the holiday.</span></span>

5. <span data-ttu-id="26bd0-129">[**終了時刻**] で、予定表アイコンを選択し、休日の終了日を選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-129">Under **End time**, select the calendar icon and choose the date when you’d like the holiday to end.</span></span> 

6. <span data-ttu-id="26bd0-130">ドロップダウンリストを使用して、休日の終了時刻を選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-130">Use the drop-down list to select an end time for the holiday.</span></span>

7. <span data-ttu-id="26bd0-131">[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="26bd0-131">Select **Save**.</span></span>

## <a name="connect-a-holiday-to-an-auto-attendant"></a><span data-ttu-id="26bd0-132">休日を自動応答に接続する</span><span class="sxs-lookup"><span data-stu-id="26bd0-132">Connect a holiday to an auto attendant</span></span>

1. <span data-ttu-id="26bd0-133">Microsoft Teams 管理センターで、[**音声** > **自動応答**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-133">In the Microsoft Teams admin center, go to **Voice** > **Auto attendants**.</span></span>
2. <span data-ttu-id="26bd0-134">リストからリソースアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-134">Select a resource account from the list.</span></span>
3. <span data-ttu-id="26bd0-135">左側のウィンドウで、[**ホリデー通話の設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-135">In the left pane, select **Holiday call settings**.</span></span>
4. <span data-ttu-id="26bd0-136">[**新しい休日**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-136">Select **New holiday**.</span></span>
5. <span data-ttu-id="26bd0-137">ドロップダウンリストから休日を選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-137">Select the holiday from the drop-down list.</span></span>
6. <span data-ttu-id="26bd0-138">オプションのあいさつ文を追加できます。</span><span class="sxs-lookup"><span data-stu-id="26bd0-138">You can add an optional greeting:</span></span>
    - <span data-ttu-id="26bd0-139">録音した応答メッセージを再生するには、[**オーディオファイルの再生**] を選択し、[**ファイルのアップロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-139">To play a recorded greeting, select **Play an audio file**, and then select **Upload file**.</span></span> <span data-ttu-id="26bd0-140">オーディオファイルの場所を参照し、ファイルを選択して、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-140">Browse to the location of the audio file, select the file, and then select **Open**.</span></span>
    - <span data-ttu-id="26bd0-141">あいさつ文を作成するには、[**あいさつ文の入力**] を選択し、メッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-141">To create a greeting, select **Type a greeting message**, and then type your message.</span></span> <span data-ttu-id="26bd0-142">音声ファイルを指定していない場合、発信者はこのメッセージを読み上げます。</span><span class="sxs-lookup"><span data-stu-id="26bd0-142">Callers will hear this message if you haven’t provided an audio file.</span></span>
7. <span data-ttu-id="26bd0-143">応答メッセージの後に通話を終了するには、[**アクション**] の [**切断**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="26bd0-143">To end the call after the greeting, under **Actions**, select **Disconnect**.</span></span> 

    <span data-ttu-id="26bd0-144">通話をリダイレクトするには、[**通話のリダイレクト**] を選択し、ドロップダウンリストからリダイレクトされた通話を受信するユーザーを選択するか、表示名で相手を検索します。</span><span class="sxs-lookup"><span data-stu-id="26bd0-144">To redirect the call, select **Redirect call**, and then select the person who will receive the redirected call from the drop-down list or search for the person by display name.</span></span>
8. <span data-ttu-id="26bd0-145">[**保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="26bd0-145">Select **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="26bd0-146">関連トピック</span><span class="sxs-lookup"><span data-stu-id="26bd0-146">Related topics</span></span>

<span data-ttu-id="26bd0-147">[クラウド自動応答とは何](what-are-phone-system-auto-attendants.md)ですか?</span><span class="sxs-lookup"><span data-stu-id="26bd0-147">[What are Cloud auto attendants](what-are-phone-system-auto-attendants.md)?</span></span>