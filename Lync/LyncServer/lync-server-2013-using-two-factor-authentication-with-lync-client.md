---
title: 'Lync Server 2013: Lync クライアントで2要素認証を使用する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5af9e9b5268fd218bfe5856473124514cfe34945
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="fcd3f-102">Lync クライアントおよび Lync Server 2013 での2要素認証の使用</span><span class="sxs-lookup"><span data-stu-id="fcd3f-102">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcd3f-103">_**最終更新日:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="fcd3f-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="fcd3f-104">このトピックでは、Lync 2013 クライアントで2要素認証を利用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-104">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="fcd3f-105">Lync 2013 に初めてサインインする</span><span class="sxs-lookup"><span data-stu-id="fcd3f-105">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="fcd3f-106">Lync のサインイン情報は、Lync 2013 がインストールされているときに自動的に構成されます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-106">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="fcd3f-107">ただし、初めて Lync を使用する場合は、クライアントを手動で開始しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-107">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="fcd3f-108">**Lync に初めてサインインするには**</span><span class="sxs-lookup"><span data-stu-id="fcd3f-108">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="fcd3f-109">組織のネットワークにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-109">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="fcd3f-110">[ **Microsoft \> lync lync 2013**の**すべてのプログラム** \>を**起動** \>する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-110">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="fcd3f-111">Lync のサインイン画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-111">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="fcd3f-112">[サインイン アドレス] ボックスが既に入力されている場合は、表示されているアドレスが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="fcd3f-113">正しくない場合、またはボックスが空の場合は、Lync のサインインアドレス (通常はメールアドレスと同じ) を入力します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-113">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="fcd3f-114">パスワードを入力するボックスが空の場合は、パスワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-114">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="fcd3f-115">[**サインイン**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-115">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="fcd3f-116">Lync からサインアウトする</span><span class="sxs-lookup"><span data-stu-id="fcd3f-116">Sign out of Lync</span></span>

<span data-ttu-id="fcd3f-117">Lync の使用が完了したら、[ファイル] メニューから表示を閉じたり、セッションからサインアウトしたり、プログラムから退出したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-117">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="fcd3f-118">次の表で、オプションの違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-118">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcd3f-119">オプション</span><span class="sxs-lookup"><span data-stu-id="fcd3f-119">Option</span></span></th>
<th><span data-ttu-id="fcd3f-120">機能</span><span class="sxs-lookup"><span data-stu-id="fcd3f-120">What it does</span></span></th>
<th><span data-ttu-id="fcd3f-121">実行する方法</span><span class="sxs-lookup"><span data-stu-id="fcd3f-121">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcd3f-122">閉じる</span><span class="sxs-lookup"><span data-stu-id="fcd3f-122">Close</span></span></p></td>
<td><p><span data-ttu-id="fcd3f-123">Lync ディスプレイを閉じますが、ユーザー ID で識別された Lync セッションは引き続き実行できます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-123">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="fcd3f-124">したがって、引き続き通知を受け取り、他のユーザーと対話できます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-124">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="fcd3f-125">タスクバーまたは画面の下部にある通知領域の Lync アイコンをクリックすると、いつでも表示を元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-125">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="fcd3f-126">Lync メインウィンドウで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-126">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="fcd3f-127">[<strong>オプション</strong>] ボタンを選択し、[<strong>ファイル</strong> &gt;を<strong>閉じる</strong>] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-127">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="fcd3f-128">ウィンドウの右上隅にある [<strong>閉じる</strong>] ボタン (X) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-128">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcd3f-129">サインアウトする</span><span class="sxs-lookup"><span data-stu-id="fcd3f-129">Sign out</span></span></p></td>
<td><p><span data-ttu-id="fcd3f-130">ユーザー ID に関連付けられた Lync セッションを終了しますが、Lync はバックグラウンドで実行され続けます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-130">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="fcd3f-131">サインアウトすると、サインイン ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-131">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="fcd3f-p105">[<STRONG>サインイン情報を削除</STRONG>] を選ぶと、サインアウトするときにコンピューターからログオン ID とパスワードの記録を削除できます。このようにすると、サポート担当者が行うサインインの問題のトラブルシューティングが容易になることがあります。また、権限のないユーザーがあなたの資格情報でログインすることは難しくなるため、サインイン情報のセキュリティも確保できます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-p105">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer. Doing this might make it easier for support people to troubleshoot sign-in issues. It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="fcd3f-135">Lync メインウィンドウで、[<strong>オプション</strong>] ボタンを選択し、[<strong>ファイル</strong> &gt; <strong></strong>]、[サインアウト] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-135">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcd3f-136">終了する</span><span class="sxs-lookup"><span data-stu-id="fcd3f-136">Exit</span></span></p></td>
<td><p><span data-ttu-id="fcd3f-137">Lync セッションが終了し、コンピューター上の Lync がシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-137">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="fcd3f-138">終了後、Lync を再起動する場合は、[ <strong>Microsoft lync</strong> &gt; <strong>lync 2013</strong>の<strong>すべてのプログラム</strong> &gt;を<strong>起動</strong> &gt;する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-138">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="fcd3f-139">Lync メインウィンドウで、[<strong>オプション</strong>] ボタンを選択し、[<strong>ファイル</strong> &gt; <strong>終了</strong>] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-139">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="fcd3f-140">スマートカードを使って Lync にサインインする</span><span class="sxs-lookup"><span data-stu-id="fcd3f-140">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="fcd3f-141">一部の組織では、Lync 2013 ユーザーのセキュリティを強化するために、2要素認証と呼ばれるマルチステップのサインインプロセスを使用しています。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="fcd3f-142">このオプションを使用することが予想される場合は、Lync にサインインするには「スマートカード」が必要です。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-142">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="fcd3f-143">スマートカードには、物理と仮想の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-143">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="fcd3f-144">\*\*\*\*   クレジットカードのサイズについての情報をご紹介します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-144">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="fcd3f-145">ログインするときにスマート カード リーダーに挿入します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-145">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="fcd3f-146">**Virtual**   は物理オブジェクトではありませんが、コンピューター上の特殊なチップに書き込まれる電子的な識別子であり、基本的には、スマートカードをコンピューターに作成します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-146">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="fcd3f-147">TPM (トラステッドプラットフォームモジュール) チップが含まれている Windows 8 コンピューターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="fcd3f-148">スマート カードを登録する</span><span class="sxs-lookup"><span data-stu-id="fcd3f-148">Enroll your smart card</span></span>

<span data-ttu-id="fcd3f-149">スマートカードでサインインするには、カードが "登録" されている必要があります。つまり、カードでユーザーの資格情報を識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-149">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="fcd3f-150">これは、カードが物理または仮想のどちらであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="fcd3f-151">このプロセスは、Lync Server 管理者によって既に実行されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-151">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="fcd3f-152">実行されているかどうかがわからない場合は、確認してください。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-152">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fcd3f-153">各仮想スマートカードは、それがインストールされているデバイスのみに関連付けられているため、使用する Windows 8 コンピューターごとに別のカードを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-153">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="fcd3f-154">**スマート カードを手動で登録するには、次の操作を行います。**</span><span class="sxs-lookup"><span data-stu-id="fcd3f-154">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="fcd3f-155">Lync を実行しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-155">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="fcd3f-156">Internet Explorer を使って、組織の証明機関 Web 登録ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-156">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="fcd3f-157">まだインストールしていない場合は、このリソースの web アドレスを Lync Server 管理者に確認してください。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-157">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="fcd3f-158">URL は次https://MyCA.\のようになります。 [companyname\]/certsrv] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-158">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fcd3f-159">Internet Explorer 10 を使っている場合は、この Web サイトを互換モードで見る必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-159">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="fcd3f-160">証明書のページにログオンするよう求められた場合は、ユーザーのドメイン アカウントを使ってログオンします (コンピューターの管理者としてはログオンしません)。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-160">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="fcd3f-161">Web サイトのようこそページで、[**証明書の要求**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-161">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="fcd3f-162">[**証明書の要求の詳細設定**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-162">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="fcd3f-163">[**この CA への要求を作成し送信する。**] を選んで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="fcd3f-164">「スマート カードの登録ステーション」というページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-164">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="fcd3f-165">要求を承認して ActiveX コントロールをインストールし、[証明書の要求の詳細設定] を次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="fcd3f-166">[**証明書のテンプレート**] ボックスの一覧から [**スマート カード ユーザー**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-166">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="fcd3f-167">[**新しいキー セットを作成する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-167">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="fcd3f-168">スマート カードのラベルから製造元情報を確認し、[**CSP**] ボックスの一覧から製造元を選びます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-168">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="fcd3f-169">まだ選んでいない場合は、要求の形式として [**CSP**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-169">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="fcd3f-170">まだ選んでいない場合は、[ハッシュ アルゴリズム] ボックスの一覧から [**sha1**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-170">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="fcd3f-171">証明書に分かりやすい名前を付けて、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-171">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="fcd3f-172">登録ステーションに接続したカード リーダーに空のスマート カードを挿入し、[**登録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-172">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="fcd3f-173">要求メッセージが表示されたら、暗証番号 (PIN) を入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-173">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fcd3f-174">スマート カードを登録するために使う特別な PIN をテクニカル サポート担当者から受け取っていない場合は、既定のスマート カード PIN の値である 12345678 を使用します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-174">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="fcd3f-175">スマート カードを最初に使うときに PIN の変更をユーザーに強制するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-175">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="fcd3f-176">登録ステーションに接続したカード リーダーに空のスマート カードを挿入し、[**登録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-176">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="fcd3f-177">要求メッセージが表示されたら、暗証番号 (PIN) を入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-177">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fcd3f-178">スマート カードを登録するために使う特別な PIN をテクニカル サポート担当者から受け取っていない場合は、既定のスマート カード PIN の値である 12345678 を使用します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-178">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="fcd3f-179">スマート カードを最初に使うときに PIN の変更をユーザーに強制するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-179">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="fcd3f-180">表示された証明書に記載されたユーザーの情報を確認したら、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-180">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="fcd3f-181">証明書が発行されたことを知らせる通知を確認したら、[**この証明書のインストール**] をクリックして登録プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-181">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="fcd3f-182">スマートカードの資格情報を使用して Lync にサインインする</span><span class="sxs-lookup"><span data-stu-id="fcd3f-182">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="fcd3f-183">スマートカードを初めて使用する前に、Lync のサインインページで [**サインイン情報を削除**する] をクリックすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-183">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="fcd3f-184">これにより、コンピューターに保存されているすべてのサインイン情報がクリアされ、エラーの原因を取り除くことができます。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-184">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="fcd3f-185">**スマートカードの資格情報を使用して Lync にサインインするには**</span><span class="sxs-lookup"><span data-stu-id="fcd3f-185">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="fcd3f-186">Lync クライアントを起動します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-186">Start the Lync client.</span></span>

2.  <span data-ttu-id="fcd3f-187">サインイン画面で、ユーザーのアカウント名を [**サインイン アドレス**] ボックスに入力し、[**サインイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-187">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="fcd3f-188">仮想スマート カードを使っている場合は、この手順は省略します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-188">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="fcd3f-189">物理スマート カードを使っている場合は、メッセージが表示されたらスマート カードをスマート カード リーダーに挿入し、カードが認識されたら [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-189">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="fcd3f-190">スマート カードの PIN 番号を入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-190">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fcd3f-191">サポート担当者からスマート カードの PIN 番号が割り当てられなかった場合は、既定の値 (12345678) を入力します。</span><span class="sxs-lookup"><span data-stu-id="fcd3f-191">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

