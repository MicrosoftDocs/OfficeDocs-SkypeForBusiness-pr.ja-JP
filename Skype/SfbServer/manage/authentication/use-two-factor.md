---
title: Skype for Business クライアントと Skype for Business Server で2要素認証を使用する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: '概要: Skype for Business Server および Skype for Business での2要素認証を使用します。'
ms.openlocfilehash: 378b76b61acd004dfe16f04dba922cc2b6fedc83
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818709"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a><span data-ttu-id="18e5c-103">Skype for Business クライアントと Skype for Business Server で2要素認証を使用する</span><span class="sxs-lookup"><span data-stu-id="18e5c-103">Use two-factor authentication with Skype for Business client and Skype for Business Server</span></span>
 
<span data-ttu-id="18e5c-104">**概要:** Skype for Business Server および Skype for Business では、2要素認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-104">**Summary:** Use two-factor authentication with Skype for Business Server and Skype for Business.</span></span>
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a><span data-ttu-id="18e5c-105">Skype for Business に初めてサインインする</span><span class="sxs-lookup"><span data-stu-id="18e5c-105">Sign in to Skype for Business for the first time</span></span>

<span data-ttu-id="18e5c-106">通常、サインイン情報は、Skype for Business をインストールしたときに自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-106">Your sign-in information is usually configured automatically when Skype for Business is installed.</span></span> <span data-ttu-id="18e5c-107">ただし、初めて Skype for Business を使用する場合は、クライアントを手動で開始しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="18e5c-107">But the first time you use Skype for Business, you might have to manually start the client.</span></span>
  
### <a name="to-sign-in-for-the-first-time"></a><span data-ttu-id="18e5c-108">初めてサインインするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="18e5c-108">To sign in for the first time</span></span>

1. <span data-ttu-id="18e5c-109">組織のネットワークにログオンします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-109">Log on to your organization's network.</span></span>
    
