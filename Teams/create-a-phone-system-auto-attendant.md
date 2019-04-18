---
title: クラウドの自動応答を設定します
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 設定し、組織の処理効率の呼び出しに自動応答をクラウドをテストする方法について説明します。
ms.openlocfilehash: 8ab3dd318e8ae4c815a78dcc8f7430b2b6d08b04
ms.sourcegitcommit: 6949c957224949ccc6f5958d3c84294d382ee405
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "31914671"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="3718b-103">クラウドの自動応答を設定します</span><span class="sxs-lookup"><span data-stu-id="3718b-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="3718b-104">自動応答は、組織へのコールし、右の部門にそれらを取得するには、キュー、人、または演算子を呼び出すメニュー システムを移動するユーザーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="3718b-105">マイクロソフトのチーム管理センターを使用して、組織の自動応答を作成できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="3718b-106">**音声**には、左側のナビゲーションで、**自動応答**を選択し、新しい自動アテンダントを作成する > **新規追加**します。</span><span class="sxs-lookup"><span data-stu-id="3718b-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="3718b-107">自動応答の詳細についてはする場合を参照してください[雲の自動応答は何ですか?](/microsoftteams/what-are-phone-system-auto-attendants)</span><span class="sxs-lookup"><span data-stu-id="3718b-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="3718b-108">この資料は、オンライン ビジネスは、マイクロソフトのチームと Skype の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3718b-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>



## <a name="step-1---get-started"></a><span data-ttu-id="3718b-109">手順 1 - 開始します。</span><span class="sxs-lookup"><span data-stu-id="3718b-109">Step 1 - Get started</span></span>

- <span data-ttu-id="3718b-110">自動応答は、関連付けられているリソース アカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="3718b-111">リソース アカウントの詳細については、[チーム内のリソース アカウントの管理](manage-resource-accounts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3718b-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="3718b-112">取得し、リソース アカウントに次のライセンスを割り当てる必要があります直接ルーティング番号を割り当てる場合は、 \(Office 365 エンタープライズ E1、E3、E5、電話システムのアドオンを\)。</span><span class="sxs-lookup"><span data-stu-id="3718b-112">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="3718b-113">取得し、リソース アカウントに次のライセンスを割り当てる必要がある場合は代わりに、マイクロソフトのサービス番号を割り当てることは、 \(Office 365 エンタープライズ E1、E3、E5、電話システムのアドオンを呼び出す計画と\)。</span><span class="sxs-lookup"><span data-stu-id="3718b-113">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>

> [!NOTE] 
> <span data-ttu-id="3718b-114">マイクロソフトは、ユーザー数ライセンス モデルを使用する必要がありますのクラウドの自動応答、通話キューなどのアプリケーションの適切なライセンス ・ モデルの中です。</span><span class="sxs-lookup"><span data-stu-id="3718b-114">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!CAUTION]
> <span data-ttu-id="3718b-115">取得し、フリー ダイヤル電話番号を使用して、通信のクレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-115">To get and use toll-free phone numbers, you need to set up Communications Credits.</span></span> <span data-ttu-id="3718b-116">この参照を行うに[通信のクレジットは何ですか?](what-are-communications-credits.md)し、[組織の通信のクレジットを設定](set-up-communications-credits-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="3718b-116">To do this see [What are Communications Credits?](what-are-communications-credits.md) and [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>

> [!TIP]
> <span data-ttu-id="3718b-117">演算子または**電話システム**のライセンスを持つオンラインのユーザーは、メニュー ・ オプションへの呼び出しをリダイレクトするには、エンタープライズ VoIP を有効にするか、Office 365 のプランを呼び出すことを割り当てることにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-117">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice or assign Calling Plans in Office 365 to them.</span></span> <span data-ttu-id="3718b-118">[ビジネス ライセンスの割り当ての Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)または[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3718b-118">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="3718b-119">Windows PowerShell を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="3718b-119">You can also use Windows PowerShell.</span></span> <span data-ttu-id="3718b-120">などを実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="3718b-120">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2---create-a-new-auto-attendant"></a><span data-ttu-id="3718b-121">ステップ 2 - 新しい自動応答の作成</span><span class="sxs-lookup"><span data-stu-id="3718b-121">Step 2 - Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3718b-122">すべての自動応答は、関連付けられている[リソースのアカウント](manage-resource-accounts.md)を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-122">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="3718b-123">最初に、リソース アカウントを作成する必要がありますし、自動応答に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-123">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="3718b-124">マイクロソフトのチーム管理センターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="3718b-124">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="3718b-125">**マイクロソフトのチーム管理センター**の [**音声**] をクリックします > **自動応答**、 **+ 新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3718b-125">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="3718b-126">[全般情報] ページ</span><span class="sxs-lookup"><span data-stu-id="3718b-126">General info page</span></span>

