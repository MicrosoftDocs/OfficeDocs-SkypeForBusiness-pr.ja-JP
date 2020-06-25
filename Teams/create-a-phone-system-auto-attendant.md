---
title: クラウドの自動応答をセットアップする
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Microsoft Teams のクラウド自動応答をセットアップしてテストする方法について説明します。
ms.openlocfilehash: 0cdba07297e22b116bbfe120f4d1e5640ee9a892
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "44874248"
---
# <a name="set-up-a-cloud-auto-attendant"></a><span data-ttu-id="aea0c-103">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="aea0c-103">Set up a Cloud auto attendant</span></span>

<span data-ttu-id="aea0c-104">自動応答を使うと、ユーザーが組織を呼び出したり、メニューシステムを移動して、適切な部門、通話キュー、人、またはオペレーターと話すことができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="aea0c-105">Microsoft Teams 管理センターまたは Powershell を使用して、組織の自動応答を作成できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with Powershell.</span></span> <span data-ttu-id="aea0c-106">自動応答を作成するには、左側のナビゲーションで [**音声**] に移動し、[**自動応答**の追加] を選択し  >  **Add new**ます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-106">To create an auto attendant, go to **Voice** in the left navigation, and then select **Auto attendants** > **Add new**.</span></span>

<span data-ttu-id="aea0c-107">自動応答の詳細については、「[クラウド自動応答とは何ですか?](/microsoftteams/what-are-phone-system-auto-attendants) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aea0c-107">If you want to learn more about auto attendants, see [What are Cloud auto attendants?](/microsoftteams/what-are-phone-system-auto-attendants)</span></span>

> [!NOTE]
> <span data-ttu-id="aea0c-108">この記事は、Microsoft Teams と Skype for Business Online の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-108">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

<span data-ttu-id="aea0c-109">電話番号は自動応答に直接割り当てられるのではなく、自動応答に関連付けられている[リソースアカウント](manage-resource-accounts.md)に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-109">Phone numbers are not directly assigned to the auto attendant, but rather to a [resource account](manage-resource-accounts.md) that is associated to the auto attendant.</span></span>

<span data-ttu-id="aea0c-110">自動応答の実装には、多くの場合、自動応答がいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="aea0c-110">Auto attendant implementations often involve several auto attendants.</span></span> <span data-ttu-id="aea0c-111">通常、*第1レベル*の自動応答には、電話番号が割り当てられたリソースアカウントがあります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-111">A *first-level* auto attendant usually has a resource account with an assigned phone number.</span></span> <span data-ttu-id="aea0c-112">入れ子になった自動応答は第2レベルのメニューとして使用され、第*1*レベルの自動応答は呼び出しとして接続します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-112">A nested auto attendant is used as a second-level menu that the *first-level* auto attendant connects  as call to.</span></span> <span data-ttu-id="aea0c-113">*入れ子になっ*た自動応答では、リソースアカウントに電話番号を割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="aea0c-113">A *nested* auto attendant isn't required to  have a phone number assigned to its resource account.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="aea0c-114">手順 1-はじめに</span><span class="sxs-lookup"><span data-stu-id="aea0c-114">Step 1 — Get started</span></span>

