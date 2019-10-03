---
title: クラウドの自動応答をセットアップする
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Microsoft Teams のクラウド自動応答をセットアップしてテストする方法について説明します。
ms.openlocfilehash: 0cac6b1bb7d19e91e4042bcb0673f6c677e77d2e
ms.sourcegitcommit: 2d31209aae9e0171693389db97b0b5c974864673
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "37375711"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="288dc-103">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="288dc-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="288dc-104">自動応答は、組織にコールインしているユーザーに対して、適切な部署、通話キュー、人、またはオペレーターにアクセスするためのメニューシステムの操作を許可します。</span><span class="sxs-lookup"><span data-stu-id="288dc-104">Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator.</span></span> <span data-ttu-id="288dc-105">Microsoft Teams 管理センターを使用して、組織の自動応答を作成できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-105">You can create an auto attendant for your organization by using the Microsoft Teams admin center.</span></span> <span data-ttu-id="288dc-106">新しい自動応答を作成するには、左側のナビゲーションで [**音声**] に移動し、[**自動応答** > の**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="288dc-106">To create a new auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="288dc-107">自動応答の詳細については、「[クラウド自動応答とは何ですか?](/microsoftteams/what-are-phone-system-auto-attendants) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="288dc-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="288dc-108">この記事は、Microsoft Teams と Skype for Business Online の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="288dc-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="288dc-109">手順 1-はじめに</span><span class="sxs-lookup"><span data-stu-id="288dc-109">Step 1 — Get started</span></span>

- <span data-ttu-id="288dc-110">自動応答には、関連するリソースアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="288dc-110">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="288dc-111">必要なリソースアカウントとすべてのライセンスの詳細については、「 [Teams のリソースアカウントを管理](manage-resource-accounts.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="288dc-111">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span>

> [!TIP]
> <span data-ttu-id="288dc-112">**電話システム**のライセンスを持つオンラインユーザーであるオペレーターまたはメニューオプションへの通話をリダイレクトするには、エンタープライズ voip に対して通話を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="288dc-112">To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="288dc-113">「 [Skype For business ライセンスの割り当て](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)」または「 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="288dc-113">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="288dc-114">Windows PowerShell を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="288dc-114">You can also use Windows PowerShell.</span></span> <span data-ttu-id="288dc-115">たとえば、次を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="288dc-115">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2--create-a-new-auto-attendant"></a><span data-ttu-id="288dc-116">手順 2-新しい自動応答を作成する</span><span class="sxs-lookup"><span data-stu-id="288dc-116">Step 2 — Create a new auto attendant</span></span>

> [!IMPORTANT]
> <span data-ttu-id="288dc-117">各自動応答には、[リソースアカウント](manage-resource-accounts.md)が関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="288dc-117">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="288dc-118">最初にリソースアカウントを作成してから、自動応答に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-118">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="288dc-119">Microsoft Teams 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="288dc-119">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="288dc-120">**Microsoft Teams 管理センター**で、[**音声** > **自動応答**] をクリックし、[ **+ 新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="288dc-120">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ New**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="288dc-121">[一般的な情報] ページ</span><span class="sxs-lookup"><span data-stu-id="288dc-121">General info page</span></span>

![[自分の自動応答] ページのスクリーンショット](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="288dc-124">**名前**自動応答のわかりやすい表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="288dc-124">**Name** Enter a descriptive display name for your auto attendant.</span></span> <span data-ttu-id="288dc-125">名前の入力は必須で、空白を含む最大 64 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-125">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="288dc-126">[**自動応答**] タブの [**名前**] 列に表示されています。</span><span class="sxs-lookup"><span data-stu-id="288dc-126">It is listed in the **Name** column on the **Auto attendants** tab.</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

<span data-ttu-id="288dc-128"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="288dc-128"></span></span>

<span data-ttu-id="288dc-129">**リソースアカウント**このボタンをクリックして、新しい自動応答に接続する1つ以上のリソースアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="288dc-129">**Resource account** Click this button to select one or more resource accounts to connect to your new auto attendant.</span></span> <span data-ttu-id="288dc-130">すべての自動応答には、リソースアカウントが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="288dc-130">All auto attendants are required to have an associated resource account.</span></span> <span data-ttu-id="288dc-131">リソースアカウントには、アカウントに関連付けられた電話番号を割り当てることができますが、電話番号は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="288dc-131">A resource account can have a phone number associated to the account, but a phone number isn't a requirement.</span></span> <span data-ttu-id="288dc-132">通常、トップレベルの自動応答には、電話番号が割り当てられているリソースアカウントがありますが、入れ子になった自動応答 (第2レベルの自動応答の接続先として使用されるレベル2のメニュー) には、リソースアカウントに割り当てられている電話番号がない場合があります。</span><span class="sxs-lookup"><span data-stu-id="288dc-132">A top-level auto attendant usually has a resource account with an assigned phone number, but nested auto attendant (used as a level 2 menu that the first-level auto attendant connects to) might not have a phone number assigned to its resource account.</span></span>

* * *

<span data-ttu-id="288dc-133">![前のスクリーンショット](media/sfbcallout3.png)
 <a name="timezone"> </a>で吹き出しを参照している数値3のアイコン</span><span class="sxs-lookup"><span data-stu-id="288dc-133">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png)
<a name="timezone"> </a></span></span>

<span data-ttu-id="288dc-134">**タイムゾーン**自動応答のタイムゾーンを設定する必要がありますが、組織に対して一覧表示されているメインアドレスのタイムゾーンに対応する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="288dc-134">**Time zone** You must set the time zone for your auto attendant, but it doesn't need to correspond to the time zone of the main address listed for your organization.</span></span> <span data-ttu-id="288dc-135">各自動応答には別のタイムゾーンを設定することができ、自動応答に設定された営業時間は、ここで選択したタイムゾーンに基づいて設定されます。</span><span class="sxs-lookup"><span data-stu-id="288dc-135">Each auto attendant can have a different time zone, and the business hours set for the auto attendant are set based on the time zone that you select here.</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している数値4のアイコン](media/sfbcallout4.png)

<span data-ttu-id="288dc-137"><a name="language"> </a></span><span class="sxs-lookup"><span data-stu-id="288dc-137"></span></span>

<span data-ttu-id="288dc-138">**言語** 自動応答に使用する言語を、一覧表示されている使用可能な言語の中から選択します。</span><span class="sxs-lookup"><span data-stu-id="288dc-138">**Language** Select the language that you want to use for your auto attendant from any of the available languages listed.</span></span> <span data-ttu-id="288dc-139">ここで設定した言語は、自動応答がこの自動応答を呼び出したユーザーとやり取りするために使用する言語です。また、すべてのシステムプロンプトはこの言語で再生されます。</span><span class="sxs-lookup"><span data-stu-id="288dc-139">The language you set here is the language that the auto attendant uses to interact with people that call in to this auto attendant, and all the system prompts are played in this language.</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している数値5のアイコン](media/sfbcallout5.png)

<span data-ttu-id="288dc-141"><a name="operator"> </a></span><span class="sxs-lookup"><span data-stu-id="288dc-141"></span></span>

<span data-ttu-id="288dc-142">**Operator**これは省略可能ですが、**オペレーター**のオプションを設定して、発信者がメニューから抜けて相手に向かって話すことができるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-142">**Operator** This is optional, but you can set the **Operator** option to allow callers to break out of the menus and speak to a person.</span></span>

<span data-ttu-id="288dc-143">既定では、0キーがオペレーターに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="288dc-143">The 0 key is assigned to Operator by default.</span></span>

<span data-ttu-id="288dc-144">オペレーターを設定した場合は、[**勤務時間の通話処理**] ページの [**編集] メニューのオプション**で、そのオプションについての通話相手にも通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="288dc-144">If you set an Operator, you will also need to tell people who call about the option in the **Edit menu options** on the **Business hours call handling** page.</span></span> <span data-ttu-id="288dc-145">自動応答でオペレーターを設定した場合は、対応するメッセージテキストを [発信者に**聞こえる**] ボックスに入力するか、音声ファイルを変更してこのオプションを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="288dc-145">If you set an operator on your auto attendant, you need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="288dc-146">たとえば、「オペレーターに繋ぐには、0 を押してください。」などです。</span><span class="sxs-lookup"><span data-stu-id="288dc-146">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="288dc-147">オペレーターを設定するには、次のいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="288dc-147">You have several ways to set the Operator:</span></span>

- <span data-ttu-id="288dc-148">Enterprise Voice で有効にされているか、Office 365 の通話プランを割り当てられた**電話システム**を使用している**社内の担当者**。</span><span class="sxs-lookup"><span data-stu-id="288dc-148">**Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span>

     > [!Note]
     > <span data-ttu-id="288dc-149">**社内の担当者**は、Online のユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーとなることができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-149">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

- <span data-ttu-id="288dc-150">**音声アプリケーション**既に作成されている通話キューまたは自動応答に関連付けられているリソースアカウントの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="288dc-150">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>
- <span data-ttu-id="288dc-151">通話相手がボイスメールに送信されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-151">You can set it up so the person calling is sent to voicemail.</span></span> <span data-ttu-id="288dc-152">これを行うには、[**社内の人**] を選択して、このユーザの着信をボイスメールに直接転送するように設定します。</span><span class="sxs-lookup"><span data-stu-id="288dc-152">To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail.</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している番号6のアイコン](media/sfbcallout6.png)

<span data-ttu-id="288dc-154">**音声入力を有効にする**音声認識は、このオプションが選択されている場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-154">**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="288dc-155">発信者は、[設定した言語](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)で音声入力を使用できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-155">People that call in can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="288dc-156">他のユーザーに電話機のキーパッドのみを使用させる場合は、音声認識をオフに設定することができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-156">If you want to only let people use their phone keypad, you can disable speech recognition by setting it to off.</span></span>

* * *

<span data-ttu-id="288dc-157">選択が完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="288dc-157">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-page"></a><span data-ttu-id="288dc-158">営業時間ページ</span><span class="sxs-lookup"><span data-stu-id="288dc-158">Business hours page</span></span>

<span data-ttu-id="288dc-159">既定では、勤務時間は、月曜日から金曜日までの午前9:00 から 5:00 pm までに設定されています。</span><span class="sxs-lookup"><span data-stu-id="288dc-159">By default, business hours are set to 9:00 am to 5:00 pm, Monday through Friday.</span></span> <span data-ttu-id="288dc-160">営業時間に含まれていないすべての時間は、業務時間外に考慮されます。</span><span class="sxs-lookup"><span data-stu-id="288dc-160">All hours that aren't included in business hours are considered after business hours.</span></span> <span data-ttu-id="288dc-161">[24/7 の**選択**] をクリックして、すべての勤務時間を作成できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-161">You can click **Select 24/7** to make all hours business hours.</span></span> <span data-ttu-id="288dc-162">**[24/7 の選択**] オプションを選択しない限り、[**時間経過後の通話の設定**] ページが、自動応答の営業時間後の通話処理ルールの構成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="288dc-162">Unless you select the **Select 24/7** option, the **After hours call settings** page will be used to configure the call handling rules for after business hours for the auto attendant.</span></span>

![[勤務時間] ページのスクリーンショット](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="288dc-165">既定では、勤務時間は月曜日から金曜日の5:00 午前9:00 に設定されています。</span><span class="sxs-lookup"><span data-stu-id="288dc-165">By default, business hours are set to Monday to Friday, 9:00 am-5:00 pm.</span></span> <span data-ttu-id="288dc-166">スケジュールのすべての時間を選択解除するには、[**すべての時間をクリア**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="288dc-166">Select **Clear all hours** option to unselect all hours in the schedule.</span></span> <span data-ttu-id="288dc-167">[**既定に戻す**] を選択すると、勤務時間は月曜日から金曜日まで、9:00 am ~ 5:00 pm にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="288dc-167">When you select **Reset to default**, business hours are reset to Monday to Friday, 9:00 am-5:00 pm.</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

<span data-ttu-id="288dc-169">稼働時間を変更するには、予定表に設定する勤務時間を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="288dc-169">To change business hours, highlight the business hours you want to set in the calendar.</span></span> <span data-ttu-id="288dc-170">カレンダーでは、30分間隔で勤務時間を選択できます。ここで選択する業務時間は、[**一般情報**] ページで設定したタイムゾーンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="288dc-170">The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here are based on the time zone that you set on the **General info** page.</span></span> <span data-ttu-id="288dc-171">休憩 (昼食休憩など) を設定するには、選択解除するか、カレンダーの時間を選択解除にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="288dc-171">To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar.</span></span> <span data-ttu-id="288dc-172">営業時間内に複数の休憩時間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-172">You can set multiple breaks within business hours.</span></span>

* * *

<span data-ttu-id="288dc-173">選択が完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="288dc-173">When you are finished with your selections, click **Next**.</span></span>

#### <a name="business-hours-call-settings"></a><span data-ttu-id="288dc-174">営業時間通話の設定</span><span class="sxs-lookup"><span data-stu-id="288dc-174">Business hours call settings</span></span>

> [!TIP]
> <span data-ttu-id="288dc-175">独自の勤務時間スケジュールを使用している場合は、[営業時間外通話の設定] ページを使用して、業務時間の経過に応じて発信**処理**を設定する必要があります。これにより、**営業時間通話の設定**と同じオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="288dc-175">If you use a custom business hours schedule, you will also need to set up call handing for after business hours using the **After hours call handling** page, which will give you the same options as **Business hours call settings**.</span></span>

<span data-ttu-id="288dc-176">勤務時間中に組織の自動応答にリンクされた電話番号に通話を発信するときに、応答メッセージ、プロンプト、メニューを設定できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-176">You can set up greetings, prompts, and menus that people hear when they call to the phone number linked to your organization's auto attendant during business hours.</span></span>

<span data-ttu-id="288dc-177">![営業時間の通話処理ページのあいさつ文](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![のスクリーンショット (勤務時間の通話処理ページアクションセクションのスクリーンショット)](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span><span class="sxs-lookup"><span data-stu-id="288dc-177">![Screenshot of the Business hours call handling page Greeting section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Screenshot of the Business hours call handling page Actions section](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)</span></span>

* * *

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="288dc-179"><a name="greetingsandrouting"> </a></span><span class="sxs-lookup"><span data-stu-id="288dc-179"></span></span>

<span data-ttu-id="288dc-180">**あいさつ文**[勤務時間] 応答メッセージはオプションであり、**あいさつ文**に設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="288dc-180">**Greeting** A business hours greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="288dc-181">この場合、発信者は、選択したいずれかのアクションによって通話が処理される前に、メッセージまたは応答メッセージを読み上げません。</span><span class="sxs-lookup"><span data-stu-id="288dc-181">In this case, the caller won't hear a message or greeting before the call is handled by one of the actions you select.</span></span> <span data-ttu-id="288dc-182">音声ファイル (.wav、mp3 または .wma 形式) をアップロードしたり、テキスト読み上げを使用してカスタムの応答メッセージを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="288dc-182">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>
- <span data-ttu-id="288dc-183">**オーディオファイルをアップロードする**このオプションを選択した場合は、応答メッセージを録音して、音声ファイル (.wav、.mp3 または .wma 形式) をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="288dc-183">**Upload an audio file** If you choose this, record the greeting and then upload your audio file (in a .wav, .mp3 or .wma format).</span></span>
- <span data-ttu-id="288dc-184">**あいさつ文を入力する**このオプションを選択する場合は、システムで読み取るテキスト (最大1000文字) を入力します。</span><span class="sxs-lookup"><span data-stu-id="288dc-184">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="288dc-185">たとえば、「Contoso へようこそ。</span><span class="sxs-lookup"><span data-stu-id="288dc-185">For example, you might enter "Welcome to Contoso.</span></span> <span data-ttu-id="288dc-186">お電話ありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="288dc-186">Your call is important to us."</span></span> <span data-ttu-id="288dc-187">などと、[**発信者が聞く内容**] ボックスに入力できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-187">in the **Callers will hear** box.</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

<span data-ttu-id="288dc-189">営業時間中に着信する呼び出しに対する動作内容を選択できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-189">You can select what happens to calls that arrive during business hours.</span></span> <span data-ttu-id="288dc-190">次の操作から選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-190">You can chose from the following actions:</span></span>

<span data-ttu-id="288dc-191"><a name="redirectcalls"> </a></span><span class="sxs-lookup"><span data-stu-id="288dc-191"></span></span>

- <span data-ttu-id="288dc-192">**切断** これを選択すると、発信者が営業時間の応答メッセージを聞いた後に切断されます。</span><span class="sxs-lookup"><span data-stu-id="288dc-192">**Disconnect** If you select it, the person calling in will be disconnected after hearing a business hours greeting.</span></span>
- <span data-ttu-id="288dc-193">**呼び出しをリダイレクト** 以下に対して呼び出しを自動的に送信するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-193">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="288dc-194">Office 365 でエンタープライズボイスまたは割り当てられた通話プランに対応している**電話システム**のライセンスを持っている**会社のユーザー** 。</span><span class="sxs-lookup"><span data-stu-id="288dc-194">**Person in company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="288dc-195">発信中のユーザーがボイスメールに送信されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-195">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="288dc-196">これを行うには、「**会社内のユーザ**」を選択し、ボイスメールに直接通話を転送するように設定します。</span><span class="sxs-lookup"><span data-stu-id="288dc-196">To do this, select **Person in company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="288dc-197">**会社内の**ユーザーは、Skype For business Server 2015 または Lync server 2013 を使用してオンプレミスでホストされているユーザーまたはオンラインユーザーになることができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-197">**Person in company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="288dc-198">その他の**自動応答**</span><span class="sxs-lookup"><span data-stu-id="288dc-198">Another **Auto attendant**</span></span>

   <span data-ttu-id="288dc-199">既存の自動応答を使って、サブメニューを含む第2レベルのメニューオプションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-199">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="288dc-200">これらは入れ子の自動応答と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="288dc-200">These are called nested auto attendants.</span></span> <span data-ttu-id="288dc-201">ネストされた自動応答に通話を送信するには、[**会社内のユーザー** ] を選び、関連付けられた自動応答を既に持っているリソースアカウントか、この自動応答の作成が完了したら、自動応答に関連付ける1つのリソースアカウントを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="288dc-201">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

- <span data-ttu-id="288dc-202">**[再生] メニューのオプション**を使って、再生するプロンプトを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="288dc-202">**Play menu options** can also be used to let you set up a prompt you want played.</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している数値3のアイコン](media/sfbcallout3.png)

<span data-ttu-id="288dc-204">**メニュープロンプト**メインメニューのプロンプトを作成するには、音声合成を使用するか、音声ファイル (.wav、.mp3 または .wma) をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="288dc-204">**Menu prompt** To create main menu prompt, you can either use Text-to-Speech or upload an audio file (.wav, .mp3 or .wma).</span></span> <span data-ttu-id="288dc-205">「**発信者のメニューナビゲーションを設定**する」ボックスにメッセージを入力するか、音声ファイルを録音して、たとえば「売上のために」、「話す、または1と言って」と言います。</span><span class="sxs-lookup"><span data-stu-id="288dc-205">You can type the prompt in the **Set your menu navigation for callers** box or record an audio file and say, for example: "For Sales, say or press or say 1.</span></span> <span data-ttu-id="288dc-206">サービスの場合は、2を押すか、2と発声します。</span><span class="sxs-lookup"><span data-stu-id="288dc-206">For Services, press or say 2.</span></span> <span data-ttu-id="288dc-207">カスタマサポートについては、「3」または「3」と発声します。</span><span class="sxs-lookup"><span data-stu-id="288dc-207">For Customer Support, press or say 3.</span></span> <span data-ttu-id="288dc-208">演算子の場合は、0を押すか、0と発声します。</span><span class="sxs-lookup"><span data-stu-id="288dc-208">For the operator, press or say 0.</span></span> <span data-ttu-id="288dc-209">このメニューをもう一度読み上げるには、星のキーを押すか、「繰り返す」と発声します。</span><span class="sxs-lookup"><span data-stu-id="288dc-209">To hear this menu again, press the star key or say repeat."</span></span> <span data-ttu-id="288dc-210">**あいさつ文を入力する**この設定を選択した場合は、システムが読み上げるテキスト (最大1000文字) を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="288dc-210">**Type a greeting message** If you chose this, you should enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="288dc-211">**オーディオファイルをアップロードする**この設定を選択した場合は、応答メッセージを録音して、音声ファイル (.wav、mp3 または .wma 形式) をアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="288dc-211">**Upload an audio file** If you chose this, you will need to record the greeting and then upload your audio file (in a .wav, mp3 or .wma format).</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している数値4のアイコン](media/sfbcallout4.png)

<span data-ttu-id="288dc-213">**メニューオプションのセットアップ**キーボタンを使用したメニューオプションは、追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-213">**Menu options setup** Menu options using key buttons on the keypad can be added or removed.</span></span> <span data-ttu-id="288dc-214">メニューオプションを追加するには、 **+ enter キーを**押します。</span><span class="sxs-lookup"><span data-stu-id="288dc-214">To add a menu option, press **+ Assign a dial key**.</span></span> <span data-ttu-id="288dc-215">対応するオプションの行が下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="288dc-215">A corresponding row of options will appear below.</span></span> <span data-ttu-id="288dc-216">メニューオプションを削除するには、キーパッドコントロールで対応するキーの左側をクリックして、上の [削除] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="288dc-216">To delete a menu option, simply click to the left of the corresponding key on the keypad control and click on the delete icon above.</span></span> <span data-ttu-id="288dc-217">キー マッピング行が削除されます。</span><span class="sxs-lookup"><span data-stu-id="288dc-217">The key mapping row will be removed.</span></span>

> [!TIP]
> <span data-ttu-id="288dc-218">削除オプションを追加するときに、既存のメニュープロンプトに対して自動的に実行されないため、メニュープロンプトテキストを更新するか、オーディオを個別に再録音する必要があります。</span><span class="sxs-lookup"><span data-stu-id="288dc-218">You will have to update menu prompts text or re-record the audio separately when adding to removing options because it won't be automatically done for the existing menu prompt.</span></span>  
>
><span data-ttu-id="288dc-219">メニュー オプションはどのような順番でも追加、削除でき、キー マッピングは連続的である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="288dc-219">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="288dc-220">たとえば、キー 2 を使用せず、キー 0、1、3 をオプションにマッピングしてメニューを作成することが可能です。</span><span class="sxs-lookup"><span data-stu-id="288dc-220">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="288dc-221">キー \* (繰り返し) と\# (戻る) は、システムによって予約されているため、再割り当てすることはできません。</span><span class="sxs-lookup"><span data-stu-id="288dc-221">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="288dc-222">音声認識が有効になっている場合、\* を押すと「繰り返し」、# を押すと「戻る」の音声コマンドに対応します。</span><span class="sxs-lookup"><span data-stu-id="288dc-222">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="288dc-223">メニューオプションを設定するには、ダイヤルキーを選択した後、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="288dc-223">To set up your menu options, after you select the dial key(s), you will need to:</span></span>

- <span data-ttu-id="288dc-224">オプションの**音声コマンド**を入力します。</span><span class="sxs-lookup"><span data-stu-id="288dc-224">Enter the **Voice command**  of the option.</span></span> <span data-ttu-id="288dc-225">これは最大64文字で、"カスタマサービス" や "運営および根拠" などの複数の単語を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-225">This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="288dc-226">音声認識を有効にしている場合は、名前は自動的に認識されます。発信者は 3 を押すか、「さん」と音声入力するか、または 「顧客サービス」 と音声入力して、キー 3 にマッピングされたオプションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-226">If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span>
- <span data-ttu-id="288dc-227">対応するキーが押された場合に、通話を送信する場所を選択するか、音声認識を使ってオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="288dc-227">Select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="288dc-228">次の場所に呼び出しを送信できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-228">The call can be sent to:</span></span>

  - <span data-ttu-id="288dc-229">**オペレーター** オペレーターがすでにセットアップされている場合は、キー 0 に自動的にマッピングされますが、削除するか別のキーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="288dc-229">**Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="288dc-230">オペレーターがどのキーにも設定されていない場合は、音声コマンド 「オペレーター」 も無効になります。</span><span class="sxs-lookup"><span data-stu-id="288dc-230">If operator isn't set to any key, then the voice command "Operator" will be disabled too.</span></span>
  - <span data-ttu-id="288dc-231">Enterprise Voice で有効になっているか、Office 365 の通話プランを割り当てられている、**電話システム**のライセンスをもつ**社内の担当者**</span><span class="sxs-lookup"><span data-stu-id="288dc-231">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365.</span></span> <span data-ttu-id="288dc-232">発信中のユーザーがボイスメールに送信されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-232">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="288dc-233">そのためには、「**会社内のユーザ**」を選択し、ボイスメールに直接通話を転送するように設定します。</span><span class="sxs-lookup"><span data-stu-id="288dc-233">To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="288dc-234">**会社内の**ユーザーは、Skype For business Server または Lync server 2013 を使用してオンプレミスでホストされているユーザーまたはオンラインユーザーになることができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-234">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server or Lync Server 2013.</span></span>

  - <span data-ttu-id="288dc-235">その他の**自動応答**</span><span class="sxs-lookup"><span data-stu-id="288dc-235">Another **Auto attendant**</span></span>

       <span data-ttu-id="288dc-236">既存の自動応答を使って、サブメニューを含む第2レベルのメニューオプションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-236">You can use an existing auto attendant to create a second level of menu options containing a sub-menu.</span></span> <span data-ttu-id="288dc-237">これらは入れ子の自動応答と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="288dc-237">These are called nested auto attendants.</span></span> <span data-ttu-id="288dc-238">ネストされた自動応答に通話を送信するには、[**会社内のユーザー** ] を選び、関連付けられた自動応答を既に持っているリソースアカウントか、この自動応答の作成が完了したら、自動応答に関連付ける1つのリソースアカウントを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="288dc-238">To send the call to a nested auto attendant, select **Person in company** and assign a resource account, either one that already has an associated auto attendant or one that you will associate to an auto attendant once you are done creating this auto attendant.</span></span>

        > [!Note]
        > The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.

    - <span data-ttu-id="288dc-239">**音声アプリケーション**既に作成されている通話キューまたは自動応答に関連付けられているリソースアカウントの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="288dc-239">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している数値5のアイコン](media/sfbcallout5.png)

<span data-ttu-id="288dc-241">**名前によるダイヤル** このオプションを選択すると、発信者はディレクトリ検索を使用して組織内の人を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-241">**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search.</span></span> <span data-ttu-id="288dc-242">[**ダイヤル スコープ**] ページでこれらのオプションをセットアップすることにより、名前によるダイヤルで誰が対応可能または対応不可として一覧表示されるのかを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-242">You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page.</span></span> <span data-ttu-id="288dc-243">**電話システム**のライセンスを持つオンラインユーザー、または Skype For business Server または Lync server 2013 を使用してオンプレミスでホストされているすべてのユーザーは、名前でダイヤルすることができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-243">Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server or Lync Server 2013, can be found with Dial by Name.</span></span>

* * *

<span data-ttu-id="288dc-244">選択が完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="288dc-244">When you are finished with your selections, click on **Next**.</span></span>

#### <a name="holiday-call-settings"></a><span data-ttu-id="288dc-245">ホリデーシーズン通話の設定</span><span class="sxs-lookup"><span data-stu-id="288dc-245">Holiday call settings</span></span>

<span data-ttu-id="288dc-246"><a name="holidaygreetings"> </a></span><span class="sxs-lookup"><span data-stu-id="288dc-246"></span></span>

<span data-ttu-id="288dc-247">各自動応答には、最大 20 個の決められた休業日を追加できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-247">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

> [!TIP]
> <span data-ttu-id="288dc-248">**組織全体の設定** > の**休日**の画面に休日を作成したり、新しい通話ハンドラーの作成の一部として作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-248">You can go the the screen at **Org-wide settings** > **Holidays** to create Holidays, or you can create them as part of creating a new call handler.</span></span>

![[ホリデー通話の設定] ページのスクリーンショット](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="288dc-251">既に他の自動応答を作成している場合は、この一覧に表示されているオプションを使用したり、編集したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-251">If you've already created other auto attendants, you might see an option you can use or edit into what you need on this list.</span></span> <span data-ttu-id="288dc-252">それ以外の場合は、新しい呼び出しハンドラーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="288dc-252">If not, you'll need to create a new call handler.</span></span>

<span data-ttu-id="288dc-253">新しい通話ハンドラーを追加するには、[ **+ new call handler**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="288dc-253">To add a new call handler, click on **+ New call handler**.</span></span>

* * *

![新しい通話ハンドラーの追加を示すスクリーンショット](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="288dc-256">新しいウィンドウで、画面の上部に新しい通話ハンドラーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="288dc-256">In the new window, enter a name for your new Call  handler at the top of the screen.</span></span>

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

<span data-ttu-id="288dc-258">休日の名前が、**休日**のプルダウンリストに既に存在している場合は、それを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-258">If the name of your holiday already exists in the **Holiday** pull-down list, you can use it.</span></span> <span data-ttu-id="288dc-259">必要な祝日の名前がまだ存在しない場合は、プルダウンリストで [新しい祝日の**作成**] を選択し、表示された新しい画面に新しい祝日の名前と日付を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="288dc-259">If the holiday name you need does not already exist, select **Create new holiday** in the pull-down list and assign a name and a date for the new holiday in the new screen that appears.</span></span> <span data-ttu-id="288dc-260">準備ができたら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="288dc-260">Click on **Save** when ready.</span></span>

<span data-ttu-id="288dc-261">休業日名は最大 64 文字で構成でき、同じ自動応答に対して一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="288dc-261">Holiday names may consist of up to 64 characters and must be unique for the same auto attendant.</span></span> <span data-ttu-id="288dc-262">たとえば、同じ自動応答で 「感謝祭」という名前の休業日を 2 つもつことはできません。</span><span class="sxs-lookup"><span data-stu-id="288dc-262">For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.</span></span>

![前のスクリーンショットで吹き出しを参照している数値3のアイコン](media/sfbcallout3.png)

<span data-ttu-id="288dc-264">**あいさつ文**応答メッセージは省略可能で**あり、あいさつ文**に設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="288dc-264">**Greeting** The greeting is optional and can be set to **No greeting**.</span></span> <span data-ttu-id="288dc-265">この場合、発信者には選択したオプションによって通話が処理されるまでメッセージまたは応答メッセージは再生されません。</span><span class="sxs-lookup"><span data-stu-id="288dc-265">In this case, the caller will hear no message or greeting before the call is handled by one of the options you select.</span></span> <span data-ttu-id="288dc-266">音声ファイル (.wav、mp3 または .wma 形式) をアップロードしたり、テキスト読み上げを使用してカスタムの応答メッセージを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="288dc-266">You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.</span></span>

- <span data-ttu-id="288dc-267">**応答なし**自動応答の電話番号に通話を発信しても、応答メッセージは再生されません。</span><span class="sxs-lookup"><span data-stu-id="288dc-267">**No greeting** No greeting will be played when people call in to the auto attendant phone number.</span></span>
- <span data-ttu-id="288dc-268">**オーディオファイルをアップロードする**このオプションを選択した場合は、休日の応答メッセージを録音して、音声ファイル (.wav、.mp3 または .wma 形式) をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="288dc-268">**Upload an audio file** If you choose this, record the holiday greeting and then upload your audio file (in a .wav, .mp3 or .wma format)</span></span>
- <span data-ttu-id="288dc-269">**あいさつ文を入力する**このオプションを選択する場合は、システムで読み取るテキスト (最大1000文字) を入力します。</span><span class="sxs-lookup"><span data-stu-id="288dc-269">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters).</span></span> <span data-ttu-id="288dc-270">たとえば、「あけましておめでとうございます。</span><span class="sxs-lookup"><span data-stu-id="288dc-270">For example, you might enter "Happy New Year!</span></span> <span data-ttu-id="288dc-271">当社は現在、休業中です。」</span><span class="sxs-lookup"><span data-stu-id="288dc-271">Our offices are currently closed."</span></span> <span data-ttu-id="288dc-272">[**あいさつ文を入力**してください] ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="288dc-272">in the **Type a greeting message** box.</span></span>

![前のスクリーンショットで吹き出しを参照している数値4のアイコン](media/sfbcallout4.png)

<span data-ttu-id="288dc-274">**操作**この休日の間に到着した通話はどうなるかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-274">**Actions** You can select what happens to the calls that arrive during this holiday.</span></span> <span data-ttu-id="288dc-275">次のオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-275">You can chose from the following options:</span></span>

- <span data-ttu-id="288dc-276">**切断** 休業日の応答メッセージが流れてから、通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="288dc-276">**Disconnect** The person calling in will be disconnected after hearing the holiday greeting.</span></span>
- <span data-ttu-id="288dc-277">**呼び出しをリダイレクト** 以下に対して呼び出しを自動的に送信するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-277">**Redirect call** This can be used to automatically send the call to:</span></span>
  - <span data-ttu-id="288dc-278">Enterprise Voice で有効にされているか、Office 365 の通話プランを割り当てられた**電話システム**を使用している**社内の担当者**。</span><span class="sxs-lookup"><span data-stu-id="288dc-278">A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365.</span></span> <span data-ttu-id="288dc-279">発信中のユーザーがボイスメールに送信されるように設定できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-279">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="288dc-280">そのためには、「**会社内のユーザ**」を選択し、ボイスメールに直接通話を転送するように設定します。</span><span class="sxs-lookup"><span data-stu-id="288dc-280">To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="288dc-281">**社内の担当者**は、Online のユーザーか、 Skype for Business Server 2015 または Lync Server 2013 を使用してオンプレミスでホストされたユーザーとなることができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-281">**Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span>

   - <span data-ttu-id="288dc-282">**音声アプリケーション**既に作成されている通話キューまたは自動応答に関連付けられているリソースアカウントの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="288dc-282">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

    > [!Note]
    > <span data-ttu-id="288dc-283">既定では、休業期間中に着信したすべての呼び出しは、応答メッセージの後に切断されます。よって、違うビヘイビアーが望ましい場合には、リダイレクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="288dc-283">By default, all calls arriving during a holiday period are set to disconnect after the greeting (if any), so you must specify a redirect if a different behavior is desired.</span></span>

<a name="dialscope"></a>
#### <a name="select-dial-scope-page"></a><span data-ttu-id="288dc-284">ダイヤルの範囲を選択ページ</span><span class="sxs-lookup"><span data-stu-id="288dc-284">Select dial scope page</span></span>

<span data-ttu-id="288dc-285">このページでは、組織内のユーザーが自分の組織に電話をかけているユーザーに対して、自分のディレクトリに一覧表示され、名前でダイヤルできるように設定することができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-285">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

![[ダイヤルの範囲] ページを示すスクリーンショット](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

<span data-ttu-id="288dc-287">![数値1のアイコン。 [**含める**] オプションを使って、](media/sfbcallout1.png)前のスクリーンショットの吹き出しを参照するには、次の2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="288dc-287">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png) Using the **Include** option, you have two options:</span></span>

- <span data-ttu-id="288dc-288">**すべての Online ユーザー** このオプションを使用すると、組織のすべてのユーザーがディレクトリ検索に含められます。</span><span class="sxs-lookup"><span data-stu-id="288dc-288">**All Online users** Using this option allows all of the people in your organization to be included in directory search.</span></span> <span data-ttu-id="288dc-289">**電話システム**のライセンスを持っているすべてのオンラインユーザーと、Skype For business Server または Lync server 2013 を使用してオンプレミスでホストされ、Office 365 の通話プランを持っているユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="288dc-289">All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server or Lync Server 2013 who have Calling Plans in Office 365, will be listed.</span></span>
- <span data-ttu-id="288dc-290">**カスタムユーザーグループ**このオプションを使うと、組織内で作成された Office 365 グループ、配布リスト、またはセキュリティグループを検索できます。また、この Office 365 グループ、配布リスト、またはセキュリティグループに追加されたユーザーは **、** Skype For Business Server 2015 または Lync server 2013 を使用して、電話システムライセンスまたはオンプレミスでホストされている。</span><span class="sxs-lookup"><span data-stu-id="288dc-290">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013.</span></span> <span data-ttu-id="288dc-291">複数の Office 365 グループ、配布リスト、セキュリティ グループを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-291">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

* * *

![前のスクリーンショットで吹き出しを参照している数値2のアイコン](media/sfbcallout2.png)

<span data-ttu-id="288dc-293">[**除外**] オプションを使用する場合、次の2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="288dc-293">Using the **Exclude** option, you have two options:</span></span>

- <span data-ttu-id="288dc-294">**なし** このオプションを使用すると、いずれの Online ユーザーもディレクトリ検索から除外しません。</span><span class="sxs-lookup"><span data-stu-id="288dc-294">**None** Using this option will indicate that no Online users will be excluded from directory search.</span></span>
- <span data-ttu-id="288dc-295">**カスタムユーザーグループ**このオプションを使用すると、Office 365 グループ、配布リスト、または組織内で作成されたセキュリティグループを検索できます。この Office 365 グループ、配布リスト、セキュリティグループに追加されたすべてのユーザーは、ディレクトリ検索から除外されます。</span><span class="sxs-lookup"><span data-stu-id="288dc-295">**Custom user group** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search.</span></span> <span data-ttu-id="288dc-296">複数の Office 365 グループ、配布リスト、セキュリティ グループを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-296">You can add multiple Office 365 Groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="288dc-297">他のユーザーが音声認識で名前でダイヤルを使用している場合、新しいユーザーの名前がディレクトリに表示されるまでに最大36時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="288dc-297">It might take up to 36 hours for a new user to have their name listed in the directory when someone uses Dial by Name with speech recognition.</span></span>

<span data-ttu-id="288dc-298">すべての必要なフィールドを入力し、通話処理のメニューとオプションを設定したら、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="288dc-298">After you enter all the required fields and set up call handling menus and options, click **Submit**.</span></span>

## <a name="editing-and-testing-auto-attendants"></a><span data-ttu-id="288dc-299">自動応答の編集とテスト</span><span class="sxs-lookup"><span data-stu-id="288dc-299">Editing and testing auto attendants</span></span>

<span data-ttu-id="288dc-300">自動応答を保存すると、[ **自動応答**] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="288dc-300">After you have saved your auto attendant, it will be listed on the **Auto attendants** page.</span></span> <span data-ttu-id="288dc-301">これにより、設定したオプションの一部 (名前、電話番号、言語、状態など) をすばやく確認できます。</span><span class="sxs-lookup"><span data-stu-id="288dc-301">This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.</span></span>

<span data-ttu-id="288dc-302">自動応答に変更を加える場合は、[自動応答] を選択し、[操作] ウィンドウで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="288dc-302">If you want to make changes to an auto attendant, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<span data-ttu-id="288dc-303">操作ウィンドウの [**テスト**] ボタンを使用して、自動応答にテスト通話をすばやく配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="288dc-303">You can also quickly place a test call to your auto attendant by using the **Test** button in the Action pane.</span></span>

## <a name="auto-attendant-cmdlets"></a><span data-ttu-id="288dc-304">自動応答のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="288dc-304">Auto attendant cmdlets</span></span>

<span data-ttu-id="288dc-305">Windows PowerShell を使用して自動応答を作成し、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="288dc-305">You can also use Windows PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="288dc-306">自動応答を管理するために必要なコマンドレットを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="288dc-306">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="288dc-307">新しい-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="288dc-307">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="288dc-308">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="288dc-308">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="288dc-309">CsAutoAttendant の入手</span><span class="sxs-lookup"><span data-stu-id="288dc-309">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [<span data-ttu-id="288dc-310">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="288dc-310">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="288dc-311">CsAutoAttendant の削除</span><span class="sxs-lookup"><span data-stu-id="288dc-311">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="288dc-312">新規-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="288dc-312">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="288dc-313">新しい-Csonline Audiofile</span><span class="sxs-lookup"><span data-stu-id="288dc-313">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="288dc-314">新規-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="288dc-314">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="288dc-315">エクスポート-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="288dc-315">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="288dc-316">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="288dc-316">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="288dc-317">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="288dc-317">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="288dc-318">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="288dc-318">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="288dc-319">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="288dc-319">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="288dc-320">新規-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="288dc-320">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="288dc-321">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="288dc-321">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="288dc-322">インポート-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="288dc-322">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="288dc-323">新規-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="288dc-323">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="288dc-324">Windows PowerShell の詳細について</span><span class="sxs-lookup"><span data-stu-id="288dc-324">More about Windows PowerShell</span></span>

- <span data-ttu-id="288dc-325">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="288dc-325">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="288dc-326">Windows PowerShell を使用すると、複数のタスクがある場合に、1つの管理ポイントを使用して Office 365 および Microsoft Teams を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-326">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="288dc-327">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="288dc-327">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="288dc-328">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="288dc-328">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="288dc-329">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="288dc-329">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="288dc-330">Windows PowerShell には、多くのユーザーについて同時に設定を変更する場合など、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="288dc-330">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="288dc-331">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="288dc-331">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="288dc-332">Office 365 PowerShell で Office 365 を管理する</span><span class="sxs-lookup"><span data-stu-id="288dc-332">Manage Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="288dc-333">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="288dc-333">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="288dc-334">関連トピック</span><span class="sxs-lookup"><span data-stu-id="288dc-334">Related topics</span></span>

[<span data-ttu-id="288dc-335">Office 365 の電話システムでできること</span><span class="sxs-lookup"><span data-stu-id="288dc-335">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="288dc-336">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="288dc-336">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="288dc-337">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="288dc-337">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="288dc-338">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="288dc-338">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="288dc-339">クラウドの自動応答とは？</span><span class="sxs-lookup"><span data-stu-id="288dc-339">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="288dc-340">小規模ビジネスの例: 自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="288dc-340">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  
