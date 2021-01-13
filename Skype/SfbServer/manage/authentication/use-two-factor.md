---
title: Skype for Business クライアントと Skype for Business Server で 2 要素認証を使用する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: '概要: Skype for Business Server と Skype for Business で 2 要素認証を使用します。'
ms.openlocfilehash: 72ec3570d632eecefd28ebfd0aa50eb70c54ff99
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806543"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a><span data-ttu-id="78c94-103">Skype for Business クライアントと Skype for Business Server で 2 要素認証を使用する</span><span class="sxs-lookup"><span data-stu-id="78c94-103">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>
 
<span data-ttu-id="78c94-104">**概要:** Skype for Business Server と Skype for Business で 2 要素認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="78c94-104">**Summary:** Use two-factor authentication with Skype for Business Server and Skype for Business.</span></span>
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a><span data-ttu-id="78c94-105">初めて Skype for Business にサインインする</span><span class="sxs-lookup"><span data-stu-id="78c94-105">Sign in to Skype for Business for the first time</span></span>

<span data-ttu-id="78c94-106">サインイン情報は、通常、Skype for Business のインストール時に自動的に構成されます。</span><span class="sxs-lookup"><span data-stu-id="78c94-106">Your sign-in information is usually configured automatically when Skype for Business is installed.</span></span> <span data-ttu-id="78c94-107">ただし、初めて Skype for Business を使用する場合は、クライアントを手動で開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78c94-107">But the first time you use Skype for Business, you might have to manually start the client.</span></span>
  
### <a name="to-sign-in-for-the-first-time"></a><span data-ttu-id="78c94-108">初めてサインインするには</span><span class="sxs-lookup"><span data-stu-id="78c94-108">To sign in for the first time</span></span>

1. <span data-ttu-id="78c94-109">組織のネットワークにログオンします。</span><span class="sxs-lookup"><span data-stu-id="78c94-109">Log on to your organization's network.</span></span>
    
2. <span data-ttu-id="78c94-110">[すべての **プログラム**  >  **を**  >  **起動する] Skype for Business を選択します**。</span><span class="sxs-lookup"><span data-stu-id="78c94-110">Select **Start** > **All Programs** > **Skype for Business**.</span></span>
    
    <span data-ttu-id="78c94-111">サインイン画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78c94-111">You should see the sign-in screen.</span></span>
    
    - <span data-ttu-id="78c94-112">サインイン アドレス ボックスが既に入力されている場合は、表示されているアドレスが正しいか確認します。</span><span class="sxs-lookup"><span data-stu-id="78c94-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
    - <span data-ttu-id="78c94-113">正しく表示されない場合、またはボックスが空の場合は、サインイン アドレスを入力します (通常、これはメール アドレスと同じです)。</span><span class="sxs-lookup"><span data-stu-id="78c94-113">If it's not correct, or if the box is empty, enter your sign-in address (this is usually the same as your email address).</span></span>
    
    - <span data-ttu-id="78c94-114">空のパスワード ボックスが表示される場合は、パスワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="78c94-114">If an empty password box is displayed, add your password.</span></span>
    
3. <span data-ttu-id="78c94-115">[ **サインイン] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="78c94-115">Select **Sign-in**.</span></span>
    
## <a name="sign-out-of-skype-for-business"></a><span data-ttu-id="78c94-116">Skype for Business からサインアウトする</span><span class="sxs-lookup"><span data-stu-id="78c94-116">Sign out of Skype for Business</span></span>

<span data-ttu-id="78c94-117">Skype for Business の使用が完了したら、[ファイル] メニューから表示を閉じるか、セッションからサインアウトするか、プログラムを終了できます。</span><span class="sxs-lookup"><span data-stu-id="78c94-117">When you're finished using Skype for Business, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="78c94-118">次の表に、オプションの違いを示します。</span><span class="sxs-lookup"><span data-stu-id="78c94-118">The following table explains the differences in the options.</span></span>
  
