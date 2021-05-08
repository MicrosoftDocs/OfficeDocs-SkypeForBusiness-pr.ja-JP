---
title: サービスの自動応答を設定Microsoft Teams
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
description: アプリの自動応答を設定してテストする方法Microsoft Teams。
ms.openlocfilehash: 9efd30eb91e9760f800dd24935724d2a3cdd97c2
ms.sourcegitcommit: c56c87e912a4b3729c7c52d8de78fd4d24448a8d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51926053"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="011e0-103">自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="011e0-103">Set up an auto attendant</span></span>

<span data-ttu-id="011e0-104">自動応答を使用すると、ユーザーが組織に電話をかけ、メニュー システム内を移動して、適切な部署、通話キュー、ユーザー、またはオペレーターと話し合います。</span><span class="sxs-lookup"><span data-stu-id="011e0-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="011e0-105">組織の自動応答は、管理者センターまたは PowerShell Microsoft Teamsして作成できます。</span><span class="sxs-lookup"><span data-stu-id="011e0-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span>

<span data-ttu-id="011e0-106">この記事の手順に従う前に[、「Teams](plan-auto-attendant-call-queue.md)自動応答と通話キューの計画」を[](plan-auto-attendant-call-queue.md#getting-started)読み、概要の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="011e0-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="011e0-107">自動応答は、呼び出し元の入力に基づいて、次のいずれかの宛先に通話を送信できます。 <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="011e0-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="011e0-108">**演算子** - 自動応答に対して定義された演算子。</span><span class="sxs-lookup"><span data-stu-id="011e0-108">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="011e0-109">演算子の定義は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="011e0-109">Defining an operator is optional.</span></span> <span data-ttu-id="011e0-110">演算子は、この一覧の他の任意の宛先として定義できます。</span><span class="sxs-lookup"><span data-stu-id="011e0-110">The operator can be defined as any of the other destinations in this list.</span></span>
- <span data-ttu-id="011e0-111">**組織内のユーザー** - 音声通話を受信できる組織内のユーザー。</span><span class="sxs-lookup"><span data-stu-id="011e0-111">**Person in the organization** - a person in your organization who can receive voice calls.</span></span> <span data-ttu-id="011e0-112">このユーザーには、オンライン ユーザーまたはオンプレミスでホストされているユーザーを、Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="011e0-112">This person can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="011e0-113">**音声アプリ** - 別の自動応答または通話キュー。</span><span class="sxs-lookup"><span data-stu-id="011e0-113">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="011e0-114">(この宛先を選択するときに、自動応答または通話キューに関連付けられているリソース アカウントを選択します)。</span><span class="sxs-lookup"><span data-stu-id="011e0-114">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="011e0-115">**ボイス** メール - 指定したグループに関連Microsoft 365ボイス メールボックス。</span><span class="sxs-lookup"><span data-stu-id="011e0-115">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="011e0-116">**外部電話番号** - 任意の電話番号。</span><span class="sxs-lookup"><span data-stu-id="011e0-116">**External phone number** - any phone number.</span></span> <span data-ttu-id="011e0-117">(「 [外部転送の技術的な詳細」を参照してください](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details))。</span><span class="sxs-lookup"><span data-stu-id="011e0-117">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="011e0-118">**アナウンス (オーディオ ファイル)** - オーディオ ファイルを再生します。</span><span class="sxs-lookup"><span data-stu-id="011e0-118">**Announcement (Audio file)** - Play an audio file.</span></span> <span data-ttu-id="011e0-119">アップロードした録音されたアナウンス メッセージは、 にオーディオとして保存されます。WAV、.MP3、または 。WMA 形式。</span><span class="sxs-lookup"><span data-stu-id="011e0-119">A recorded announcement message you upload that's saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="011e0-120">記録は 5 MB 以下にできます。</span><span class="sxs-lookup"><span data-stu-id="011e0-120">The recording can be no larger than 5 MB.</span></span> <span data-ttu-id="011e0-121">システムがアナウンスを再生し、自動応答メニューに戻ります。</span><span class="sxs-lookup"><span data-stu-id="011e0-121">The system plays the announcement, and then returns to the auto attendant menu.</span></span>
- <span data-ttu-id="011e0-122">**お知らせ (入力)** - メッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="011e0-122">**Announcement (Typed)** - Type in a message.</span></span> <span data-ttu-id="011e0-123">システムで読み取るテキスト。</span><span class="sxs-lookup"><span data-stu-id="011e0-123">Text you want the system to read.</span></span> <span data-ttu-id="011e0-124">最大 1,000 文字を入力できます。</span><span class="sxs-lookup"><span data-stu-id="011e0-124">You can enter up to 1000 characters.</span></span> <span data-ttu-id="011e0-125">システムがアナウンスを再生し、自動応答メニューに戻ります。</span><span class="sxs-lookup"><span data-stu-id="011e0-125">The system plays the announcement, and then returns to the auto attendant menu.</span></span>

<span data-ttu-id="011e0-126">自動応答を設定すると、さまざまな段階でこれらのオプションのいずれかを選択するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="011e0-126">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

> [!NOTE]
> <span data-ttu-id="011e0-127">宛先として [ボイスメール] を選択すると、次の 2 つのオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="011e0-127">When choosing Voicemail as a destination, two additional options are available:</span></span>
> - <span data-ttu-id="011e0-128">**文字** 起こし (既定: オフ) - 有効にすると、ボイスメール メッセージが文字起こしされ、メールの一部として含まれます。</span><span class="sxs-lookup"><span data-stu-id="011e0-128">**Transcription** (Default: Off) - when enabled, the voicemail message will be transcribed and included as part of the email.</span></span>
> - <span data-ttu-id="011e0-129">**あいさつ** メッセージを表示しません (既定値: オフ) - 有効にすると、標準のシステム メッセージ "トーンの後にメッセージを残してください。</span><span class="sxs-lookup"><span data-stu-id="011e0-129">**Suppress Greeting** (Default: Off) - when enabled, the standard system message "Please leave a message after the tone.</span></span> <span data-ttu-id="011e0-130">完了したら、その他のオプションを表示するには、電話を切るか、ハッシュ キーを押してください。"</span><span class="sxs-lookup"><span data-stu-id="011e0-130">When you have finished please hang up or press the hash key for more options."</span></span> <span data-ttu-id="011e0-131">は抑制されます。</span><span class="sxs-lookup"><span data-stu-id="011e0-131">will be suppressed.</span></span>

<span data-ttu-id="011e0-132">自動応答を設定するには、Teams 管理センターで、[音声] を展開し、[自動応答] を選択し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="011e0-132">To set up an auto attendant, in the Teams admin center, expand **Voice**, select **Auto attendants**, and then select **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="011e0-133">一般的な情報</span><span class="sxs-lookup"><span data-stu-id="011e0-133">General info</span></span>

![名前、オペレーター、タイム ゾーン、言語、音声入力の自動応答設定のスクリーンショット](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="011e0-135">上部のボックスに自動応答の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="011e0-135">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="011e0-136">演算子を指定するには、演算子の呼び出し先を指定します。</span><span class="sxs-lookup"><span data-stu-id="011e0-136">To designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="011e0-137">この指定は省略可能です (ただし、推奨)。</span><span class="sxs-lookup"><span data-stu-id="011e0-137">This designation is optional (but recommended).</span></span> <span data-ttu-id="011e0-138">[オペレーター **] オプション** を設定して、発信者がメニューから抜け出し、指定されたユーザーと話し合うのを許可します。</span><span class="sxs-lookup"><span data-stu-id="011e0-138">Set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="011e0-139">この自動応答のタイム ゾーンを指定します。</span><span class="sxs-lookup"><span data-stu-id="011e0-139">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="011e0-140">時間外の別の通話フローを作成する場合、タイム ゾーンは営業時間の [計算に使用されます](#call-flow-for-after-hours)。</span><span class="sxs-lookup"><span data-stu-id="011e0-140">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="011e0-141">この自動 [応答でサポートされている](create-a-phone-system-auto-attendant-languages.md) 言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="011e0-141">Specify a [supported language](create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="011e0-142">これは、システムによって生成される音声プロンプトに使用される言語です。</span><span class="sxs-lookup"><span data-stu-id="011e0-142">This is the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="011e0-143">音声入力を有効にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="011e0-143">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="011e0-144">有効にすると、すべてのメニュー オプションの名前が音声認識キーワードになります。</span><span class="sxs-lookup"><span data-stu-id="011e0-144">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="011e0-145">たとえば、発信者が "One" と言ってキー 1 にマップされているメニュー オプションを選択したり、"Sales" と言って "Sales" という名前のメニュー オプションを選択したりします。</span><span class="sxs-lookup"><span data-stu-id="011e0-145">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

> [!NOTE]
> <span data-ttu-id="011e0-146">手順 4 で音声入力をサポートしない言語を選択した場合、このオプションは無効になります。</span><span class="sxs-lookup"><span data-stu-id="011e0-146">If you choose a language in Step 4 that doesn't support voice inputs this option will be disabled.</span></span>

6. <span data-ttu-id="011e0-147">[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="011e0-147">Select **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="011e0-148">呼び出しフロー</span><span class="sxs-lookup"><span data-stu-id="011e0-148">Call flow</span></span>

![あいさつメッセージの設定のスクリーンショット](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="011e0-150">自動応答が通話に応答するときにあいさつメッセージを再生する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="011e0-150">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="011e0-151">[オーディオ ファイル **の再生]** を選択した場合は、[アップロード **ファイル**] ボタンを使用して、 にオーディオとして保存された録音されたあいさつメッセージをアップロードできます。WAV、.MP3、または 。WMA 形式。</span><span class="sxs-lookup"><span data-stu-id="011e0-151">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="011e0-152">記録は 5 MB 以下にできます。</span><span class="sxs-lookup"><span data-stu-id="011e0-152">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="011e0-153">[あいさつ文を入力する] を選択すると、自動応答が通話に応答すると、入力したテキスト (最大 1,000 文字) がシステムによって読み上げされます。</span><span class="sxs-lookup"><span data-stu-id="011e0-153">If you select **Type a greeting message** the system will read the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![通話ルーティング設定のスクリーンショット](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="011e0-155">通話のルーティング方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="011e0-155">Choose how you want to route the call.</span></span>

<span data-ttu-id="011e0-156">[切断] **を選択** すると、自動応答によって通話が停止します。</span><span class="sxs-lookup"><span data-stu-id="011e0-156">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="011e0-157">[通話の **リダイレクト] を選択** した場合は、通話ルーティング先のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="011e0-157">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="011e0-158">[再生]**メニュー オプション を選択** した場合は、[音声ファイルの再生] または [あいさつメッセージに入力] を選択し、メニュー オプションとディレクトリ検索から選択できます。</span><span class="sxs-lookup"><span data-stu-id="011e0-158">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="011e0-159">メニュー オプション</span><span class="sxs-lookup"><span data-stu-id="011e0-159">Menu options</span></span>

![ダイヤル キー オプションのスクリーンショット](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="011e0-161">ダイヤル オプションの場合は、電話のキーパッドの 0 ~ 9 キーを通話ルーティング先の 1 つに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="011e0-161">For dialing options, assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="011e0-162">(キー \* (繰り返し) と (戻る) はシステムによって予約され \# 、再割り当てはできません)。</span><span class="sxs-lookup"><span data-stu-id="011e0-162">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="011e0-163">キー マッピングを連続する必要はない。</span><span class="sxs-lookup"><span data-stu-id="011e0-163">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="011e0-164">キー 0、1、3 がオプションにマップされているメニューを作成できます。数値 2 キーは使用されません。</span><span class="sxs-lookup"><span data-stu-id="011e0-164">It's possible to create a menu with keys 0, 1, and 3 mapped to options, while the number 2 key isn't used.</span></span>

<span data-ttu-id="011e0-165">ゼロ キーを構成している場合は、演算子にマッピングすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="011e0-165">We recommend mapping the zero key to the operator if you've configured one.</span></span> <span data-ttu-id="011e0-166">オペレーターがキーに設定されていない場合、音声コマンド "Operator" も無効になります。</span><span class="sxs-lookup"><span data-stu-id="011e0-166">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span>

<span data-ttu-id="011e0-167">メニュー オプションごとに、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="011e0-167">For each menu option, specify the following settings:</span></span>

- <span data-ttu-id="011e0-168">**[ダイヤル キー** ] - このオプションにアクセスするには、電話のキーパッドのキーを押します。</span><span class="sxs-lookup"><span data-stu-id="011e0-168">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="011e0-169">音声入力が使用可能な場合は、発信者もこの番号を言ってオプションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="011e0-169">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="011e0-170">**[音声コマンド** ] - 音声入力が有効になっている場合に、呼び出し元がこのオプションにアクセスするために指定できる音声コマンドを定義します。</span><span class="sxs-lookup"><span data-stu-id="011e0-170">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="011e0-171">"顧客サービス" や "操作と根拠" など、複数の単語を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="011e0-171">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="011e0-172">たとえば、呼び出し元は 2 キーを押したり、"two" と言って "Sales" と言って、2 つのキーにマップされているオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="011e0-172">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the two keys.</span></span> <span data-ttu-id="011e0-173">このテキストは、サービス確認プロンプトのテキスト読み上げによってもレンダリングされます。これは、"通話を販売に転送する" のようなものです。</span><span class="sxs-lookup"><span data-stu-id="011e0-173">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="011e0-174">**[リダイレクト先** ] - 呼び出し元がこのオプションを選択するときに使用される通話ルーティング先。</span><span class="sxs-lookup"><span data-stu-id="011e0-174">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="011e0-175">自動応答または通話キューにリダイレクトする場合は、関連付けられているリソース アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="011e0-175">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="011e0-176">ディレクトリ検索</span><span class="sxs-lookup"><span data-stu-id="011e0-176">Directory search</span></span>

<span data-ttu-id="011e0-177">ダイヤル キーを宛先に割り当てる場合は、[ディレクトリ検索] で [**なし] を選択\*\*\*\*することをお勧めします**。</span><span class="sxs-lookup"><span data-stu-id="011e0-177">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="011e0-178">呼び出し元が、特定の宛先に割り当てられているキーを使用して名前または内線番号をダイヤルしようとすると、名前または内線番号の入力が完了する前に、予期せず宛先にルーティングされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="011e0-178">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they might be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="011e0-179">ディレクトリ検索用に別の自動応答を作成し、メインの自動応答にダイヤル キーでリンクすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="011e0-179">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it with a dial key.</span></span>

<span data-ttu-id="011e0-180">ダイヤル キーを割り当てなかった場合は、[ディレクトリ検索] のオプション **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="011e0-180">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="011e0-181">**[名前でダイヤル** ] - このオプションを有効にすると、発信者はユーザーの名前を言い、電話のキーパッドに入力できます。</span><span class="sxs-lookup"><span data-stu-id="011e0-181">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="011e0-182">Skype for Business Server を使用してオンプレミスでホストされているオンライン ユーザーまたは任意のユーザーは、対象ユーザーであり、名前でダイヤルします。</span><span class="sxs-lookup"><span data-stu-id="011e0-182">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="011e0-183">([ダイヤル スコープ] ページで、ディレクトリに含まれているユーザーと含まれていないユーザー [を設定](#dial-scope) できます)。</span><span class="sxs-lookup"><span data-stu-id="011e0-183">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="011e0-184">**内線番号による** ダイヤル - このオプションを有効にすると、発信者は内線番号にダイヤルして組織内のユーザーと接続できます。</span><span class="sxs-lookup"><span data-stu-id="011e0-184">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="011e0-185">Skype for Business Server を使用してオンプレミスでホストされているオンライン ユーザーまたは任意のユーザーは、有資格ユーザーであり、内線番号で **ダイヤルで確認できます**。</span><span class="sxs-lookup"><span data-stu-id="011e0-185">Any online user or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="011e0-186">([ダイヤル スコープ] ページで、ディレクトリに含まれているユーザーと含まれていないユーザー [を設定](#dial-scope) できます)。</span><span class="sxs-lookup"><span data-stu-id="011e0-186">(You can set who is and isn't included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="011e0-187">ダイヤル バイ 拡張機能を利用するには、Active Directory または Azure Active Directory で定義されている次のいずれかの電話属性の一部として拡張機能を指定する必要があります (詳細[](/microsoft-365/admin/add-users/add-users)については、「ユーザーを個別または一括で追加する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="011e0-187">Users you want to make available for Dial By Extension need to have an extension specified as part of one of the following phones attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="011e0-188">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="011e0-188">OfficePhone</span></span>
- <span data-ttu-id="011e0-189">HomePhone</span><span class="sxs-lookup"><span data-stu-id="011e0-189">HomePhone</span></span>
- <span data-ttu-id="011e0-190">Mobile/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="011e0-190">Mobile/MobilePhone</span></span>
- <span data-ttu-id="011e0-191">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="011e0-191">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="011e0-192">OtherTelephone</span><span class="sxs-lookup"><span data-stu-id="011e0-192">OtherTelephone</span></span>

<span data-ttu-id="011e0-193">[ユーザーの電話番号] フィールドに内線番号を入力するために必要な形式は、次のいずれかの形式です。</span><span class="sxs-lookup"><span data-stu-id="011e0-193">The required format to enter the extension in the user phone number field can be one of the following formats:</span></span>

- <span data-ttu-id="011e0-194">*+\<phone number>;ext=\<extension>*</span><span class="sxs-lookup"><span data-stu-id="011e0-194">*+\<phone number>;ext=\<extension>*</span></span>
- <span data-ttu-id="011e0-195">*+\<phone number>x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="011e0-195">*+\<phone number>x\<extension>*</span></span>
- <span data-ttu-id="011e0-196">*x\<extension>*</span><span class="sxs-lookup"><span data-stu-id="011e0-196">*x\<extension>*</span></span>

- <span data-ttu-id="011e0-197">例 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span><span class="sxs-lookup"><span data-stu-id="011e0-197">Example 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"</span></span>
- <span data-ttu-id="011e0-198">例 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span><span class="sxs-lookup"><span data-stu-id="011e0-198">Example 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"</span></span>
- <span data-ttu-id="011e0-199">例 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span><span class="sxs-lookup"><span data-stu-id="011e0-199">Example 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"</span></span>

<span data-ttu-id="011e0-200">拡張機能は、管理センターまたは管理センター [Microsoft 365で](https://admin.microsoft.com/)Azure Active Directory[設定できます](https://aad.portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="011e0-200">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="011e0-201">自動応答と通話キューで変更を利用するには、最大で 12 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="011e0-201">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="011e0-202">[名前でダイヤル] 機能と [ダイヤルバイ拡張機能] の両方を使用する場合は、メイン自動応答でダイヤル キーを割り当て、名前でダイヤルが有効になっている自動応答に到達 **できます**。</span><span class="sxs-lookup"><span data-stu-id="011e0-202">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="011e0-203">その自動応答内で、1 つのキー (関連付けられている文字がない) を割り当て、内線番号によるダイヤル自動応答 **に** 到達できます。</span><span class="sxs-lookup"><span data-stu-id="011e0-203">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="011e0-204">ディレクトリ検索オプションを選択したら **、[次へ]** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="011e0-204">Once you have selected a **Directory search** option, select **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="011e0-205">時間外の通話フロー</span><span class="sxs-lookup"><span data-stu-id="011e0-205">Call flow for after hours</span></span>

![時間外の日と時刻の設定のスクリーンショット](media/auto-attendant-business-hours.png)

<span data-ttu-id="011e0-207">各自動応答に対して営業時間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="011e0-207">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="011e0-208">営業時間が設定されていない場合、24 時間 365 日のスケジュールが既定で設定されているので、その日のすべての日とすべての時間が営業時間と見なされます。</span><span class="sxs-lookup"><span data-stu-id="011e0-208">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="011e0-209">営業時間は、その日の間の時間内の休憩で設定できます。営業時間として設定されていないすべての時間は、時間外と見なされます。</span><span class="sxs-lookup"><span data-stu-id="011e0-209">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="011e0-210">さまざまな着信通話処理オプションと応答メッセージを時間外に設定できます。</span><span class="sxs-lookup"><span data-stu-id="011e0-210">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="011e0-211">自動応答と通話キューの構成によっては、直接の電話番号を含む自動応答の時間外通話ルーティングのみを指定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="011e0-211">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="011e0-212">営業時間外の発信者に対して個別の通話ルーティングが必要な場合は、各日の営業時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="011e0-212">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="011e0-213">[ **新しい時刻の追加** ] を選択して、特定の日に複数の時間セットを指定します 。たとえば、昼食休憩を指定します。</span><span class="sxs-lookup"><span data-stu-id="011e0-213">Select **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="011e0-214">営業時間を指定したら、時間外の通話ルーティング オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="011e0-214">Once you've specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="011e0-215">上記で指定した営業時間の通話ルーティングと同じオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="011e0-215">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="011e0-216">完了したら **、[** 次へ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="011e0-216">Select **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="011e0-217">祝日中の通話フロー</span><span class="sxs-lookup"><span data-stu-id="011e0-217">Call flows during holidays</span></span>

![休日と休日のあいさつ設定のスクリーンショット](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="011e0-219">自動応答には、設定した各祝日の通話 [フローを設定できます](set-up-holidays-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="011e0-219">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="011e0-220">各自動応答には、最大 20 個の決められた休業日を追加できます。</span><span class="sxs-lookup"><span data-stu-id="011e0-220">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="011e0-221">[休日の通話設定] ページで、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="011e0-221">On the Holiday call settings page, select **Add**.</span></span>

2. <span data-ttu-id="011e0-222">この休日設定の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="011e0-222">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="011e0-223">[ **休日] ドロップダウン** から、使用する休日を選択します。</span><span class="sxs-lookup"><span data-stu-id="011e0-223">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="011e0-224">使用するあいさつメッセージの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="011e0-224">Choose the type of greeting that you want to use.</span></span>

    ![休日の通話アクションの設定のスクリーンショット](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="011e0-226">[切断] または [通話の **リダイレクト\*\*\*\*] を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="011e0-226">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="011e0-227">リダイレクトを選択した場合は、通話の通話ルーティング先を選択します。</span><span class="sxs-lookup"><span data-stu-id="011e0-227">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="011e0-228">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="011e0-228">Select **Save**.</span></span>

![休日が表示されている休日設定のスクリーンショット](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="011e0-230">追加の祝日ごとに、必要に応じて手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="011e0-230">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="011e0-231">すべての休日を追加した場合は、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="011e0-231">When you've added all your holidays, select **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="011e0-232">ダイヤル スコープ</span><span class="sxs-lookup"><span data-stu-id="011e0-232">Dial scope</span></span>

![ダイヤル スコープに含めるオプションと除外オプションのスクリーンショット](media/auto-attendant-dial-scope.png)

<span data-ttu-id="011e0-234">ダイヤル *スコープは、* 呼び出し元がダイヤル バイ ネームまたはダイヤル バイ 拡張機能を使用する場合にディレクトリ内で使用できるユーザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="011e0-234">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="011e0-235">[すべてのオンライン **ユーザー] の既定値には**、オンライン ユーザーまたはオンプレミスでホストされている組織内のすべてのユーザーが、Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="011e0-235">The default of **All online users** includes all users in your organization that are Online users or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="011e0-236">[含める] または [除外] で [カスタムユーザー グループ] を選択し、1 つ以上の Microsoft 365 グループ、配布リスト、またはセキュリティ グループを選択することで、特定のユーザーを含めるか除外できます。 </span><span class="sxs-lookup"><span data-stu-id="011e0-236">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="011e0-237">たとえば、組織内のエグゼクティブをダイヤル ディレクトリから除外することができます。</span><span class="sxs-lookup"><span data-stu-id="011e0-237">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="011e0-238">(ユーザーが両方のリストにある場合は、ディレクトリから除外されます)。</span><span class="sxs-lookup"><span data-stu-id="011e0-238">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="011e0-239">新しいユーザーの名前がディレクトリに表示されるには、最大 36 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="011e0-239">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="011e0-240">ダイヤル スコープの設定が完了したら、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="011e0-240">When you're done setting the dial scope, select **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="011e0-241">リソース アカウント</span><span class="sxs-lookup"><span data-stu-id="011e0-241">Resource accounts</span></span>

<span data-ttu-id="011e0-242">すべての自動応答には、関連付けられているリソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="011e0-242">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="011e0-243">第 1 レベルの自動応答には、サービス番号が関連付けられている少なくとも 1 つのリソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="011e0-243">First-level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="011e0-244">必要な場合は、複数のリソース アカウントを自動応答に割り当て、それぞれに個別のサービス番号を割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="011e0-244">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![リソース アカウントの [アカウントの追加] パネルのスクリーンショット](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="011e0-246">リソース アカウントを追加するには、[アカウントの **追加] を選択** し、追加するアカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="011e0-246">To add a resource account, select **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="011e0-247">[追加 **] を** 選択し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="011e0-247">Select **Add**, and then select **Add**.</span></span>

![割り当てられたサービス番号が割り当てられたリソース アカウントを示すリソース アカウントの一覧のスクリーンショット](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="011e0-249">サービス アカウントの追加が完了したら、[送信] を **選択して自動** 応答の構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="011e0-249">When you have finished adding service accounts, select **Submit** to complete auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="011e0-250">外部電話番号の転送 - 技術的な詳細</span><span class="sxs-lookup"><span data-stu-id="011e0-250">External phone number transfers - technical details</span></span>

<span data-ttu-id="011e0-251">自動応答が [外部から通話](plan-auto-attendant-call-queue.md#prerequisites) を転送するには、「前提条件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="011e0-251">Refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="011e0-252">さらに：</span><span class="sxs-lookup"><span data-stu-id="011e0-252">In addition:</span></span>

- <span data-ttu-id="011e0-253">通話プラン ライセンスを持[](calling-plans-for-office-365.md)つリソース アカウントの場合、外部転送電話番号は E.164 形式 (+[国コード][市外コード][電話番号]) で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="011e0-253">For a resource account with a [Calling Plan license](calling-plans-for-office-365.md), the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="011e0-254">電話システム ライセンスと直接ルーティングのオンライン音声ルーティング ポリシーを持つリソース アカウントの場合、外部転送の電話番号の形式は、セッション ボーダー コントローラー [(SBC)](direct-routing-connect-the-sbc.md)の設定によって異なっています。</span><span class="sxs-lookup"><span data-stu-id="011e0-254">For a resource account with a Phone System License and Direct Routing online voice routing policy, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="011e0-255">表示される送信電話番号は、次のように決定されます。</span><span class="sxs-lookup"><span data-stu-id="011e0-255">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="011e0-256">通話プラン番号の場合、元の発信者の電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="011e0-256">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="011e0-257">ダイレクト ルーティング番号の場合、送信される数は、次のように SBC の P-Asserted-Identity (ASSERTed-Identity) 設定に基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="011e0-257">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="011e0-258">[無効] に設定すると、元の発信者の電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="011e0-258">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="011e0-259">これは既定の推奨設定です。</span><span class="sxs-lookup"><span data-stu-id="011e0-259">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="011e0-260">[有効] に設定すると、リソース アカウントの電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="011e0-260">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="011e0-261">ハイブリッド環境Skype for Business、自動応答通話を PSTN に転送するには、PSTN 番号に設定された通話転送を使用して新しいオンプレミス ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="011e0-261">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="011e0-262">ユーザーは、ユーザーに対して有効エンタープライズ VoIP音声ポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="011e0-262">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="011e0-263">詳細については、「PSTN への自動応答 [通話転送」を参照してください](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)。</span><span class="sxs-lookup"><span data-stu-id="011e0-263">To learn more, see [Auto attendant call transfer to PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="011e0-264">PowerShell を使用して自動応答を作成する</span><span class="sxs-lookup"><span data-stu-id="011e0-264">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="011e0-265">PowerShell を使用して自動応答を作成および設定できます。</span><span class="sxs-lookup"><span data-stu-id="011e0-265">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="011e0-266">自動応答を管理するために必要なコマンドレットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="011e0-266">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="011e0-267">New-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="011e0-267">New-CsAutoAttendant</span></span>](/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="011e0-268">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="011e0-268">Set-CsAutoAttendant</span></span>](/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="011e0-269">Get-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="011e0-269">Get-CsAutoAttendant</span></span>](/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="011e0-270">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="011e0-270">Get-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="011e0-271">Remove-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="011e0-271">Remove-CsAutoAttendant</span></span>](/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="011e0-272">New-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="011e0-272">New-CsAutoAttendantMenu</span></span>](/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="011e0-273">New-CsOnlineAudioFile</span><span class="sxs-lookup"><span data-stu-id="011e0-273">New-CsOnlineAudioFile</span></span>](/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="011e0-274">New-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="011e0-274">New-CsAutoAttendantCallFlow</span></span>](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="011e0-275">Export-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="011e0-275">Export-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="011e0-276">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="011e0-276">New-CsOnlineTimeRange</span></span>](/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="011e0-277">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="011e0-277">New-CsOnlineDateTimeRange</span></span>](/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="011e0-278">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="011e0-278">New-CsOnlineSchedule</span></span>](/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="011e0-279">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="011e0-279">Get-CsAutoAttendantSupportedTimeZone</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="011e0-280">New-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="011e0-280">New-CsAutoAttendantCallHandlingAssociation</span></span>](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="011e0-281">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="011e0-281">Get-CsAutoAttendantSupportedLanguage</span></span>](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="011e0-282">Import-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="011e0-282">Import-CsAutoAttendantHolidays</span></span>](/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="011e0-283">New-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="011e0-283">New-CsAutoAttendantCallableEntity</span></span>](/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a><span data-ttu-id="011e0-284">関連トピック</span><span class="sxs-lookup"><span data-stu-id="011e0-284">Related topics</span></span>

[<span data-ttu-id="011e0-285">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="011e0-285">Here's what you get with Phone System</span></span>](./here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="011e0-286">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="011e0-286">Getting service phone numbers</span></span>](./getting-service-phone-numbers.md)

[<span data-ttu-id="011e0-287">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="011e0-287">Country and region availability for Audio Conferencing and Calling Plans</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="011e0-288">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="011e0-288">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
