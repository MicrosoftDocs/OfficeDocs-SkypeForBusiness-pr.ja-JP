---
title: Microsoft Teams の自動応答を設定する - 小規模ビジネス向けチュートリアル
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: dobro
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Microsoft 365 Business Voice の自動応答を設定してテストする方法について説明します。
ms.openlocfilehash: 7ee7dad833119778ceb64bd1e52bd30da4529ba8
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506654"
---
# <a name="set-up-an-auto-attendant---small-business-tutorial"></a><span data-ttu-id="a2a81-103">自動応答を設定する - 小規模ビジネス向けチュートリアル</span><span class="sxs-lookup"><span data-stu-id="a2a81-103">Set up an auto attendant - small business tutorial</span></span>

<span data-ttu-id="a2a81-104">自動応答を使用すると、ユーザーは組織に電話をかけ、メニュー システムを操作して、適切な部門、通話キュー、ユーザー、またはオペレーターに話しかけたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="a2a81-105">Microsoft Teams 管理センターを使用して、組織の自動応答を作成できます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-105">You can create auto attendants for your organization with the Microsoft Teams admin center.</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="a2a81-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="a2a81-106">Before you begin</span></span>

<span data-ttu-id="a2a81-107">組織外から直接ダイヤルすることで、アクセス可能な自動応答に必要なサービス番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-107">Get the service numbers that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="a2a81-108">これには、別の [プロバイダーからの番号の移行や](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 、新しい [サービス番号の要求が含まれる場合があります](../getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="a2a81-108">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="a2a81-109">電話システム [の取得 - 作成する](../teams-add-on-licensing/virtual-user.md) 各自動応答の仮想ユーザー ライセンス。</span><span class="sxs-lookup"><span data-stu-id="a2a81-109">Get a [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md) for each auto attendant that you plan to create.</span></span> <span data-ttu-id="a2a81-110">これらのライセンスは無料なので、後でセットアップを変更する場合に備え、追加のライセンスを取得する方法をお勧めしています。</span><span class="sxs-lookup"><span data-stu-id="a2a81-110">These licenses are free, so we suggest getting a few extra in case you decide to make changes to your setup in the future.</span></span>

