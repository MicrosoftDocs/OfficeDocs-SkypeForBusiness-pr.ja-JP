---
title: Microsoft Teams の自動応答を設定する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
description: Microsoft Teams の自動応答を設定してテストする方法について説明します。
ms.openlocfilehash: deb9bf013136bb8efd9171e5562de5e2ba1b631f
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347868"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="26cfd-103">自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="26cfd-103">Set up an auto attendant</span></span>

<span data-ttu-id="26cfd-104">自動応答を使用すると、ユーザーは組織に電話をかけ、メニュー システムを操作して、適切な部門、通話キュー、ユーザー、またはオペレーターに話しかけたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="26cfd-105">Microsoft Teams 管理センターまたは PowerShell を使用して、組織の自動応答を作成できます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="26cfd-106">この記事の手順に従う前に[、「Teams](plan-auto-attendant-call-queue.md)の自動応答と通話キューの[](plan-auto-attendant-call-queue.md#getting-started)計画」を読み、開始手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="26cfd-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="26cfd-107">自動応答では、発信者の入力に基づいて、次のいずれかの発信先に通話を発信できます。 <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="26cfd-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="26cfd-108">**オペレーター** - 自動応答に定義された演算子。</span><span class="sxs-lookup"><span data-stu-id="26cfd-108">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="26cfd-109">演算子の定義は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="26cfd-109">Defining an operator is optional.</span></span> <span data-ttu-id="26cfd-110">演算子は、このリストの他の宛先として定義できます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-110">The operator can be defined as any of the other destinations in this list.</span></span>
- <span data-ttu-id="26cfd-111">**組織内のユーザー** - 音声通話を受信できる組織内のユーザー。</span><span class="sxs-lookup"><span data-stu-id="26cfd-111">**Person in the organization** - a person in your organization who can receive voice calls.</span></span> <span data-ttu-id="26cfd-112">これは、オンライン ユーザーまたは Skype for Business Server を使用するオンプレミスでホストされているユーザーです。</span><span class="sxs-lookup"><span data-stu-id="26cfd-112">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="26cfd-113">**音声アプリ** - 別の自動応答または通話キュー。</span><span class="sxs-lookup"><span data-stu-id="26cfd-113">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="26cfd-114">(この宛先を選ぶときに、自動応答または通話キューに関連付けられているリソース アカウントを選ぶ。</span><span class="sxs-lookup"><span data-stu-id="26cfd-114">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="26cfd-115">**ボイス** メール - 指定した Microsoft 365 グループに関連付けられているボイス メールボックス。</span><span class="sxs-lookup"><span data-stu-id="26cfd-115">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="26cfd-116">**外部電話番号** - 任意の電話番号。</span><span class="sxs-lookup"><span data-stu-id="26cfd-116">**External phone number** - any phone number.</span></span> <span data-ttu-id="26cfd-117">(外部 [転送の技術的な詳細を参照してください](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details))。</span><span class="sxs-lookup"><span data-stu-id="26cfd-117">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="26cfd-118">**お知** らせ - オーディオ ファイルを再生します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-118">**Announcement** - Play an audio file.</span></span> <span data-ttu-id="26cfd-119">アップロードした録音されたアナウンス メッセージで、オーディオとして保存されます。WAV、.MP3、または .WMA 形式。</span><span class="sxs-lookup"><span data-stu-id="26cfd-119">A recorded announcement message you upload that's saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="26cfd-120">記録できるサイズは 5 MB 以下です。</span><span class="sxs-lookup"><span data-stu-id="26cfd-120">The recording can be no larger than 5 MB.</span></span> <span data-ttu-id="26cfd-121">システムがアナウンスを再生し、自動応答メニューに戻ります。</span><span class="sxs-lookup"><span data-stu-id="26cfd-121">The system plays the announcement, and then returns to the auto attendant menu.</span></span>
- <span data-ttu-id="26cfd-122">**お知** らせ - メッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-122">**Announcement** - Type in a message.</span></span> <span data-ttu-id="26cfd-123">システムで読み取るテキスト。</span><span class="sxs-lookup"><span data-stu-id="26cfd-123">Text you want the system to read.</span></span> <span data-ttu-id="26cfd-124">最大 1000 文字を入力できます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-124">You can enter up to 1000 characters.</span></span> <span data-ttu-id="26cfd-125">システムがアナウンスを再生し、自動応答メニューに戻ります。</span><span class="sxs-lookup"><span data-stu-id="26cfd-125">The system plays the announcement, and then returns to the auto attendant menu.</span></span>

<span data-ttu-id="26cfd-126">自動応答を設定する場合、さまざまな段階でこれらのオプションのいずれかを選択するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-126">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="26cfd-127">自動応答を設定するには、Teams 管理センターで [音声] を展開し、[**自動** 応答] を選択し、[追加] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="26cfd-127">To set up an auto attendant, in the Teams admin center, expand **Voice**, select **Auto attendants**, and then select **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="26cfd-128">一般的な情報</span><span class="sxs-lookup"><span data-stu-id="26cfd-128">General info</span></span>

![名前、オペレーター、タイム ゾーン、言語、音声入力の自動応答設定のスクリーンショット](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="26cfd-130">上部のボックスに自動応答の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-130">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="26cfd-131">演算子を指定する場合は、演算子の呼び出し先を指定します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-131">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="26cfd-132">これは省略可能です (ただし、推奨)。</span><span class="sxs-lookup"><span data-stu-id="26cfd-132">This is optional (but recommended).</span></span> <span data-ttu-id="26cfd-133">発信者 **がメニューから** 抜け出し、指定されたユーザーと話し合う場合にオペレーター オプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-133">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="26cfd-134">この自動応答のタイム ゾーンを指定します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-134">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="26cfd-135">タイム ゾーンは、営業時間外の別のコール フローを作成する場合に、営業時間 [の計算に使用されます](#call-flow-for-after-hours)。</span><span class="sxs-lookup"><span data-stu-id="26cfd-135">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="26cfd-136">この自動 [応答でサポートされている](create-a-phone-system-auto-attendant-languages.md) 言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-136">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="26cfd-137">これは、システム生成の音声プロンプトに使用される言語です。</span><span class="sxs-lookup"><span data-stu-id="26cfd-137">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="26cfd-138">音声入力を有効にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-138">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="26cfd-139">有効にすると、すべてのメニュー オプションの名前が音声認識キーワードになります。</span><span class="sxs-lookup"><span data-stu-id="26cfd-139">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="26cfd-140">たとえば、発信者は"1" と言ってキー 1 に対応付けられたメニュー オプションを選択したり、"営業" と言って "営業" という名前のメニュー オプションを選択したりします。</span><span class="sxs-lookup"><span data-stu-id="26cfd-140">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

> [!NOTE]
> <span data-ttu-id="26cfd-141">手順 4 で音声入力をサポートしない言語を選択した場合、このオプションは無効になります。</span><span class="sxs-lookup"><span data-stu-id="26cfd-141">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="26cfd-142">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-142">Select **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="26cfd-143">コール フロー</span><span class="sxs-lookup"><span data-stu-id="26cfd-143">Call flow</span></span>

![あいさつメッセージの設定のスクリーンショット](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="26cfd-145">自動応答が通話に応答するときに応答メッセージを再生する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-145">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="26cfd-146">[オーディオ ファイル **の再生] を選** ぶと、[ファイルのアップロード] ボタンを使用して、音声として保存された録音されたあいさつメッセージをアップロードできます。WAV、.MP3、または .WMA 形式。</span><span class="sxs-lookup"><span data-stu-id="26cfd-146">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="26cfd-147">記録できるサイズは 5 MB 以下です。</span><span class="sxs-lookup"><span data-stu-id="26cfd-147">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="26cfd-148">[あいさつ文を入力] を選択した場合、自動応答が通話に応答すると、入力したテキスト (最大 1000 文字) が読み上げされます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-148">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![通話ルーティング設定のスクリーンショット](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="26cfd-150">通話のルーティング方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-150">Choose how you want to route the call.</span></span>

<span data-ttu-id="26cfd-151">[切断] を **選ぶ** と、自動応答によって通話が切断されます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-151">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="26cfd-152">[通話の **リダイレクト] を選択** した場合は、通話ルーティング先のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-152">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="26cfd-153">[再生] メニュー **オプションを** 選択した場合は、[オーディオ ファイルの再生] または [あいさつメッセージを入力] を選び、メニュー オプションとディレクトリ検索から選びます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-153">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="26cfd-154">メニュー オプション</span><span class="sxs-lookup"><span data-stu-id="26cfd-154">Menu options</span></span>

![ダイヤル キー オプションのスクリーンショット](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="26cfd-156">ダイヤル オプションの場合は、電話のキーパッドの 0 から 9 キーを通話ルーティング先の 1 つに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-156">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="26cfd-157">(キー \* (Repeat) と (Back) はシステムによって予約され、再割り当 \# てはできません)。</span><span class="sxs-lookup"><span data-stu-id="26cfd-157">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="26cfd-158">キー マッピングは連続している必要はなかった。</span><span class="sxs-lookup"><span data-stu-id="26cfd-158">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="26cfd-159">たとえば、キー 0、1、3 がオプションにマップされたメニューを作成し、2 つのキーは使用されません。</span><span class="sxs-lookup"><span data-stu-id="26cfd-159">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the two key isn't used.</span></span>

<span data-ttu-id="26cfd-160">ゼロ キーを設定している場合は、オペレーターにマッピングすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="26cfd-160">We recommend mapping the zero key to the operator if you have configured one.</span></span> <span data-ttu-id="26cfd-161">オペレーターが任意のキーに設定されていない場合、音声コマンドの "オペレーター" も無効になります。</span><span class="sxs-lookup"><span data-stu-id="26cfd-161">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="26cfd-162">メニュー オプションごとに、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-162">For each menu option, specify the following settings:</span></span>

- <span data-ttu-id="26cfd-163">**ダイヤル キー** - このオプションにアクセスするには、電話機のキーパッドのキー。</span><span class="sxs-lookup"><span data-stu-id="26cfd-163">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="26cfd-164">音声入力が使用可能な場合は、発信者はオプションにアクセスするためにこの番号を音声で入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-164">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="26cfd-165">**音声コマンド** - 音声入力が有効になっている場合に、発信者がこのオプションにアクセスするために与える音声コマンドを定義します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-165">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="26cfd-166">"カスタマー サービス" や "Operations and Grounds" のような複数の単語を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-166">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="26cfd-167">たとえば、発信者は 2 を押したり、"2" と言い、"営業" と言って 2 つのキーにマップされたオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-167">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the two key.</span></span> <span data-ttu-id="26cfd-168">このテキストは、サービスの確認プロンプトの音声合成によってもレンダリングされます。これは、"通話を販売に転送する" のような場合があります。</span><span class="sxs-lookup"><span data-stu-id="26cfd-168">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="26cfd-169">**[リダイレクト先** ] - 発信者がこのオプションを選択するときに使用される通話ルーティング先。</span><span class="sxs-lookup"><span data-stu-id="26cfd-169">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="26cfd-170">自動応答または通話キューにリダイレクトする場合は、関連付けられているリソース アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-170">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="26cfd-171">ディレクトリ検索</span><span class="sxs-lookup"><span data-stu-id="26cfd-171">Directory search</span></span>

<span data-ttu-id="26cfd-172">ダイヤル キーを接続先に割り当てる場合は、ディレクトリ検索で **[なし** ] を選択することをお **勧めします**。</span><span class="sxs-lookup"><span data-stu-id="26cfd-172">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="26cfd-173">発信者が特定の宛先に割り当てられているキーを使用して名前または内線番号をダイヤルしようとすると、発信者が名前または内線番号の入力を完了する前に、予期せず宛先にルーティングされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="26cfd-173">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="26cfd-174">ディレクトリ検索用に別の自動応答を作成し、ダイヤル キーを使用してメインの自動応答へのリンクを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="26cfd-174">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="26cfd-175">ダイヤル キーを割り当てなかった場合は、ディレクトリ検索のオプションを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="26cfd-175">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="26cfd-176">**名前でダイヤル** - このオプションを有効にすると、発信者はユーザーの名前を音声で入力したり、電話機のキーパッドに入力できます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-176">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="26cfd-177">オンライン ユーザー、または Skype for Business Server を使用するオンプレミスでホストされているユーザーは、対象ユーザーであり、名前でダイヤルで検索できます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-177">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="26cfd-178">(ダイヤル スコープ ページのディレクトリに含まれるユーザーと含まれていないユーザー [を設定](#dial-scope) できます)。</span><span class="sxs-lookup"><span data-stu-id="26cfd-178">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="26cfd-179">**内線番号で** ダイヤルする - このオプションを有効にすると、発信者は内線番号にダイヤルして組織内のユーザーと接続できます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-179">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="26cfd-180">Skype for Business Server を使用するオンライン ユーザーまたはオンプレミスでホストされているユーザーは対象ユーザーであり、内線でダイヤル **機能を使用して見つけることができます**。</span><span class="sxs-lookup"><span data-stu-id="26cfd-180">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="26cfd-181">(ダイヤル スコープ ページのディレクトリに含まれるユーザーと含まれていないユーザー [を設定](#dial-scope) できます)。</span><span class="sxs-lookup"><span data-stu-id="26cfd-181">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="26cfd-182">ダイヤルバイ拡張機能を利用するには、Active Directory または Azure Active Directory で定義されている次のいずれかの電話機属性の一部として、内線番号を指定[](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)する必要があります (詳細については、「ユーザーを個別に、または一括で追加する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="26cfd-182">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phones attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="26cfd-183">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="26cfd-183">OfficePhone</span></span>
- <span data-ttu-id="26cfd-184">HomePhone</span><span class="sxs-lookup"><span data-stu-id="26cfd-184">HomePhone</span></span>
- <span data-ttu-id="26cfd-185">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="26cfd-185">Mobile/MobilePhone</span></span>
- <span data-ttu-id="26cfd-186">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="26cfd-186">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="26cfd-187">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="26cfd-187">OtherTelephone</span></span>

<span data-ttu-id="26cfd-188">ユーザーの電話番号フィールドに内線番号を入力するために必要な形式は次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="26cfd-188">The required format to enter the extension in the user phone number field is either:</span></span>

- <span data-ttu-id="26cfd-189">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="26cfd-189">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="26cfd-190">*+\<phone number>x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="26cfd-190">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="26cfd-191">*x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="26cfd-191">*x\<extension>*</span></span>

- <span data-ttu-id="26cfd-192">例 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="26cfd-192">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="26cfd-193">例 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="26cfd-193">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="26cfd-194">例 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="26cfd-194">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="26cfd-195">拡張機能は [、Microsoft 365](https://admin.microsoft.com/) 管理センターまたは Azure Active Directory 管理センター [で設定できます](https://aad.portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="26cfd-195">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="26cfd-196">自動応答と通話キューで変更を利用するには、最大で 12 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="26cfd-196">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="26cfd-197">名前でダイヤル機能と内線番号でダイヤル機能の両方を使用する場合は、メインの自動応答にダイヤル キーを割り当て、名前でダイヤルが有効になっている自動応答にアクセス **できます**。</span><span class="sxs-lookup"><span data-stu-id="26cfd-197">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="26cfd-198">その自動応答内で、内線番号自動応答でダイヤルに到達する 1 つのキー (関連付けられた文字がない) **を割り** 当てできます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-198">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="26cfd-199">ディレクトリ検索オプションを選択したら、[ **次へ** ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="26cfd-199">Once you have selected a **Directory search** option, select **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="26cfd-200">営業時間外のコール フロー</span><span class="sxs-lookup"><span data-stu-id="26cfd-200">Call flow for after hours</span></span>

![営業時間外の日と時刻の設定のスクリーンショット](media/auto-attendant-business-hours.png)

<span data-ttu-id="26cfd-202">各自動応答に営業時間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-202">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="26cfd-203">営業時間が設定されていない場合、既定では 24 時間 7 日のスケジュールが設定されている場合、その日のすべての日とすべての時間が営業時間と見なされます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-203">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="26cfd-204">営業時間は、日中の時間内の休憩を使用して設定できます。営業時間として設定されていないすべての時間は、営業時間外と見なされます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-204">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="26cfd-205">営業時間外の通話処理オプションと応答メッセージをさまざまな方法で設定できます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-205">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="26cfd-206">自動応答と通話キューの構成によっては、直接の電話番号を含む自動応答の営業時間外の通話ルーティングのみを指定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="26cfd-206">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="26cfd-207">営業時間外の発信者に対して個別の通話ルーティングが必要な場合は、各日の営業時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-207">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="26cfd-208">[ **新しい時間の追加** ] を選び、1 日に複数の時間セットを指定します (たとえば、昼休みなど)。</span><span class="sxs-lookup"><span data-stu-id="26cfd-208">Select **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="26cfd-209">営業時間を指定したら、営業時間外の通話ルーティング オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-209">Once you've specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="26cfd-210">上記で指定した営業時間内の通話ルーティングと同じオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-210">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="26cfd-211">完了 **したら、[** 次へ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-211">Select **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="26cfd-212">祝日中のコール フロー</span><span class="sxs-lookup"><span data-stu-id="26cfd-212">Call flows during holidays</span></span>

![休日および休日のあいさつメッセージの設定のスクリーンショット](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="26cfd-214">自動応答には、設定した休日ごとにコール [フローを設定できます](set-up-holidays-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="26cfd-214">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="26cfd-215">各自動応答には、最大 20 個の決められた休業日を追加できます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-215">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="26cfd-216">[休日の通話の設定] ページで、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="26cfd-216">On the Holiday call settings page, select **Add**.</span></span>

2. <span data-ttu-id="26cfd-217">この休日設定の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-217">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="26cfd-218">[休日 **] ドロップダウン** から、使用する休日を選択します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-218">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="26cfd-219">使用する応答メッセージの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-219">Choose the type of greeting that you want to use.</span></span>

    ![休日の通話アクション設定のスクリーンショット](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="26cfd-221">通話を切断 **またはリダイレクト\*\*\*\*する場合に** 選択します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-221">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="26cfd-222">リダイレクトを選択した場合は、通話の通話ルーティング先を選択します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-222">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="26cfd-223">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-223">Select **Save**.</span></span>

![祝日が一覧表示された祝日設定のスクリーンショット](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="26cfd-225">追加の祝日ごとに、必要に応じて手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-225">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="26cfd-226">すべての休日を追加した場合は、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="26cfd-226">When you've added all your holidays, select **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="26cfd-227">ダイヤルスコープ</span><span class="sxs-lookup"><span data-stu-id="26cfd-227">Dial scope</span></span>

![ダイヤル範囲に含めるオプションと除外オプションのスクリーンショット](media/auto-attendant-dial-scope.png)

<span data-ttu-id="26cfd-229">ダイヤル *スコープは、* 発信者が名前でダイヤルバイネームまたはダイヤルバイ拡張機能を使用する場合にディレクトリ内で使用できるユーザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-229">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="26cfd-230">既定の **[すべてのオンライン ユーザー] には** 、オンライン ユーザーまたは Skype for Business Server を使用するオンプレミスの組織内のすべてのユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-230">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="26cfd-231">[含める] または [除外] で [カスタムユーザー グループ] を選択し、1 つ以上の Microsoft 365 グループ、配布リスト、またはセキュリティ グループを選択して、特定のユーザーを含めるか除外することができます。 </span><span class="sxs-lookup"><span data-stu-id="26cfd-231">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="26cfd-232">たとえば、組織内のエグゼクティブをダイヤル ディレクトリから除外することができます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-232">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="26cfd-233">(ユーザーが両方のリストにある場合は、ディレクトリから除外されます)。</span><span class="sxs-lookup"><span data-stu-id="26cfd-233">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="26cfd-234">新しいユーザーの名前がディレクトリに一覧表示されるには、最大 36 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="26cfd-234">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="26cfd-235">ダイヤルスコープの設定が完了したら、[次へ] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="26cfd-235">When you're done setting the dial scope, select **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="26cfd-236">リソース アカウント</span><span class="sxs-lookup"><span data-stu-id="26cfd-236">Resource accounts</span></span>

<span data-ttu-id="26cfd-237">すべての自動応答には、リソース アカウントが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="26cfd-237">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="26cfd-238">第 1 レベルの自動応答には、サービス番号が関連付けられているリソース アカウントが少なくとも 1 つ必要です。</span><span class="sxs-lookup"><span data-stu-id="26cfd-238">First-level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="26cfd-239">必要に合った場合は、複数のリソース アカウントを自動応答に割り当て、それぞれに個別のサービス番号を割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-239">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![リソース アカウントの [アカウントの追加] パネルのスクリーンショット](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="26cfd-241">リソース アカウントを追加するには、[アカウントの追加] を **選択** し、追加するアカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-241">To add a resource account, select **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="26cfd-242">[追加 **] を** 選択し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="26cfd-242">Select **Add**, and then select **Add**.</span></span>

![サービス番号が割り当てられているリソース アカウントを示すリソース アカウント リストのスクリーンショット](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="26cfd-244">サービス アカウントの追加が完了したら、[送信] を選択 **して** 自動応答の構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-244">When you have finished adding service accounts, select **Submit** to complete auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="26cfd-245">外部電話番号の転送 - 技術的な詳細</span><span class="sxs-lookup"><span data-stu-id="26cfd-245">External phone number transfers - technical details</span></span>

<span data-ttu-id="26cfd-246">自動応答が [通話を](plan-auto-attendant-call-queue.md#prerequisites) 外部に転送するには、「前提条件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26cfd-246">Refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="26cfd-247">さらに：</span><span class="sxs-lookup"><span data-stu-id="26cfd-247">In addition:</span></span>

- <span data-ttu-id="26cfd-248">通話プラン番号を持つ[](calling-plans-for-office-365.md)リソース アカウントの場合、外部転送電話番号は E.164 形式 (+[国コード][市外コード][電話番号]) で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26cfd-248">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="26cfd-249">直接ルーティング番号を持つリソース アカウントの場合、外部転送電話番号の形式は、セッション ボーダー コントローラー [(SBC)](direct-routing-connect-the-sbc.md) の設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="26cfd-249">For a resource account with a Direct Routing number, the external transfer phone number format is dependent on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="26cfd-250">表示される発信電話番号は、次のように決定されます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-250">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="26cfd-251">通話プラン番号の場合、元の発信者の電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-251">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="26cfd-252">直接ルーティング番号の場合、送信される番号は、SBC の P-Asserted-Identity (IDENTITY) 設定に基づいて、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="26cfd-252">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="26cfd-253">[無効] に設定すると、元の発信者の電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-253">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="26cfd-254">これは既定の推奨設定です。</span><span class="sxs-lookup"><span data-stu-id="26cfd-254">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="26cfd-255">[有効] に設定すると、リソース アカウントの電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-255">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="26cfd-256">Skype for Business ハイブリッド環境では、自動応答通話を PSTN に転送するには、PSTN 番号に設定された通話転送を使用して新しいオンプレミス ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-256">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="26cfd-257">ユーザーは音声ポリシーを有効にエンタープライズ VoIP音声ポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="26cfd-257">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="26cfd-258">詳細については、「PSTN への自動 [応答通話転送」を参照してください](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)。</span><span class="sxs-lookup"><span data-stu-id="26cfd-258">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="26cfd-259">PowerShell で自動応答を作成する</span><span class="sxs-lookup"><span data-stu-id="26cfd-259">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="26cfd-260">また、PowerShell を使用して自動応答を作成および設定できます。</span><span class="sxs-lookup"><span data-stu-id="26cfd-260">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="26cfd-261">自動応答を管理するために必要なコマンドレットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="26cfd-261">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="26cfd-262">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="26cfd-262">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="26cfd-263">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="26cfd-263">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="26cfd-264">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="26cfd-264">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="26cfd-265">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="26cfd-265">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="26cfd-266">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="26cfd-266">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="26cfd-267">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="26cfd-267">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="26cfd-268">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="26cfd-268">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="26cfd-269">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="26cfd-269">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="26cfd-270">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="26cfd-270">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="26cfd-271">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="26cfd-271">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="26cfd-272">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="26cfd-272">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="26cfd-273">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="26cfd-273">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="26cfd-274">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="26cfd-274">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="26cfd-275">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="26cfd-275">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="26cfd-276">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="26cfd-276">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="26cfd-277">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="26cfd-277">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="26cfd-278">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="26cfd-278">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="26cfd-279">関連トピック</span><span class="sxs-lookup"><span data-stu-id="26cfd-279">Related topics</span></span>

[<span data-ttu-id="26cfd-280">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="26cfd-280">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="26cfd-281">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="26cfd-281">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="26cfd-282">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="26cfd-282">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="26cfd-283">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="26cfd-283">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
