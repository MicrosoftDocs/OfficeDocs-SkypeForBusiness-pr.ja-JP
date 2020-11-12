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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Microsoft Teams の自動応答をセットアップしてテストする方法について説明します。
ms.openlocfilehash: 00cf80578564db122d4eaf206456b465a21668af
ms.sourcegitcommit: 950c04ce49064209ee04880e7c7473a4f931df50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2020
ms.locfileid: "48999216"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="a4cdb-103">自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="a4cdb-103">Set up an auto attendant</span></span>

<span data-ttu-id="a4cdb-104">自動応答を使うと、ユーザーが組織を呼び出したり、メニューシステムを移動して、適切な部門、通話キュー、人、またはオペレーターと話すことができます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="a4cdb-105">Microsoft Teams 管理センターまたは PowerShell を使用して、組織の自動応答を作成できます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span> 

<span data-ttu-id="a4cdb-106">この記事に記載されている手順を実行する前に、「 [Teams の自動応答と通話キューのプラン](plan-auto-attendant-call-queue.md) 」を参照して、 [作業の開始の手順](plan-auto-attendant-call-queue.md#getting-started) に従っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="a4cdb-107">自動応答では、発信者の入力に基づいて、次のいずれかの宛先に通話を転送できます。 <a name="call-routing-options" ></a></span><span class="sxs-lookup"><span data-stu-id="a4cdb-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a></span></span>

- <span data-ttu-id="a4cdb-108">**組織内のユーザー** -音声通話を受信できる組織内のユーザー。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="a4cdb-109">これは、オンラインユーザーまたは Skype for Business Server を使用してオンプレミスでホストされているユーザーのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="a4cdb-110">**音声アプリ** -別の自動応答または通話キュー。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="a4cdb-111">(この宛先を選択するときに、自動応答または通話キューに関連付けられているリソースアカウントを選びます。)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="a4cdb-112">**外部電話番号** -任意の電話番号。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="a4cdb-113">(「 [外部転送技術の詳細](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="a4cdb-114">**ボイス** メール-指定した Microsoft 365 グループに関連付けられているボイスメールボックス。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="a4cdb-115">**Operator** -自動応答に対して定義されているオペレーター。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="a4cdb-116">演算子の定義は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-116">Defining an operator is optional.</span></span> <span data-ttu-id="a4cdb-117">このリストでは、演算子を他の任意の宛先として定義できます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="a4cdb-118">自動応答をセットアップするときに、これらのオプションのいずれかを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="a4cdb-119">自動応答を設定するには、Teams 管理センターで、[ **音声** ]、[ **自動応答** ]、[ **追加** ] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-119">To set up an auto attendant, in the Teams admin center, expand **Voice** , click **Auto attendants** , and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="a4cdb-120">一般的な情報</span><span class="sxs-lookup"><span data-stu-id="a4cdb-120">General info</span></span>

![名前、演算子、タイムゾーン、言語、および音声入力の自動応答設定のスクリーンショット](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="a4cdb-122">上部のボックスに自動応答の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-122">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="a4cdb-123">オペレーターを指定する場合は、オペレーターへの通話の送信先を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-123">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="a4cdb-124">これはオプションです (ただし推奨)。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-124">This is optional (but recommended).</span></span> <span data-ttu-id="a4cdb-125">[ **オペレーター** ] オプションを設定すると、発信者はメニューから抜け、指定したユーザーに向かって話すことができます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-125">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="a4cdb-126">この自動応答のタイムゾーンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-126">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="a4cdb-127">タイムゾーンは、勤務時間の計算に使用されます。これには、 [時間の経過に応じて個別のコールフローを作成](#call-flow-for-after-hours)します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-127">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="a4cdb-128">この自動応答の言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-128">Specify a language for this auto attendant.</span></span> <span data-ttu-id="a4cdb-129">これは、システムによって生成される音声プロンプトで使用される言語です。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-129">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="a4cdb-130">音声入力を有効にするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-130">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="a4cdb-131">有効にすると、すべてのメニューオプションの名前が音声認識のキーワードになります。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-131">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="a4cdb-132">たとえば、発信者は "One" と言って、キー1にマップされているメニューオプションを選ぶか、"売上" という名前のメニューオプションを選ぶために "売上" と言うことができます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-132">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="a4cdb-133">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-133">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="a4cdb-134">コールフロー</span><span class="sxs-lookup"><span data-stu-id="a4cdb-134">Call flow</span></span>

![応答メッセージの設定のスクリーンショット](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="a4cdb-136">自動応答が着信に応答したときに応答メッセージを再生するかどうかを選びます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-136">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="a4cdb-137">[ **オーディオファイルの再生** ] を選択した場合は、[ **ファイルのアップロード** ] ボタンを使用して、録音したグリーティングメッセージをオーディオとして保存することができます。WAV、。MP3、またはです。WMA 形式。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-137">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="a4cdb-138">記録は 5 MB 以下でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-138">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="a4cdb-139">[ **グリーティングメッセージの入力** ] を選択した場合は、自動応答が着信に応答したときに、入力したテキスト (最大1000文字) のテキストが読み上げられます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-139">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![通話ルーティング設定のスクリーンショット](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="a4cdb-141">通話のルーティング方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-141">Choose how you want to route the call.</span></span>

<span data-ttu-id="a4cdb-142">[ **切断** ] を選択すると、自動応答が通話を切断します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-142">If you select **Disconnect** , the auto attendant will hang up the call.</span></span>

<span data-ttu-id="a4cdb-143">[通話の **リダイレクト** ] を選択した場合は、いずれかの通話ルーティング先を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-143">If you select **Redirect call** , you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="a4cdb-144">[ **再生] メニューのオプション** を選択した場合は、 **オーディオファイルを再生** するか、 **あいさつメッセージを入力** するかを選択して、メニューオプションとディレクトリ検索のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-144">If you select **Play menu options** , you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="a4cdb-145">メニューオプション</span><span class="sxs-lookup"><span data-stu-id="a4cdb-145">Menu options</span></span>

![ダイヤルキーオプションのスクリーンショット](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="a4cdb-147">ダイヤルオプションの場合、電話のキーパッドの0-9 キーをいずれかの通話ルーティング先に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-147">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="a4cdb-148">(キー \* (繰り返し) と \# (戻る) は、システムによって予約されているため、再割り当てすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-148">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="a4cdb-149">キーマッピングは、継続的である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-149">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="a4cdb-150">たとえば、キー0、1、3のメニューを作成してオプションにマップし、2つのキーを使用しないことができます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-150">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="a4cdb-151">構成済みの場合は、オペレーターに0キーをマッピングすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-151">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="a4cdb-152">演算子がいずれのキーにも設定されていない場合は、音声コマンド "Operator" も無効になります。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-152">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span> 

<span data-ttu-id="a4cdb-153">各メニューオプションについて、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-153">For each menu option, specify the following:</span></span>

- <span data-ttu-id="a4cdb-154">**ダイヤルキー** : 電話のキーパッドのキーを使用して、このオプションにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-154">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="a4cdb-155">音声入力が利用可能な場合、発信者はこの番号を使ってオプションにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-155">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="a4cdb-156">**音声コマンド** -音声入力が有効になっている場合に、発信者がこのオプションにアクセスできる音声コマンドを定義します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-156">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="a4cdb-157">"カスタマーサービス" や "運営および根拠" など、複数の単語を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-157">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="a4cdb-158">たとえば、発信者は2を押すか、「2」と言って、「売上」と言って2つのキーに対応するオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-158">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="a4cdb-159">このテキストは、サービス確認プロンプトの音声合成によっても表示されます。これは、「売上への通話転送」のようなものである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-159">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="a4cdb-160">[ **Redirect to** ]: 発信者がこのオプションを選択したときに使用される通話ルーティング先。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-160">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="a4cdb-161">自動応答または通話キューにリダイレクトする場合は、それに関連付けられているリソースアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-161">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="a4cdb-162">ディレクトリ検索</span><span class="sxs-lookup"><span data-stu-id="a4cdb-162">Directory search</span></span>

<span data-ttu-id="a4cdb-163">ダイヤルキーを宛先に割り当てる場合は、[ **ディレクトリ検索** ] で [ **なし** ] を選ぶことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-163">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="a4cdb-164">発信者が、特定の宛先に割り当てられているキーを使用して名前または内線番号をダイヤルしようとした場合、名前または内線番号の入力が完了する前に、送信先に予期せずルーティングされることがあります。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-164">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="a4cdb-165">ディレクトリ検索用に別の自動応答を作成し、ダイヤルキーを使用して、メインの自動応答へのリンクを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-165">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="a4cdb-166">ダイヤルキーを割り当てなかった場合は、 **ディレクトリ検索** のオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-166">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="a4cdb-167">**名前でダイヤル** -このオプションを有効にした場合、発信者は電話のキーパッドでユーザーの名前を読み上げるか、入力することができます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-167">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="a4cdb-168">電話システムのライセンスを持っているか、または Skype for Business Server を使用してオンプレミスでホストされているすべてのユーザーは、資格のあるユーザーであり、名前でダイヤルすることができます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-168">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="a4cdb-169">([ [ダイヤルのスコープ](#dial-scope) ] ページのディレクトリに含まれていないユーザーを設定することができます。)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-169">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="a4cdb-170">**内線番号でダイヤル** -このオプションを有効にすると、発信者は電話内線番号をダイヤルして組織内のユーザーに接続できます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-170">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="a4cdb-171">電話システムのライセンスを持っているか、または Skype for Business Server を使用してオンプレミスでホストされているすべてのユーザーは、資格のあるユーザーであり、 **内線でダイヤル** することができます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-171">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="a4cdb-172">([ [ダイヤルのスコープ](#dial-scope) ] ページのディレクトリに含まれていないユーザーを設定することができます。)</span><span class="sxs-lookup"><span data-stu-id="a4cdb-172">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="a4cdb-173">内線番号を使用できるようにするには、Active Directory または Azure Active Directory で定義されている次のいずれかの電話属性の一部として内線番号を指定する必要があります (詳しくは、「 [ユーザーを個別にまたは一括で追加](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) する」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-173">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="a4cdb-174">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="a4cdb-174">OfficePhone</span></span>
- <span data-ttu-id="a4cdb-175">HomePhone</span><span class="sxs-lookup"><span data-stu-id="a4cdb-175">HomePhone</span></span>
- <span data-ttu-id="a4cdb-176">携帯電話/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="a4cdb-176">Mobile/MobilePhone</span></span>
- <span data-ttu-id="a4cdb-177">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="a4cdb-177">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="a4cdb-178">その他の電話</span><span class="sxs-lookup"><span data-stu-id="a4cdb-178">OtherTelephone</span></span>

<span data-ttu-id="a4cdb-179">[ユーザー電話番号] フィールドに内線番号を入力するために必要な形式は、" *+ \<phone number> ext = \<extension>* " または " *+ \<phone number> x \<extension>* " のどちらかです。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-179">The required format to enter the extension in the user phone number field is either *+\<phone number>ext=\<extension>* or *+\<phone number>x\<extension>*.</span></span>

<span data-ttu-id="a4cdb-180">拡張機能は、 [Microsoft 365 管理センター](https://admin.microsoft.com/) または [Azure Active Directory 管理センター](https://aad.portal.azure.com)で設定できます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-180">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="a4cdb-181">自動応答と通話キューに対して変更が利用可能になるまでに最大12時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-181">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="a4cdb-182">[ **名前によるダイヤル** ] と [ **内線番号** ] の両方の機能を使用する場合は、メインの自動応答でダイヤルキーを割り当てることで、 **名前でダイヤル** できる自動応答に到達することができます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-182">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="a4cdb-183">この自動応答では、 **内線番号** の自動応答に到達するために、1つのキー (文字が関連付けられていないもの) を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-183">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="a4cdb-184">**ディレクトリ検索** オプションを選んだら、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-184">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="a4cdb-185">営業時間外の通話フロー</span><span class="sxs-lookup"><span data-stu-id="a4cdb-185">Call flow for after hours</span></span>

![時間と時刻の設定後のスクリーンショット](media/auto-attendant-business-hours.png)

<span data-ttu-id="a4cdb-187">営業時間は、自動応答ごとに設定できます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-187">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="a4cdb-188">勤務時間が設定されていない場合、24/7 のスケジュールは既定で設定されているため、その日のすべての曜日とすべての時間は営業時間と見なされます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-188">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="a4cdb-189">営業時間は、その日の休暇によって設定できます。また、業務時間として設定されていない時間は、時間の経過に応じて処理されます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-189">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="a4cdb-190">異なる着信通話処理オプションと応答メッセージは、時間経過に応じて設定できます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-190">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="a4cdb-191">自動応答と通話キューをどのように設定したかに応じて、直通電話番号を使用した自動応答に対して、時間の経過後の通話ルーティングを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-191">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="a4cdb-192">発信者に対して個別の通話ルーティングを使用する場合は、各曜日の勤務時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-192">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="a4cdb-193">[ **新しい日時の追加** ] をクリックして、昼食を指定するなど、特定の日に複数の時間のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-193">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="a4cdb-194">勤務時間を指定したら、時間の経過後に通話ルーティングオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-194">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="a4cdb-195">上記で指定した勤務時間の通話ルーティングの場合と同じオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-195">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="a4cdb-196">完了したら、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-196">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="a4cdb-197">休日中の通話フロー</span><span class="sxs-lookup"><span data-stu-id="a4cdb-197">Call flows during holidays</span></span>

![ホリデーシーズンとホリデーシーズンの案内応答の設定のスクリーンショット](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="a4cdb-199">自動応答には、設定した [休日](set-up-holidays-in-teams.md)ごとにコールフローを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-199">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="a4cdb-200">各自動応答には、最大 20 個の決められた休業日を追加できます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-200">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="a4cdb-201">[ホリデー通話の設定] ページで、[ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-201">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="a4cdb-202">この祝日設定の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-202">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="a4cdb-203">[ **休日** ] ドロップダウンから、使用する休日を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-203">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="a4cdb-204">使用する応答メッセージの種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-204">Choose the type of greeting that you want to use.</span></span>

    ![ホリデー呼のアクション設定のスクリーンショット](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="a4cdb-206">通話を **切断** するか、または **リダイレクト** するかを選びます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-206">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="a4cdb-207">リダイレクトを選択した場合は、通話の通話ルーティング先を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-207">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="a4cdb-208">[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-208">Click **Save**.</span></span>

![休日が表示されている休日の設定のスクリーンショット](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="a4cdb-210">追加の休日ごとに、必要に応じて手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-210">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="a4cdb-211">すべての祝日を追加したら、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-211">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="a4cdb-212">ダイヤルスコープ</span><span class="sxs-lookup"><span data-stu-id="a4cdb-212">Dial scope</span></span>

![ダイヤルスコープのオプションと除外オプションのスクリーンショット](media/auto-attendant-dial-scope.png)

<span data-ttu-id="a4cdb-214">*ダイヤルスコープ* は、発信者がダイヤルバイネームまたはダイヤルバイエクステンションを使用しているときに、どのユーザーがディレクトリで利用できるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-214">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="a4cdb-215">**すべてのオンラインユーザー** の既定値には、電話システムのライセンスを持っているか、または Skype For business Server を使用してオンプレミスでホストされている組織内のすべてのユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-215">The default of **All online users** includes all users in your organization that are Online users with a Phone System license or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="a4cdb-216">特定のユーザーを含めたり除外したりするには、1つ以上の Microsoft 365 グループ、配布リスト、またはセキュリティグループを **含める** か **除外** するかの下にある [ **カスタムユーザーグループ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-216">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="a4cdb-217">たとえば、組織の役職をダイヤルディレクトリから除外することができます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-217">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="a4cdb-218">(両方のリストに含まれているユーザーは、ディレクトリから除外されます)。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-218">(If a user is in both lists, they will be excluded from the directory.)</span></span>

> [!NOTE]
> <span data-ttu-id="a4cdb-219">新しいユーザーの名前がディレクトリに表示されるまでに、最大36時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-219">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="a4cdb-220">ダイヤルスコープの設定が完了したら、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-220">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="a4cdb-221">リソースアカウント</span><span class="sxs-lookup"><span data-stu-id="a4cdb-221">Resource accounts</span></span>

<span data-ttu-id="a4cdb-222">自動応答には、リソースアカウントが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-222">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="a4cdb-223">第1レベルの自動応答には、サービス番号が関連付けられた少なくとも1つのリソースアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-223">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="a4cdb-224">必要に応じて、複数のリソースアカウントを1つの自動応答に割り当てることができます。それぞれに個別のサービス番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-224">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![リソースアカウントの [アカウントの追加] パネルのスクリーンショット](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="a4cdb-226">リソースアカウントを追加するには、[ **アカウントの追加** ] をクリックして、追加するアカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-226">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="a4cdb-227">[ **追加** ] をクリックし、[ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-227">Click **Add** , and then click **Add**.</span></span>

![割り当てられたサービス番号のリソースアカウントを示すリソースアカウント一覧のスクリーンショット](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="a4cdb-229">サービスアカウントの追加が完了したら、[ **送信** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-229">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="a4cdb-230">これで自動応答の構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-230">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="a4cdb-231">外部電話番号の転送-技術的な詳細</span><span class="sxs-lookup"><span data-stu-id="a4cdb-231">External phone number transfers - technical details</span></span>

<span data-ttu-id="a4cdb-232">自動応答が外部から通話を転送できるようにするには、 [前提条件](plan-auto-attendant-call-queue.md#prerequisites) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-232">Please refer to the [Prerequisites](plan-auto-attendant-call-queue.md#prerequisites) in order to allow auto attendants to transfer calls externally.</span></span>  <span data-ttu-id="a4cdb-233">さらに：</span><span class="sxs-lookup"><span data-stu-id="a4cdb-233">In addition:</span></span>

- <span data-ttu-id="a4cdb-234">[通話プラン](calling-plans-for-office-365.md)番号のあるリソースアカウントの場合、外部の転送先電話番号は、e.i 形式 (+ [国コード] [市外局番] [電話番号]) に入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-234">For a resource account with a [Calling Plan](calling-plans-for-office-365.md) number, the external transfer phone number must be entered in E.164 format (+[country code][area code][phone number]).</span></span>

- <span data-ttu-id="a4cdb-235">直接ルーティング番号を持つリソースアカウントの場合、[外部転送電話番号] 形式は、 [セッション境界コントローラー (SBC)](direct-routing-connect-the-sbc.md) の設定に依存します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-235">For a resource account with a Direct Routing number, the external transfer phone number format is dependant on the [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) settings.</span></span>

<span data-ttu-id="a4cdb-236">表示される発信電話番号は、次のように決定されます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-236">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="a4cdb-237">プラン番号を呼び出すには、元の発信者の電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-237">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="a4cdb-238">直接ルーティング番号の場合、送信された番号は、次のように、SBC の P (PAI) 設定に基づいています。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-238">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="a4cdb-239">[無効] に設定すると、元の発信者の電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-239">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="a4cdb-240">これは既定の推奨設定です。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-240">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="a4cdb-241">[有効] に設定されている場合は、リソースアカウントの電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-241">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="a4cdb-242">Skype for Business のハイブリッド環境で、自動応答の着信を PSTN に転送するには、[着信の転送] が PSTN 番号に設定された新しいオンプレミスユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-242">In a Skype for Business hybrid environment, to transfer an auto attendant call to the PSTN, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="a4cdb-243">ユーザーはエンタープライズ Voip 用に有効になっていて、音声ポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-243">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="a4cdb-244">詳細については、「 [自動応答で PSTN に転送](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-244">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="a4cdb-245">PowerShell を使用して自動応答を作成する</span><span class="sxs-lookup"><span data-stu-id="a4cdb-245">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="a4cdb-246">PowerShell を使用して自動応答を作成し、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-246">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="a4cdb-247">自動応答を管理するために必要なコマンドレットを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="a4cdb-247">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="a4cdb-248">新しい-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="a4cdb-248">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [<span data-ttu-id="a4cdb-249">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="a4cdb-249">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [<span data-ttu-id="a4cdb-250">CsAutoAttendant の入手</span><span class="sxs-lookup"><span data-stu-id="a4cdb-250">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [<span data-ttu-id="a4cdb-251">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="a4cdb-251">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [<span data-ttu-id="a4cdb-252">CsAutoAttendant の削除</span><span class="sxs-lookup"><span data-stu-id="a4cdb-252">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [<span data-ttu-id="a4cdb-253">新規-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="a4cdb-253">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [<span data-ttu-id="a4cdb-254">新しい-Csonline Audiofile</span><span class="sxs-lookup"><span data-stu-id="a4cdb-254">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [<span data-ttu-id="a4cdb-255">新規-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="a4cdb-255">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [<span data-ttu-id="a4cdb-256">エクスポート-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="a4cdb-256">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [<span data-ttu-id="a4cdb-257">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="a4cdb-257">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [<span data-ttu-id="a4cdb-258">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="a4cdb-258">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [<span data-ttu-id="a4cdb-259">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="a4cdb-259">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [<span data-ttu-id="a4cdb-260">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="a4cdb-260">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [<span data-ttu-id="a4cdb-261">新規-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="a4cdb-261">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [<span data-ttu-id="a4cdb-262">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="a4cdb-262">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [<span data-ttu-id="a4cdb-263">インポート-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="a4cdb-263">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [<span data-ttu-id="a4cdb-264">新規-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="a4cdb-264">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)


## <a name="related-topics"></a><span data-ttu-id="a4cdb-265">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4cdb-265">Related topics</span></span>

[<span data-ttu-id="a4cdb-266">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="a4cdb-266">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="a4cdb-267">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="a4cdb-267">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="a4cdb-268">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="a4cdb-268">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="a4cdb-269">小規模企業の例—自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="a4cdb-269">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa) 

[<span data-ttu-id="a4cdb-270">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="a4cdb-270">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
