#### <a name="before-you-begin"></a><span data-ttu-id="5b9f9-101">はじめに</span><span class="sxs-lookup"><span data-stu-id="5b9f9-101">Before you begin</span></span>

<span data-ttu-id="5b9f9-102">組織外から直接ダイヤルしてアクセスできる自動応答に必要なサービス番号 (サービス番号は、自動応答で使用される特殊な種類の電話番号) を取得します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-102">Get the service numbers (service numbers are a special type of phone number that are used by auto attendants) that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="5b9f9-103">これには、別 [のプロバイダーからの番号の転送](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) や、新 [しいサービス番号の要求が含まれる場合があります](../getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-103">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="5b9f9-104">各自動応答には、仮想ユーザー ライセンス電話システム割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-104">Each auto attendant needs to be assigned a Phone System - Virtual User license.</span></span> <span data-ttu-id="5b9f9-105">Business Voice を購入した場合は、多数の仮想電話システムライセンスも受け取ったので、それ以上要求する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-105">When you purchased Business Voice, you also received a number of Phone System - Virtual User licenses, so you probably don't need to request more.</span></span> <span data-ttu-id="5b9f9-106">ただし、今後さらに必要な場合は、「仮想ユーザー ライセンス 」 の手順に従電話システム[取得できます](../teams-add-on-licensing/virtual-user.md)。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-106">However, if you need more in the future, you can get them by following the instructions in [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="5b9f9-107">休日に自動応答ルートの呼び出しを異なる方法で行[](../set-up-holidays-in-teams.md)う場合は、自動応答を作成する前に、使用する祝日を作成します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-107">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="5b9f9-108">自動応答を設定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-108">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="5b9f9-109">手順 1 電話 <br> 番号</span><span class="sxs-lookup"><span data-stu-id="5b9f9-109">Step 1<br>Phone number</span></span>](#tab/phone-number)