<span data-ttu-id="a2a81-111">休日に自動応答のルート通話を別の方法で呼び出す[](../set-up-holidays-in-teams.md)場合は、自動応答を作成する前に使用する祝日を作成します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-111">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="a2a81-112">自動応答を設定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a2a81-112">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="a2a81-113">手順 1 <br> 電話番号</span><span class="sxs-lookup"><span data-stu-id="a2a81-113">Step 1<br>Phone number</span></span>](#tab/phone-number)

<span data-ttu-id="a2a81-114">作成する各自動応答には、リソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="a2a81-114">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="a2a81-115">これはユーザー アカウントに似ていますが、アカウントがユーザーではなく自動応答または通話キューに関連付けられている場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-115">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="a2a81-116">この手順では、アカウントを作成し *、Microsoft 365* 電話システム - 仮想ユーザー ライセンスを割り当て、サービス番号を割り当てします。</span><span class="sxs-lookup"><span data-stu-id="a2a81-116">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="a2a81-117">リソース アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="a2a81-117">Create a resource account</span></span>

<span data-ttu-id="a2a81-118">Teams 管理センターでリソース アカウントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-118">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="a2a81-119">Teams 管理センターで、組織全体の設定 **を** 展開し、[リソース アカウント] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a2a81-119">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="a2a81-120">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2a81-120">Click **Add**.</span></span>

3. <span data-ttu-id="a2a81-121">[リソース アカウント **の追加]** ウィンドウで、[表示名]、[**ユーザー** 名]、および [リソース アカウントの種類の自動応答] の入力を **行います。**</span><span class="sxs-lookup"><span data-stu-id="a2a81-121">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![リソース アカウントのユーザー インターフェイスの追加のスクリーンショット](../media/resource-account-add.png)

4. <span data-ttu-id="a2a81-123">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2a81-123">Click **Save**.</span></span>

<span data-ttu-id="a2a81-124">新しいアカウントがアカウントの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-124">The new account will appear in the list of accounts.</span></span>

![リソース アカウントの一覧のスクリーンショット](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="a2a81-126">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a2a81-126">Assign a license</span></span>

<span data-ttu-id="a2a81-127">Microsoft *365* 電話システム - 仮想ユーザー ライセンスをリソース アカウントに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2a81-127">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="a2a81-128">Microsoft 365 管理センターで、ライセンスを割り当てるリソース アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2a81-128">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="a2a81-129">[ライセンスと **アプリ] タブの** [ **ライセンス]** で **、[Microsoft 365 電話システム - 仮想ユーザー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a2a81-129">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="a2a81-130">[変更を **保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="a2a81-130">Click **Save changes**.</span></span>

    ![Microsoft 365 管理センターのライセンスの割り当てユーザー インターフェイスのスクリーンショット](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="a2a81-132">サービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="a2a81-132">Assign a service number</span></span>

<span data-ttu-id="a2a81-133">この自動応答に電話番号でアクセスする必要がある場合は、その番号をリソース アカウントに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2a81-133">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="a2a81-134">Teams 管理センターの [リソースアカウント] ページで、サービス番号を割り当てるリソース アカウントを選び、[割り当て/割り当て解除] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a2a81-134">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="a2a81-135">[電話番号 **の種類] ドロップダウン** で、使用する番号の種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-135">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="a2a81-136">[割 **り当てられた電話番号]** ボックスで、使用する番号を検索し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a2a81-136">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![サービス番号の割り当てユーザー インターフェイスのスクリーンショット](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="a2a81-138">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2a81-138">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a2a81-139">手順 2 - 自動応答の一般的な></span><span class="sxs-lookup"><span data-stu-id="a2a81-139">Step 2 - Auto attendant general info ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="a2a81-140">手順 2 <br> Attendant の一般的な情報</span><span class="sxs-lookup"><span data-stu-id="a2a81-140">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="a2a81-141">自動応答を設定するには</span><span class="sxs-lookup"><span data-stu-id="a2a81-141">To set up an auto attendant</span></span>

1. <span data-ttu-id="a2a81-142">Teams 管理センターで、[音声] を **展開** し、[ **自動** 応答] をクリックして、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="a2a81-142">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="a2a81-143">上部のボックスに自動応答の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-143">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="a2a81-144">演算子を指定する場合は、演算子の呼び出し先を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-144">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="a2a81-145">これは省略可能です (ただし、推奨)。</span><span class="sxs-lookup"><span data-stu-id="a2a81-145">This is optional (but recommended).</span></span> <span data-ttu-id="a2a81-146">発信者 **がメニューから** 抜け出し、指定されたユーザーと話し合う場合にオペレーター オプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-146">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="a2a81-147">この自動応答のタイム ゾーンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-147">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="a2a81-148">タイム ゾーンは、営業時間外の別のコール フローを作成する場合に、営業時間の計算に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-148">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="a2a81-149">この自動応答の言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-149">Specify a language for this auto attendant.</span></span> <span data-ttu-id="a2a81-150">システム生成の音声プロンプトに使用される言語です。</span><span class="sxs-lookup"><span data-stu-id="a2a81-150">This the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="a2a81-151">音声入力を有効にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-151">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="a2a81-152">有効にすると、すべてのメニュー オプションの名前が音声認識キーワードになります。</span><span class="sxs-lookup"><span data-stu-id="a2a81-152">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="a2a81-153">たとえば、発信者は"1" と言ってキー 1 にマップされたメニュー オプションを選択したり、"営業" と言って "営業" という名前のメニュー オプションを選択したりします。</span><span class="sxs-lookup"><span data-stu-id="a2a81-153">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![名前、オペレーター、タイム ゾーン、言語、音声入力の自動応答設定のスクリーンショット](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="a2a81-155">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2a81-155">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a2a81-156">手順 3 - コール フロー ></span><span class="sxs-lookup"><span data-stu-id="a2a81-156">Step 3 - Call flow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="a2a81-157">手順 3 <br> コール フロー</span><span class="sxs-lookup"><span data-stu-id="a2a81-157">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="a2a81-158">コール フロー オプションを選択する</span><span class="sxs-lookup"><span data-stu-id="a2a81-158">Choose your call flow options</span></span>

1. <span data-ttu-id="a2a81-159">自動応答が通話に応答するときに応答メッセージを再生する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-159">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="a2a81-160">[オーディオ ファイルの **再生] を選** ぶと、[ファイルのアップロード] ボタンを使用して、音声として保存された録音されたあいさつメッセージをアップロードできます。WAV、.MP3、または .WMA 形式。</span><span class="sxs-lookup"><span data-stu-id="a2a81-160">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="a2a81-161">記録できるサイズは 5 MB 以下です。</span><span class="sxs-lookup"><span data-stu-id="a2a81-161">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="a2a81-162">[あいさつ文を入力する] を選択した場合、自動応答が通話に応答すると、入力したテキスト (最大 1000 文字) が読み上げされます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-162">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![あいさつメッセージの設定のスクリーンショット](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="a2a81-164">通話のルーティング方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-164">Choose how you want to route the call.</span></span>

    <span data-ttu-id="a2a81-165">[切断] を **選ぶ** と、自動応答によって通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-165">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="a2a81-166">[通話の **リダイレクト] を選択** した場合は、通話ルーティング先のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-166">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="a2a81-167">[再生] メニュー **オプションを** 選択した場合は、[オーディオ ファイルの再生] または [あいさつメッセージを入力] を選び、メニュー オプションとディレクトリ検索から選びます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-167">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![通話ルーティング設定のスクリーンショット](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="a2a81-169">発信者がダイヤル キーを使用して移動する場合は、[メニューオプションの設定] で、発信者がダイヤル キーを押した場合に行う操作を選びます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-169">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="a2a81-170">(この自動応答を会社のディレクトリとして作成する場合は、ダイヤル キー オプションを空白のままにします)。</span><span class="sxs-lookup"><span data-stu-id="a2a81-170">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="a2a81-171">ダイヤル キーは、次の宛先に設定できます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-171">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="a2a81-172">**組織内のユーザー** - 音声通話を受信できる組織内のユーザー。</span><span class="sxs-lookup"><span data-stu-id="a2a81-172">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="a2a81-173">**音声アプリ** - 別の自動応答または通話キュー。</span><span class="sxs-lookup"><span data-stu-id="a2a81-173">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="a2a81-174">**外部電話番号** - 任意の電話番号。</span><span class="sxs-lookup"><span data-stu-id="a2a81-174">**External phone number** - any phone number.</span></span> <span data-ttu-id="a2a81-175">次の形式を使用します: +[国コード][郵便番号][電話番号]</span><span class="sxs-lookup"><span data-stu-id="a2a81-175">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="a2a81-176">**ボイス** メール - 指定した Microsoft 365 グループに関連付けられているボイス メールボックス。</span><span class="sxs-lookup"><span data-stu-id="a2a81-176">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="a2a81-177">**オペレーター** - 自動応答に定義された演算子。</span><span class="sxs-lookup"><span data-stu-id="a2a81-177">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="a2a81-178">演算子の定義は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a2a81-178">Defining an operator is optional.</span></span> <span data-ttu-id="a2a81-179">演算子は、このリストの他の宛先として定義できます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-179">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="a2a81-180">演算子には 0 キーを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a2a81-180">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="a2a81-181">メニュー オプションごとに、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-181">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="a2a81-182">**ダイヤル キー** - このオプションにアクセスするには、電話機のキーパッドのキー。</span><span class="sxs-lookup"><span data-stu-id="a2a81-182">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="a2a81-183">**音声コマンド** - 音声入力が有効になっている場合に、発信者がこのオプションにアクセスするために与える音声コマンドを定義します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-183">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="a2a81-184">"カスタマー サービス" や "Operations and Grounds" のような複数の単語を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-184">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="a2a81-185">**[リダイレクト先** ] - 発信者がこのオプションを選択するときに通話を発信する場所。</span><span class="sxs-lookup"><span data-stu-id="a2a81-185">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="a2a81-186">自動応答または通話キューにリダイレクトする場合は、関連付けられているリソース アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-186">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![ダイヤル キー オプションのスクリーンショット](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="a2a81-188">この自動応答を会社のディレクトリとして使用する場合は、[ディレクトリ検索] で [名前でダイヤル]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a2a81-188">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="a2a81-189">このオプションを有効にすると、発信者はユーザーの名前を音声で入力したり、電話機のキーパッドに入力できます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-189">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="a2a81-190">電話システム ライセンスを持つオンライン ユーザーは、対象ユーザーであり、名前でダイヤルで検索できます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-190">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="a2a81-191">([内線番号 **でダイヤル]** を選択することもできますが、Azure Active Directory で拡張機能を構成する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="a2a81-191">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="a2a81-192">ディレクトリ検索オプションを選択したら、[ **次へ** ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="a2a81-192">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a2a81-193">手順 4 - 営業時間外のコール フロー></span><span class="sxs-lookup"><span data-stu-id="a2a81-193">Step 4 - After hours call flow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="a2a81-194">手順 4 営業時間 <br> 外</span><span class="sxs-lookup"><span data-stu-id="a2a81-194">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="a2a81-195">各自動応答に営業時間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-195">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="a2a81-196">営業時間が設定されていない場合、既定では 24 時間 7 日のスケジュールが設定されている場合、その日のすべての日とすべての時間が営業時間と見なされます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-196">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="a2a81-197">営業時間は、日中の時間内の休憩を使用して設定できます。営業時間として設定されていないすべての時間は、営業時間外と見なされます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-197">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="a2a81-198">さまざまな着信通話処理オプションと応答メッセージを営業時間外に設定できます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-198">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="a2a81-199">自動応答と通話キューの構成によっては、直接の電話番号を含む自動応答の営業時間外の通話ルーティングのみを指定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2a81-199">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="a2a81-200">営業時間外の発信者に対して個別の通話ルーティングが必要な場合は、各日の営業時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-200">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="a2a81-201">[ **新しい時間の追加** ] をクリックして、昼休みなど、指定した日に複数の時間セットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-201">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![営業時間外の日と時刻の設定のスクリーンショット](../media/auto-attendant-business-hours.png)

<span data-ttu-id="a2a81-203">営業時間を指定したら、営業時間外の通話ルーティング オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-203">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="a2a81-204">手順 3 - コール フローで指定した営業時間内の通話ルーティングと同じ **オプションを使用できます**。</span><span class="sxs-lookup"><span data-stu-id="a2a81-204">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="a2a81-205">完了 **したら、[** 次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2a81-205">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a2a81-206">手順 5 - 休日のコール フロー ></span><span class="sxs-lookup"><span data-stu-id="a2a81-206">Step 5 - Holiday call flow ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="a2a81-207">手順 5 <br> 祝日</span><span class="sxs-lookup"><span data-stu-id="a2a81-207">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="a2a81-208">自動応答への通話は、他の日とは異なる方法で休日にルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-208">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="a2a81-209">(休日の別のコール フローを使用したくない場合は、この手順をスキップできます)。</span><span class="sxs-lookup"><span data-stu-id="a2a81-209">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>



<span data-ttu-id="a2a81-210">自動応答には、設定した休日ごとにコール フローを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-210">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="a2a81-211">各自動応答には、最大 20 個の決められた休業日を追加できます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-211">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="a2a81-212">[休日の通話の設定] ページで、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a2a81-212">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="a2a81-213">この休日設定の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-213">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="a2a81-214">[休日 **] ドロップダウン** から、使用する休日を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-214">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="a2a81-215">使用する応答メッセージの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-215">Choose the type of greeting that you want to use.</span></span>

    ![休日および休日のあいさつメッセージの設定のスクリーンショット](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="a2a81-217">通話を切断 **またはリダイレクト\*\*\*\*する場合に** 選択します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-217">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="a2a81-218">リダイレクトを選択した場合は、通話の通話ルーティング先を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-218">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![休日の通話アクション設定のスクリーンショット](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="a2a81-220">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2a81-220">Click **Save**.</span></span>

<span data-ttu-id="a2a81-221">追加の祝日ごとに、必要に応じて手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-221">Repeat the procedure as needed for each additional holiday.</span></span>

![祝日が一覧表示された祝日設定のスクリーンショット](../media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="a2a81-223">すべての休日を追加した後、[次へ] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="a2a81-223">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a2a81-224">手順 6 - ディレクトリ 内のユーザーを選択></span><span class="sxs-lookup"><span data-stu-id="a2a81-224">Step 6 - Choose who's in the directory ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="a2a81-225">手順 6 <br> ディレクトリ メンバー</span><span class="sxs-lookup"><span data-stu-id="a2a81-225">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="a2a81-226">ダイヤル *スコープは、* 発信者が名前でダイヤルバイネームまたはダイヤルバイ拡張機能を使用する場合にディレクトリ内で使用できるユーザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-226">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="a2a81-227">[すべてのオンライン ユーザー **] の既定値には** 、電話システム ライセンスを持つオンライン ユーザーである組織内のすべてのユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-227">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="a2a81-228">[含める] または [除外] で [カスタムユーザー グループ] を選択し、1 つ以上の Microsoft 365 グループ、配布リスト、またはセキュリティ グループを選択して、特定のユーザーを含めるか除外することができます。 </span><span class="sxs-lookup"><span data-stu-id="a2a81-228">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="a2a81-229">たとえば、組織内のエグゼクティブをダイヤル ディレクトリから除外することができます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-229">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="a2a81-230">(ユーザーが両方のリストにある場合は、ディレクトリから除外されます)。</span><span class="sxs-lookup"><span data-stu-id="a2a81-230">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![ダイヤル範囲の含めるオプションと除外オプションのスクリーンショット](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="a2a81-232">新しいユーザーの名前がディレクトリに一覧表示されるには、最大 36 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2a81-232">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="a2a81-233">ダイヤルスコープの設定が完了したら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a2a81-233">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a2a81-234">手順 7 - リソース アカウントを割り当></span><span class="sxs-lookup"><span data-stu-id="a2a81-234">Step 7 - Assign a resource account ></span></span>](/microsoftteams/business-voice/create-a-phone-system-auto-attendant-smb?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="a2a81-235">手順 7 <br> リソース アカウント</span><span class="sxs-lookup"><span data-stu-id="a2a81-235">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="a2a81-236">すべての自動応答には、リソース アカウントが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2a81-236">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="a2a81-237">第 1 レベルの自動応答には、サービス番号が関連付けられているリソース アカウントが少なくとも 1 つ必要です。</span><span class="sxs-lookup"><span data-stu-id="a2a81-237">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="a2a81-238">必要な場合は、複数のリソース アカウントを自動応答に割り当て、それぞれに個別のサービス番号を割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="a2a81-238">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="a2a81-239">リソース アカウントを追加するには</span><span class="sxs-lookup"><span data-stu-id="a2a81-239">To add a resource account</span></span>

1. <span data-ttu-id="a2a81-240">[ **アカウントの追加]** をクリックし、追加するアカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-240">Click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="a2a81-241">[追加 **] をクリック** し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a2a81-241">Click **Add**, and then click **Add**.</span></span>

    ![リソース アカウントの [アカウントの追加] パネルのスクリーンショット](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="a2a81-243">サービス アカウントの追加が完了したら、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a2a81-243">When you have finished adding service accounts, click **Submit**.</span></span>

    ![サービス番号が割り当てられているリソース アカウントを示すリソース アカウント リストのスクリーンショット](../media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="a2a81-245">これで自動応答の構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="a2a81-245">This completes the auto attendant configuration.</span></span>

---


