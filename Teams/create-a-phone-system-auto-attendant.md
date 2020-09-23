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
ms.openlocfilehash: 2cb796db37f40025dc7a78123da729fd5812bbbb
ms.sourcegitcommit: 22e2f51abf879b34701064839d0e410758b6a3dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48220238"
---
# <a name="set-up-an-auto-attendant"></a><span data-ttu-id="90058-103">自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="90058-103">Set up an auto attendant</span></span>

<span data-ttu-id="90058-104">自動応答を使うと、ユーザーが組織を呼び出したり、メニューシステムを移動して、適切な部門、通話キュー、人、またはオペレーターと話すことができます。</span><span class="sxs-lookup"><span data-stu-id="90058-104">Auto attendants let people call your organization and navigate a menu system to speak to the right department, call queue, person, or an operator.</span></span> <span data-ttu-id="90058-105">Microsoft Teams 管理センターまたは PowerShell を使用して、組織の自動応答を作成できます。</span><span class="sxs-lookup"><span data-stu-id="90058-105">You can create auto attendants for your organization with the Microsoft Teams admin center, or with PowerShell.</span></span> 

<span data-ttu-id="90058-106">この記事に記載されている手順を実行する前に、「 [Teams の自動応答と通話キューのプラン](plan-auto-attendant-call-queue.md) 」を参照して、 [作業の開始の手順](plan-auto-attendant-call-queue.md#getting-started) に従っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="90058-106">Be sure you have read [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) and followed the [getting started steps](plan-auto-attendant-call-queue.md#getting-started) before you follow the procedures in this article.</span></span>

<span data-ttu-id="90058-107">自動応答では、発信者の入力に基づいて、次のいずれかの宛先に通話を転送できます。</span><span class="sxs-lookup"><span data-stu-id="90058-107">Auto attendants can direct calls, based on callers' input, to one of the following destinations:</span></span>

- <span data-ttu-id="90058-108">**組織内のユーザー** -音声通話を受信できる組織内のユーザー。</span><span class="sxs-lookup"><span data-stu-id="90058-108">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span> <span data-ttu-id="90058-109">これは、オンラインユーザーまたは Skype for Business Server を使用してオンプレミスでホストされているユーザーのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="90058-109">This can be an online user or a user hosted on-premises using Skype for Business Server.</span></span>
- <span data-ttu-id="90058-110">**音声アプリ** -別の自動応答または通話キュー。</span><span class="sxs-lookup"><span data-stu-id="90058-110">**Voice app** - another auto attendant or a call queue.</span></span> <span data-ttu-id="90058-111">(この宛先を選択するときに、自動応答または通話キューに関連付けられているリソースアカウントを選びます。)</span><span class="sxs-lookup"><span data-stu-id="90058-111">(Choose the resource account associated with the auto attendant or call queue when choosing this destination.)</span></span>
- <span data-ttu-id="90058-112">**外部電話番号** -任意の電話番号。</span><span class="sxs-lookup"><span data-stu-id="90058-112">**External phone number** - any phone number.</span></span> <span data-ttu-id="90058-113">(「 [外部転送技術の詳細](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="90058-113">(See [external transfer technical details](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).</span></span>
- <span data-ttu-id="90058-114">**ボイス** メール-指定した Microsoft 365 グループに関連付けられているボイスメールボックス。</span><span class="sxs-lookup"><span data-stu-id="90058-114">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
- <span data-ttu-id="90058-115">**Operator** -自動応答に対して定義されているオペレーター。</span><span class="sxs-lookup"><span data-stu-id="90058-115">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="90058-116">演算子の定義は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="90058-116">Defining an operator is optional.</span></span> <span data-ttu-id="90058-117">このリストでは、演算子を他の任意の宛先として定義できます。</span><span class="sxs-lookup"><span data-stu-id="90058-117">The operator can be defined as any of the other destinations in this list.</span></span>

<span data-ttu-id="90058-118">自動応答をセットアップするときに、これらのオプションのいずれかを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="90058-118">You'll be prompted to choose one of these options at various stages as you set up an auto attendant.</span></span>

<span data-ttu-id="90058-119">自動応答を設定するには、Teams 管理センターで、[ **音声**]、[ **自動応答**]、[ **追加**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="90058-119">To set up an auto attendant, in the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

## <a name="general-info"></a><span data-ttu-id="90058-120">一般的な情報</span><span class="sxs-lookup"><span data-stu-id="90058-120">General info</span></span>

![](media/auto-attendant-general-info-page-new.png)

1. <span data-ttu-id="90058-121">上部のボックスに自動応答の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="90058-121">Type a name for the auto attendant in the box at the top.</span></span>

2. <span data-ttu-id="90058-122">オペレーターを指定する場合は、オペレーターへの通話の送信先を指定します。</span><span class="sxs-lookup"><span data-stu-id="90058-122">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="90058-123">これはオプションです (ただし推奨)。</span><span class="sxs-lookup"><span data-stu-id="90058-123">This is optional (but recommended).</span></span> <span data-ttu-id="90058-124">[ **オペレーター** ] オプションを設定すると、発信者はメニューから抜け、指定したユーザーに向かって話すことができます。</span><span class="sxs-lookup"><span data-stu-id="90058-124">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

3. <span data-ttu-id="90058-125">この自動応答のタイムゾーンを指定します。</span><span class="sxs-lookup"><span data-stu-id="90058-125">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="90058-126">タイムゾーンは、勤務時間の計算に使用されます。これには、 [時間の経過に応じて個別のコールフローを作成](#call-flow-for-after-hours)します。</span><span class="sxs-lookup"><span data-stu-id="90058-126">The time zone is used for calculating business hours if you [create a separate call flow for after hours](#call-flow-for-after-hours).</span></span>

4. <span data-ttu-id="90058-127">この自動応答の言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="90058-127">Specify a language for this auto attendant.</span></span> <span data-ttu-id="90058-128">これは、システムによって生成される音声プロンプトで使用される言語です。</span><span class="sxs-lookup"><span data-stu-id="90058-128">This the language that will be used for system-generated voice prompts.</span></span>

5. <span data-ttu-id="90058-129">音声入力を有効にするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="90058-129">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="90058-130">有効にすると、すべてのメニューオプションの名前が音声認識のキーワードになります。</span><span class="sxs-lookup"><span data-stu-id="90058-130">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="90058-131">たとえば、発信者は "One" と言って、キー1にマップされているメニューオプションを選ぶか、"売上" という名前のメニューオプションを選ぶために "売上" と言うことができます。</span><span class="sxs-lookup"><span data-stu-id="90058-131">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

6. <span data-ttu-id="90058-132">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90058-132">Click **Next**.</span></span>

## <a name="call-flow"></a><span data-ttu-id="90058-133">コールフロー</span><span class="sxs-lookup"><span data-stu-id="90058-133">Call flow</span></span>

![](media/auto-attendant-call-flow-greeting-message.png)

<span data-ttu-id="90058-134">自動応答が着信に応答したときに応答メッセージを再生するかどうかを選びます。</span><span class="sxs-lookup"><span data-stu-id="90058-134">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

<span data-ttu-id="90058-135">[ **オーディオファイルの再生** ] を選択した場合は、[ **ファイルのアップロード** ] ボタンを使用して、録音したグリーティングメッセージをオーディオとして保存することができます。WAV、。MP3、またはです。WMA 形式。</span><span class="sxs-lookup"><span data-stu-id="90058-135">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="90058-136">記録は 5 MB 以下でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="90058-136">The recording can be no larger than 5 MB.</span></span>

<span data-ttu-id="90058-137">[ **グリーティングメッセージの入力** ] を選択した場合は、自動応答が着信に応答したときに、入力したテキスト (最大1000文字) のテキストが読み上げられます。</span><span class="sxs-lookup"><span data-stu-id="90058-137">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

![](media/auto-attendant-call-flow-route-call-message.png)

<span data-ttu-id="90058-138">通話のルーティング方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="90058-138">Choose how you want to route the call.</span></span>

<span data-ttu-id="90058-139">[ **切断**] を選択すると、自動応答が通話を切断します。</span><span class="sxs-lookup"><span data-stu-id="90058-139">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

<span data-ttu-id="90058-140">[通話の **リダイレクト**] を選択した場合は、いずれかの通話ルーティング先を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="90058-140">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

<span data-ttu-id="90058-141">[ **再生] メニューのオプション**を選択した場合は、 **オーディオファイルを再生** するか、 **あいさつメッセージを入力** するかを選択して、メニューオプションとディレクトリ検索のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="90058-141">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

### <a name="menu-options"></a><span data-ttu-id="90058-142">メニューオプション</span><span class="sxs-lookup"><span data-stu-id="90058-142">Menu options</span></span>

![](media/auto-attendant-call-flow-menu-options-complete.png)

<span data-ttu-id="90058-143">ダイヤルオプションの場合、電話のキーパッドの0-9 キーをいずれかの通話ルーティング先に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="90058-143">For dialing options, you can assign the 0-9 keys on the telephone keypad to one of the call routing destinations.</span></span> <span data-ttu-id="90058-144">(キー \* (繰り返し) と \# (戻る) は、システムによって予約されているため、再割り当てすることはできません。</span><span class="sxs-lookup"><span data-stu-id="90058-144">(The keys \* (Repeat) and \# (Back) are reserved by the system and can't be reassigned.)</span></span>

<span data-ttu-id="90058-145">キーマッピングは、継続的である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="90058-145">Key mappings don't have to be continuous.</span></span> <span data-ttu-id="90058-146">たとえば、キー0、1、3のメニューを作成してオプションにマップし、2つのキーを使用しないことができます。</span><span class="sxs-lookup"><span data-stu-id="90058-146">It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the 2 key isn't used.</span></span>

<span data-ttu-id="90058-147">構成済みの場合は、オペレーターに0キーをマッピングすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90058-147">We recommend mapping the 0 key to the operator if you have configured one.</span></span> <span data-ttu-id="90058-148">演算子がいずれのキーにも設定されていない場合は、音声コマンド "Operator" も無効になります。</span><span class="sxs-lookup"><span data-stu-id="90058-148">If the operator isn't set to any key, the voice command "Operator" is also disabled.</span></span> 

<span data-ttu-id="90058-149">各メニューオプションについて、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="90058-149">For each menu option, specify the following:</span></span>

- <span data-ttu-id="90058-150">**ダイヤルキー** : 電話のキーパッドのキーを使用して、このオプションにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="90058-150">**Dial key** - the key on the telephone keypad to access this option.</span></span> <span data-ttu-id="90058-151">音声入力が利用可能な場合、発信者はこの番号を使ってオプションにアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="90058-151">If voice inputs are available, callers can also say this number to access the option.</span></span>

- <span data-ttu-id="90058-152">**音声コマンド** -音声入力が有効になっている場合に、発信者がこのオプションにアクセスできる音声コマンドを定義します。</span><span class="sxs-lookup"><span data-stu-id="90058-152">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="90058-153">"カスタマーサービス" や "運営および根拠" など、複数の単語を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="90058-153">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> <span data-ttu-id="90058-154">たとえば、発信者は2を押すか、「2」と言って、「売上」と言って2つのキーに対応するオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="90058-154">For example, the caller can press 2, say "two," or say "Sales" to select the option mapped to the 2 key.</span></span> <span data-ttu-id="90058-155">このテキストは、サービス確認プロンプトの音声合成によっても表示されます。これは、「売上への通話転送」のようなものである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90058-155">This text is also rendered by text to speech for the service confirmation prompt, which might be something like "Transferring your call to sales."</span></span>

- <span data-ttu-id="90058-156">[ **Redirect to** ]: 発信者がこのオプションを選択したときに使用される通話ルーティング先。</span><span class="sxs-lookup"><span data-stu-id="90058-156">**Redirect to** - the call routing destination used when callers choose this option.</span></span> <span data-ttu-id="90058-157">自動応答または通話キューにリダイレクトする場合は、それに関連付けられているリソースアカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="90058-157">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

### <a name="directory-search"></a><span data-ttu-id="90058-158">ディレクトリ検索</span><span class="sxs-lookup"><span data-stu-id="90058-158">Directory search</span></span>

<span data-ttu-id="90058-159">ダイヤルキーを宛先に割り当てる場合は、[**ディレクトリ検索**] で [**なし**] を選ぶことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90058-159">If you assign dial keys to destinations, we recommend that you choose **None** for **Directory search**.</span></span> <span data-ttu-id="90058-160">発信者が、特定の宛先に割り当てられているキーを使用して名前または内線番号をダイヤルしようとした場合、名前または内線番号の入力が完了する前に、送信先に予期せずルーティングされることがあります。</span><span class="sxs-lookup"><span data-stu-id="90058-160">If a caller attempts to dial a name or extension using keys that are assigned to specific destinations, they may be unexpectedly routed to a destination before they finish entering the name or extension.</span></span> <span data-ttu-id="90058-161">ディレクトリ検索用に別の自動応答を作成し、ダイヤルキーを使用して、メインの自動応答へのリンクを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90058-161">We recommend that you create a separate auto attendant for directory search and have your main auto attendant link to it via a dial key.</span></span>

<span data-ttu-id="90058-162">ダイヤルキーを割り当てなかった場合は、 **ディレクトリ検索**のオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="90058-162">If you didn't assign dial keys, then choose an option for **Directory search**.</span></span>

<span data-ttu-id="90058-163">**名前でダイヤル** -このオプションを有効にした場合、発信者は電話のキーパッドでユーザーの名前を読み上げるか、入力することができます。</span><span class="sxs-lookup"><span data-stu-id="90058-163">**Dial by name** - If you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="90058-164">電話システムのライセンスを持っているか、または Skype for Business Server を使用してオンプレミスでホストされているすべてのユーザーは、資格のあるユーザーであり、名前でダイヤルすることができます。</span><span class="sxs-lookup"><span data-stu-id="90058-164">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with Dial by name.</span></span> <span data-ttu-id="90058-165">([ [ダイヤルのスコープ](#dial-scope) ] ページのディレクトリに含まれていないユーザーを設定することができます。)</span><span class="sxs-lookup"><span data-stu-id="90058-165">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="90058-166">**内線番号でダイヤル** -このオプションを有効にすると、発信者は電話内線番号をダイヤルして組織内のユーザーに接続できます。</span><span class="sxs-lookup"><span data-stu-id="90058-166">**Dial by extension** - If you enable this option, callers can connect with users in your organization by dialing their phone extension.</span></span> <span data-ttu-id="90058-167">電話システムのライセンスを持っているか、または Skype for Business Server を使用してオンプレミスでホストされているすべてのユーザーは、資格のあるユーザーであり、 **内線でダイヤル**することができます。</span><span class="sxs-lookup"><span data-stu-id="90058-167">Any online user with a Phone System license, or any user hosted on-premises using Skype for Business Server, is an eligible user and can be found with **Dial by extension**.</span></span> <span data-ttu-id="90058-168">([ [ダイヤルのスコープ](#dial-scope) ] ページのディレクトリに含まれていないユーザーを設定することができます。)</span><span class="sxs-lookup"><span data-stu-id="90058-168">(You can set who is and is not included in the directory on the [Dial scope](#dial-scope) page.)</span></span>

<span data-ttu-id="90058-169">内線番号を使用できるようにするには、Active Directory または Azure Active Directory で定義されている次のいずれかの電話属性の一部として内線番号を指定する必要があります (詳しくは、「 [ユーザーを個別にまたは一括で追加](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) する」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="90058-169">Users you wish to make available for Dial By Extension need to have an extension specified as part of one of the following phone attributes defined in Active Directory or Azure Active Directory (See [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) for more information.)</span></span>

- <span data-ttu-id="90058-170">OfficePhone</span><span class="sxs-lookup"><span data-stu-id="90058-170">OfficePhone</span></span>
- <span data-ttu-id="90058-171">HomePhone</span><span class="sxs-lookup"><span data-stu-id="90058-171">HomePhone</span></span>
- <span data-ttu-id="90058-172">携帯電話/MobilePhone</span><span class="sxs-lookup"><span data-stu-id="90058-172">Mobile/MobilePhone</span></span>
- <span data-ttu-id="90058-173">TelephoneNumber/PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="90058-173">TelephoneNumber/PhoneNumber</span></span>
- <span data-ttu-id="90058-174">その他の電話</span><span class="sxs-lookup"><span data-stu-id="90058-174">OtherTelephone</span></span>

<span data-ttu-id="90058-175">[ユーザー電話番号] フィールドに内線番号を入力するために必要な形式は、" \* + <phone number> ext = <extension> \* " または " \* + <phone number> x <extension> \*" のどちらかです。</span><span class="sxs-lookup"><span data-stu-id="90058-175">The required format to enter the extension in the user phone number field is either *+<phone number>ext=<extension>* or *+<phone number>x<extension>*.</span></span>

<span data-ttu-id="90058-176">拡張機能は、 [Microsoft 365 管理センター](https://admin.microsoft.com/) または [Azure Active Directory 管理センター](https://aad.portal.azure.com)で設定できます。</span><span class="sxs-lookup"><span data-stu-id="90058-176">You can set the extension in the [Microsoft 365 admin center](https://admin.microsoft.com/) or the [Azure Active Directory admin center](https://aad.portal.azure.com).</span></span> <span data-ttu-id="90058-177">自動応答と通話キューに対して変更が利用可能になるまでに最大12時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="90058-177">It can take up to 12 hours before changes are available to auto attendants and call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="90058-178">[ **名前によるダイヤル** ] と [ **内線番号** ] の両方の機能を使用する場合は、メインの自動応答でダイヤルキーを割り当てることで、 **名前でダイヤル**できる自動応答に到達することができます。</span><span class="sxs-lookup"><span data-stu-id="90058-178">If you want to use both the **Dial by name** and **Dial by extension** features, you can assign a dial key on your main auto attendant to reach an auto attendant enabled for **Dial by name**.</span></span> <span data-ttu-id="90058-179">この自動応答では、 **内線番号** の自動応答に到達するために、1つのキー (文字が関連付けられていないもの) を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="90058-179">Within that auto attendant, you can assign the 1 key (which has no letters associated with it) to reach the **Dial by extension** auto attendant.</span></span>

<span data-ttu-id="90058-180">**ディレクトリ検索**オプションを選んだら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90058-180">Once you have selected a **Directory search** option, click **Next**.</span></span>

## <a name="call-flow-for-after-hours"></a><span data-ttu-id="90058-181">営業時間外の通話フロー</span><span class="sxs-lookup"><span data-stu-id="90058-181">Call flow for after hours</span></span>

![](media/auto-attendant-business-hours.png)

<span data-ttu-id="90058-182">営業時間は、自動応答ごとに設定できます。</span><span class="sxs-lookup"><span data-stu-id="90058-182">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="90058-183">勤務時間が設定されていない場合、24/7 のスケジュールは既定で設定されているため、その日のすべての曜日とすべての時間は営業時間と見なされます。</span><span class="sxs-lookup"><span data-stu-id="90058-183">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="90058-184">営業時間は、その日の休暇によって設定できます。また、業務時間として設定されていない時間は、時間の経過に応じて処理されます。</span><span class="sxs-lookup"><span data-stu-id="90058-184">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="90058-185">異なる着信通話処理オプションと応答メッセージは、時間経過に応じて設定できます。</span><span class="sxs-lookup"><span data-stu-id="90058-185">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="90058-186">自動応答と通話キューをどのように設定したかに応じて、直通電話番号を使用した自動応答に対して、時間の経過後の通話ルーティングを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90058-186">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="90058-187">発信者に対して個別の通話ルーティングを使用する場合は、各曜日の勤務時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="90058-187">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="90058-188">[ **新しい日時の追加** ] をクリックして、昼食を指定するなど、特定の日に複数の時間のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="90058-188">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

<span data-ttu-id="90058-189">勤務時間を指定したら、時間の経過後に通話ルーティングオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="90058-189">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="90058-190">上記で指定した勤務時間の通話ルーティングの場合と同じオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="90058-190">The same options are available as for the business hours call routing that you specified above.</span></span>

<span data-ttu-id="90058-191">完了したら、[ **次へ** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90058-191">Click **Next** when you're done.</span></span>

## <a name="call-flows-during-holidays"></a><span data-ttu-id="90058-192">休日中の通話フロー</span><span class="sxs-lookup"><span data-stu-id="90058-192">Call flows during holidays</span></span>

![](media/auto-attendant-holiday-greeting.png)

<span data-ttu-id="90058-193">自動応答には、設定した [休日](set-up-holidays-in-teams.md)ごとにコールフローを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="90058-193">Your auto attendant can have a call flow for each [Holiday you've set up](set-up-holidays-in-teams.md).</span></span> <span data-ttu-id="90058-194">各自動応答には、最大 20 個の決められた休業日を追加できます。</span><span class="sxs-lookup"><span data-stu-id="90058-194">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="90058-195">[ホリデー通話の設定] ページで、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90058-195">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="90058-196">この祝日設定の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="90058-196">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="90058-197">[ **休日** ] ドロップダウンから、使用する休日を選択します。</span><span class="sxs-lookup"><span data-stu-id="90058-197">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="90058-198">使用する応答メッセージの種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="90058-198">Choose the type of greeting that you want to use.</span></span>

    ![](media/auto-attendant-holiday-actions.png)

5. <span data-ttu-id="90058-199">通話を **切断** するか、または **リダイレクト** するかを選びます。</span><span class="sxs-lookup"><span data-stu-id="90058-199">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="90058-200">リダイレクトを選択した場合は、通話の通話ルーティング先を選択します。</span><span class="sxs-lookup"><span data-stu-id="90058-200">If you chose to redirect, choose the call routing destination for the call.</span></span>

7. <span data-ttu-id="90058-201">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90058-201">Click **Save**.</span></span>

![](media/auto-attendant-holiday-call-settings.png)

<span data-ttu-id="90058-202">追加の休日ごとに、必要に応じて手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="90058-202">Repeat the procedure as needed for each additional holiday.</span></span>

<span data-ttu-id="90058-203">すべての祝日を追加したら、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90058-203">When you've added all your holidays, click **Next**.</span></span>

## <a name="dial-scope"></a><span data-ttu-id="90058-204">ダイヤルスコープ</span><span class="sxs-lookup"><span data-stu-id="90058-204">Dial scope</span></span>

![](media/auto-attendant-dial-scope.png)

<span data-ttu-id="90058-205">*ダイヤルスコープ*は、発信者がダイヤルバイネームまたはダイヤルバイエクステンションを使用しているときに、どのユーザーがディレクトリで利用できるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="90058-205">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="90058-206">**すべてのオンラインユーザー**の既定値には、電話システムのライセンスを持っているか、または Skype For business Server を使用してオンプレミスでホストされている組織内のすべてのユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="90058-206">The default of **All online users** includes all users in your organization that are Online users with a Phone System license or hosted on-premises using Skype for Business Server.</span></span>

<span data-ttu-id="90058-207">特定のユーザーを含めたり除外したりするには、1つ以上の Microsoft 365 グループ、配布リスト、またはセキュリティグループを**含める**か**除外**するかの下にある [**カスタムユーザーグループ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="90058-207">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="90058-208">たとえば、組織の役職をダイヤルディレクトリから除外することができます。</span><span class="sxs-lookup"><span data-stu-id="90058-208">For example, you might want to exclude executives in your organization from the dialing directory.</span></span>

> [!NOTE]
> <span data-ttu-id="90058-209">新しいユーザーの名前がディレクトリに表示されるまでに、最大36時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="90058-209">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="90058-210">ダイヤルスコープの設定が完了したら、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90058-210">When you're done setting the dial scope, click **Next**.</span></span>

## <a name="resource-accounts"></a><span data-ttu-id="90058-211">リソースアカウント</span><span class="sxs-lookup"><span data-stu-id="90058-211">Resource accounts</span></span>

<span data-ttu-id="90058-212">自動応答には、リソースアカウントが関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="90058-212">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="90058-213">第1レベルの自動応答には、サービス番号が関連付けられた少なくとも1つのリソースアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="90058-213">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="90058-214">必要に応じて、複数のリソースアカウントを1つの自動応答に割り当てることができます。それぞれに個別のサービス番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="90058-214">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

![](media/auto-attendant-add-resource-account.png)

<span data-ttu-id="90058-215">リソースアカウントを追加するには、[ **アカウントの追加** ] をクリックして、追加するアカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="90058-215">To add a resource account, click **Add account** and search for the account that you want to add.</span></span> <span data-ttu-id="90058-216">[ **追加**] をクリックし、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90058-216">Click **Add**, and then click **Add**.</span></span>

![](media/auto-attendant-resource-account-assigned.png)

<span data-ttu-id="90058-217">サービスアカウントの追加が完了したら、[ **送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90058-217">When you have finished adding service accounts, click **Submit**.</span></span> <span data-ttu-id="90058-218">これで自動応答の構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="90058-218">This completes the auto attendant configuration.</span></span>

## <a name="external-phone-number-transfers---technical-details"></a><span data-ttu-id="90058-219">外部電話番号の転送-技術的な詳細</span><span class="sxs-lookup"><span data-stu-id="90058-219">External phone number transfers - technical details</span></span>

<span data-ttu-id="90058-220">外部電話番号に通話を転送する場合、自動応答または通話キューに関連付けられているリソースアカウントには、電話番号と Microsoft 365 電話システム仮想ユーザーライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="90058-220">When transferring calls to an external phone number, the resource account associated with the auto attendant or call queue must have a phone number and a Microsoft 365 Phone System - Virtual User license.</span></span> <span data-ttu-id="90058-221">かつ：</span><span class="sxs-lookup"><span data-stu-id="90058-221">Additionally:</span></span>

- <span data-ttu-id="90058-222">通話プラン番号を持つリソースアカウントの場合は、 [通話プラン](calling-plans-for-office-365.md) ライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="90058-222">For a resource account with a Calling Plan number, assign a [Calling Plan](calling-plans-for-office-365.md) license.</span></span>
- <span data-ttu-id="90058-223">直接ルーティング番号を持つリソースアカウントの場合は、 [オンラインボイスルーティングポリシー](manage-voice-routing-policies.md)を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="90058-223">For a resource account with a Direct Routing number, assign an [online voice routing policy](manage-voice-routing-policies.md).</span></span>

<span data-ttu-id="90058-224">表示される発信電話番号は、次のように決定されます。</span><span class="sxs-lookup"><span data-stu-id="90058-224">The outbound phone number that's displayed is determined as follows:</span></span>

  - <span data-ttu-id="90058-225">プラン番号を呼び出すには、元の発信者の電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90058-225">For Calling Plan numbers, the original caller's phone number is displayed.</span></span>
  - <span data-ttu-id="90058-226">直接ルーティング番号の場合、送信された番号は、次のように、SBC の P (PAI) 設定に基づいています。</span><span class="sxs-lookup"><span data-stu-id="90058-226">For Direct Routing numbers, the number sent is based on the P-Asserted-Identity (PAI) setting on the SBC, as follows:</span></span>
    - <span data-ttu-id="90058-227">[無効] に設定すると、元の発信者の電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90058-227">If set to Disabled, the original caller's phone number is displayed.</span></span> <span data-ttu-id="90058-228">これは既定の推奨設定です。</span><span class="sxs-lookup"><span data-stu-id="90058-228">This is the default and recommended setting.</span></span>
    - <span data-ttu-id="90058-229">[有効] に設定されている場合は、リソースアカウントの電話番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="90058-229">If set to Enabled, the resource account phone number is displayed.</span></span>

<span data-ttu-id="90058-230">通話プラン trunks と直接ルーティング trunks の間の転送はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="90058-230">Transfers between Calling Plan trunks and Direct Routing trunks aren't supported.</span></span>

<span data-ttu-id="90058-231">ハイブリッド環境で、Skype for Business PSTN 統合経由で PSTN に自動応答の通話を転送するには、PSTN 番号に設定された通話転送を使用して、新しいオンプレミスユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="90058-231">In a hybrid environment, to transfer an auto attendant call to the PSTN via Skype for Business PSTN integration, create a new on-premises user with call forwarding set to the PSTN number.</span></span> <span data-ttu-id="90058-232">ユーザーはエンタープライズ Voip 用に有効になっていて、音声ポリシーが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="90058-232">The user must be enabled for Enterprise Voice and have a voice policy assigned.</span></span> <span data-ttu-id="90058-233">詳細については、「 [自動応答で PSTN に転送](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90058-233">To learn more, see [Auto attendant call transfer to PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).</span></span>

### <a name="create-an-auto-attendant-with-powershell"></a><span data-ttu-id="90058-234">PowerShell を使用して自動応答を作成する</span><span class="sxs-lookup"><span data-stu-id="90058-234">Create an auto attendant with PowerShell</span></span>

<span data-ttu-id="90058-235">PowerShell を使用して自動応答を作成し、設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="90058-235">You can also use PowerShell to create and set up auto attendants.</span></span> <span data-ttu-id="90058-236">自動応答を管理するために必要なコマンドレットを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="90058-236">Here are the cmdlets that you need to manage an auto attendant:</span></span>

- [<span data-ttu-id="90058-237">新しい-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="90058-237">New-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [<span data-ttu-id="90058-238">Set-CsAutoAttendant</span><span class="sxs-lookup"><span data-stu-id="90058-238">Set-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [<span data-ttu-id="90058-239">CsAutoAttendant の入手</span><span class="sxs-lookup"><span data-stu-id="90058-239">Get-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant?view=skype-ps)
- [<span data-ttu-id="90058-240">Get-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="90058-240">Get-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="90058-241">CsAutoAttendant の削除</span><span class="sxs-lookup"><span data-stu-id="90058-241">Remove-CsAutoAttendant</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [<span data-ttu-id="90058-242">新規-CsAutoAttendantMenu</span><span class="sxs-lookup"><span data-stu-id="90058-242">New-CsAutoAttendantMenu</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [<span data-ttu-id="90058-243">新しい-Csonline Audiofile</span><span class="sxs-lookup"><span data-stu-id="90058-243">New-CsOnlineAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [<span data-ttu-id="90058-244">新規-CsAutoAttendantCallFlow</span><span class="sxs-lookup"><span data-stu-id="90058-244">New-CsAutoAttendantCallFlow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [<span data-ttu-id="90058-245">エクスポート-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="90058-245">Export-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="90058-246">New-CsOnlineTimeRange</span><span class="sxs-lookup"><span data-stu-id="90058-246">New-CsOnlineTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [<span data-ttu-id="90058-247">New-CsOnlineDateTimeRange</span><span class="sxs-lookup"><span data-stu-id="90058-247">New-CsOnlineDateTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [<span data-ttu-id="90058-248">New-CsOnlineSchedule</span><span class="sxs-lookup"><span data-stu-id="90058-248">New-CsOnlineSchedule</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [<span data-ttu-id="90058-249">Get-CsAutoAttendantSupportedTimeZone</span><span class="sxs-lookup"><span data-stu-id="90058-249">Get-CsAutoAttendantSupportedTimeZone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [<span data-ttu-id="90058-250">新規-CsAutoAttendantCallHandlingAssociation</span><span class="sxs-lookup"><span data-stu-id="90058-250">New-CsAutoAttendantCallHandlingAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [<span data-ttu-id="90058-251">Get-CsAutoAttendantSupportedLanguage</span><span class="sxs-lookup"><span data-stu-id="90058-251">Get-CsAutoAttendantSupportedLanguage</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [<span data-ttu-id="90058-252">インポート-CsAutoAttendantHolidays</span><span class="sxs-lookup"><span data-stu-id="90058-252">Import-CsAutoAttendantHolidays</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [<span data-ttu-id="90058-253">新規-CsAutoAttendantCallableEntity</span><span class="sxs-lookup"><span data-stu-id="90058-253">New-CsAutoAttendantCallableEntity</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)


## <a name="related-topics"></a><span data-ttu-id="90058-254">関連項目</span><span class="sxs-lookup"><span data-stu-id="90058-254">Related topics</span></span>

[<span data-ttu-id="90058-255">電話システムで利用できる機能</span><span class="sxs-lookup"><span data-stu-id="90058-255">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="90058-256">サービス電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="90058-256">Getting service phone numbers</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="90058-257">国および地域ごとの電話会議および通話プランの利用可能性</span><span class="sxs-lookup"><span data-stu-id="90058-257">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[<span data-ttu-id="90058-258">小規模企業の例—自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="90058-258">Small business example — Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa) 

[<span data-ttu-id="90058-259">Windows PowerShell と Skype for Business Online の概要</span><span class="sxs-lookup"><span data-stu-id="90058-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