![New auto attendant page 1.](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![ナンバー 1](media/sfbcallout1.png)

<span data-ttu-id="3718b-129">**名**自動アテンダントのわかりやすい表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="3718b-129">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="3718b-130">名前の入力は必須で、空白を含む最大 64 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-130">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="3718b-131">この名前は [ **自動応答**] タブの [ **名前**] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3718b-131">It will be listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![ナンバー 2](media/sfbcallout2.png)

<span data-ttu-id="3718b-133">**リソース アカウント**新しい自動応答に接続する 1 つまたは複数のリソース アカウントを選択するのには、このボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3718b-133">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="3718b-134">すべての自動応答は、関連付けられているリソース アカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-134">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="3718b-135">リソース アカウントは、アカウントに関連付けられている電話番号を持つことができますが、その可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-135">A resource account can have a phone number associated to the account, but it might not.</span></span> <span data-ttu-id="3718b-136">通常、トップレベルの自動応答は、割り当てられた電話番号にリソース アカウントを持っていますが、(最初のレベルの自動応答に接続するレベル 2 のメニューとして使用) の入れ子になった自動応答には、リソース アカウントに割り当てられている電話番号を持たない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-136">A top-level auto attendant usually have a resource account with an assigned phone number, but nested auto attendant (used as a level 2 menu that the first level auto attendant connects to) might not have a phone number assigned to its resource account.</span></span>

* * *

![ナンバー 3](media/sfbcallout3.png)

<span data-ttu-id="3718b-p108">**タイム ゾーン** 自動応答にはタイム ゾーンを設定する必要があります。ただし、組織のメイン アドレスのタイム ゾーンと一致している必要はありません。各自動応答には、異なるタイム ゾーンを設定できます。自動応答の営業時間の設定は、ここで選択したタイムゾーンに基づきます。</span><span class="sxs-lookup"><span data-stu-id="3718b-p108">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization. Each auto attendant can have a different time zone, and the business hours set for the auto attendant will be set based on the time zone that you select here.</span></span>

* * *

![ナンバー 4](media/sfbcallout4.png)

<span data-ttu-id="3718b-141">**言語** 自動応答に使用する言語を、一覧表示されている使用可能な言語の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="3718b-141">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="3718b-142">ここで設定した言語は、この自動の応答へのコールの人と対話する自動応答を使用し、この言語ですべてのシステム プロンプトが再生する言語です。</span><span class="sxs-lookup"><span data-stu-id="3718b-142">The language you set here is the language that the auto attendant will use to interact with people that call in to this auto attendant, and all the system prompts will be played in this language.</span></span>

* * *

![ナンバー 5](media/sfbcallout5.png)

<span data-ttu-id="3718b-144">**オペレーター** このオプションは省略可能で、自動応答で設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3718b-144">**Operator** This is optional and doesn't need to be set for the auto attendant.</span></span> <span data-ttu-id="3718b-145">ただし、電話することを支援してくれる人に話をするメニューを解除することをする人の**オペレーター**のオプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-145">However, you can set the **Operator** option for people that call in to be able to break out of the menus to speak to a person to help them.</span></span>

<span data-ttu-id="3718b-146">オペレーターには、キー 0 が自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="3718b-146">The key 0 is automatically assigned to Operator.</span></span>

<span data-ttu-id="3718b-147">このセットアップをした場合、発信者に、[**営業時間の通話ハンドリング**] ページの [**メニュー オプションの編集**] で利用可能なオプションであることを伝える必要もあります。</span><span class="sxs-lookup"><span data-stu-id="3718b-147">If you set this up, you will also need to tell people who call in that this is an available option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="3718b-148">自動応答でオペレーターを設定する場合は、 [**発信者が聞く内容**] ボックスに、対応するプロンプト テキストを入力するか、オーディオ ファイルを変更して、このオプションを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-148">If you set an operator on your auto attendant, you will need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="3718b-149">たとえば、「オペレーターに繋ぐには、0 を押してください。」などです。</span><span class="sxs-lookup"><span data-stu-id="3718b-149">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="3718b-150">次の項目のいずれかをオペレーターとして設定できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-150">You can set one of the following as Operator:</span></span>

- <span data-ttu-id="3718b-151">Enterprise Voice で有効にされているか、Office 365 の通話プランを割り当てられた**電話システム**を使用している**社内の担当者**。</span><span class="sxs-lookup"><span data-stu-id="3718b-151">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="3718b-152">**社内の担当者**は、Online のユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーとなることができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-152">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="3718b-153">**キューの呼び出し**を設定しました。</span><span class="sxs-lookup"><span data-stu-id="3718b-153">A **call queue** that you have set up.</span></span>
- <span data-ttu-id="3718b-154">発信者がボイスメールに送られるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-154">You can set it up so the person calling will be sent to voicemail.</span></span> <span data-ttu-id="3718b-155">これを行うには、**あなたの会社の担当者**を選択し、ボイスメールに直接転送するのにはこのメンバーの呼び出しを設定します。</span><span class="sxs-lookup"><span data-stu-id="3718b-155">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![ナンバー 6](media/sfbcallout6.png)

<span data-ttu-id="3718b-157">**音声入力を有効にします。** 音声認識機能では、このオプションが選択されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-157">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="3718b-158">人を呼び出すには、[設定した言語](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)で音声入力を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-158">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="3718b-159">のみ、電話のキーパッドを使用してユーザーを許可する場合にオフに設定し、音声認識機能を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="3718b-159">You can disable speech recognition by setting it to off if you want to only let people use their phone keypad.</span></span>

* * *

<span data-ttu-id="3718b-160">選択が終わったら [**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3718b-160">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="3718b-161">営業時間ページ</span><span class="sxs-lookup"><span data-stu-id="3718b-161">Business hours page</span></span>

<span data-ttu-id="3718b-162">既定では、営業時間は午後 5 時まで、月曜日から金曜日までの 9 am に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3718b-162">By default, business hours are set to 9am to 5pm, Monday through Friday.</span></span>  <span data-ttu-id="3718b-163">営業時間に含まれない時間は営業時間外として考慮されます。</span><span class="sxs-lookup"><span data-stu-id="3718b-163">All of the hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="3718b-164">**24/7 を選択**をするとすべての時間の業務時間をクリックすることができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-164">You can click on **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="3718b-165">**24/7 を選択する**オプションを選択した場合を除き、業務時間終了後、自動アテンダントの処理の呼び出しを構成するのには**時間の設定の呼び出し後**のページが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3718b-165">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling for after business hours for the auto attendant.</span></span>

![New auto attendant Hours of operation.](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![ナンバー 1](media/sfbcallout1.png)

<span data-ttu-id="3718b-168">既定では、営業時間は月曜日から金曜日、午前 9時 00分 ~ 午後 5時 00分に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3718b-168">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="3718b-169">スケジュール内のすべての時間時間の選択を解除するオプションを**オフにすべての時間**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3718b-169">Select **Clear all hours** option to unselect all hours hours in the schedule.</span></span> <span data-ttu-id="3718b-170">**既定値にリセット**を選択すると、営業時間は月曜日から金曜日、午前 9時 00分 ~ 午後 5時 00分にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="3718b-170">When you select **Reset to default**, business hours will be reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![ナンバー 2](media/sfbcallout2.png)

<span data-ttu-id="3718b-172">営業時間を変更するには、予定表を使用して設定したい営業時間を選択してください。</span><span class="sxs-lookup"><span data-stu-id="3718b-172">To change business hours, highlight the business hours you want to set using the calendar.</span></span> <span data-ttu-id="3718b-173">予定表を使用すると、30 分間隔で営業時間を選択できます。ここで選択する営業時間は、[**全般情報**] ページで設定したタイム ゾーンに基づいて設定されます。</span><span class="sxs-lookup"><span data-stu-id="3718b-173">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here will be set based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="3718b-174">休憩 (昼食休憩など) を設定するには、選択解除するか、カレンダーの時間を選択解除にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="3718b-174">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="3718b-175">営業時間内に複数の休憩時間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-175">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="3718b-176">選択が終わったら [**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3718b-176">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="3718b-177">営業時間の設定を呼び出す</span><span class="sxs-lookup"><span data-stu-id="3718b-177">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="3718b-178">カスタムの勤務時間のスケジュールを使用する場合**営業時間の設定の呼び出し**と同様のオプションを与える**時間の問い合わせ対応後**ページを使用して、業務時間終了後の処理の呼び出しを設定する必要がありますがもします。</span><span class="sxs-lookup"><span data-stu-id="3718b-178">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="3718b-179">その人が勤務時間中に、組織の自動応答の電話番号への呼び出しが聞こえますごきげんよう、プロンプト、およびメニューを設定できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-179">You can set up greetings, prompts, and menus that people who call in to your organization's auto attendant phone number will hear during the business hours.</span></span>

<span data-ttu-id="3718b-180">![営業時間は、処理を呼び出します。](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![営業時間内の呼び出しの処理を継続します。](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="3718b-180">![Business hours call handling.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Business hours call handling continued.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![ナンバー 1](media/sfbcallout1.png)

<span data-ttu-id="3718b-182">**あいさつ文の挿入**業務時間の案内応答は省略可能で**ない応答メッセージ**に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-182">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="3718b-183">この例では、呼び出し元が鳴らないメッセージまたは応答メッセージで選択したアクションのいずれかの呼び出しを処理する前に。</span><span class="sxs-lookup"><span data-stu-id="3718b-183">In this case, the caller will hear no message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="3718b-184">音声ファイル (.wav、mp3 または .wma 形式) をアップロードしたり、テキスト読み上げを使用してカスタムの応答メッセージを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3718b-184">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="3718b-185">**なしのあいさつ文**自動アテンダントの電話番号への人を呼び出すには、あいさつ文は再生されません。</span><span class="sxs-lookup"><span data-stu-id="3718b-185">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="3718b-186">**オーディオ ファイルをアップロード**これを選択する場合は、あいさつ文を記録し、オーディオ (.wav、.mp3 や .wma 形式) でファイルをアップロードしています。</span><span class="sxs-lookup"><span data-stu-id="3718b-186">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="3718b-187">**あいさつのメッセージの種類**このオプションを選択する場合は、(1000 文字以内) を読み取るシステムを設定するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="3718b-187">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="3718b-188">たとえば、「Contoso へようこそ。</span><span class="sxs-lookup"><span data-stu-id="3718b-188">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="3718b-189">お電話ありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="3718b-189">Your call is important to us."</span></span> <span data-ttu-id="3718b-190">などと、[**発信者が聞く内容**] ボックスに入力できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-190">in the **Callers will hear** box.</span></span>

* * *

![ナンバー 2](media/sfbcallout2.png)

<span data-ttu-id="3718b-192">営業時間中に着信する呼び出しに対する動作内容を選択できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-192">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="3718b-193">次のアクションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-193">You can chose from the following actions:</span></span>

- <span data-ttu-id="3718b-194">**切断** これを選択すると、発信者が営業時間の応答メッセージを聞いた後に切断されます。</span><span class="sxs-lookup"><span data-stu-id="3718b-194">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="3718b-195">**呼び出しをリダイレクト** 以下に対して呼び出しを自動的に送信するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-195">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="3718b-196">エンタープライズ VoIP を有効にするか Office 365 のプランを呼び出すことを割り当てられている**電話システム**のライセンスは、**会社の担当者**です。</span><span class="sxs-lookup"><span data-stu-id="3718b-196">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="3718b-197">発信中のユーザーがボイスメールに送信されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-197">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="3718b-198">これを行うには、**会社の担当者**を選択し、通話をボイスメールに直接転送されるには、このユーザーを設定します。</span><span class="sxs-lookup"><span data-stu-id="3718b-198">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="3718b-199">**会社の担当者**は、オンラインのユーザーまたはユーザーには、設置がホストされているビジネス サーバー 2015 または Lync Server 2013 の Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="3718b-199">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="3718b-200">別**の自動応答**</span><span class="sxs-lookup"><span data-stu-id="3718b-200">Another **Auto attendant**</span></span>

   <span data-ttu-id="3718b-201">既存の自動応答を使用すると、サブメニューを含むメニューのオプションの 2 番目のレベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3718b-201">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="3718b-202">これらは入れ子の自動応答と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3718b-202">These are called nested auto attendants.</span></span> <span data-ttu-id="3718b-203">入れ子になった自動応答に呼び出しを送信するには、**会社の担当者**を選択し、いずれかの関連付けられた自動応答またはしたら、自動応答と関連するすべてのものが既にある、リソース アカウントを割り当てるこの自動応答を作成します。</span><span class="sxs-lookup"><span data-stu-id="3718b-203">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="3718b-204">**再生] メニュー オプション**は、再生するプロンプトを設定することにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-204">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![ナンバー 3](media/sfbcallout3.png)

<span data-ttu-id="3718b-206">**メニュー プロンプト**メイン メニューのプロンプトを作成するには、音声合成を使用するか、オーディオ ファイル (.wav、.mp3 や .wma ファイル) をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="3718b-206">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="3718b-207">**呼び出し元に、メニューのナビゲーションの設定**] ボックスに、プロンプトを入力するか、記録、オーディオ ファイルと、たとえば:"販売と言いますか、または 1 を言います。</span><span class="sxs-lookup"><span data-stu-id="3718b-207">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="3718b-208">サービスは、キーを押してまたは 2 を言います。</span><span class="sxs-lookup"><span data-stu-id="3718b-208">For Services, press or say 2.</span></span> <span data-ttu-id="3718b-209">カスタマー サポートでは、キーを押してまたは 3 と答えるとします。</span><span class="sxs-lookup"><span data-stu-id="3718b-209">For Customer Support, press or say 3.</span></span> <span data-ttu-id="3718b-210">演算子を押すか、0 と答えてください。</span><span class="sxs-lookup"><span data-stu-id="3718b-210">For the operator, press or say 0.</span></span> <span data-ttu-id="3718b-211">このメニューをもう一度聞くには、アスタリスク キーを押しますの繰り返しを言う」</span><span class="sxs-lookup"><span data-stu-id="3718b-211">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="3718b-212">**あいさつのメッセージの種類**これを選択した場合 (1000 文字以内) を読み取るシステムを設定するテキストを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-212">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="3718b-213">**オーディオ ファイルをアップロード**これを選択した場合は、応答メッセージを記録し、オーディオ ファイル (.wav、mp3 または .wma 形式) をアップロードし、必要があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-213">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![ナンバー 4](media/sfbcallout4.png)

<span data-ttu-id="3718b-215">**メニューの [オプション]** キーパッドのキーのボタンを使用してメニュー オプションを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-215">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="3718b-216">メニュー オプションを追加するを押して**ダイヤル キーを割り当てます**。</span><span class="sxs-lookup"><span data-stu-id="3718b-216">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="3718b-217">下のオプションの対応する行が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3718b-217">A corresponding row of options will appear below.</span></span> <span data-ttu-id="3718b-218">メニュー オプションを削除するには、キーパッド制御に対応するキーの左側にクリックし、上の [削除] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3718b-218">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="3718b-219">キー マッピング行が削除されます。</span><span class="sxs-lookup"><span data-stu-id="3718b-219">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="3718b-220">メニュー プロンプトのテキストを更新または再録音とは別に既存のメニューのプロンプトを自動的に行われませんので、オプションを削除するのに追加する場合する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-220">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="3718b-221">メニュー オプションはどのような順番でも追加、削除でき、キー マッピングは連続的である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3718b-221">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="3718b-222">たとえば、キー 2 を使用せず、キー 0、1、3 をオプションにマッピングしてメニューを作成することが可能です。</span><span class="sxs-lookup"><span data-stu-id="3718b-222">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="3718b-223">キー \* (繰り返し) と\#(戻る)、システムによって予約されており、再割り当てすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3718b-223">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="3718b-224">音声認識が有効になっている場合、\* を押すと「繰り返し」、# を押すと「戻る」の音声コマンドに対応します。</span><span class="sxs-lookup"><span data-stu-id="3718b-224">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="3718b-225">ダイヤル キーを選択した後に、メニューのオプションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-225">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="3718b-226">オプションの**音声コマンド**を入力します。</span><span class="sxs-lookup"><span data-stu-id="3718b-226">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="3718b-227">最大 64 文字を入力でき、これと、「顧客サービス」または「操作土地とします」のように複数の単語を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-227">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="3718b-228">音声認識を有効にしている場合は、名前は自動的に認識されます。発信者は 3 を押すか、「さん」と音声入力するか、または 「顧客サービス」 と音声入力して、キー 3 にマッピングされたオプションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-228">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="3718b-229">呼び出しのかどうか、対応するキーが押された、またはオプションを選択する音声認識機能を使用して送信する先を選択します。</span><span class="sxs-lookup"><span data-stu-id="3718b-229">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="3718b-230">次の場所に呼び出しを送信できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-230">The call can be sent to:</span></span>

  - <span data-ttu-id="3718b-231">**オペレーター** オペレーターがすでにセットアップされている場合は、キー 0 に自動的にマッピングされますが、削除するか別のキーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="3718b-231">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="3718b-232">オペレーターがどのキーにも設定されていない場合は、音声コマンド 「オペレーター」 も無効になります。</span><span class="sxs-lookup"><span data-stu-id="3718b-232">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="3718b-233">Enterprise Voice で有効になっているか、Office 365 の通話プランを割り当てられている、**電話システム**のライセンスをもつ**社内の担当者**</span><span class="sxs-lookup"><span data-stu-id="3718b-233">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="3718b-234">発信中のユーザーがボイスメールに送信されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-234">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="3718b-235">これを行うには、**社内の担当者**を選択しの呼び出しは、ボイスメールに直接転送するには、このユーザーを設定します。</span><span class="sxs-lookup"><span data-stu-id="3718b-235">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="3718b-236">**社内の担当者**は、Online のユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーとなることができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-236">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> 
    - <span data-ttu-id="3718b-237">別**の自動応答**</span><span class="sxs-lookup"><span data-stu-id="3718b-237">Another **Auto attendant**</span></span>

       <span data-ttu-id="3718b-238">既存の自動応答を使用すると、サブメニューを含むメニューのオプションの 2 番目のレベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3718b-238">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="3718b-239">これらは入れ子の自動応答と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3718b-239">These are called nested auto attendants.</span></span> <span data-ttu-id="3718b-240">入れ子になった自動応答に呼び出しを送信するには、**会社の担当者**を選択し、いずれかの関連付けられた自動応答またはしたら、自動応答と関連するすべてのものが既にある、リソース アカウントを割り当てるこの自動応答を作成します。</span><span class="sxs-lookup"><span data-stu-id="3718b-240">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > <span data-ttu-id="3718b-241">入れ子 (または第 2 レベル) の自動応答の **営業時間** も使用されます。これには、セットアップされた他の自動応答から送信された呼び出しへ向けたものも含まれます。</span><span class="sxs-lookup"><span data-stu-id="3718b-241">The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.</span></span>

<!--    - **call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. -->

* * *

![ナンバー 5](media/sfbcallout5.png)

<span data-ttu-id="3718b-243">**名前によるダイヤル** このオプションを選択すると、発信者はディレクトリ検索を使用して組織内の人を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-243">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="3718b-244">[**ダイヤル スコープ**] ページでこれらのオプションをセットアップすることにより、名前によるダイヤルで誰が対応可能または対応不可として一覧表示されるのかを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-244">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="3718b-245">**電話システム** のライセンスをもつオンライン ユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされているユーザーであれば、名前によるダイヤルで探すことができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-245">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013, can be found with Dial by Name.</span></span>


* * *

<span data-ttu-id="3718b-246">選択が終わったら [**次へ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3718b-246">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="3718b-247">休日呼び出しの設定</span><span class="sxs-lookup"><span data-stu-id="3718b-247">Holiday call settings</span></span>

<span data-ttu-id="3718b-248">各自動応答には、最大 20 個の決められた休業日を追加できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-248">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="3718b-249">移動することができます、**組織全体の設定**時に画面 > の呼び出しハンドラーを新規作成の一部として、**祝日**を休日、またはを作成するを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-249">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![自動応答で休業日をセットアップする](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![ナンバー 1](media/sfbcallout1.png)

<span data-ttu-id="3718b-252">その他の自動応答を既に作成した場合は、オプションを使用するか、このリストに必要な情報を編集するを参照してください可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-252">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="3718b-253">それ以外の場合は、新しい呼び出しハンドラーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-253">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="3718b-254">新しい呼び出しハンドラーを追加するには、**ハンドラーを呼び出して新規 +** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3718b-254">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![自動アテンダントの続きで休日を設定](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![ナンバー 1](media/sfbcallout1.png)

<span data-ttu-id="3718b-257">新しいウィンドウで、画面の上部にある新しい呼び出しハンドラーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="3718b-257">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![ナンバー 2](media/sfbcallout2.png)

<span data-ttu-id="3718b-259">**休日**のプルダウン ・ リストで既に、休日の名前が存在する場合を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-259">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="3718b-260">休日の名前をする必要がありますが既に存在しない場合は、プルダウン ・ リストおよび割り当ての名前と新しい画面が表示されたら新しい休日の日付で**新しい祝日を作成する**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3718b-260">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="3718b-261">準備ができたら、**保存**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3718b-261">Click on **Save** when ready.</span></span>

<span data-ttu-id="3718b-262">休業日名は最大 64 文字で構成でき、同じ自動応答に対して一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-262">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="3718b-263">たとえば、同じ自動応答で 「感謝祭」という名前の休業日を 2 つもつことはできません。</span><span class="sxs-lookup"><span data-stu-id="3718b-263">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![ナンバー 3](media/sfbcallout3.png)

<span data-ttu-id="3718b-265">**あいさつ文の挿入**あいさつ文は省略可能で**ない応答メッセージ**に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-265">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="3718b-266">この場合、発信者には選択したオプションによって通話が処理されるまでメッセージまたは応答メッセージは再生されません。</span><span class="sxs-lookup"><span data-stu-id="3718b-266">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="3718b-267">音声ファイル (.wav、mp3 または .wma 形式) をアップロードしたり、テキスト読み上げを使用してカスタムの応答メッセージを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3718b-267">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="3718b-268">**なしのあいさつ文**自動アテンダントの電話番号への人を呼び出すには、あいさつ文は再生されません。</span><span class="sxs-lookup"><span data-stu-id="3718b-268">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="3718b-269">**オーディオ ファイルをアップロード**これを選択する場合は、時候のあいさつを記録し、オーディオ ファイル (.wav、.mp3 や .wma 形式) をアップロードし、</span><span class="sxs-lookup"><span data-stu-id="3718b-269">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="3718b-270">**あいさつのメッセージの種類**このオプションを選択する場合は、(1000 文字以内) を読み取るシステムを設定するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="3718b-270">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="3718b-271">たとえば、「あけましておめでとうございます。</span><span class="sxs-lookup"><span data-stu-id="3718b-271">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="3718b-272">当社は現在、休業中です。」</span><span class="sxs-lookup"><span data-stu-id="3718b-272">Our offices are currently closed."</span></span> <span data-ttu-id="3718b-273">**あいさつのメッセージの種類**] ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="3718b-273">in the **Type a greeting message** box.</span></span>

![ナンバー 4](media/sfbcallout4.png)

<span data-ttu-id="3718b-275">**アクション**このホリデー シーズン中に着信した呼び出しの動作を選択します。</span><span class="sxs-lookup"><span data-stu-id="3718b-275">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="3718b-276">次のオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-276">You can chose from the following options:</span></span>

- <span data-ttu-id="3718b-277">**切断** 休業日の応答メッセージが流れてから、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="3718b-277">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="3718b-278">**呼び出しをリダイレクト** 以下に対して呼び出しを自動的に送信するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-278">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="3718b-279">Enterprise Voice で有効にされているか、Office 365 の通話プランを割り当てられた**電話システム**を使用している**社内の担当者**。</span><span class="sxs-lookup"><span data-stu-id="3718b-279">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="3718b-280">発信中のユーザーがボイスメールに送信されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-280">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="3718b-281">これを行うには、**あなたの会社の人**を選択し、この人を通話をボイスメールに直接転送します。</span><span class="sxs-lookup"><span data-stu-id="3718b-281">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="3718b-282">**社内の担当者**は、Online のユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーとなることができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-282">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> 

  - <span data-ttu-id="3718b-283">**キューの呼び出し**を設定している既存の呼び出し待ち行列への呼び出しを転送します。</span><span class="sxs-lookup"><span data-stu-id="3718b-283">A **call queue** to transfer the call to an existing call queue that you have set up.</span></span>
  - <span data-ttu-id="3718b-284">別**の自動応答**、2 番目のレベルのサブメニューを含むメニュー オプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3718b-284">Another **Auto attendant**, to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="3718b-285">これらは入れ子の自動応答と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3718b-285">These are called nested auto attendants.</span></span>

    > [!Note]
    > <span data-ttu-id="3718b-286">既定では、休業期間中に着信したすべての呼び出しは、応答メッセージの後に切断されます。よって、違うビヘイビアーが望ましい場合には、リダイレクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-286">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

#### <a name="select-dial-scope-page"></a><span data-ttu-id="3718b-287">ダイヤルの範囲を選択ページ</span><span class="sxs-lookup"><span data-stu-id="3718b-287">Select dial scope page</span></span>

<span data-ttu-id="3718b-288">このページには、組織内のどのユーザーになりますディレクトリに一覧表示されているとダイヤルの利用可能な場合で組織を呼び出す人の名前でを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-288">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![Dial scope for searching with dial by name.](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="3718b-290">![1](media/sfbcallout1.png)を**含める**] オプションを使用すると、2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3718b-290">![Number 1](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="3718b-291">**すべての Online ユーザー** このオプションを使用すると、組織のすべてのユーザーがディレクトリ検索に含められます。</span><span class="sxs-lookup"><span data-stu-id="3718b-291">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="3718b-292">**電話システム** のライセンスをもつすべての Online ユーザーと、Office 365 の通話プランをもつ、Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="3718b-292">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server 2015 or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="3718b-293">**カスタム ユーザー グループ**このオプションを使用して、Office 365 のグループ、配布リスト、または組織内で作成されたセキュリティ グループを検索することができます、人がこの Office 365 のグループ、配布リスト、またはいずれかの**は、ユーザー セキュリティ グループにでオンラインのユーザーを追加する場合、電話システムのライセンス**またはオンプレミスでホストされているビジネス サーバー 2015 または Lync Server 2013 の Skype を使用しています。</span><span class="sxs-lookup"><span data-stu-id="3718b-293">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="3718b-294">複数の Office 365 グループ、配布リスト、セキュリティ グループを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-294">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![ナンバー 2](media/sfbcallout2.png)

<span data-ttu-id="3718b-296">**除外**オプションを使用すると、2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="3718b-296">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="3718b-297">**なし** このオプションを使用すると、いずれの Online ユーザーもディレクトリ検索から除外しません。</span><span class="sxs-lookup"><span data-stu-id="3718b-297">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="3718b-298">**カスタム ユーザー グループ**このオプションを使用する場合、Office 365 のグループ、配布リスト、または組織内で作成されたセキュリティ グループを検索することができますおよびすべてのユーザーが Office 365、そのグループに配布リストを追加またはセキュリティ グループは、ディレクトリ検索から除外されます。</span><span class="sxs-lookup"><span data-stu-id="3718b-298">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="3718b-299">複数の Office 365 グループ、配布リスト、セキュリティ グループを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="3718b-299">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="3718b-300">ディレクトリに一覧表示、ダイヤルを使用するときに名前で音声認識でその名前を持つ新しいユーザーには、最大で 36 時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3718b-300">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="3718b-301">すべての必須フィールドに入力して、メニューとオプションを処理する呼び出しを設定して後、は、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3718b-301">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="3718b-302">編集と自動応答をテストします。</span><span class="sxs-lookup"><span data-stu-id="3718b-302">Editing and testing auto attendants</span></span>

<span data-ttu-id="3718b-303">自動応答を保存すると、[ **自動応答**] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3718b-303">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="3718b-304">これによって、迅速にいくつかのオプションを設定するなどの名前、電話番号、言語、およびステータスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3718b-304">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="3718b-305">自動応答を変更する場合は、自動応答を選択し、操作ウィンドウの [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3718b-305">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="3718b-306">アクション ペインで、[**テスト**] ボタンを使用して、自動アテンダントをテストの呼び出しも簡単に配置できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-306">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="want-to-know-more"></a><span data-ttu-id="3718b-307">詳細情報</span><span class="sxs-lookup"><span data-stu-id="3718b-307">Want to know more?</span></span>

<span data-ttu-id="3718b-308">Windows PowerShell を使用して自動応答を作成し、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3718b-308">You can also use Windows PowerShell to create and set up auto attendants.</span></span>

### <a name="auto-attendant-cmdlets"></a><span data-ttu-id="3718b-309">自動応答のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="3718b-309">Auto attendant cmdlets</span></span>

<span data-ttu-id="3718b-310">自動応答で管理する必要があるコマンドレットを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="3718b-310">Here are the cmdlets that you need to manage an auto attendant.</span></span>

- [<span data-ttu-id="3718b-311">新しい-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="3718b-311">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="3718b-312">セット CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="3718b-312">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps) 
- [<span data-ttu-id="3718b-313">Get CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="3718b-313">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csattendant?view=skype-ps) 
- [<span data-ttu-id="3718b-314">Get CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="3718b-314">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps) 
- [<span data-ttu-id="3718b-315">削除 CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="3718b-315">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps) 
- [<span data-ttu-id="3718b-316">新しい-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="3718b-316">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps) 
- [<span data-ttu-id="3718b-317">新しい-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="3718b-317">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps) 
- [<span data-ttu-id="3718b-318">新しい-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="3718b-318">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps) 
- [<span data-ttu-id="3718b-319">エクスポート CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="3718b-319">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-Export-CsAutoAttendantHolidays?view=skype-ps) 
- [<span data-ttu-id="3718b-320">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="3718b-320">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-New-CsOnlineTimeRange?view=skype-ps) 
- [<span data-ttu-id="3718b-321">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="3718b-321">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) 
- [<span data-ttu-id="3718b-322">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="3718b-322">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps) 
- [<span data-ttu-id="3718b-323">Get CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="3718b-323">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="3718b-324">新しい-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="3718b-324">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="3718b-325">Get CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="3718b-325">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="3718b-326">インポート-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="3718b-326">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps) 
- [<span data-ttu-id="3718b-327">新しい-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="3718b-327">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps) 

### <a name="more-about-windows-powershell"></a><span data-ttu-id="3718b-328">Windows PowerShell の詳細について</span><span class="sxs-lookup"><span data-stu-id="3718b-328">More about Windows PowerShell</span></span>

- <span data-ttu-id="3718b-329">Windows PowerShell は、ユーザーを管理するユーザーを許可または許可されません。</span><span class="sxs-lookup"><span data-stu-id="3718b-329">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="3718b-330">Windows PowerShell では、Office 365 と一元管理を行う複数のタスクがある場合、日常的な作業を簡素化するを使用してマイクロソフトのチームを管理できます。</span><span class="sxs-lookup"><span data-stu-id="3718b-330">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="3718b-331">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3718b-331">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="3718b-332">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="3718b-332">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="3718b-333">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="3718b-333">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="3718b-p145">Windows PowerShell には、ただ Office 365 管理センターを使用するだけではなく、速度、単純さ、生産性において多くの利点があります。次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="3718b-p145">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="3718b-336">Office 365 の PowerShell では、Office 365 を管理します。</span><span class="sxs-lookup"><span data-stu-id="3718b-336">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="3718b-337">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="3718b-337">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="3718b-338">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3718b-338">Related topics</span></span>

[<span data-ttu-id="3718b-339">Office 365 での電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="3718b-339">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="3718b-340">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="3718b-340">Getting service phone numbers</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[<span data-ttu-id="3718b-341">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="3718b-341">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="3718b-342">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="3718b-342">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="3718b-343">自動応答をクラウドとは?</span><span class="sxs-lookup"><span data-stu-id="3718b-343">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="3718b-344">小規模ビジネスの例: 自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="3718b-344">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/skypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)  