2. <span data-ttu-id="18e5c-110">[ \*\*\*\* > **すべてのプログラム** > を**Skype for business**から開始する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-110">Select **Start** > **All Programs** > **Skype for Business**.</span></span>
    
    <span data-ttu-id="18e5c-111">サインイン画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-111">You should see the sign-in screen.</span></span>
    
    - <span data-ttu-id="18e5c-112">[サインイン アドレス] ボックスが既に入力されている場合は、表示されているアドレスが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
    - <span data-ttu-id="18e5c-113">正しくない場合、またはボックスが空の場合は、サインインアドレス (通常はメールアドレスと同じ) を入力します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-113">If it's not correct, or if the box is empty, enter your sign-in address (this is usually the same as your email address).</span></span>
    
    - <span data-ttu-id="18e5c-114">パスワードを入力するボックスが空の場合は、パスワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-114">If an empty password box is displayed, add your password.</span></span>
    
3. <span data-ttu-id="18e5c-115">[**サインイン**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-115">Select **Sign-in**.</span></span>
    
## <a name="sign-out-of-skype-for-business"></a><span data-ttu-id="18e5c-116">Skype for Business からサインアウトする</span><span class="sxs-lookup"><span data-stu-id="18e5c-116">Sign out of Skype for Business</span></span>

<span data-ttu-id="18e5c-117">Skype for Business の使用が完了したら、[ファイル] メニューから表示を閉じて、セッションからサインアウトするか、プログラムから退出することができます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-117">When you're finished using Skype for Business, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="18e5c-118">次の表で、オプションの違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-118">The following table explains the differences in the options.</span></span>
  
|<span data-ttu-id="18e5c-119">**オプション**</span><span class="sxs-lookup"><span data-stu-id="18e5c-119">**Option**</span></span>|<span data-ttu-id="18e5c-120">**機能**</span><span class="sxs-lookup"><span data-stu-id="18e5c-120">**What it does**</span></span>|<span data-ttu-id="18e5c-121">**実行する方法**</span><span class="sxs-lookup"><span data-stu-id="18e5c-121">**How to perform it**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="18e5c-122">閉じる</span><span class="sxs-lookup"><span data-stu-id="18e5c-122">Close</span></span>  <br/> |<span data-ttu-id="18e5c-123">ディスプレイを閉じますが、ユーザー ID で識別された Skype for Business セッションは引き続き実行できます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-123">Closes your display but lets the Skype for Business session identified with your user ID continue to run.</span></span> <span data-ttu-id="18e5c-124">したがって、引き続き通知を受け取り、他のユーザーと対話できます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-124">This is so you can continue to get notifications and interact with others.</span></span> <br/> <br/> <span data-ttu-id="18e5c-125">タスクバーまたは画面の下部にある通知領域の Skype for Business アイコンをクリックすると、いつでも表示を元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-125">You can get the display back at any time by clicking the Skype for Business icon on the taskbar or the notification area at the bottom of your screen.</span></span>  <br/> | <span data-ttu-id="18e5c-126">Skype for Business メインウィンドウで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="18e5c-126">On the Skype for Business main window, do one of the following:</span></span> <br/> <span data-ttu-id="18e5c-127">1. [**オプション**] ボタンを選択し、[**ファイル** > を**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-127">1. Select the **Options** button, then select **File** > **Close**.</span></span>  <br/> <span data-ttu-id="18e5c-128">2. ウィンドウの右上隅にある [**閉じる**] ボタン (X) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-128">2. Click the **Close** button (X) in the upper-right corner of the window.</span></span> <br/> |
|<span data-ttu-id="18e5c-129">サインアウトする</span><span class="sxs-lookup"><span data-stu-id="18e5c-129">Sign out</span></span>  <br/> |<span data-ttu-id="18e5c-130">ユーザー ID に関連付けられているセッションを終了しますが、Skype for Business はバックグラウンドで実行され続けます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-130">Ends the session associated with your user ID, but Skype for Business continues to run in the background.</span></span> <span data-ttu-id="18e5c-131">サインアウトすると、サインイン ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-131">When you sign out, the sign-in window will appear.</span></span>  <br/> <span data-ttu-id="18e5c-132">**ヒント:**[サインアウトするときに**サインイン情報を削除**する] を選択して、コンピューターからログオン ID とパスワードの記録を削除します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-132">**Tip:** Select **Delete my sign-in information** when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="18e5c-133">このようにすると、サポート担当者が行うサインインの問題のトラブルシューティングが容易になることがあります。</span><span class="sxs-lookup"><span data-stu-id="18e5c-133">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="18e5c-134">また、権限のないユーザーがあなたの資格情報でログインすることは難しくなるため、サインイン情報のセキュリティも確保できます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-134">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span> <br/> |<span data-ttu-id="18e5c-135">Skype for business メインウィンドウで、[**オプション**] ボタンを選択し、[**ファイル** > ]、[サインアウト] の順に選択**します。**</span><span class="sxs-lookup"><span data-stu-id="18e5c-135">On the Skype for Business main window, select the **Options** button, then select **File** > **Sign Out**.</span></span>  <br/> |
|<span data-ttu-id="18e5c-136">終了する</span><span class="sxs-lookup"><span data-stu-id="18e5c-136">Exit</span></span>  <br/> |<span data-ttu-id="18e5c-137">Skype for business セッションを終了し、コンピューター上の Skype for Business をシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-137">Ends your Skype for Business session and shuts down Skype for Business on your computer.</span></span> <span data-ttu-id="18e5c-138">終了後、再起動する場合は、[Skype for business >**すべてのプログラム**を**起動** > する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-138">After exiting, if you want to restart, select **Start** > **All Programs** > Skype for Business.</span></span> <br/> |<span data-ttu-id="18e5c-139">Skype for business のメインウィンドウで、[**オプション**] ボタンを選択し、[**ファイル** > を**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-139">On the Skype for Business main window, select the **Options** button, then select **File** > **Exit**.</span></span>  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a><span data-ttu-id="18e5c-140">スマート カードで Skype for Business にサインインする</span><span class="sxs-lookup"><span data-stu-id="18e5c-140">Sign in to Skype for Business with a Smart Card</span></span>

<span data-ttu-id="18e5c-141">一部の組織では、ユーザーのセキュリティを強化するために、2 要素認証と呼ばれる、複数ステップのサインイン プロセスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="18e5c-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their users.</span></span> <span data-ttu-id="18e5c-142">このオプションを使用することが予想される場合は、Skype for Business にサインインするには「スマートカード」が必要です。</span><span class="sxs-lookup"><span data-stu-id="18e5c-142">If you're expected to use this option, you'll need a "smart card" to sign in to Skype for Business.</span></span> <span data-ttu-id="18e5c-143">スマートカードは、物理または仮想のいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-143">Smart cards can be either physical or virtual:</span></span>
  
- <span data-ttu-id="18e5c-144">**物理**クレジットカードのサイズについて。</span><span class="sxs-lookup"><span data-stu-id="18e5c-144">**Physical** About the size of a credit card.</span></span> <span data-ttu-id="18e5c-145">ログインするときにスマート カード リーダーに挿入します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-145">You insert it into a smart card reader when you log in.</span></span>
    
- <span data-ttu-id="18e5c-146">**仮想**物理的なオブジェクトではありませんが、コンピューター上の特殊なチップに書き込まれる電子的な識別子であり、これにより、基本的にスマートカードがコンピューターに作成されます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-146">**Virtual** Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="18e5c-147">TPM (トラステッドプラットフォームモジュール) チップが含まれている Windows 8 コンピューターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>
    
### <a name="enroll-your-smart-card"></a><span data-ttu-id="18e5c-148">スマート カードを登録する</span><span class="sxs-lookup"><span data-stu-id="18e5c-148">Enroll your smart card</span></span>

<span data-ttu-id="18e5c-149">スマートカードでサインインするには、カードが "登録" されている必要があります。つまり、カードでユーザーの資格情報を識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18e5c-149">Before you can sign in with a smart card, the card must be "enrolled"—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="18e5c-150">これは、カードが物理または仮想のどちらであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="18e5c-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="18e5c-151">このプロセスは、Skype for Business Server 管理者によって既に実行されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18e5c-151">This process may already been carried out by your Skype for Business Server administrator.</span></span> <span data-ttu-id="18e5c-152">実行されているかどうかがわからない場合は、確認してください。</span><span class="sxs-lookup"><span data-stu-id="18e5c-152">Check with them if you're not sure whether that has been done.</span></span>
  
> [!NOTE]
> <span data-ttu-id="18e5c-153">各仮想スマートカードは、それがインストールされているデバイスのみに関連付けられているため、使用する Windows 8 コンピューターごとに別のカードを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18e5c-153">Since each virtual smart card is associated only with the device it's installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span> 
  
### <a name="to-manually-enroll-your-smart-card"></a><span data-ttu-id="18e5c-154">スマート カードを手動で登録するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="18e5c-154">To manually enroll your smart card</span></span>

1. <span data-ttu-id="18e5c-155">Skype for Business を実行しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-155">Log on to the computer you'll be running Skype for Business on.</span></span>
    
2. <span data-ttu-id="18e5c-156">Internet Explorer を使用して、組織の証明機関の Web 登録ページを参照します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-156">Using Internet Explorer, browse to your organization's Certificate Authority Web Enrollment page.</span></span> 
    
    <span data-ttu-id="18e5c-157">まだインストールしていない場合は、このリソースの web アドレスについては、Skype for Business Server の管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="18e5c-157">Ask your Skype for Business Server administrator for the web address of this resource if you don't already have it.</span></span> <span data-ttu-id="18e5c-158">URL は次https://MyCAのようになります。[会社名] .com/certsrv</span><span class="sxs-lookup"><span data-stu-id="18e5c-158">The URL will look something like this: https://MyCA.[yourcompanyname].com/certsrv.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="18e5c-159">Internet Explorer 10 を使用している場合は、互換モードでこの web サイトを表示する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="18e5c-159">If you're using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span> 
  
3. <span data-ttu-id="18e5c-160">[証明書] ページにログオンするように求められたら、(コンピューターの管理者としてではなく) 自分のドメインアカウントを使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-160">When you're prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>
    
4. <span data-ttu-id="18e5c-161">Web サイトのようこそページで、[**証明書の要求**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-161">On the website Welcome Page, select **Request a certificate**.</span></span>
    
5. <span data-ttu-id="18e5c-162">[**証明書の要求の詳細設定**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-162">Select **Advanced Request**.</span></span>
    
6. <span data-ttu-id="18e5c-163">[**この CA への要求を作成し送信する。**] を選んで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>
    
7. <span data-ttu-id="18e5c-164">これで、スマートカード登録ステーションというページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-164">Now you'll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="18e5c-165">要求を承認して ActiveX コントロールをインストールし、[証明書の要求の詳細設定] を次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    <span data-ttu-id="18e5c-166">a.</span><span class="sxs-lookup"><span data-stu-id="18e5c-166">a.</span></span> <span data-ttu-id="18e5c-167">[**証明書のテンプレート**] ボックスの一覧から [**スマート カード ユーザー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-167">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    <span data-ttu-id="18e5c-168">b.</span><span class="sxs-lookup"><span data-stu-id="18e5c-168">b.</span></span> <span data-ttu-id="18e5c-169">[**新しいキー セットを作成する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-169">Select **Create new key set**.</span></span>
    
    <span data-ttu-id="18e5c-170">c.</span><span class="sxs-lookup"><span data-stu-id="18e5c-170">c.</span></span> <span data-ttu-id="18e5c-171">スマート カードのラベルから製造元情報を確認し、[**CSP**] ボックスの一覧から製造元を選びます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-171">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    <span data-ttu-id="18e5c-172">d.</span><span class="sxs-lookup"><span data-stu-id="18e5c-172">d.</span></span> <span data-ttu-id="18e5c-173">まだ選択されていない場合は、要求形式として [ **CSP** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-173">Select **CSP** as the Request Format, if it's not already selected.</span></span>
    
    <span data-ttu-id="18e5c-174">•.</span><span class="sxs-lookup"><span data-stu-id="18e5c-174">e.</span></span> <span data-ttu-id="18e5c-175">まだ選択されていない場合は、ハッシュアルゴリズムのドロップダウンリストから [ **sha1** ] を選びます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-175">Select **sha1** from the Hash Algorithm dropdown list, if it's not already selected.</span></span>
    
    <span data-ttu-id="18e5c-176">f.</span><span class="sxs-lookup"><span data-stu-id="18e5c-176">f.</span></span> <span data-ttu-id="18e5c-177">証明書にわかりやすい名前を付け、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-177">Give your certificate a name you'll recognize, and click **Submit**.</span></span>
    
8. <span data-ttu-id="18e5c-178">登録ステーションに接続したカード リーダーに空のスマート カードを挿入し、[**登録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-178">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>
    
9. <span data-ttu-id="18e5c-179">要求メッセージが表示されたら、暗証番号 (PIN) を入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-179">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="18e5c-180">スマート カードを登録するために使う特別な PIN をテクニカル サポート担当者から受け取っていない場合は、既定のスマート カード PIN の値である 12345678 を使用します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-180">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span> 
  
10. <span data-ttu-id="18e5c-181">スマート カードを最初に使うときに PIN の変更をユーザーに強制するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-181">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>
    
11. <span data-ttu-id="18e5c-182">登録ステーションに接続したカード リーダーに空のスマート カードを挿入し、[**登録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-182">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>
    
12. <span data-ttu-id="18e5c-183">要求メッセージが表示されたら、暗証番号 (PIN) を入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-183">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="18e5c-184">スマート カードを登録するために使う特別な PIN をテクニカル サポート担当者から受け取っていない場合は、既定のスマート カード PIN の値である 12345678 を使用します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-184">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span> 
  
13. <span data-ttu-id="18e5c-185">スマート カードを最初に使うときに PIN の変更をユーザーに強制するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-185">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>
    
14. <span data-ttu-id="18e5c-186">表示された証明書に記載されたユーザーの情報を確認したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-186">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>
    
15. <span data-ttu-id="18e5c-187">証明書が発行されたことを知らせる通知を確認したら、[**この証明書のインストール**] をクリックして登録プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-187">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a><span data-ttu-id="18e5c-188">自分のスマート カードの資格情報で Skype for Business にサインインする</span><span class="sxs-lookup"><span data-stu-id="18e5c-188">Sign in to Skype for Business with your smart card credentials</span></span>

<span data-ttu-id="18e5c-189">スマートカードを初めて使う場合は、Skype for Business のサインインページで [**サインイン情報を削除**] をクリックすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-189">Before you use your smart card for the first time, it's recommended that you click **Delete my sign-in info** on the Skype for Business sign-in page.</span></span> <span data-ttu-id="18e5c-190">これにより、コンピューターに保存されているすべてのサインイン情報がクリアされ、エラーの原因を取り除くことができます。</span><span class="sxs-lookup"><span data-stu-id="18e5c-190">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a><span data-ttu-id="18e5c-191">自分のスマート カードの資格情報で Skype for Business にサインインするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="18e5c-191">To sign in to Skype for Business with your smart card credentials</span></span>

1. <span data-ttu-id="18e5c-192">Skype for Business クライアントを起動します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-192">Start the Skype for Business client.</span></span>
    
2. <span data-ttu-id="18e5c-193">サインイン画面で、ユーザーのアカウント名を [**サインイン アドレス**] ボックスに入力し、[**サインイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-193">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>
    
3. <span data-ttu-id="18e5c-194">仮想スマート カードを使っている場合は、この手順は省略します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-194">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="18e5c-195">物理スマート カードを使っている場合は、メッセージが表示されたらスマート カードをスマート カード リーダーに挿入し、カードが認識されたら [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-195">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>
    
4. <span data-ttu-id="18e5c-196">スマート カードの PIN 番号を入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18e5c-196">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="18e5c-197">サポート担当者からスマート カードの PIN 番号が割り当てられなかった場合は、既定の値 (12345678) を入力します。</span><span class="sxs-lookup"><span data-stu-id="18e5c-197">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="18e5c-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="18e5c-198">See also</span></span>

[<span data-ttu-id="18e5c-199">Skype for Business Server で2要素認証を管理する</span><span class="sxs-lookup"><span data-stu-id="18e5c-199">Manage two-factor authentication in Skype for Business Server</span></span>](two-factor-authentication.md)
  
[<span data-ttu-id="18e5c-200">Skype for Business Server で2要素認証を構成する</span><span class="sxs-lookup"><span data-stu-id="18e5c-200">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