|<span data-ttu-id="78c94-119">**オプション**</span><span class="sxs-lookup"><span data-stu-id="78c94-119">**Option**</span></span>|<span data-ttu-id="78c94-120">**目的**</span><span class="sxs-lookup"><span data-stu-id="78c94-120">**What it does**</span></span>|<span data-ttu-id="78c94-121">**実行方法**</span><span class="sxs-lookup"><span data-stu-id="78c94-121">**How to perform it**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="78c94-122">閉じる</span><span class="sxs-lookup"><span data-stu-id="78c94-122">Close</span></span>  <br/> |<span data-ttu-id="78c94-123">表示を閉じますが、ユーザー ID で識別された Skype for Business セッションは引き続き実行できます。</span><span class="sxs-lookup"><span data-stu-id="78c94-123">Closes your display but lets the Skype for Business session identified with your user ID continue to run.</span></span> <span data-ttu-id="78c94-124">これにより、引き続き通知を受け取り、他のユーザーとやり取りすることができます。</span><span class="sxs-lookup"><span data-stu-id="78c94-124">This is so you can continue to get notifications and interact with others.</span></span> <br/> <br/> <span data-ttu-id="78c94-125">画面の下部にあるタスク バーまたは通知領域の Skype for Business アイコンをクリックすると、いつでも表示を取得できます。</span><span class="sxs-lookup"><span data-stu-id="78c94-125">You can get the display back at any time by clicking the Skype for Business icon on the taskbar or the notification area at the bottom of your screen.</span></span>  <br/> | <span data-ttu-id="78c94-126">Skype for Business のメイン ウィンドウで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="78c94-126">On the Skype for Business main window, do one of the following:</span></span> <br/> <span data-ttu-id="78c94-127">1. [オプション] ボタン **を選択** し、[ファイルを閉じる]**を選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="78c94-127">1. Select the **Options** button, then select **File** > **Close**.</span></span>  <br/> <span data-ttu-id="78c94-128">2. ウィンドウ **の右上隅** にある [閉じる] ボタン (X) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78c94-128">2. Click the **Close** button (X) in the upper-right corner of the window.</span></span> <br/> |
|<span data-ttu-id="78c94-129">サインアウト</span><span class="sxs-lookup"><span data-stu-id="78c94-129">Sign out</span></span>  <br/> |<span data-ttu-id="78c94-130">ユーザー ID に関連付けられているセッションを終了しますが、Skype for Business はバックグラウンドで引き続き実行されます。</span><span class="sxs-lookup"><span data-stu-id="78c94-130">Ends the session associated with your user ID, but Skype for Business continues to run in the background.</span></span> <span data-ttu-id="78c94-131">サインアウトすると、サインイン ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="78c94-131">When you sign out, the sign-in window will appear.</span></span>  <br/> <span data-ttu-id="78c94-132">**ヒント:** サイン **アウト時に [サインイン情報を** 削除する] を選択して、コンピューターからログオン ID とパスワードのレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="78c94-132">**Tip:** Select **Delete my sign-in information** when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="78c94-133">これにより、サポートユーザーがサインインの問題を簡単にトラブルシューティングできます。</span><span class="sxs-lookup"><span data-stu-id="78c94-133">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="78c94-134">また、承認されていないユーザーが資格情報を使用してログオンするのが難しくなるので、サインイン情報のセキュリティを高めることができます。</span><span class="sxs-lookup"><span data-stu-id="78c94-134">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span> <br/> |<span data-ttu-id="78c94-135">Skype for Business のメイン ウィンドウで、[オプション] ボタンを選択し、[ファイルのサインアウト  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="78c94-135">On the Skype for Business main window, select the **Options** button, then select **File** > **Sign Out**.</span></span>  <br/> |
|<span data-ttu-id="78c94-136">Exit</span><span class="sxs-lookup"><span data-stu-id="78c94-136">Exit</span></span>  <br/> |<span data-ttu-id="78c94-137">Skype for Business セッションを終了し、コンピューターで Skype for Business をシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="78c94-137">Ends your Skype for Business session and shuts down Skype for Business on your computer.</span></span> <span data-ttu-id="78c94-138">終了した後、再起動する場合は、Skype for Business で [すべてのプログラム>  >  選択します。</span><span class="sxs-lookup"><span data-stu-id="78c94-138">After exiting, if you want to restart, select **Start** > **All Programs** > Skype for Business.</span></span> <br/> |<span data-ttu-id="78c94-139">Skype for Business のメイン ウィンドウで、[オプション] ボタンを **選択し、[** ファイルの終了]**を選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="78c94-139">On the Skype for Business main window, select the **Options** button, then select **File** > **Exit**.</span></span>  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a><span data-ttu-id="78c94-140">スマート カードを使用して Skype for Business にサインインする</span><span class="sxs-lookup"><span data-stu-id="78c94-140">Sign in to Skype for Business with a Smart Card</span></span>

<span data-ttu-id="78c94-141">一部の組織では、ユーザーのセキュリティを強化するために、2 要素認証と呼ばれる複数ステップのサインイン プロセスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="78c94-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their users.</span></span> <span data-ttu-id="78c94-142">このオプションを使用する場合は、Skype for Business にサインインするための "スマート カード" が必要です。</span><span class="sxs-lookup"><span data-stu-id="78c94-142">If you're expected to use this option, you'll need a "smart card" to sign in to Skype for Business.</span></span> <span data-ttu-id="78c94-143">スマート カードは、物理カードまたは仮想カードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="78c94-143">Smart cards can be either physical or virtual:</span></span>
  
- <span data-ttu-id="78c94-144">**物理** クレジット カードのサイズについて。</span><span class="sxs-lookup"><span data-stu-id="78c94-144">**Physical** About the size of a credit card.</span></span> <span data-ttu-id="78c94-145">ログイン時にスマート カード リーダーに挿入します。</span><span class="sxs-lookup"><span data-stu-id="78c94-145">You insert it into a smart card reader when you log in.</span></span>
    
- <span data-ttu-id="78c94-146">**仮想** 物理オブジェクトではなく、コンピューター上の特別なチップに書き込まれる電子識別子です。本質的には、スマート カードがコンピューターに組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="78c94-146">**Virtual** Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="78c94-147">TPM (トラステッド プラットフォーム モジュール) Windows 8コンピューターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="78c94-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>
    
### <a name="enroll-your-smart-card"></a><span data-ttu-id="78c94-148">スマート カードを登録する</span><span class="sxs-lookup"><span data-stu-id="78c94-148">Enroll your smart card</span></span>

<span data-ttu-id="78c94-149">スマート カードでサインインする前に、カードを "登録" する必要があります。つまり、ユーザー資格情報をカードで識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78c94-149">Before you can sign in with a smart card, the card must be "enrolled"—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="78c94-150">カードが物理カードか仮想カードかは、この場合です。</span><span class="sxs-lookup"><span data-stu-id="78c94-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="78c94-151">このプロセスは、Skype for Business Server 管理者によって既に実行されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78c94-151">This process may already been carried out by your Skype for Business Server administrator.</span></span> <span data-ttu-id="78c94-152">それが完了したかどうか不明な場合は、確認してください。</span><span class="sxs-lookup"><span data-stu-id="78c94-152">Check with them if you're not sure whether that has been done.</span></span>
  
> [!NOTE]
> <span data-ttu-id="78c94-153">各仮想スマート カードは、それがインストールされているデバイスにのみ関連付けられているので、使用する各仮想スマート カードに個別のカードを登録Windows 8必要があります。</span><span class="sxs-lookup"><span data-stu-id="78c94-153">Since each virtual smart card is associated only with the device it's installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span> 
  
### <a name="to-manually-enroll-your-smart-card"></a><span data-ttu-id="78c94-154">スマート カードを手動で登録するには</span><span class="sxs-lookup"><span data-stu-id="78c94-154">To manually enroll your smart card</span></span>

1. <span data-ttu-id="78c94-155">Skype for Business を実行するコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="78c94-155">Log on to the computer you'll be running Skype for Business on.</span></span>
    
2. <span data-ttu-id="78c94-156">このInternet Explorer、組織の証明機関 Web 登録ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="78c94-156">Using Internet Explorer, browse to your organization's Certificate Authority Web Enrollment page.</span></span> 
    
    <span data-ttu-id="78c94-157">このリソースが存在しない場合は、Skype for Business Server 管理者にこのリソースの Web アドレスを問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="78c94-157">Ask your Skype for Business Server administrator for the web address of this resource if you don't already have it.</span></span> <span data-ttu-id="78c94-158">URL は次のように表示されます。 https://MyCA .[yourcompanyname].com/certsrv.</span><span class="sxs-lookup"><span data-stu-id="78c94-158">The URL will look something like this: https://MyCA.[yourcompanyname].com/certsrv.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78c94-159">Internet Explorer 10 を使用している場合は、この Web サイトを互換モードで表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78c94-159">If you're using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span> 
  
3. <span data-ttu-id="78c94-160">認定ページにログオンするように求めるメッセージが表示されたら、(コンピューターの管理者としてではなく) ドメイン アカウントを使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="78c94-160">When you're prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>
    
4. <span data-ttu-id="78c94-161">Web サイトのウェルカム ページで、[証明書の要求 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="78c94-161">On the website Welcome Page, select **Request a certificate**.</span></span>
    
5. <span data-ttu-id="78c94-162">[高度 **な要求] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="78c94-162">Select **Advanced Request**.</span></span>
    
6. <span data-ttu-id="78c94-163">Select **Create and submit a request to this CA,** then click **Next**.</span><span class="sxs-lookup"><span data-stu-id="78c94-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>
    
7. <span data-ttu-id="78c94-164">これで、スマート カード登録ステーションというページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="78c94-164">Now you'll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="78c94-165">ActiveX コントロールをインストールする要求を承認し、次のように [証明書の要求の詳細設定] フォームに入力します。</span><span class="sxs-lookup"><span data-stu-id="78c94-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    <span data-ttu-id="78c94-166">a. </span><span class="sxs-lookup"><span data-stu-id="78c94-166">a.</span></span> <span data-ttu-id="78c94-167">[ **証明書テンプレート] ドロップダウン** リスト **から [Smartcard** ユーザー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="78c94-167">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    <span data-ttu-id="78c94-168">b.</span><span class="sxs-lookup"><span data-stu-id="78c94-168">b.</span></span> <span data-ttu-id="78c94-169">[新 **しいキー セットの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="78c94-169">Select **Create new key set**.</span></span>
    
    <span data-ttu-id="78c94-170">c.</span><span class="sxs-lookup"><span data-stu-id="78c94-170">c.</span></span> <span data-ttu-id="78c94-171">スマート カードのラベルで製造元の情報を見つけ **、CSP** のドロップダウン リストからその製造元を選択します。</span><span class="sxs-lookup"><span data-stu-id="78c94-171">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    <span data-ttu-id="78c94-172">d. </span><span class="sxs-lookup"><span data-stu-id="78c94-172">d.</span></span> <span data-ttu-id="78c94-173">CSP **を** 要求形式として選択します (まだ選択されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="78c94-173">Select **CSP** as the Request Format, if it's not already selected.</span></span>
    
    <span data-ttu-id="78c94-174">e. </span><span class="sxs-lookup"><span data-stu-id="78c94-174">e.</span></span> <span data-ttu-id="78c94-175">まだ選択されていない場合は、[ハッシュ アルゴリズム] ドロップダウン リストから **sha1** を選択します。</span><span class="sxs-lookup"><span data-stu-id="78c94-175">Select **sha1** from the Hash Algorithm dropdown list, if it's not already selected.</span></span>
    
    <span data-ttu-id="78c94-176">f.</span><span class="sxs-lookup"><span data-stu-id="78c94-176">f.</span></span> <span data-ttu-id="78c94-177">証明書に認識される名前を付け、[送信] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="78c94-177">Give your certificate a name you'll recognize, and click **Submit**.</span></span>
    
8. <span data-ttu-id="78c94-178">次に、登録ステーションに接続されているカード リーダーに空白のスマート カードを挿入し、[登録] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="78c94-178">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>
    
9. <span data-ttu-id="78c94-179">メッセージが表示されたら、暗証番号 (PIN) を入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78c94-179">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78c94-180">テクニカル サポート担当者からスマート カードの登録に使用する特別な PIN が提供されていない場合は、既定のスマート カード PIN 値 (12345678) を使用します。</span><span class="sxs-lookup"><span data-stu-id="78c94-180">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span> 
  
10. <span data-ttu-id="78c94-181">スマート カードを初めて使用する場合にユーザーに PIN の変更を強制するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="78c94-181">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>
    
11. <span data-ttu-id="78c94-182">次に、登録ステーションに接続されているカード リーダーに空白のスマート カードを挿入し、[登録] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="78c94-182">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>
    
12. <span data-ttu-id="78c94-183">メッセージが表示されたら、暗証番号 (PIN) を入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78c94-183">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78c94-184">テクニカル サポート担当者からスマート カードの登録に使用する特別な PIN が提供されていない場合は、既定のスマート カード PIN 値 (12345678) を使用します。</span><span class="sxs-lookup"><span data-stu-id="78c94-184">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span> 
  
13. <span data-ttu-id="78c94-185">スマート カードを初めて使用する場合にユーザーに PIN の変更を強制するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="78c94-185">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>
    
14. <span data-ttu-id="78c94-186">**[OK]** をクリックして、表示される証明書に自分の情報が含されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="78c94-186">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>
    
15. <span data-ttu-id="78c94-187">証明書が発行されたという通知が表示された後、[この証明書のインストール] をクリックして登録プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="78c94-187">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a><span data-ttu-id="78c94-188">スマート カードの資格情報を使用して Skype for Business にサインインする</span><span class="sxs-lookup"><span data-stu-id="78c94-188">Sign in to Skype for Business with your smart card credentials</span></span>

<span data-ttu-id="78c94-189">スマート カードを初めて使用する前に、Skype for Business のサインイン ページで [サインイン情報の削除] をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="78c94-189">Before you use your smart card for the first time, it's recommended that you click **Delete my sign-in info** on the Skype for Business sign-in page.</span></span> <span data-ttu-id="78c94-190">これにより、コンピューターに保存されているサインイン資格情報が消去され、考えられるエラーの原因が排除されます。</span><span class="sxs-lookup"><span data-stu-id="78c94-190">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a><span data-ttu-id="78c94-191">スマート カードの資格情報を使用して Skype for Business にサインインするには</span><span class="sxs-lookup"><span data-stu-id="78c94-191">To sign in to Skype for Business with your smart card credentials</span></span>

1. <span data-ttu-id="78c94-192">Skype for Business クライアントを起動します。</span><span class="sxs-lookup"><span data-stu-id="78c94-192">Start the Skype for Business client.</span></span>
    
2. <span data-ttu-id="78c94-193">[サインイン] 画面の [サインイン アドレス] ボックスにサインイン ユーザー アカウント名を入力し、[サインイン] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="78c94-193">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>
    
3. <span data-ttu-id="78c94-194">仮想スマート カードを使用している場合は、この手順を省略します。</span><span class="sxs-lookup"><span data-stu-id="78c94-194">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="78c94-195">物理スマート カードを使用している場合は、スマート カードリーダーにスマート カードを挿入し、入力を求めるメッセージを表示して、カードが検出されたら **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78c94-195">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>
    
4. <span data-ttu-id="78c94-196">スマート カードの PIN 番号を入力し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78c94-196">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78c94-197">サポート担当者によってスマート カードの PIN 番号が割り当てられていない場合は、既定値である 12345678 を使用します。</span><span class="sxs-lookup"><span data-stu-id="78c94-197">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="78c94-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="78c94-198">See also</span></span>

[<span data-ttu-id="78c94-199">Skype for Business Server で 2 要素認証を管理する</span><span class="sxs-lookup"><span data-stu-id="78c94-199">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)
  
[<span data-ttu-id="78c94-200">Skype for Business Server で 2 要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="78c94-200">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
