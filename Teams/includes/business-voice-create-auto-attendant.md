#### <a name="video-demonstration"></a><span data-ttu-id="14421-101">ビデオデモ</span><span class="sxs-lookup"><span data-stu-id="14421-101">Video demonstration</span></span>

<span data-ttu-id="14421-102">このビデオでは、自動応答を作成する方法の基本的な例をTeams。</span><span class="sxs-lookup"><span data-stu-id="14421-102">This video shows a basic example of how to create an auto attendant in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

#### <a name="before-you-begin"></a><span data-ttu-id="14421-103">はじめに</span><span class="sxs-lookup"><span data-stu-id="14421-103">Before you begin</span></span>

<span data-ttu-id="14421-104">組織外から直接ダイヤルしてアクセスする自動応答に必要なサービス番号 (サービス番号は、自動応答で使用される特殊な種類の電話番号) を取得します。</span><span class="sxs-lookup"><span data-stu-id="14421-104">Get the service numbers (service numbers are a special type of phone number that are used by auto attendants) that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="14421-105">これには、別 [のプロバイダーから番号を転送](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) したり、新 [しいサービス番号を要求したりする場合があります](../getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="14421-105">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="14421-106">各自動応答には、仮想ユーザー ライセンス電話システム割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="14421-106">Each auto attendant needs to be assigned a Phone System - Virtual User license.</span></span> <span data-ttu-id="14421-107">Business Voice を購入した場合、多数の 電話システム - Virtual User ライセンスも受け取ったので、それ以上要求する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="14421-107">When you purchased Business Voice, you also received a number of Phone System - Virtual User licenses, so you probably don't need to request more.</span></span> <span data-ttu-id="14421-108">ただし、将来さらに必要な場合は、「仮想ユーザー ライセンス」の手順に従[電話システム取得できます](../teams-add-on-licensing/virtual-user.md)。</span><span class="sxs-lookup"><span data-stu-id="14421-108">However, if you need more in the future, you can get them by following the instructions in [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="14421-109">自動応答のルート呼び出しを休日に異なる方法で行[](../set-up-holidays-in-teams.md)う場合は、自動応答を作成する前に使用する祝日を作成します。</span><span class="sxs-lookup"><span data-stu-id="14421-109">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="14421-110">自動応答を設定するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="14421-110">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="14421-111">手順 1. <br> 電話番号</span><span class="sxs-lookup"><span data-stu-id="14421-111">Step 1<br>Phone number</span></span>](#tab/phone-number)

> [!NOTE]
> <span data-ttu-id="14421-112">Business Voice を初めてセットアップする手順に従っている場合は、「手順 **6:** 会社のメイン電話番号の自動応答を設定する」を参照してください。このタブの手順は既に完了しています。次のタブに移動します。 [自動応答の一般的な情報](?tabs=general-info#steps)。</span><span class="sxs-lookup"><span data-stu-id="14421-112">If you're following the steps to set up Business Voice for the first time and you're on **Step 6: Set up an auto attendant for your company's main phone number**, you've already finished the steps on this tab. Move to the next tab: [Auto attendant general info](?tabs=general-info#steps).</span></span>

<span data-ttu-id="14421-113">作成する各自動応答には、リソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="14421-113">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="14421-114">これはユーザー アカウントに似ていますが、アカウントがユーザーではなく自動応答または通話キューに関連付けられている点が除きます。</span><span class="sxs-lookup"><span data-stu-id="14421-114">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="14421-115">この手順では、アカウントを作成し、仮想ユーザー ライセンスMicrosoft 365 電話システム *割* り当て、サービス番号を割り当てします。</span><span class="sxs-lookup"><span data-stu-id="14421-115">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="14421-116">リソース アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="14421-116">Create a resource account</span></span>

<span data-ttu-id="14421-117">リソース アカウントは、管理センター Teams作成できます。</span><span class="sxs-lookup"><span data-stu-id="14421-117">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="14421-118">管理センター Teams、[組織全体の設定]**を展開し**、[リソース アカウント]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="14421-118">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="14421-119">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14421-119">Click **Add**.</span></span>

3. <span data-ttu-id="14421-120">[リソース **アカウントの追加]** ウィンドウで、[ **表示名]**、[ **ユーザー** 名] に入力し、[リソース アカウントの種類] に [ **自動応答** ] **を選択します。**</span><span class="sxs-lookup"><span data-stu-id="14421-120">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![リソース アカウントのユーザー インターフェイスの追加のスクリーンショット](../media/resource-account-add.png)

4. <span data-ttu-id="14421-122">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14421-122">Click **Save**.</span></span>

    <span data-ttu-id="14421-123">新しいアカウントがアカウントの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="14421-123">The new account will appear in the list of accounts.</span></span>

    ![リソース アカウントの一覧のスクリーンショット](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="14421-125">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="14421-125">Assign a license</span></span>

<span data-ttu-id="14421-126">リソース アカウントに Microsoft 365 電話システム *- 仮想ユーザー ライセンスを* 割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="14421-126">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="14421-127">管理センター Microsoft 365、ライセンスを割り当てるリソース アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="14421-127">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="14421-128">[ライセンスと **アプリ] タブの**[ライセンス]**で**、[仮想Microsoft 365 電話システム **- 仮想ユーザー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="14421-128">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="14421-129">[変更の **保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="14421-129">Click **Save changes**.</span></span>

    ![管理センターでのライセンスの割り当てユーザー インターフェイスMicrosoft 365スクリーンショット](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="14421-131">サービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="14421-131">Assign a service number</span></span>

<span data-ttu-id="14421-132">この自動応答に電話番号で到達できる必要がある場合は、その番号をリソース アカウントに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="14421-132">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="14421-133">管理センター Teamsの [リソース アカウント]ページで、サービス番号を割り当てるリソース アカウントを選択し、[割り当て/割り当て解除]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="14421-133">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="14421-134">[数値 **電話] ドロップダウンで**、使用する数値の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="14421-134">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="14421-135">[割 **り当てられた電話番号]** ボックスで、使用する番号を検索し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="14421-135">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![サービス番号の割り当てユーザー インターフェイスのスクリーンショット](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="14421-137">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14421-137">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="14421-138">手順 2 - 自動応答の一般的な情報></span><span class="sxs-lookup"><span data-stu-id="14421-138">Step 2 - Auto attendant general info ></span></span>](?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="14421-139">手順 2 <br> アテンダントの一般的な情報</span><span class="sxs-lookup"><span data-stu-id="14421-139">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="14421-140">自動応答を設定するには</span><span class="sxs-lookup"><span data-stu-id="14421-140">To set up an auto attendant</span></span>

1. <span data-ttu-id="14421-141">管理センター Teams、[音声] を **展開** し、[**自動** 応答] をクリックし、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="14421-141">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="14421-142">上部のボックスに自動応答の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="14421-142">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="14421-143">演算子を指定する場合は、演算子の呼び出し先を指定します。</span><span class="sxs-lookup"><span data-stu-id="14421-143">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="14421-144">これは省略可能です (ただし、推奨)。</span><span class="sxs-lookup"><span data-stu-id="14421-144">This is optional (but recommended).</span></span> <span data-ttu-id="14421-145">[オペレーター] **オプションを設定** して、発信者がメニューから抜け出し、指定されたユーザーと話し合うのを許可できます。</span><span class="sxs-lookup"><span data-stu-id="14421-145">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="14421-146">この自動応答のタイム ゾーンを指定します。</span><span class="sxs-lookup"><span data-stu-id="14421-146">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="14421-147">時間外の通話フローを個別に作成する場合、タイム ゾーンは営業時間の計算に使用されます。</span><span class="sxs-lookup"><span data-stu-id="14421-147">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="14421-148">この自動 [応答でサポートされている](../create-a-phone-system-auto-attendant-languages.md) 言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="14421-148">Specify a [supported language](../create-a-phone-system-auto-attendant-languages.md) for this auto attendant.</span></span> <span data-ttu-id="14421-149">これは、システムによって生成される音声プロンプトに使用される言語です。</span><span class="sxs-lookup"><span data-stu-id="14421-149">This is the language that will be used for system-generated voice prompts.</span></span> 

6. <span data-ttu-id="14421-150">音声入力を有効にする場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="14421-150">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="14421-151">有効にすると、すべてのメニュー オプションの名前が音声認識キーワードになります。</span><span class="sxs-lookup"><span data-stu-id="14421-151">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="14421-152">たとえば、発信者が "One" と言ってキー 1 にマップされているメニュー オプションを選択したり、"Sales" と言って "Sales" という名前のメニュー オプションを選択したりします。</span><span class="sxs-lookup"><span data-stu-id="14421-152">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![名前、オペレーター、タイム ゾーン、言語、音声入力の自動応答設定のスクリーンショット](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="14421-154">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14421-154">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="14421-155">手順 3 - 呼び出しフロー ></span><span class="sxs-lookup"><span data-stu-id="14421-155">Step 3 - Call flow ></span></span>](?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="14421-156">手順 3 通話 <br> フロー</span><span class="sxs-lookup"><span data-stu-id="14421-156">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="14421-157">通話フローのオプションを選択する</span><span class="sxs-lookup"><span data-stu-id="14421-157">Choose your call flow options</span></span>

1. <span data-ttu-id="14421-158">自動応答が通話に応答するときにあいさつメッセージを再生する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="14421-158">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="14421-159">[オーディオ ファイル **の再生]** を選択した場合は、[アップロード **ファイル**] ボタンを使用して、 にオーディオとして保存された録音されたあいさつメッセージをアップロードできます。WAV、.MP3、または 。WMA 形式。</span><span class="sxs-lookup"><span data-stu-id="14421-159">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="14421-160">記録は 5 MB 以下にできます。</span><span class="sxs-lookup"><span data-stu-id="14421-160">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="14421-161">[あいさつ文を入力する] を選択すると、自動応答が通話に応答すると、入力したテキスト (最大 1,000 文字) が読み上げされます。</span><span class="sxs-lookup"><span data-stu-id="14421-161">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![あいさつメッセージの設定のスクリーンショット](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="14421-163">通話のルーティング方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="14421-163">Choose how you want to route the call.</span></span>

    <span data-ttu-id="14421-164">[切断] **を選択** すると、自動応答によって通話が停止します。</span><span class="sxs-lookup"><span data-stu-id="14421-164">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="14421-165">[通話の **リダイレクト] を選択** した場合は、通話ルーティング先のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="14421-165">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="14421-166">[再生]**メニュー オプション を選択** した場合は、[音声ファイルの再生] または [あいさつメッセージに入力] を選択し、メニュー オプションとディレクトリ検索から選択できます。</span><span class="sxs-lookup"><span data-stu-id="14421-166">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![通話ルーティング設定のスクリーンショット](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="14421-168">発信者がダイヤル キーを使用して移動する場合は、[メニューオプションの設定] で、発信者がダイヤル キーを押した場合に実行する操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="14421-168">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="14421-169">(この自動応答を会社のディレクトリとして作成する場合は、ダイヤル キーオプションを空白のままにします)。</span><span class="sxs-lookup"><span data-stu-id="14421-169">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="14421-170">ダイヤル キーは、次の宛先に設定できます。</span><span class="sxs-lookup"><span data-stu-id="14421-170">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="14421-171">**組織内のユーザー** - 音声通話を受信できる組織内のユーザー。</span><span class="sxs-lookup"><span data-stu-id="14421-171">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="14421-172">**音声アプリ** - 別の自動応答または通話キュー。</span><span class="sxs-lookup"><span data-stu-id="14421-172">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="14421-173">**外部電話番号** - 任意の電話番号。</span><span class="sxs-lookup"><span data-stu-id="14421-173">**External phone number** - any phone number.</span></span> <span data-ttu-id="14421-174">+[国コード][地域コード][電話番号] の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="14421-174">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="14421-175">**ボイス** メール - 指定したグループに関連Microsoft 365ボイス メールボックス。</span><span class="sxs-lookup"><span data-stu-id="14421-175">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span> <span data-ttu-id="14421-176">ボイスメールの文字起こしと "トーンの後にメッセージを残してください" を選択できます。</span><span class="sxs-lookup"><span data-stu-id="14421-176">You can choose if you want voicemail transcriptions and the "Please leave a message after the tone."</span></span> <span data-ttu-id="14421-177">システム プロンプト。</span><span class="sxs-lookup"><span data-stu-id="14421-177">system prompt.</span></span>
    - <span data-ttu-id="14421-178">**演算子** - 自動応答に対して定義された演算子。</span><span class="sxs-lookup"><span data-stu-id="14421-178">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="14421-179">演算子の定義は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="14421-179">Defining an operator is optional.</span></span> <span data-ttu-id="14421-180">演算子は、この一覧の他の任意の宛先として定義できます。</span><span class="sxs-lookup"><span data-stu-id="14421-180">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="14421-181">演算子に 0 キーを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="14421-181">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="14421-182">メニュー オプションごとに、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="14421-182">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="14421-183">**[ダイヤル キー** ] - このオプションにアクセスするには、電話のキーパッドのキーを押します。</span><span class="sxs-lookup"><span data-stu-id="14421-183">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="14421-184">**[音声コマンド** ] - 音声入力が有効になっている場合に、呼び出し元がこのオプションにアクセスするために指定できる音声コマンドを定義します。</span><span class="sxs-lookup"><span data-stu-id="14421-184">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="14421-185">"顧客サービス" や "操作と根拠" など、複数の単語を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="14421-185">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="14421-186">**[リダイレクト先** ] - 呼び出し元がこのオプションを選択するときに通話を行う場所。</span><span class="sxs-lookup"><span data-stu-id="14421-186">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="14421-187">自動応答または通話キューにリダイレクトする場合は、関連付けられているリソース アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="14421-187">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![ダイヤル キー オプションのスクリーンショット](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="14421-189">この自動応答を会社のディレクトリとして使用する場合は、[ディレクトリ検索] で [名前でダイヤル]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="14421-189">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="14421-190">このオプションを有効にすると、発信者はユーザーの名前を言い、電話のキーパッドに入力できます。</span><span class="sxs-lookup"><span data-stu-id="14421-190">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="14421-191">ライセンスを持つオンライン 電話システムは、対象ユーザーであり、名前でダイヤルします。</span><span class="sxs-lookup"><span data-stu-id="14421-191">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="14421-192">([内線番号 **でダイヤルする]** を選択できます。ただし、拡張機能は、Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="14421-192">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="14421-193">ディレクトリ検索オプションを選択したら、[ **次へ]** を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="14421-193">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="14421-194">手順 4 - 時間後の通話フローの></span><span class="sxs-lookup"><span data-stu-id="14421-194">Step 4 - After hours call flow ></span></span>](?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="14421-195">手順 4 <br> 時間後</span><span class="sxs-lookup"><span data-stu-id="14421-195">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="14421-196">各自動応答に対して営業時間を設定できます。</span><span class="sxs-lookup"><span data-stu-id="14421-196">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="14421-197">営業時間が設定されていない場合、24 時間 365 日のスケジュールが既定で設定されているので、その日のすべての日とすべての時間が営業時間と見なされます。</span><span class="sxs-lookup"><span data-stu-id="14421-197">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="14421-198">営業時間は、その日の間の時間内の休憩で設定できます。営業時間として設定されていないすべての時間は、時間外と見なされます。</span><span class="sxs-lookup"><span data-stu-id="14421-198">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="14421-199">さまざまな着信通話処理オプションと応答メッセージを時間外に設定できます。</span><span class="sxs-lookup"><span data-stu-id="14421-199">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="14421-200">自動応答と通話キューの構成によっては、直接の電話番号を含む自動応答の時間外通話ルーティングのみを指定する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="14421-200">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="14421-201">営業時間外の発信者に対して個別の通話ルーティングが必要な場合は、各日の営業時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="14421-201">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="14421-202">[ **新しい時刻の追加** ] をクリックして、特定の日に複数の時間のセットを指定します 。たとえば、昼食休憩を指定します。</span><span class="sxs-lookup"><span data-stu-id="14421-202">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![時間外の日と時刻の設定のスクリーンショット](../media/auto-attendant-business-hours.png)

<span data-ttu-id="14421-204">営業時間を指定したら、時間外の通話ルーティング オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="14421-204">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="14421-205">手順 3 - 通話フロー で指定した営業時間の通話ルーティングと同 **じオプションを使用できます**。</span><span class="sxs-lookup"><span data-stu-id="14421-205">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="14421-206">完了 **したら、[** 次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14421-206">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="14421-207">手順 5 - 休日の呼び出しフロー></span><span class="sxs-lookup"><span data-stu-id="14421-207">Step 5 - Holiday call flow ></span></span>](?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="14421-208">手順 5 <br> の祝日</span><span class="sxs-lookup"><span data-stu-id="14421-208">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="14421-209">自動応答の呼び出しは、他の日とは異なる方法で休日にルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="14421-209">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="14421-210">(休日に別のコール フローを設定したくない場合は、この手順をスキップできます)。</span><span class="sxs-lookup"><span data-stu-id="14421-210">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>

<span data-ttu-id="14421-211">自動応答には、設定した各休日の通話フローを設定できます。</span><span class="sxs-lookup"><span data-stu-id="14421-211">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="14421-212">各自動応答には、最大 20 個の決められた休業日を追加できます。</span><span class="sxs-lookup"><span data-stu-id="14421-212">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="14421-213">[休日の通話設定] ページで、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="14421-213">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="14421-214">この休日設定の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="14421-214">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="14421-215">[ **休日] ドロップダウン** から、使用する休日を選択します。</span><span class="sxs-lookup"><span data-stu-id="14421-215">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="14421-216">使用するあいさつメッセージの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="14421-216">Choose the type of greeting that you want to use.</span></span>

    ![休日と休日のあいさつ設定のスクリーンショット](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="14421-218">[切断] または [通話の **リダイレクト\*\*\*\*] を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="14421-218">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="14421-219">リダイレクトを選択した場合は、通話の通話ルーティング先を選択します。</span><span class="sxs-lookup"><span data-stu-id="14421-219">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![休日の通話アクションの設定のスクリーンショット](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="14421-221">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14421-221">Click **Save**.</span></span>

    <span data-ttu-id="14421-222">追加の祝日ごとに、必要に応じて手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="14421-222">Repeat the procedure as needed for each additional holiday.</span></span>

    ![休日が表示されている休日設定のスクリーンショット](../media/auto-attendant-holiday-call-settings.png)

    <span data-ttu-id="14421-224">すべての祝日を追加した後、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="14421-224">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="14421-225">手順 6 - ディレクトリ 内のユーザーを選択></span><span class="sxs-lookup"><span data-stu-id="14421-225">Step 6 - Choose who's in the directory ></span></span>](?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="14421-226">手順 6 <br> ディレクトリ メンバー</span><span class="sxs-lookup"><span data-stu-id="14421-226">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="14421-227">ダイヤル *スコープは、* 呼び出し元がダイヤル バイ ネームまたはダイヤル バイ 拡張機能を使用する場合にディレクトリ内で使用できるユーザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="14421-227">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="14421-228">[すべてのオンライン **ユーザー] の既定値には**、組織内のすべてのユーザーが含まれます。このユーザーは、ライセンスを持つオンライン ユーザー電話システムされます。</span><span class="sxs-lookup"><span data-stu-id="14421-228">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="14421-229">[含める] または [除外] で [カスタムユーザー グループ] を選択し、1 つ以上の Microsoft 365 グループ、配布リスト、またはセキュリティ グループを選択することで、特定のユーザーを含めるか除外できます。 </span><span class="sxs-lookup"><span data-stu-id="14421-229">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="14421-230">たとえば、組織内のエグゼクティブをダイヤル ディレクトリから除外することができます。</span><span class="sxs-lookup"><span data-stu-id="14421-230">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="14421-231">(ユーザーが両方のリストにある場合は、ディレクトリから除外されます)。</span><span class="sxs-lookup"><span data-stu-id="14421-231">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![ダイヤル スコープに含めるオプションと除外オプションのスクリーンショット](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="14421-233">新しいユーザーの名前がディレクトリに表示されるには、最大 36 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="14421-233">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="14421-234">ダイヤル スコープの設定が完了したら、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="14421-234">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="14421-235">手順 7 - リソース アカウントを割り当></span><span class="sxs-lookup"><span data-stu-id="14421-235">Step 7 - Assign a resource account ></span></span>](?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="14421-236">手順 7 <br> リソース アカウント</span><span class="sxs-lookup"><span data-stu-id="14421-236">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="14421-237">すべての自動応答には、関連付けられているリソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="14421-237">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="14421-238">第 1 レベルの自動応答には、サービス番号が関連付けられている少なくとも 1 つのリソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="14421-238">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="14421-239">必要な場合は、複数のリソース アカウントを自動応答に割り当て、それぞれに個別のサービス番号を割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="14421-239">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="14421-240">リソース アカウントを追加するには</span><span class="sxs-lookup"><span data-stu-id="14421-240">To add a resource account</span></span>

1. <span data-ttu-id="14421-241">[ **追加]** をクリックし、追加するアカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="14421-241">Click **Add** and search for the account that you want to add.</span></span> <span data-ttu-id="14421-242">[追加 **] を** クリックし、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="14421-242">Click **Add**, and then click **Add**.</span></span>

    ![リソース アカウントの [アカウントの追加] パネルのスクリーンショット](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="14421-244">サービス アカウントの追加が完了したら、[送信] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="14421-244">When you have finished adding service accounts, click **Submit**.</span></span>

    ![割り当てられたサービス番号が割り当てられたリソース アカウントを示すリソース アカウントの一覧のスクリーンショット](../media/auto-attendant-resource-account-assigned.png)

    <span data-ttu-id="14421-246">これで自動応答の構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="14421-246">This completes the auto attendant configuration.</span></span>

---