<span data-ttu-id="aea0c-115">自動応答には、関連するリソースアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="aea0c-115">An auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="aea0c-116">必要なリソースアカウントとすべてのライセンスの詳細については、「 [Teams のリソースアカウントを管理](manage-resource-accounts.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aea0c-116">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts and all licenses required.</span></span> 
 
<!-- When you create a new auto attendant in Teams after October 10th, 2019, the required auto attendant is automatically created and linked with the new auto attendant. -->
 
> [!TIP]
> <span data-ttu-id="aea0c-117">電話システムのライセンスを持つオンラインユーザーであるオペレーターまたはメニューオプションへの通話をリダイレクトするには、エンタープライズ Voip に対して通話を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-117">To redirect calls to an operator or a menu option that is an Online user with a Phone System license, you will need to enable them for Enterprise Voice.</span></span> <span data-ttu-id="aea0c-118">「 [Skype For business ライセンスの割り当て](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)」または「 [Microsoft Teams のアドオンライセンスの割り当て](teams-add-on-licensing/assign-teams-add-on-licenses.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aea0c-118">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span> <span data-ttu-id="aea0c-119">Windows PowerShell を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-119">You can also use Windows PowerShell.</span></span> <span data-ttu-id="aea0c-120">たとえば、次を実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="aea0c-120">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

## <a name="step-2--create-auto-attendants"></a><span data-ttu-id="aea0c-121">手順 2-自動応答を作成する</span><span class="sxs-lookup"><span data-stu-id="aea0c-121">Step 2 — Create auto attendants</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aea0c-122">各自動応答には、[リソースアカウント](manage-resource-accounts.md)が関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-122">Every auto attendant is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="aea0c-123">最初にリソースアカウントを作成してから、自動応答に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-123">You must create the resource account first, then you can associate it to the auto attendant.</span></span>

### <a name="with-the-microsoft-teams-admin-center"></a><span data-ttu-id="aea0c-124">Microsoft Teams 管理センターでの操作</span><span class="sxs-lookup"><span data-stu-id="aea0c-124">With the Microsoft Teams admin center</span></span>

<span data-ttu-id="aea0c-125">**Microsoft Teams 管理センター**で、[**音声**  >  **自動応答**] をクリックし、[ **+ 追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aea0c-125">In the **Microsoft Teams admin center**, click   **Voice** > **Auto attendants**, then click **+ Add**:</span></span>

#### <a name="general-info-page"></a><span data-ttu-id="aea0c-126">[一般的な情報] ページ</span><span class="sxs-lookup"><span data-stu-id="aea0c-126">General info page</span></span>

![[自分の自動応答] ページのスクリーンショット](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

<span data-ttu-id="aea0c-128">![番号1のアイコン、前のスクリーンショット名の吹き出しは ](media/teamscallout1.png)
 **Name**自動応答の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-128">![Icon of the number 1, a callout in the previous screenshot](media/teamscallout1.png)
**Name** Enter a display name for your auto attendant.</span></span> <span data-ttu-id="aea0c-129">名前の入力は必須で、空白を含む最大 64 文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-129">The name is required and can contain up to 64 characters, including spaces.</span></span> <span data-ttu-id="aea0c-130">ここで指定した**名前**が、[**自動応答**] タブの列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-130">The **Name** you designate here is listed in a column on the **Auto attendants** tab.</span></span>

<span data-ttu-id="aea0c-131"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="aea0c-131"><a name="phonenumber"> </a></span></span>

* * *

<span data-ttu-id="aea0c-132">![数字2のアイコン、前のスクリーンショット ](media/teamscallout2.png)
 <a name="operator"> </a> 
 **演算子**の吹き出し。これは省略可能です (ただし推奨)。</span><span class="sxs-lookup"><span data-stu-id="aea0c-132">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png)
<a name="operator"> </a>
**Operator** This is optional (but recommended).</span></span> <span data-ttu-id="aea0c-133">[**オペレーター** ] オプションを設定すると、発信者はメニューから抜け、指定したユーザーに向かって話すことができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-133">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

<span data-ttu-id="aea0c-134">既定では、0キーがオペレーターに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-134">The 0 key is assigned to Operator by default.</span></span>

<span data-ttu-id="aea0c-135">オペレーターを設定する場合は、[**通話フロー** ] ページの [**編集] メニューオプション**のオプションについて他のユーザーに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="aea0c-135">If you set an Operator, tell people who call about the option in **Edit menu options** on the **Call flow** page.</span></span> <span data-ttu-id="aea0c-136">自動応答でオペレーターを設定した場合は、対応するメッセージテキストを [発信者に**聞こえる**] ボックスに入力するか、音声ファイルを変更してこのオプションを含めます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-136">If you set an operator on your auto attendant, you enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option.</span></span> <span data-ttu-id="aea0c-137">たとえば、「オペレーターに繋ぐには、0 を押してください。」などです。</span><span class="sxs-lookup"><span data-stu-id="aea0c-137">For example, "For the Operator, press zero."</span></span>

<span data-ttu-id="aea0c-138">オペレーターを設定するには、次のいくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-138">You have several ways to set the Operator:</span></span>

- <span data-ttu-id="aea0c-139">[**演算子なし**] は、"operator" と "Press 0" オプションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="aea0c-139">**No operator** disables the "Operator" and "Press 0" options.</span></span> <span data-ttu-id="aea0c-140">これは現在の既定値です。</span><span class="sxs-lookup"><span data-stu-id="aea0c-140">This is the current default.</span></span>
- <span data-ttu-id="aea0c-141">**組織内のユーザー**が、Microsoft 365 または Office 365 でエンタープライズボイスまたは割り当てられた通話プランで有効になっている電話システムのライセンスを持つユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-141">**Person in organization** assigns a person with a Phone System license that is enabled for Enterprise Voice or assigned Calling Plans in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="aea0c-142">また、発信者がボイスメールに送信されるように設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-142">You can also set it up so the caller is sent to voicemail.</span></span> <span data-ttu-id="aea0c-143">発信者をボイスメールに送信するには、[**組織内のユーザー** ] を選択し、そのアカウントの設定でボイスメールに直接通話を送信するように設定します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-143">To send a caller to voicemail, select **Person in organization** and set that account's settings to send calls directly to voicemail.</span></span>

     > [!Note]
     > <span data-ttu-id="aea0c-144">**組織内の**ユーザーは、オンラインユーザーまたは Skype For business Server を使用してオンプレミスでホストされているユーザーになることができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-144">**Person in organization** can be an Online user or a user hosted on-premises using Skype for Business Server.</span></span> <span data-ttu-id="aea0c-145">[**組織内のユーザー** ] を選ぶと、共有メールボックスまたはユーザーのメールボックスを含むアカウントを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-145">When selecting **Person in organization** you can select an account with a shared mailbox or with a user mailbox.</span></span>

- <span data-ttu-id="aea0c-146">**音声アプリ** 既に作成されている自動応答または通話キューにリンクされているリソースアカウントの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-146">**Voice app**  Select the name of the resource account linked to an auto attendant or call queue that has already been created.</span></span> <span data-ttu-id="aea0c-147">オペレーターを要求する呼び出し元は、そこにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-147">Callers that request an operator are redirected there.</span></span>  
<!--   

- **Auto attendant** Select the name of the resource account linked to an auto attendant that has already been created. Callers that request an operator are redirected there.
- **Call queue** Select the name of the resource account linked to a call queue that has already been created. Callers that request an operator are redirected there.

**Phone number (optional)** Enter the service phone number you want to assign to the new resource account this wizard creates and links to the new auto attendant. If you intend this auto attendant to be a nested auto attendant, it doesn't need a phone number. You can add one if for some reason you require several ways to connect to the auto attendant system.

> [!NOTE]
> Auto attendants created after October 10th, 2019 also create a new [resource account](manage-resource-accounts.md) that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available.
-->

* * *

<span data-ttu-id="aea0c-148"><a name="timezone"> </a></span><span class="sxs-lookup"><span data-stu-id="aea0c-148"><a name="timezone"> </a></span></span>

<span data-ttu-id="aea0c-149">![数字3のアイコン。前のスクリーンショットの ](media/teamscallout3.png) **タイムゾーン**の吹き出しで、自動応答のタイムゾーンを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-149">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) **Time zone** You are required to set the time zone for your auto attendant.</span></span> <span data-ttu-id="aea0c-150">この設定は、組織の一覧に表示されているメインアドレスのタイムゾーンまたは別のタイムゾーンと同じにすることができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-150">The setting can be the same as the time zone of the main address listed for your organization, or a different time zone.</span></span> <span data-ttu-id="aea0c-151">各自動応答には、異なるタイムゾーンを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-151">Each auto attendant can have a different time zone.</span></span> <span data-ttu-id="aea0c-152">自動応答に設定された勤務時間は、このタイムゾーンも使用します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-152">The business hours set for the auto attendant also use this time zone.</span></span> <span data-ttu-id="aea0c-153">すべての地域に夏時間が含まれていないため、業務時間の不一致を回避するために正しいタイムゾーンを設定してください。</span><span class="sxs-lookup"><span data-stu-id="aea0c-153">Make sure to set the right timezone to avoid business-hours discrepancies since not all regions have Daylight Saving.</span></span> 

* * *

<span data-ttu-id="aea0c-154">![数字4のアイコン、前のスクリーンショット ](media/teamscallout4.png)
 <a name="language"> </a>言語の吹き出しで、 
 **Language**自動応答に使用する言語を選びます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-154">![Icon of the number 4,  a callout in the previous screenshot](media/teamscallout4.png)
<a name="language"> </a>
**Language** Select the language that you want to use for your auto attendant.</span></span> <span data-ttu-id="aea0c-155">自動応答は呼び出し元でその言語を使用し、すべてのシステムプロンプトはこの言語で再生されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-155">The auto attendant uses that language with callers, and all system prompts are played in this language.</span></span>

 * * *

<span data-ttu-id="aea0c-156">![数字5のアイコン、前のスクリーンショットの吹き出しは、 ](media/teamscallout5.png)
 このオプションが選択されている場合**に音声入力**音声認識を使用できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-156">![Icon of the number 5,  a callout in the previous screenshot](media/teamscallout5.png)
**Enable voice inputs** Speech recognition is available if this option is selected.</span></span> <span data-ttu-id="aea0c-157">発信者は、[設定した言語](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)で音声入力を使用できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-157">Callers can use voice input in the  [language you set](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span> <span data-ttu-id="aea0c-158">他のユーザーが電話のキーパッドを使って選択できるようにする場合は、音声認識を [**オフ**] に設定したままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-158">If you want to only let people use their phone keypad to make selections, you can leave speech recognition set to **Off**.</span></span>

* * *  

<span data-ttu-id="aea0c-159">選択が完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aea0c-159">When you finish with your selections, click **Next**.</span></span>

#### <a name="call-flow"></a><span data-ttu-id="aea0c-160">コールフロー</span><span class="sxs-lookup"><span data-stu-id="aea0c-160">Call flow</span></span>

<span data-ttu-id="aea0c-161"><a name="greetingsandrouting"> </a></span><span class="sxs-lookup"><span data-stu-id="aea0c-161"><a name="greetingsandrouting"> </a></span></span>

> [!TIP]
> <span data-ttu-id="aea0c-162">独自の勤務時間のスケジュールを設定して、営業時間中および営業時間外にさまざまな通話フロー動作を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-162">You can choose to set up a custom business hours schedule, with different call flow behaviors during and after business hours.</span></span> <span data-ttu-id="aea0c-163">ユーザー設定のスケジュールを設定するには、[時間の経過後にオプションのコールフロー](#call-flow-for-after-hours)を設定します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-163">To set a custom schedule, set the optional [Call flow for after hours](#call-flow-for-after-hours).</span></span> <span data-ttu-id="aea0c-164">既定では、自動応答では営業時間の通話フローが使用されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-164">By default, an auto attendant uses business hours call flows.</span></span>

<span data-ttu-id="aea0c-165">ユーザーが自動応答に到着したときに聞こえる、カスタマイズされたあいさつ文、プロンプト、メニューを設定できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-165">You can set up customized greetings, prompts, and menus that people hear when they reach your auto attendant.</span></span>

![スクリーンショット: 通話処理ページのあいさつ文セクション](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

* * *

<span data-ttu-id="aea0c-167">**最初にグリーティングメッセージを再生する**応答メッセージは省略可能で**あり、応答なし**に設定したり、**音声ファイルを再生**したり、**あいさつメッセージを入力**したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-167">**First play a greeting message** A greeting is optional and can be set to **No greeting**, **Play an audio file**, or **Type a greeting message**.</span></span>

> [!NOTE]
> <span data-ttu-id="aea0c-168">応答メッセージは、第1レベルの自動応答で最も重要です。</span><span class="sxs-lookup"><span data-stu-id="aea0c-168">A greeting is most valuable for a first-level auto attendant.</span></span> <span data-ttu-id="aea0c-169">入れ子になった自動応答には、多くの場合、応答メッセージは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="aea0c-169">A nested auto attendant often doesn't need a greeting.</span></span>

<span data-ttu-id="aea0c-170">![番号1のアイコン、前のスクリーンショットの吹き出し ](media/teamscallout1.png) [あいさつをし**ない**] を選択した場合、発信者は、後で選んだ操作のいずれかによって通話が処理される前に、メッセージまたは応答メッセージを読み上げません。</span><span class="sxs-lookup"><span data-stu-id="aea0c-170">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) If you select **No Greeting**, the caller doesn't hear a message or greeting before the call is handled by one of the actions you select later.</span></span> 

<!-- You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.-->

<span data-ttu-id="aea0c-171">![前のスクリーンショットの1つのアイコン ](media/teamscallout2.png) 。 [**オーディオファイルの再生**] を選択すると、[**ファイルのアップロード**] ボタンを使用して、録音したグリーティングメッセージをオーディオとして保存することができます。WAV、。MP3、またはです。WMA 形式。</span><span class="sxs-lookup"><span data-stu-id="aea0c-171">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="aea0c-172">記録は 5 MB 以下でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="aea0c-172">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="aea0c-173">![数値3のアイコン、前のスクリーンショットの吹き出しテキスト ](media/teamscallout3.png) **メッセージを入力**します。このオプションを選択する場合は、提供されたフィールドにシステムで読み上げるテキスト (最大1000文字) を入力します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-173">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) **Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters) in the field provided.</span></span> <span data-ttu-id="aea0c-174">たとえば、「Contoso へようこそ」と入力します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-174">For example, enter "Welcome to Contoso.</span></span> <span data-ttu-id="aea0c-175">お電話ありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-175">Your call is important to us."</span></span> <span data-ttu-id="aea0c-176">出力は、音声合成ソフトウェアによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-176">Output is created by text-to-voice software.</span></span>

* * *

<span data-ttu-id="aea0c-177">「**通話**」セクションでは、次のアクションからの通話の横に行われる処理を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-177">You can select what happens next to calls from the following actions in the  **Then route the call** section.</span></span> <span data-ttu-id="aea0c-178">設定は、**切断**、**リダイレクト通話**、**再生メニューのオプション**です。</span><span class="sxs-lookup"><span data-stu-id="aea0c-178">Settings are **Disconnect**, **Redirect call**, or **Play menu options**.</span></span>

<span data-ttu-id="aea0c-179">[**切断**] を選択すると、応答メッセージが再生された後、発信者は切断されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-179">If you select **Disconnect**, the caller is disconnected after the greeting plays.</span></span> 

<span data-ttu-id="aea0c-180"><a name="redirectcalls"> </a></span><span class="sxs-lookup"><span data-stu-id="aea0c-180"><a name="redirectcalls"> </a></span></span>

<span data-ttu-id="aea0c-181">![数字4のアイコン: 前のスクリーンショットの [リダイレクト] を選ぶと、 ](media/teamscallout4.png) **Redirect call**オプションを選択せずに、選択した宛先に発信者が送信されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-181">![Icon of the number 4,  a callout in the previous screenshot](media/teamscallout4.png) **Redirect call** sends the caller to the chosen destination without choosing from options.</span></span> <span data-ttu-id="aea0c-182">次の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-182">The possible settings are:</span></span>

  - <span data-ttu-id="aea0c-183">**組織内のユーザー**選択するアカウントには、エンタープライズ Voip の電話システムライセンスが有効になっているか、Microsoft 365 または Office 365 で通話プランが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-183">**Person in organization** The account you choose must have a Phone System license enabled for Enterprise Voice or have an assigned Calling Plan in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="aea0c-184">発信者がボイスメールに送信できるように設定することができます。 [**組織内のユーザー** ] を選択し、ボイスメールに直接通話を転送するようにアカウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-184">You can set it up so the caller can be sent to voicemail: select **Person in organization** and set that account to have calls forwarded directly to voicemail.</span></span>

    > [!Note]
    > <span data-ttu-id="aea0c-185">**組織内の**ユーザーは、オンラインユーザーまたは Skype For business Server を使用してオンプレミスでホストされているユーザーになることができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-185">**Person in organization** can be an Online user or a user hosted on-premises using Skype for Business Server.</span></span> <span data-ttu-id="aea0c-186">[**組織内のユーザー** ] を選ぶと、共有メールボックスまたはユーザーのメールボックスを含むアカウントを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-186">When selecting **Person in organization** you can select an account with a shared mailbox or with a user mailbox.</span></span>

  - <span data-ttu-id="aea0c-187">**音声アプリ**自動応答または設定済みの通話キューを選択します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-187">**Voice App** Select an auto attendant or call queue that has already been set up.</span></span> <span data-ttu-id="aea0c-188">サービスに関連付けられているリソースアカウントの名前で、自動応答または通話キューを検索します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-188">You search for the auto attendant or call queue by the name of the resource account associated with the service.</span></span>
  - <span data-ttu-id="aea0c-189">**ボイスメール**この自動応答で受け取ったボイスメールにアクセスする必要がある、組織内のユーザーを含む Microsoft 365 グループを選びます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-189">**Voicemail** Select the Microsoft 365 group that contains the users in your organization that need to access voicemail received by this auto attendant.</span></span> <span data-ttu-id="aea0c-190">ボイスメールメッセージは、指定した Microsoft 365 グループに送信されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-190">Voicemail messages are sent to the Microsoft 365 group you specified.</span></span> <span data-ttu-id="aea0c-191">ボイスメールメッセージにアクセスするには、Outlook のグループに移動することで、グループのメンバーがそのメッセージを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-191">To access voicemail messages, members of the group can open them by navigating to the group in Outlook.</span></span>

      <span data-ttu-id="aea0c-192">[**議事録**をオン] に切り替え**て**、ボイスメールメッセージのボイスからテキストへの送信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="aea0c-192">Switch **Transcription** to **on** to enable voice-to-text transcription of voicemail messages.</span></span>

 * * *

![スクリーンショット: 通話処理ページのアクションセクション](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

<span data-ttu-id="aea0c-194">![](media/teamscallout1.png)[**再生] メニューオプション**を選択すると表示される、前のスクリーンショットの番号1のアイコン。音声ファイルを使用するか、テキストを入力して、ダイヤルパッドメニューオプションを発信者に与えるかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-194">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) When you select **Play menu options** You can select whether to use an audio file or enter text that will be rendered as text to speech to give dialpad menu options to callers.</span></span> <span data-ttu-id="aea0c-195">[**へのリダイレクト**] または [**切断**] のオプションではなく、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-195">Select this instead of the **Redirect call to** or **Disconnect** options.</span></span>


<span data-ttu-id="aea0c-196">![数値2のアイコン: 前のスクリーンショットの音声ファイルを再生すると、発信者が選択できるようにする ](media/teamscallout2.png) **Play an audio file**ためのプロンプトとオプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-196">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) **Play an audio file** lets you set up a prompts and options for the caller to choose.</span></span> 
- <span data-ttu-id="aea0c-197">[**オーディオファイルの再生**] を選択した場合は、[**ファイルのアップロード**] ボタンを使用して、録音したグリーティングメッセージをオーディオとして保存することができます。WAV、。MP3、またはです。WMA 形式。</span><span class="sxs-lookup"><span data-stu-id="aea0c-197">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="aea0c-198">記録は 5 MB 以下でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="aea0c-198">The recording can be no larger than 5 MB.</span></span>

- <span data-ttu-id="aea0c-199">**あいさつ文を入力する**このオプションを選択した場合は、表示されるフィールドにシステムで読み取るテキスト (最大1000文字) を入力します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-199">**Type a greeting message** If you choose this option, enter the text you want the system to read (up to 1000 characters) in the field provided.</span></span> <span data-ttu-id="aea0c-200">たとえば、「Contoso へようこそ」と入力します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-200">For example, enter "Welcome to Contoso.</span></span> <span data-ttu-id="aea0c-201">お電話ありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-201">Your call is important to us."</span></span> <span data-ttu-id="aea0c-202">出力は、音声合成ソフトウェアによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-202">Output is created by text-to-voice software.</span></span>

<span data-ttu-id="aea0c-203">**メニューオプションを設定**するこのダイアログでは、電話のキーパッドまたは音声コマンドを追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-203">**Set menu options** Telephone keypad or voice commands can be added or removed in this dialog.</span></span> <span data-ttu-id="aea0c-204">メニューオプションを削除するには、音声コマンドのエントリを削除して、 **Redirect**を **[選択]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-204">To delete a menu option, remove the voice command entry and set **Redirect to** back to **Select**.</span></span>

> [!TIP]
> <span data-ttu-id="aea0c-205">メニュープロンプトテキストを更新するか、オプションを削除するときに音声メッセージを再記録します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-205">Update menu prompt text or re-record the audio prompts when you remove options.</span></span> <span data-ttu-id="aea0c-206">発信者のメニュープロンプトは、自動的には更新されません。</span><span class="sxs-lookup"><span data-stu-id="aea0c-206">The menu prompt played for callers isn't automatically updated.</span></span>  
>
> <span data-ttu-id="aea0c-207">メニュー オプションはどのような順番でも追加、削除でき、キー マッピングは連続的である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="aea0c-207">Any menu option can be added and removed in any order, and the key mappings don't have to be continuous.</span></span> <span data-ttu-id="aea0c-208">たとえば、キー 2 を使用せず、キー 0、1、3 をオプションにマッピングしてメニューを作成することが可能です。</span><span class="sxs-lookup"><span data-stu-id="aea0c-208">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="aea0c-209">キー \* (繰り返し) と \# (戻る) は、システムによって予約されているため、再割り当てすることはできません。</span><span class="sxs-lookup"><span data-stu-id="aea0c-209">The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.</span></span> <span data-ttu-id="aea0c-210">音声認識が有効になっている場合、\* を押すと「繰り返し」、# を押すと「戻る」の音声コマンドに対応します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-210">If speech recognition is enabled, pressing \* will correspond with "Repeat" and # will correspond with the "Back" voice commands.</span></span>

<span data-ttu-id="aea0c-211">![数値3のアイコン、前のスクリーンショットの吹き出し ](media/teamscallout3.png) 。メニューオプションを設定するには、[ **+** ] をクリックして、次のオプションの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-211">![Icon of the number 3, a callout in the previous screenshot](media/teamscallout3.png) To set up a menu option, click on the  **+Assign a dial key** and enter information for the following options:</span></span>

<span data-ttu-id="aea0c-212">![数字4のアイコン: 1 つのオプションの前のスクリーンショットの ](media/teamscallout4.png) **音声コマンド**列には、64文字まで入力でき、"カスタマーサービス" や "操作と根拠" など、複数の単語を含めることができます。  </span><span class="sxs-lookup"><span data-stu-id="aea0c-212">![Icon of the number 4, a callout in the previous screenshot](media/teamscallout4.png)  **Voice command** column for an option can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="aea0c-213">音声認識が有効になっている場合は、その名前が自動的に認識され、発信者は3、「3」と言って、または「カスタマーサービス」と言って、キー3にマップされているオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-213">If speech recognition is enabled, the name is automatically recognized, and the caller is able to press 3, say "three," or say "Customer Service" to select the option mapped to key 3.</span></span> <span data-ttu-id="aea0c-214">このテキストは、サービス確認プロンプトの音声合成によっても表示されます。これは、「通話をオペレーターに転送する」のようなものである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-214">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to the Operator."</span></span>

<span data-ttu-id="aea0c-215">![5のアイコン。前のスクリーンショットの吹き出し ](media/teamscallout5.png) 。対応するキーが押されている場合、または音声認識を使用してオプションを選択した場合に、通話の**転送**先のオプションセットを設定します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-215">![Icon of the number 5, a callout in the previous screenshot](media/teamscallout5.png)  The **Redirect to** option sets where the call goes if the corresponding key is pressed, or the option is selected using speech recognition.</span></span> <span data-ttu-id="aea0c-216">次の場所に呼び出しを送信できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-216">The call can be sent to:</span></span>

<!-- Is the Operator behavior changing here? Looks like operator is only an available option for dial key 0 -->

- <span data-ttu-id="aea0c-217">**Operator**オペレーターが既に設定されている場合、このオプションは自動的にキー0にマッピングされますが、別のキーに削除したり、再割り当てしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-217">**Operator** If an operator is already set up, the option is automatically mapped to key 0, but can also be deleted or reassigned to a different key.</span></span> <span data-ttu-id="aea0c-218">このオプションを選択した呼び出し元が指定の演算子に送信されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-218">The caller who selects this option is sent to the designated Operator.</span></span> <span data-ttu-id="aea0c-219">Operator がいずれのキーにも設定されていない場合は、音声コマンド "Operator" も無効になります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-219">If Operator isn't set to any key, the voice command "Operator" is also disabled.</span></span> 
- <span data-ttu-id="aea0c-220">**組織内の**ユーザーは、オンラインユーザーまたは Skype For business Server を使用してオンプレミスでホストされているユーザーになることができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-220">**Person in organization** can be an Online user or a user hosted on-premises using Skype for Business Server.</span></span> <span data-ttu-id="aea0c-221">ユーザーは、Microsoft 365 または Office 365 でエンタープライズボイスまたは割り当てられた通話プランに対応している電話システムのライセンスを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-221">The user must have a Phone System license that is enabled for Enterprise Voice or assigned Calling Plans in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="aea0c-222">[**検索名**] フィールドでユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-222">Search for the person in the **Search by name** field.</span></span>

- <span data-ttu-id="aea0c-223">**音声アプリ**自動応答または設定済みの通話キューを選択します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-223">**Voice App** Select an auto attendant or call queue that has already been set up.</span></span> <span data-ttu-id="aea0c-224">アプリケーションに関連付けられているリソースアカウントの名前で、自動応答または通話キューを検索します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-224">You search for the auto attendant or call queue by the name of the resource account associated with the application.</span></span>

- <span data-ttu-id="aea0c-225">**ボイスメール**この自動応答で受け取ったボイスメールにアクセスする必要がある、組織内のユーザーを含む Microsoft 365 グループを選びます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-225">**Voicemail** Select the Microsoft 365 group that contains the users in your organization that need to access voicemail received by this auto attendant.</span></span> <span data-ttu-id="aea0c-226">ボイスメールメッセージは、指定した Microsoft 365 グループに送信されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-226">Voicemail messages are sent to the Microsoft 365 group you specified.</span></span> <span data-ttu-id="aea0c-227">ボイスメールメッセージにアクセスするには、Outlook のグループに移動することで、グループのメンバーがそのメッセージを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-227">To access voicemail messages, members of the group can open them by navigating to the group in Outlook.</span></span>

    <span data-ttu-id="aea0c-228">[**議事録**をオン] に切り替え**て**、ボイスメールメッセージのボイスからテキストへの送信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="aea0c-228">Switch **Transcription** to **on** to enable voice-to-text transcription of voicemail messages.</span></span>

<!-- - **Auto attendant** Select the name of an existing auto attendant in the **Search by name** field. You will also have to select a resource account associated to the auto attendant. The caller who selects this option is sent to that auto attendant.
- **Call queue** Select the name of an existing call queue in the **Search by name** field. You will also have to select a resource account associated to the call queue. The caller who selects this option is sent to that call queue, where the call is answered by a call agent.
- **External phone number** routes the caller to a designated phone number outside your local system.<!-- does this have prerequisites like direct routing?
- **Group Voicemail** routes the call to a voicemail box that you select.  -->

<span data-ttu-id="aea0c-229">![数字6のアイコン、前のスクリーンショット ](media/teamscallout6.png) **ディレクトリ検索**の吹き出しこのセクションでは、自動応答の**内線番号**による**ダイヤル**を有効にすることができます。  </span><span class="sxs-lookup"><span data-stu-id="aea0c-229">![Icon of the number 6, a callout in the previous screenshot](media/teamscallout6.png)  **Directory search** In this section, you can enable **Dial by name** and **Dial by Extension** for the auto attendant.</span></span> <span data-ttu-id="aea0c-230">[オプションのダイヤルスコープ] ページでは、これらのサービスに含まれていないユーザーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-230">You can set who is and is not included in these services in the optional Dial Scope page.</span></span> <span data-ttu-id="aea0c-231">[ディレクトリ検索] は、既定では **[なし**] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="aea0c-231">Directory search is set to **None** by default.</span></span>

<span data-ttu-id="aea0c-232">**名前でダイヤル**このオプションを有効にすると、発信者は**名前でダイヤル**を使用して組織内のユーザーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-232">**Dial by name** If you enable this option, callers can search for people in your organization using **Dial by name**.</span></span> <span data-ttu-id="aea0c-233">ユーザー名と音声認識がユーザーに一致していることを示します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-233">They say the user's name and voice recognition matches them to a user.</span></span> <span data-ttu-id="aea0c-234">[オプションのダイヤルスコープ] ページでは、これらのサービスに含まれていないユーザーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-234">You can set who is and is not included in these services in the optional Dial Scope page.</span></span> <span data-ttu-id="aea0c-235">電話システムのライセンスを持っているか、または Skype for Business Server を使用してオンプレミスでホストされているすべてのユーザーは、資格のあるユーザーであり、名前でダイヤルすることができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-235">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span>


<span data-ttu-id="aea0c-236">**内線番号でダイヤル**このオプションを有効にすると、発信者は電話の内線番号を入力して組織内のユーザーに接続できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-236">**Dial by extension** If you enable this option, callers can connect with users in your organization by entering their phone extension.</span></span> <span data-ttu-id="aea0c-237">オプションの [ダイヤルスコープ] ページで、[利用可能] または [**ダイヤルイン] の内線番号**として表示されるユーザーを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-237">You can select which users are listed as available or not available for **Dial by extension** in the optional Dial Scope page.</span></span> <span data-ttu-id="aea0c-238">電話システムのライセンスを持っているか、または Skype for Business Server を使用してオンプレミスでホストされているすべてのユーザーは、資格のあるユーザーであり、内線でダイヤルすることができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-238">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by extension.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aea0c-239">次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="aea0c-239">Please observe the following:</span></span>
>- <span data-ttu-id="aea0c-240">内線番号を使用できるようにするには、Active Directory または Azure Active Directory で定義されている次のいずれかの電話属性の一部として内線番号が指定されている必要があります (詳しくは、「ユーザーを個別に追加するか、「一括で追加する」をご覧ください) https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) 。</span><span class="sxs-lookup"><span data-stu-id="aea0c-240">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk] for more information(https://docs.microsoft.com/microsoft-365/admin/add-users/add-users).</span></span>
>    - <span data-ttu-id="aea0c-241">HomePhone</span><span class="sxs-lookup"><span data-stu-id="aea0c-241">HomePhone</span></span>
>    - <span data-ttu-id="aea0c-242">携帯電話/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="aea0c-242">Mobile/MobilePhone</span></span>
>    - <span data-ttu-id="aea0c-243">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="aea0c-243">TelephoneNumber/PhoneNumber</span></span>
>    - <span data-ttu-id="aea0c-244">その他の電話</span><span class="sxs-lookup"><span data-stu-id="aea0c-244">OtherTelephone</span></span>
>- <span data-ttu-id="aea0c-245">[ユーザー電話番号] フィールドに拡張子を入力するために必要な形式は、またはのどちらか `+<phonenumber>;ext=<extension>` `x<extension>` です。</span><span class="sxs-lookup"><span data-stu-id="aea0c-245">The required format to enter the extension in the user phone number field is either `+<phonenumber>;ext=<extension>` or `x<extension>`.</span></span>
>- <span data-ttu-id="aea0c-246">Teams 管理センターでの内線番号の割り当ては、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aea0c-246">Assigning an extension in Teams Admin center is not currently supported.</span></span> <span data-ttu-id="aea0c-247">[Get-msoluser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0) PowerShell コマンドまたは Microsoft 365 管理センターのいずれかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-247">You must either use the [Set-MsolUser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0) PowerShell command or the Microsoft 365 admin center.</span></span>
>- <span data-ttu-id="aea0c-248">AAD PhoneNumber 属性と MobilePhone 属性の変更が可能になるまでに最大12時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-248">It can take up to 12 hours before changes to the AAD PhoneNumber and MobilePhone attributes are available.</span></span>
>- <span data-ttu-id="aea0c-249">ユーザーの LineUri の内線番号を定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="aea0c-249">Please do NOT define an extension for the LineUri of a user.</span></span> <span data-ttu-id="aea0c-250">現在、これはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aea0c-250">This is not supported currently.</span></span>
>- <span data-ttu-id="aea0c-251">自動応答は、ダイヤルの名前または内線番号のいずれかに対して構成することができます。両方は使用できません。</span><span class="sxs-lookup"><span data-stu-id="aea0c-251">An auto attendant can be configured for either dial by name or dial by extension, but not both.</span></span>

> [!NOTE]
> <span data-ttu-id="aea0c-252">[**名前によるダイヤル**] 機能と [**内線番号**] 機能の両方を使用する場合は、ユーザーの内線番号がわかっている場合に、呼び出し元**に対して**メニューオプションを選択するように指示するメインの自動応答を作成できます。また、そのオプションを設定して、通話をダイヤル可能な自動応答に転送することもできます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-252">If you want to use both the **Dial by name** and **Dial by extension** features, you can create  main auto attendant (enabled for **Dial by name**) that prompts callers to choose a menu option if they know the extension of the user, and set that option to transfer the call to an auto attendant enabled for Dial by extension.</span></span>

* * *

<!--
**Instructions for callers** lets you choose **Use recorded call instructions** or **Write your call instructions**.  

If you choose **Use recorded call instructions**, you have the option to record and upload new or prerecorded sound files to play as menu instructions. The same app used in recording the auto attendant greeting is used here.

If you choose **Write your call instructions**, enter the script  you want the system to read (up to 1000 characters). For example, you might enter text that begins "Please choose from one of the following menu options ... " and provide a script written to reflect your configuration.
* * *  -->

<span data-ttu-id="aea0c-253">選択が完了したら、[**次へ**] をクリックして詳細設定を変更するか、[**送信**] をクリックして、次のような既定の設定を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-253">When you are finished with your selections, you can click **Next** if you want to change advanced settings, or click **Submit** if you want to use default settings for things like:</span></span>
- <span data-ttu-id="aea0c-254">営業時間外の通話フロー</span><span class="sxs-lookup"><span data-stu-id="aea0c-254">Call flow for after hours</span></span>
- <span data-ttu-id="aea0c-255">休日のコールフロー</span><span class="sxs-lookup"><span data-stu-id="aea0c-255">Call flow for holidays</span></span>
- <span data-ttu-id="aea0c-256">ダイヤルスコープ</span><span class="sxs-lookup"><span data-stu-id="aea0c-256">Dial Scope</span></span>
- <span data-ttu-id="aea0c-257">リソースアカウント</span><span class="sxs-lookup"><span data-stu-id="aea0c-257">Resource accounts</span></span>

<span data-ttu-id="aea0c-258">自動応答はリソースアカウントを持つ必要があるため、**リソース**アカウントページに進んで、既に構成したリソースアカウントを関連付けるか、または、「 [Microsoft Teams のリソースアカウントの管理](manage-resource-accounts.md)」で説明するように、リソースアカウントを作成して自動応答に関連付けるかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-258">Since your auto attendant is required to have a resource account, you have a choice of proceeding to the **Resource account** page and associating a resource account you've already configured, or creating a resource account and associating it to the auto attendant as described in [Manage resource accounts in Microsoft Teams](manage-resource-accounts.md).</span></span> <span data-ttu-id="aea0c-259">この自動応答は、リソースアカウントに関連付けられるまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="aea0c-259">You won't be able to use this auto attendant until it has been associated to a resource account.</span></span> <span data-ttu-id="aea0c-260">これを行うには、画面の下部にある [**次へ**] ボタンをクリックし、左のナビゲーションで [**リソース**アカウント] をクリックして、[リソースアカウント] ページに直接移動し、自動応答をリソースアカウントに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-260">to do this, click the **Next** button at the bottom of the screen and then click on **Resource accounts** in the left navigation to go straight to the Resource accounts page and associate your auto attendant to a resource account.</span></span>

#### <a name="advanced-settings-optional"></a><span data-ttu-id="aea0c-261">詳細設定 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="aea0c-261">Advanced settings (optional)</span></span>

<span data-ttu-id="aea0c-262">選択した既定値に設定できる追加の画面が4つあります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-262">There are four additional screens that you can configure or leave at defaults as you choose.</span></span>

##### <a name="call-flow-for-after-hours"></a><span data-ttu-id="aea0c-263">営業時間外の通話フロー</span><span class="sxs-lookup"><span data-stu-id="aea0c-263">Call flow for after hours</span></span>

<span data-ttu-id="aea0c-264">既定では、自動応答の営業時間は、月曜日から金曜日までの 9am 5pm に設定されています。</span><span class="sxs-lookup"><span data-stu-id="aea0c-264">By default, an auto attendant's business hours are set to 9am-5pm, Monday to Friday</span></span>  <!--24/7--><span data-ttu-id="aea0c-265">通話時間は*勤務時間*と見なされるため、*時間単位*の通話後のコールフローオプションは無効になります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-265">, and the call flow options for *after hours* calls are disabled because all hours are considered *business hours*.</span></span> <span data-ttu-id="aea0c-266">[**ユーザー設定の勤務時間を設定**する] オプションを選択すると、[**時間経過後の通話フロー** ] ページで、自動応答で使用される通話処理ルールが時間後に構成されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-266">When you select the **Setup custom business hours** option, the **Call flow for after hours** page configures the call handling rules used by the auto attendant after hours.</span></span> <span data-ttu-id="aea0c-267">利用可能なオプションは同じであるため、異なるメニューや動作のスケジュールを設定する機能も異なります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-267">The options available are the same, the difference is the ability to set a schedule for different menus and behaviors.</span></span>

<span data-ttu-id="aea0c-268">自動応答のシステムでは、第1レベルの自動応答の通話処理動作の時間を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-268">A system of auto attendants may only need to set after hours call handling behavior for the first-level auto attendant.</span></span> <span data-ttu-id="aea0c-269">入れ子になった自動応答は、第1レベルの自動応答によって呼び出されることはありませんが、システムは使用する自動応答ごとに、時間の経過後の動作を定義できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-269">Nested auto attendants may not even be called by the first-level auto attendant, but alternately the system can define after-hours behavior for each auto attendant it uses.</span></span>

<span data-ttu-id="aea0c-270">最初は、勤務時間が午前12:00 から始まり、日曜日から土曜日までの 12:00 pm で終わるように定義されています。</span><span class="sxs-lookup"><span data-stu-id="aea0c-270">Initially, the business hours are defined to start at 12:00 am and end at 12:00 pm, Sunday through Saturday.</span></span> <span data-ttu-id="aea0c-271">営業時間外のすべての時間は *、時間の経過後*も考慮されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-271">All hours that aren't during business hours are considered *after hours*.</span></span>


![after hours の通話フローの設定のスクリーンショット](media/aa-afterhour.png)
 * * *

<span data-ttu-id="aea0c-273">![前のスクリーンショットの吹き出しである番号1のアイコン ](media/teamscallout1.png) 。 [ **24/7 の選択**] をクリックして、この自動応答の営業時間をすべて時間にすることができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-273">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) You can click **Select 24/7** to make all hours business hours for this auto attendant.</span></span>

<span data-ttu-id="aea0c-274">![番号2のアイコン、前のスクリーンショットの吹き出し ](media/teamscallout2.png) [既定の**設定に**戻す] オプションを選択して、スケジュールのすべての変更を元に戻し、勤務時間の既定の定義に 9:00 am から 5:00 pm の月曜日から金曜日までの既定の定義に戻ります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-274">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) Select the **Reset to default** option to revert all changes in the schedule and return to the default definition of business hours as 9:00 am to 5:00 pm Monday to Friday.</span></span>

<span data-ttu-id="aea0c-275">![数値3のアイコン、前のスクリーンショットの吹き出し ](media/teamscallout3.png) [**すべての時間をクリア**] を選んで、スケジュールを完全に消去します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-275">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) Select **Clear all hours** to completely clear the schedule.</span></span> <span data-ttu-id="aea0c-276">このチェックボックスをオンにして、[時間] の設定を解除することはお勧めできません。そのため、業務時間を完全に再利用する場合にのみ、このオプションを使用してください。</span><span class="sxs-lookup"><span data-stu-id="aea0c-276">Selecting this and leaving the hours unset is not recommended, so use this option only if you want to completely redo your business hours.</span></span>

<span data-ttu-id="aea0c-277">![数値4のアイコン、前 ](media/teamscallout4.png) ![ のスクリーンショットの数字5のスクリーンショットアイコン、前のスクリーンショットの [開始] または [終了] をクリックして、曜日の ](media/teamscallout5.png) 開始時刻**また**は終了**End at**時刻をカスタマイズし、表示されるリストから新しい時刻を選びます。  </span><span class="sxs-lookup"><span data-stu-id="aea0c-277">![Icon of the number 4,  a callout in the previous screenshot](media/teamscallout4.png)  ![Icon of the number 5,  a callout in the previous screenshot](media/teamscallout5.png) To customize start or end time for a day of the week, click on **Start at** or **End at** time you wish to reset and select the new time from the list that appears.</span></span> <span data-ttu-id="aea0c-278">リストでは、15分間隔で事業時間を選ぶことができます。ここで選択する業務時間は、[**一般情報**] ページで設定したタイムゾーンに基づいています。</span><span class="sxs-lookup"><span data-stu-id="aea0c-278">The list allows you to select business hours in 15-minute intervals, and the business hours you select here are based on the time zone that you set on the **General info** page.</span></span>

 <!-- The **Apply to all days** option can be used to reset all days of the week to match the settings for that day. This makes setting weekdays and weekends to different hours easier.-->

<span data-ttu-id="aea0c-279">![1つ目のスクリーンショットのアイコンで区切りを設定します (昼食の場合など ](media/teamscallout6.png) )。 [この曜日に新しい**時刻を追加**する] を選択して、新しいテーブルの行を作成し、新しい [開始時刻] と [終了時刻] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-279">![Icon of the number 6,  a callout in the previous screenshot](media/teamscallout6.png)  To set up a break (a lunch break, for example), select **Add new time** for that day of the week to create a new table row, and select new start and end times.</span></span> <span data-ttu-id="aea0c-280">営業時間内に複数の休憩時間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-280">You can set multiple breaks within business hours.</span></span>

<span data-ttu-id="aea0c-281">時間の後に使用可能な[コールフロー](#call-flow)オプションは、勤務時間内で利用可能なオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="aea0c-281">The [Call flow](#call-flow) options available after hours are the same as the options available during business hours.</span></span> <span data-ttu-id="aea0c-282">情報の入力ページを下にスクロールして、時間単位の通話のオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-282">Scroll down on the information entry page to set after hours call flow options.</span></span>

* * *

<span data-ttu-id="aea0c-283">選択が完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aea0c-283">When you are finished with your selections, click **Next**.</span></span> <span data-ttu-id="aea0c-284">左側のナビゲーションで [**リソースアカウント**] をクリックして、[リソースアカウント] ページに直接移動し、自動応答をリソースアカウントに関連付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-284">You can also click on **Resource accounts** in the left navigation to go straight to the Resource accounts page and associate your auto attendant to a resource account.</span></span>

##### <a name="call-flow-during-holidays"></a><span data-ttu-id="aea0c-285">休日中の通話フロー</span><span class="sxs-lookup"><span data-stu-id="aea0c-285">Call flow during holidays</span></span>

<span data-ttu-id="aea0c-286"><a name="holidaygreetings"> </a></span><span class="sxs-lookup"><span data-stu-id="aea0c-286"><a name="holidaygreetings"> </a></span></span>

<span data-ttu-id="aea0c-287">各自動応答には、最大 20 個の決められた休業日を追加できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-287">You can add up to 20 scheduled holidays to each auto attendant.</span></span> <span data-ttu-id="aea0c-288">組織では、「 [Microsoft Teams で祝日を設定](set-up-holidays-in-teams.md)する」の説明に従って、すでに休日を定義している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-288">Your organization may already have defined holidays as described in [Set up holidays in Microsoft Teams](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="aea0c-289">見つからない場合は、次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-289">If not you will see the following screen:</span></span> 

![スクリーンショット: 休日は設定されていません](media/aa-no-holidays.png)

<span data-ttu-id="aea0c-291">![番号1のアイコン、前のスクリーンショットの吹き出し。 ](media/teamscallout1.png) 自動応答で休日のカスタムコールフローを設定するには、[ **+ Add** **New ホリデー call flow** ] 画面をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aea0c-291">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) To set a custom call flow for a holiday on the auto attendant, click **+ Add** the see the **New holiday call flow** screen.</span></span>
> [!TIP]
> <span data-ttu-id="aea0c-292">休日を作成するには、**組織全体の設定**の休日の画面に移動し  >  **Holidays**ます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-292">To create Holidays you can  go to the screen at **Org-wide settings** > **Holidays**.</span></span>  



![スクリーンショット: コールハンドラーを追加する](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

* * *

<span data-ttu-id="aea0c-294">![番号1のアイコン、前のスクリーンショットの吹き出しに ](media/teamscallout1.png) 新しい通話フローの**名前**を入力します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-294">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png)  Enter a **Name** for your new call flow.</span></span>

<span data-ttu-id="aea0c-295">![[番号 2] のアイコン、前のスクリーンショットの吹き出し ](media/teamscallout2.png) (既に祝日を作成している場合は、**休日の**プルダウンメニューに表示され、それらを選ぶことができます)。</span><span class="sxs-lookup"><span data-stu-id="aea0c-295">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) If you've already created holidays, you'll see them in the **Holiday** pull-down menu and can select them.</span></span> <span data-ttu-id="aea0c-296">使用されていないオプションが表示されることがあります。必要に応じて編集できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-296">You might see an unused option that you can edit into what you need.</span></span> <span data-ttu-id="aea0c-297">表示されていない場合は、プルダウンリストの下部にある [**追加**] をクリックして新しい休日を作成します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-297">If not, click on **Add** at the bottom of the pull-down list to create a new Holiday.</span></span>  <span data-ttu-id="aea0c-298">休日の作成に使用した手順については、「 [Microsoft Teams で休日を設定](set-up-holidays-in-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aea0c-298">See [Set up holidays in Microsoft Teams](set-up-holidays-in-teams.md) for the steps used to create a holiday.</span></span> 

<span data-ttu-id="aea0c-299">休日のコールフローの名前は、最大64文字で、組織に対して一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-299">A holiday call flow name can be up to 64 characters long and must be unique for the organization.</span></span> <span data-ttu-id="aea0c-300">たとえば、同じ組織内で "感謝祭" という名前の休日のコールフローを2つ持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="aea0c-300">For example, you can't have two holiday call flows named "Thanksgiving" in the same organization.</span></span> <span data-ttu-id="aea0c-301">自動応答には、設定した各休日のコールフローを設定できますが、カスタマイズされた応答メッセージ以外に計画された共通の動作のセットが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-301">Your auto attendant can have a call flow for each Holiday you've set up, but you might want to have a common set of behaviors planned other than a customized greeting.</span></span>

<span data-ttu-id="aea0c-302">![数値3のアイコン (前のスクリーンショットの吹き出し) ](media/teamscallout3.png) 休日の通話フローに使用できる [[グリーティング](#call-flow)] オプションは、勤務時間中に利用可能なオプションと同じです。</span><span class="sxs-lookup"><span data-stu-id="aea0c-302">![Icon of the number 3,  a callout in the previous screenshot](media/teamscallout3.png) The [Greetings](#call-flow) options available for a holiday call flow are the same as the options available during business hours.</span></span> <span data-ttu-id="aea0c-303">応答メッセージの再生後に実行される**操作**も似ていますが、利用可能な操作は**切断**または**リダイレクト**のみです。また、[**リダイレクト先**] オプションでは、演算子は使用できません。</span><span class="sxs-lookup"><span data-stu-id="aea0c-303">The **Actions** performed after the greeting plays is also similar, except that the only available actions are to **Disconnect** or **Redirect to**, and when choosing the **Redirect to** option the Operator is not one of the available choices.</span></span> <span data-ttu-id="aea0c-304">休日の流れに固有のメニューを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="aea0c-304">You can't set up a menu specific to a Holiday flow.</span></span>

> [!NOTE]
> <span data-ttu-id="aea0c-305">既定では、休日期間中に受信したすべての通話は、応答メッセージ (存在する場合) の後に**切断**されるように設定されているため、カスタム動作を必要とする場合は、リダイレクトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-305">By default, all calls received during a holiday period are set to **Disconnect** after the greeting (if any), so you must specify a redirect if you want a custom behavior.</span></span>

![[休日] ページの通話フローのスクリーンショット](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

<span data-ttu-id="aea0c-307">[保存] をクリックして、休日の通話フローの作成を終了します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-307">Click on Save to finish creating the Holiday call flow.</span></span> <span data-ttu-id="aea0c-308">ホリデーシーズンの通話フローを作成すると、休日の画面に**通話**フローが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-308">Once you have created a Holiday call flow, it will show up on the **Call Flows during holidays** screen.</span></span>

<span data-ttu-id="aea0c-309">[**次**へ] をクリック**して [** ダイヤルの範囲] を設定し、[**戻る**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aea0c-309">Click on **Next** to set Dial scope, **Back** to make changes to after hour call flows, and **Submit** if you are finished.</span></span> <span data-ttu-id="aea0c-310">左側のナビゲーションで [**リソースアカウント**] をクリックして、[リソースアカウント] ページに直接移動し、自動応答をリソースアカウントに関連付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-310">You can also click on **Resource accounts** in the left navigation to go straight to the Resource accounts page and associate your auto attendant to a resource account.</span></span>

#### <a name="dial-scope"></a><span data-ttu-id="aea0c-311">ダイヤルスコープ</span><span class="sxs-lookup"><span data-stu-id="aea0c-311">Dial scope</span></span>

<span data-ttu-id="aea0c-312"><a name="dialscope"> </a></span><span class="sxs-lookup"><span data-stu-id="aea0c-312"><a name="dialscope"> </a></span></span>

![[ダイヤルの範囲] ページを示すスクリーンショット](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

<span data-ttu-id="aea0c-314">このページでは、ユーザーが組織に発信したときに、自分のディレクトリに一覧表示されていて、名前でダイヤルできるユーザーを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-314">On this page, you can set who is listed in your directory and available for Dial by Name when a person calls your organization.</span></span> <span data-ttu-id="aea0c-315">以前の画面では、[名前でダイヤル] は既定で**無効**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="aea0c-315">Dial by name is set to **Off** by default in an earlier screen.</span></span> <span data-ttu-id="aea0c-316">内線番号が選択され**て**いる場合は、拡張機能を持つすべてのユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-316">All users with an extension will be available if **Dial by extension** was selected earlier.</span></span>

<span data-ttu-id="aea0c-317">![番号1のアイコン、前のスクリーンショットの吹き出しに ](media/teamscallout1.png) は、**すべてのオンラインユーザー**または**カスタムユーザーグループ**のいずれかのオプションが**含ま**れています。</span><span class="sxs-lookup"><span data-stu-id="aea0c-317">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) **Include** The options in this section are either **All online users** or **Custom user groups**</span></span>

<span data-ttu-id="aea0c-318">[すべての**オンラインユーザー**] を選択すると、対象ユーザーがすべてディレクトリ検索に含まれます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-318">If you select **All online users**, all eligible users are included in directory search.</span></span>

<span data-ttu-id="aea0c-319">**カスタムユーザーグループ**このオプションでは、組織内で既に作成されている Microsoft 365 グループ、配布リスト、またはセキュリティグループを検索して選択することができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-319">**Custom user groups** This option lets you search for and select a Microsoft 365 group, distribution list, or security group already created in your organization.</span></span> <span data-ttu-id="aea0c-320">ユーザーは、選択した Microsoft 365 グループ、配布リスト、またはセキュリティグループに含まれており、**電話システムのライセンスを持つオンラインユーザー**であるか、Skype For business Server を使用してオンプレミスでホストされている場合、ディレクトリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-320">Users are added to the directory if they are in the chosen Microsoft 365 group, distribution list, or security group and they are **Online users with a Phone System license** or hosted on-premises using Skype for Business Server.</span></span> <span data-ttu-id="aea0c-321">複数の Microsoft 365 グループ、配布リスト、セキュリティグループをディレクトリに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-321">You can add multiple Microsoft 365 groups, distribution lists, and security groups to the directory.</span></span>

<span data-ttu-id="aea0c-322"><a name="dialscope"> </a></span><span class="sxs-lookup"><span data-stu-id="aea0c-322"><a name="dialscope"> </a></span></span>

<span data-ttu-id="aea0c-323">このページでは、組織内のユーザーが自分の組織に電話をかけているユーザーに対して、自分のディレクトリに一覧表示され、名前でダイヤルできるように設定することができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-323">On this page, you can set up which users in your organization will be listed in your directory and available for Dial by Name when a person that calls in to your organization.</span></span>

<span data-ttu-id="aea0c-324">![数字2のアイコン、前のスクリーンショットの吹き出しは ](media/teamscallout2.png) 、このセクションのオプションを**除外**することで、特定のユーザーまたはユーザーのグループを組織のディレクトリから除外できるようにします。</span><span class="sxs-lookup"><span data-stu-id="aea0c-324">![Icon of the number 2,  a callout in the previous screenshot](media/teamscallout2.png) **Exclude** The options in this section let you exclude specific users or groups of users from the organization's directory.</span></span>

<span data-ttu-id="aea0c-325">[**なし**] を選択すると、対象ユーザーはすべてディレクトリ検索に含まれます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-325">If you select **None**, all eligible users are included in directory search.</span></span>

<span data-ttu-id="aea0c-326">**カスタムユーザーグループ**組織で作成された Microsoft 365 グループ、配布リスト、またはセキュリティグループを検索できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-326">**Custom user group** You can search for a Microsoft 365 group, distribution list, or security group that has been created in your organization.</span></span> <span data-ttu-id="aea0c-327">そのグループ内のユーザーはディレクトリ検索から除外されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-327">Users in that group are excluded from directory search.</span></span> <span data-ttu-id="aea0c-328">複数の Microsoft 365 グループ、配布リスト、セキュリティグループを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-328">You can add multiple Microsoft 365 groups, distribution lists, and security groups.</span></span>

<span data-ttu-id="aea0c-329">[名前でダイヤルする] が有効になっているときに設定を既定のままにすると、対象ユーザーがすべてディレクトリ検索に含まれます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-329">If you leave settings at their default when Dial by Name is enabled, all eligible users are included in directory search.</span></span>

> [!NOTE]
> <span data-ttu-id="aea0c-330">新しいユーザーの名前がディレクトリに表示されるまでに、最大36時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-330">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span> <span data-ttu-id="aea0c-331">他のユーザーが音声認識で名前でダイヤルを使用している場合、この機能では新しいアカウントを使用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-331">When someone uses Dial by Name with speech recognition, new accounts may not be available for this feature.</span></span>

<span data-ttu-id="aea0c-332">すべての必要なフィールドを入力し、通話処理のメニューとオプションを設定したら、[**次**へ] をクリックしてリソースアカウントの関連付けに進みます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-332">After you enter all the required fields and set up call handling menus and options, click **Next** to proceed to associating a resource account.</span></span>

#### <a name="resource-accounts"></a><span data-ttu-id="aea0c-333">リソースアカウント</span><span class="sxs-lookup"><span data-stu-id="aea0c-333">Resource accounts</span></span>

<span data-ttu-id="aea0c-334">自動応答には、リソースアカウントが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-334">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="aea0c-335">第1レベルの自動応答では、少なくとも1つのリソースアカウントにサービス番号が関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-335">First level auto attendants will definitely need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="aea0c-336">必要に応じて、複数のリソースアカウントを1つの自動応答に割り当てることができます。それぞれに個別のサービス番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-336">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="aea0c-337">まだリソースアカウントを自動応答に構成していない場合は、次の画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-337">If you haven't already configured a resource account to your auto attendant, you would see the following screen:</span></span> 

![スクリーンショット: オプションのリソースアカウント管理](media/aa-ra-optional.png) 

<span data-ttu-id="aea0c-339">![1つ以上の ](media/teamscallout1.png) 既存のリソースアカウントと割り当てられていないリソースアカウントを自動応答に追加するための、1つ**Add accounts**以上の既存のリソースアカウントと割り当てられていないリソースアカウントを追加するための1つ以上の [番号 1] のアイコン。</span><span class="sxs-lookup"><span data-stu-id="aea0c-339">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) To add one or more existing and unassigned resource accounts to the auto attendant, click **Add accounts** and search and select them from the provided dialogs.</span></span>

![新しい [応答の概要] ビューのスクリーンショット](media/aa-assigned.png)

<span data-ttu-id="aea0c-341">![番号1のアイコン、前のスクリーンショットの吹き出し ](media/teamscallout1.png) 。追加のリソースアカウントを追加するには、[ **+ アカウントの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aea0c-341">![Icon of the number 1,  a callout in the previous screenshot](media/teamscallout1.png) To add an additional resource account, click on **+ Add account**.</span></span>

![1つ前のスクリーンショットの吹き出しである番号2のアイコン](media/teamscallout2.png) <span data-ttu-id="aea0c-343">この自動応答に割り当てられているリソースアカウントまたはアカウントがリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-343">The resource account or accounts assigned to this auto attendant are shown in a list.</span></span>

## <a name="edit-auto-attendants"></a><span data-ttu-id="aea0c-344">自動応答の編集</span><span class="sxs-lookup"><span data-stu-id="aea0c-344">Edit auto attendants</span></span>

<span data-ttu-id="aea0c-345">新しい自動応答を保存すると、[**自動応答**] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-345">After you save your new auto attendant, it is listed on the **Auto attendants** page.</span></span> <span data-ttu-id="aea0c-346">このページでは、[名前]、[関連付けられているリソースアカウント]、[言語]、[割り当てられたオペレーター] など、設定したオプションの一部をすばやく確認できます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-346">That page allows you to quickly see some of the options that you have set up, including the name, associated resource account, language, and assigned Operator.</span></span>

![応答一覧のスクリーンショット](media/aa-list.png)

<span data-ttu-id="aea0c-348">自動応答の設定を変更する場合は、自動応答を選び、操作ウィンドウで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aea0c-348">If you want to change auto attendant settings, select the auto attendant, and then in the Action pane click **Edit**.</span></span>

<!-- To quickly place a test call to your auto attendant, click the **Test** button in the Action pane. -->

<!-- ## Summary view

You can use the Summary page to review the settings you've created.

![screenshot of the new attendant summary view](media/aa-new-summary.png)

Press the **Create** button to finish setup of your new auto attendant. -->

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="aea0c-349">Powershell を使用して自動応答を作成する</span><span class="sxs-lookup"><span data-stu-id="aea0c-349">Create an auto attendant with Powershell</span></span>

<span data-ttu-id="aea0c-350">PowerShell を使用して自動応答を作成し、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-350">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="aea0c-351">自動応答を管理するために必要なコマンドレットを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-351">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="aea0c-352">新しい-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="aea0c-352">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="aea0c-353">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="aea0c-353">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="aea0c-354">CsAutoAttendant の入手</span><span class="sxs-lookup"><span data-stu-id="aea0c-354">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant?view=skype-ps)
- [<span data-ttu-id="aea0c-355">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="aea0c-355">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="aea0c-356">CsAutoAttendant の削除</span><span class="sxs-lookup"><span data-stu-id="aea0c-356">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="aea0c-357">新規-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="aea0c-357">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="aea0c-358">新しい-Csonline Audiofile</span><span class="sxs-lookup"><span data-stu-id="aea0c-358">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="aea0c-359">新規-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="aea0c-359">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="aea0c-360">エクスポート-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="aea0c-360">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="aea0c-361">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="aea0c-361">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="aea0c-362">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="aea0c-362">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="aea0c-363">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="aea0c-363">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="aea0c-364">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="aea0c-364">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="aea0c-365">新規-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="aea0c-365">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="aea0c-366">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="aea0c-366">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="aea0c-367">インポート-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="aea0c-367">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="aea0c-368">新規-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="aea0c-368">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="aea0c-369">Windows PowerShell の詳細について</span><span class="sxs-lookup"><span data-stu-id="aea0c-369">More about Windows PowerShell</span></span>

- <span data-ttu-id="aea0c-370">Windows PowerShell では、ユーザーの管理と、許可または許可されていないユーザーの操作について説明します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-370">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="aea0c-371">Windows PowerShell を使用すると、日常業務を簡素化できる単一の管理ポイントから Microsoft 365 または Office 365 および Microsoft Teams を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="aea0c-371">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Microsoft Teams from a single point of administration that can simplify your daily work.</span></span> <span data-ttu-id="aea0c-372">Windows PowerShell の使用を開始するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aea0c-372">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="aea0c-373">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="aea0c-373">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="aea0c-374">Office 365 PowerShell を使用する必要がある理由</span><span class="sxs-lookup"><span data-stu-id="aea0c-374">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="aea0c-375">Windows PowerShell には、多くのユーザーの変更を一度に設定するなど、Microsoft 365 管理センターを使用する場合にのみ、速度、シンプルさ、生産性の向上を実現するための多くの利点があります。</span><span class="sxs-lookup"><span data-stu-id="aea0c-375">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as making setting changes for many users at once.</span></span> <span data-ttu-id="aea0c-376">次のトピックでこれらの利点について説明します。</span><span class="sxs-lookup"><span data-stu-id="aea0c-376">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="aea0c-377">Office 365 PowerShell で Microsoft 365 または Office 365 を管理する</span><span class="sxs-lookup"><span data-stu-id="aea0c-377">Manage Microsoft 365 or Office 365 with Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="aea0c-378">Windows PowerShell による Skype for Business Online の管理</span><span class="sxs-lookup"><span data-stu-id="aea0c-378">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="aea0c-379">関連項目</span><span class="sxs-lookup"><span data-stu-id="aea0c-379">Related topics</span></span>

[<span data-ttu-id="aea0c-380">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="aea0c-380">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="aea0c-381">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="aea0c-381">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="aea0c-382">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="aea0c-382">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="aea0c-383">New-CsOrganizationalAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="aea0c-383">New-CsOrganizationalAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[<span data-ttu-id="aea0c-384">クラウドの自動応答とは</span><span class="sxs-lookup"><span data-stu-id="aea0c-384">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="aea0c-385">小規模企業の例—自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="aea0c-385">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)  