> [!NOTE]
> <span data-ttu-id="5b9f9-110">初めて Business Voice を設定する手順に従っている場合、[手順 **6:** 会社の主要電話番号の自動応答を設定する] をオンにしている場合は、このタブの手順を既に完了しています。次のタブに移動します。 [自動応答の一般的な情報](?tabs=general-info#steps)。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-110">If you're following the steps to set up Business Voice for the first time and you're on **Step 6: Set up an auto attendant for your company's main phone number**, you've already finished the steps on this tab. Move to the next tab: [Auto attendant general info](?tabs=general-info#steps).</span></span>

<span data-ttu-id="5b9f9-111">作成する各自動応答には、リソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-111">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="5b9f9-112">これは、ユーザー アカウントに似ていますが、アカウントがユーザーではなく自動応答キューまたは通話キューに関連付けられている点を除きます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-112">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="5b9f9-113">この手順では、アカウントを作成し、仮想ユーザー ライセンスMicrosoft 365 電話システム割り当て、サービス番号を割り当てします。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-113">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="5b9f9-114">リソース アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="5b9f9-114">Create a resource account</span></span>

<span data-ttu-id="5b9f9-115">リソース アカウントは、管理センター Teams作成できます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-115">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="5b9f9-116">管理センター Teams、組織全体の設定 **を** 展開し、[リソース アカウント]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-116">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="5b9f9-117">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-117">Click **Add**.</span></span>

3. <span data-ttu-id="5b9f9-118">[リソース **アカウントの追加]** ウィンドウで、[表示名] 、[ユーザー名]**を入力\*\*\*\*し**、[リソース アカウントの種類] で [**自動** 応答]**を選択します。**</span><span class="sxs-lookup"><span data-stu-id="5b9f9-118">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![リソース アカウントのユーザー インターフェイスの追加のスクリーンショット](../media/resource-account-add.png)

4. <span data-ttu-id="5b9f9-120">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-120">Click **Save**.</span></span>

    <span data-ttu-id="5b9f9-121">新しいアカウントがアカウントの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-121">The new account will appear in the list of accounts.</span></span>

    ![リソース アカウントの一覧のスクリーンショット](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="5b9f9-123">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="5b9f9-123">Assign a license</span></span>

<span data-ttu-id="5b9f9-124">リソース アカウントには、Microsoft 365 電話システム *仮想ユーザー ライセンスを割* り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-124">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="5b9f9-125">管理センター Microsoft 365、ライセンスを割り当てるリソース アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-125">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="5b9f9-126">[ライセンスと **アプリ] タブの**[ライセンス **] の下で**、[Microsoft 365 電話システム **- 仮想ユーザー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-126">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="5b9f9-127">[変更 **を保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-127">Click **Save changes**.</span></span>

    ![管理者センターでライセンスを割り当てるユーザー インターフェイスMicrosoft 365スクリーンショット](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="5b9f9-129">サービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="5b9f9-129">Assign a service number</span></span>

<span data-ttu-id="5b9f9-130">この自動応答を電話番号で到達可能にする必要がある場合は、その番号をリソース アカウントに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-130">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="5b9f9-131">管理センター Teams [リソース アカウント]ページで、サービス番号を割り当てるリソース アカウントを選択し、[割り当て/割り当て解除] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-131">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="5b9f9-132">[数値 **電話] ドロップダウン** で、使用する数値の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-132">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="5b9f9-133">[割り **当て済み電話番号]** ボックスで、使用する番号を検索し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-133">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![サービス番号の割り当てユーザー インターフェイスのスクリーンショット](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="5b9f9-135">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-135">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5b9f9-136">手順 2 - 自動応答の一般的な></span><span class="sxs-lookup"><span data-stu-id="5b9f9-136">Step 2 - Auto attendant general info ></span></span>](?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="5b9f9-137">手順 2 <br> アテンダントの一般的な情報</span><span class="sxs-lookup"><span data-stu-id="5b9f9-137">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="5b9f9-138">自動応答を設定するには</span><span class="sxs-lookup"><span data-stu-id="5b9f9-138">To set up an auto attendant</span></span>

1. <span data-ttu-id="5b9f9-139">管理センター Teams[音声] を **展開し**、[**自動** 応答] をクリックし、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-139">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="5b9f9-140">上部のボックスに自動応答の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-140">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="5b9f9-141">演算子を指定する場合は、オペレーターの呼び出し先を指定します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-141">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="5b9f9-142">これは省略可能です (ただし、推奨)。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-142">This is optional (but recommended).</span></span> <span data-ttu-id="5b9f9-143">[オペレーター] **オプションを設定** すると、呼び出し元がメニューから抜け出し、指定されたユーザーと話すことができます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-143">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="5b9f9-144">この自動応答のタイム ゾーンを指定します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-144">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="5b9f9-145">タイム ゾーンは、時間外に別の通話フローを作成する場合に、営業時間の計算に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-145">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="5b9f9-146">この自動応答の言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-146">Specify a language for this auto attendant.</span></span> <span data-ttu-id="5b9f9-147">これは、システムで生成された音声プロンプトに使用される言語です。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-147">This is the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="5b9f9-148">音声入力を有効にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-148">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="5b9f9-149">有効にすると、すべてのメニュー オプションの名前が音声認識キーワードになります。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-149">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="5b9f9-150">たとえば、呼び出し元が "One" と言ってキー 1 にマップされたメニュー オプションを選択したり、"Sales" と読み上げ、"Sales" という名前のメニュー オプションを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-150">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![名前、オペレーター、タイム ゾーン、言語、音声入力の自動応答設定のスクリーンショット](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="5b9f9-152">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-152">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5b9f9-153">手順 3 - フローの呼び出し></span><span class="sxs-lookup"><span data-stu-id="5b9f9-153">Step 3 - Call flow ></span></span>](?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="5b9f9-154">手順 3 通話 <br> フロー</span><span class="sxs-lookup"><span data-stu-id="5b9f9-154">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="5b9f9-155">通話フローのオプションを選択する</span><span class="sxs-lookup"><span data-stu-id="5b9f9-155">Choose your call flow options</span></span>

1. <span data-ttu-id="5b9f9-156">自動応答が通話に応答するときに、あいさつを再生する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-156">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="5b9f9-157">[オーディオ ファイルの **再生] を** 選択した場合は、[アップロード ファイル] ボタンを使用して、オーディオとして保存された録音済みグリーティング メッセージをアップロードできます。WAV、.MP3、または .WMA 形式。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-157">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="5b9f9-158">記録は 5 MB 以下に設定できます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-158">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="5b9f9-159">[あいさつメッセージを入力する] を選択すると、自動応答が通話に応答すると、入力したテキスト (最大 1,000 文字) が読み上げされます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-159">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![あいさつメッセージの設定のスクリーンショット](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="5b9f9-161">通話のルーティング方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-161">Choose how you want to route the call.</span></span>

    <span data-ttu-id="5b9f9-162">[切断] **を選択** すると、自動応答によって通話がハングします。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-162">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="5b9f9-163">[通話の **リダイレクト] を選択** した場合は、通話ルーティングの宛先のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-163">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="5b9f9-164">[再生] メニュー **オプションを選択した** 場合は、[音声ファイルの再生] または [あいさつメッセージに入力] を選択し、メニュー オプションとディレクトリ検索の間で選択できます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-164">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![通話ルーティング設定のスクリーンショット](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="5b9f9-166">呼び出し元がダイヤル キーを使用して移動する場合は、[メニュー オプションの設定] で、発信者がダイヤル キーを押した場合に発生する操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-166">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="5b9f9-167">(この自動応答を会社のディレクトリとして作成する場合は、ダイヤル キー オプションを空白のままにします)。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-167">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="5b9f9-168">ダイヤル キーは、次の宛先に設定できます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-168">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="5b9f9-169">**組織内のユーザー** - 音声通話を受信できる組織内のユーザー。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-169">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="5b9f9-170">**音声アプリ** - 別の自動応答または通話キュー。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-170">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="5b9f9-171">**外部電話番号** - 任意の電話番号。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-171">**External phone number** - any phone number.</span></span> <span data-ttu-id="5b9f9-172">次の形式を使用します。+[国コード][地域コード][電話番号]</span><span class="sxs-lookup"><span data-stu-id="5b9f9-172">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="5b9f9-173">**ボイス** メール - 指定したグループに関連Microsoft 365ボイス メールボックス。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-173">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="5b9f9-174">**Operator** - 自動応答に対して定義された演算子。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-174">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="5b9f9-175">演算子の定義は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-175">Defining an operator is optional.</span></span> <span data-ttu-id="5b9f9-176">演算子は、この一覧内の他の宛先として定義できます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-176">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="5b9f9-177">オペレーターに 0 キーを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-177">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="5b9f9-178">各メニュー オプションで、次の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-178">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="5b9f9-179">**ダイヤル キー** - 電話キーパッドのキーを押して、このオプションにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-179">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="5b9f9-180">**[音声コマンド** ] - 音声入力が有効になっている場合に、呼び出し元がこのオプションにアクセスするために指定できる音声コマンドを定義します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-180">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="5b9f9-181">"Customer Service" や "Operations and Grounds" など、複数の単語を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-181">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="5b9f9-182">**[リダイレクト先** ] - 呼び出し元がこのオプションを選択するときに呼び出しを行う場所。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-182">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="5b9f9-183">自動応答または通話キューにリダイレクトする場合は、関連付けられているリソース アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-183">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![ダイヤル キー オプションのスクリーンショット](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="5b9f9-185">この自動応答を会社のディレクトリとして使用する場合は、[ディレクトリ検索] で [名前でダイヤル]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-185">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="5b9f9-186">このオプションを有効にすると、発信者はユーザーの名前を言うか、電話のキーパッドに入力できます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-186">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="5b9f9-187">ライセンスを持つオンライン ユーザー電話システム資格のあるユーザーであり、名前でダイヤルします。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-187">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="5b9f9-188">([内線番号 **によるダイヤル] を選択することもできます** が、拡張機能は Azure Active Directory)</span><span class="sxs-lookup"><span data-stu-id="5b9f9-188">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="5b9f9-189">ディレクトリ検索オプションを選択したら、[ **次へ** ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-189">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5b9f9-190">手順 4 - 時間外通話フローの></span><span class="sxs-lookup"><span data-stu-id="5b9f9-190">Step 4 - After hours call flow ></span></span>](?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="5b9f9-191">手順 4 時間 <br> 後</span><span class="sxs-lookup"><span data-stu-id="5b9f9-191">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="5b9f9-192">各自動応答に対して営業時間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-192">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="5b9f9-193">営業時間が設定されていない場合、24 時間 365 日のスケジュールが既定で設定されているので、1 日のすべての日とすべての時間が営業時間と見なされます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-193">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="5b9f9-194">営業時間は、日中の時間内の休憩を使用して設定できます。営業時間として設定されていないすべての時間は、時間外と見なされます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-194">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="5b9f9-195">異なる着信呼処理オプションとグリーティングを時間外に設定できます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-195">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="5b9f9-196">自動応答と通話キューの構成方法によっては、直接の電話番号を持つ自動応答の時間外通話ルーティングのみを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-196">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="5b9f9-197">時間外の発信者に対して個別の通話ルーティングが必要な場合は、各日の営業時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-197">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="5b9f9-198">[ **新しい時刻の追加]** をクリックして、特定の日に複数の時間セットを指定します (たとえば、昼休み時間を指定します)。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-198">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![時間外の日と時刻の設定のスクリーンショット](../media/auto-attendant-business-hours.png)

<span data-ttu-id="5b9f9-200">営業時間を指定したら、時間外の通話ルーティング オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-200">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="5b9f9-201">手順 3 - 呼び出しフローで指定した営業時間の通話ルーティングと同 **じオプションを使用できます**。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-201">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="5b9f9-202">完了 **したら、[** 次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-202">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5b9f9-203">手順 5 - 休日の呼び出しフロー></span><span class="sxs-lookup"><span data-stu-id="5b9f9-203">Step 5 - Holiday call flow ></span></span>](?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="5b9f9-204">手順 <br> 5 休日</span><span class="sxs-lookup"><span data-stu-id="5b9f9-204">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="5b9f9-205">自動応答への呼び出しは、他の日とは異なる方法で休日にルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-205">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="5b9f9-206">(休日に別の通話フローを設定したくない場合は、この手順をスキップできます)。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-206">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>

<span data-ttu-id="5b9f9-207">自動応答には、設定した休日ごとに通話フローを設定できます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-207">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="5b9f9-208">各自動応答には、最大 20 個の決められた休業日を追加できます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-208">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="5b9f9-209">[休日の通話設定] ページで、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-209">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="5b9f9-210">この休日の設定の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-210">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="5b9f9-211">[休日 **] ドロップダウン** から、使用する休日を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-211">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="5b9f9-212">使用するあいさつの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-212">Choose the type of greeting that you want to use.</span></span>

    ![休日と休日のあいさつ設定のスクリーンショット](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="5b9f9-214">通話を切断またはリダイレクト **する\*\*\*\*場合に** 選択します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-214">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="5b9f9-215">リダイレクトを選択した場合は、通話の通話ルーティング先を選択します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-215">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![休日の通話アクション設定のスクリーンショット](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="5b9f9-217">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-217">Click **Save**.</span></span>

    <span data-ttu-id="5b9f9-218">追加の休日ごとに、必要に応じて手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-218">Repeat the procedure as needed for each additional holiday.</span></span>

    ![休日が表示されている休日の設定のスクリーンショット](../media/auto-attendant-holiday-call-settings.png)

    <span data-ttu-id="5b9f9-220">すべての休日を追加した場合は、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-220">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5b9f9-221">手順 6 - ディレクトリ 内のユーザーを選択></span><span class="sxs-lookup"><span data-stu-id="5b9f9-221">Step 6 - Choose who's in the directory ></span></span>](?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="5b9f9-222">手順 6 <br> ディレクトリ メンバー</span><span class="sxs-lookup"><span data-stu-id="5b9f9-222">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="5b9f9-223">ダイヤル *スコープは、* 呼び出し元がダイヤルバイネームまたはダイヤルバイエクステンションを使用するときにディレクトリ内で使用できるユーザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-223">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="5b9f9-224">[すべてのオンライン **ユーザー] の既定値には**、組織内のすべてのユーザーが含まれます。このユーザーには、オンライン ライセンス電話システムがあります。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-224">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="5b9f9-225">[含める] または [除外] で [カスタムユーザー グループ] を選択し、1 つ以上のグループ、配布リスト、またはセキュリティ グループMicrosoft 365選択して、特定のユーザーを含めるか除外することができます。 </span><span class="sxs-lookup"><span data-stu-id="5b9f9-225">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="5b9f9-226">たとえば、組織内のエグゼクティブをダイヤル ディレクトリから除外する場合があります。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-226">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="5b9f9-227">(ユーザーが両方のリストに含む場合は、ディレクトリから除外されます)。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-227">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![ダイヤル スコープのスクリーンショットには、オプションと除外オプションが含まれます。](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="5b9f9-229">新しいユーザーがディレクトリに名前を表示するには、最大で 36 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-229">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="5b9f9-230">ダイヤル スコープの設定が完了したら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-230">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5b9f9-231">手順 7 - リソース アカウントを割り当></span><span class="sxs-lookup"><span data-stu-id="5b9f9-231">Step 7 - Assign a resource account ></span></span>](?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="5b9f9-232">手順 7 <br> リソース アカウント</span><span class="sxs-lookup"><span data-stu-id="5b9f9-232">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="5b9f9-233">すべての自動応答には、関連付けられているリソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-233">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="5b9f9-234">最初のレベルの自動応答には、サービス番号が関連付けられている少なくとも 1 つのリソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-234">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="5b9f9-235">必要な場合は、複数のリソース アカウントを自動応答に割り当て、それぞれに個別のサービス番号を割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-235">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="5b9f9-236">リソース アカウントを追加するには</span><span class="sxs-lookup"><span data-stu-id="5b9f9-236">To add a resource account</span></span>

1. <span data-ttu-id="5b9f9-237">[ **追加]** をクリックし、追加するアカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-237">Click **Add** and search for the account that you want to add.</span></span> <span data-ttu-id="5b9f9-238">[追加 **] を** クリックし、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-238">Click **Add**, and then click **Add**.</span></span>

    ![リソース アカウントの [アカウントの追加] パネルのスクリーンショット](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="5b9f9-240">サービス アカウントの追加が完了したら、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-240">When you have finished adding service accounts, click **Submit**.</span></span>

    ![サービス番号が割り当てられているリソース アカウントを示すリソース アカウント 一覧のスクリーンショット](../media/auto-attendant-resource-account-assigned.png)

    <span data-ttu-id="5b9f9-242">これで自動応答の構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="5b9f9-242">This completes the auto attendant configuration.</span></span>

---
