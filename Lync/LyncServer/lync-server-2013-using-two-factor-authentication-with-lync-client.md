---
title: 'Lync Server 2013: Lync クライアントでの2要素認証の使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using two-factor authentication with Lync client
ms:assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn338071(v=OCS.15)
ms:contentKeyID: 55115593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a90dd3c40267f0994e7f41eabb689c869182cea7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508644"
---
# <a name="using-two-factor-authentication-with-lync-client-and-lync-server-2013"></a><span data-ttu-id="3f3d3-102">Lync クライアントおよび Lync Server 2013 で2要素認証を使用する</span><span class="sxs-lookup"><span data-stu-id="3f3d3-102">Using two-factor authentication with Lync client and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f3d3-103">_**トピックの最終更新日:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="3f3d3-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="3f3d3-104">このトピックでは、Lync 2013 クライアントで2要素認証を利用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-104">This topic described how to take advantage of two-factor authentication with Lync 2013 client.</span></span>

<div>

## <a name="sign-in-to-lync-2013-for-the-first-time"></a><span data-ttu-id="3f3d3-105">初めて Lync 2013 にサインインする</span><span class="sxs-lookup"><span data-stu-id="3f3d3-105">Sign in to Lync 2013 for the first time</span></span>

<span data-ttu-id="3f3d3-106">通常、lync 2013 をインストールすると、Lync サインイン情報が自動的に構成されます。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-106">Your Lync sign-in information is usually configured automatically when Lync 2013 is installed.</span></span> <span data-ttu-id="3f3d3-107">しかし、初めて Lync を使用するときは、クライアントを手動で開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-107">But the first time you use Lync, you might have to manually start the client.</span></span>

<span data-ttu-id="3f3d3-108">**初めて Lync にサインインするには**</span><span class="sxs-lookup"><span data-stu-id="3f3d3-108">**To sign in to Lync for the first time**</span></span>

1.  <span data-ttu-id="3f3d3-109">組織のネットワークにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-109">Log on to your organization’s network.</span></span>

2.  <span data-ttu-id="3f3d3-110">[ **Start** \> **すべてのプログラム**を起動] [ \> **Microsoft Lync \> lync 2013**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-110">Select **Start** \> **All Programs** \> **Microsoft Lync \> Lync 2013**.</span></span>
    
    <span data-ttu-id="3f3d3-111">Lync サインイン画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-111">You should see the Lync sign-in screen.</span></span>
    
      - <span data-ttu-id="3f3d3-112">[サインインアドレス] ボックスに既に入力されている場合は、表示されているアドレスが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-112">If the sign-in address box is already filled in, confirm that the address shown is correct.</span></span>
    
      - <span data-ttu-id="3f3d3-113">正しくない場合、またはボックスが空の場合は、Lync サインインアドレス (通常はメールアドレスと同じ) を入力します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-113">If it’s not correct, or if the box is empty, enter your Lync sign-in address (this is usually the same as your email address).</span></span>
    
      - <span data-ttu-id="3f3d3-114">[空のパスワード] ボックスが表示されている場合は、パスワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-114">If an empty password box is displayed, add your password.</span></span>

3.  <span data-ttu-id="3f3d3-115">[ **サインイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-115">Select **Sign-in**.</span></span>

</div>

<div>

## <a name="sign-out-of-lync"></a><span data-ttu-id="3f3d3-116">Lync からサインアウトする</span><span class="sxs-lookup"><span data-stu-id="3f3d3-116">Sign out of Lync</span></span>

<span data-ttu-id="3f3d3-117">Lync の使用が終了したら、[ファイル] メニューから、表示を閉じるか、セッションからサインアウトするか、またはプログラムを終了することができます。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-117">When you’re finished using Lync, you can close the display, sign out of your session, or exit from the program, all from the File menu.</span></span> <span data-ttu-id="3f3d3-118">次の表で、オプションの違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-118">The following table explains the differences in the options.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f3d3-119">オプション</span><span class="sxs-lookup"><span data-stu-id="3f3d3-119">Option</span></span></th>
<th><span data-ttu-id="3f3d3-120">目的</span><span class="sxs-lookup"><span data-stu-id="3f3d3-120">What it does</span></span></th>
<th><span data-ttu-id="3f3d3-121">実行方法</span><span class="sxs-lookup"><span data-stu-id="3f3d3-121">How to perform it</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f3d3-122">閉じる</span><span class="sxs-lookup"><span data-stu-id="3f3d3-122">Close</span></span></p></td>
<td><p><span data-ttu-id="3f3d3-123">Lync の表示を閉じますが、ユーザー ID で識別された Lync セッションを引き続き実行することができます。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-123">Closes your Lync display but lets the Lync session identified with your user ID continue to run.</span></span> <span data-ttu-id="3f3d3-124">これにより、引き続き通知を取得したり、他のユーザーと対話したりできます。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-124">This is so you can continue to get notifications and interact with others.</span></span></p>
<p><span data-ttu-id="3f3d3-125">画面の下部にある [Lync] アイコンまたは通知領域をクリックして、いつでも表示を元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-125">You can get the display back at any time by clicking the Lync icon on the taskbar or the notification area at the bottom of your screen.</span></span></p></td>
<td><p><span data-ttu-id="3f3d3-126">Lync のメインウィンドウで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-126">On the Lync main window, do one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="3f3d3-127">[<strong>オプション</strong>] ボタンを選択し、[<strong>ファイル</strong>を閉じる] を選択し &gt; <strong>Close</strong>ます。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-127">Select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Close</strong>.</span></span></p></li>
<li><p><span data-ttu-id="3f3d3-128">ウィンドウの右上隅にある [ <strong>閉じる</strong> ] ボタン (X) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-128">Click the <strong>Close</strong> button (X) in the upper-right corner of the window.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f3d3-129">サインアウト</span><span class="sxs-lookup"><span data-stu-id="3f3d3-129">Sign out</span></span></p></td>
<td><p><span data-ttu-id="3f3d3-130">ユーザー ID に関連付けられている Lync セッションを終了しますが、Lync は引き続きバックグラウンドで実行します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-130">Ends the Lync session associated with your user ID, but Lync continues to run in the background.</span></span> <span data-ttu-id="3f3d3-131">サインアウトすると、サインインウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-131">When you sign out, the sign-in window will appear.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="3f3d3-132">[サインアウト時にサインイン <STRONG>情報を削除</STRONG> する] を選択して、ログオン ID とパスワードのレコードをコンピューターから削除します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-132">Select <STRONG>Delete my sign-in information</STRONG> when you sign out to remove the record of your logon ID and password from the computer.</span></span> <span data-ttu-id="3f3d3-133">これにより、サポート担当者がサインインの問題のトラブルシューティングを容易に行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-133">Doing this might make it easier for support people to troubleshoot sign-in issues.</span></span> <span data-ttu-id="3f3d3-134">また、承認されていないユーザーが資格情報を使用してログオンすることが困難になるため、サインイン情報の安全性を確保することもできます。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-134">It can also help ensure your sign-in information is more secure by making it difficult for unauthorized users to log on with your credentials.</span></span>


</div></td>
<td><p><span data-ttu-id="3f3d3-135">Lync のメインウィンドウで、[<strong>オプション</strong>] ボタンを選択し、[<strong>ファイル</strong>] [サインアウト] を選択し &gt; <strong>Sign Out</strong>ます。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-135">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Sign Out</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f3d3-136">Exit</span><span class="sxs-lookup"><span data-stu-id="3f3d3-136">Exit</span></span></p></td>
<td><p><span data-ttu-id="3f3d3-137">Lync セッションを終了し、コンピューター上で Lync をシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-137">Ends your Lync session and shuts down Lync on your computer.</span></span> <span data-ttu-id="3f3d3-138">いったん終了した後、lync を再起動するには、[すべてのプログラムを<strong>開始</strong>する] [ &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>lync 2013</strong>] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-138">After exiting, if you want to restart Lync, select <strong>Start</strong> &gt; <strong>All Programs</strong> &gt; <strong>Microsoft Lync</strong> &gt; <strong>Lync 2013</strong>.</span></span></p></td>
<td><p><span data-ttu-id="3f3d3-139">Lync のメインウィンドウで、[<strong>オプション</strong>] ボタンを選択し、[<strong>ファイル</strong>終了] を選択し &gt; <strong>Exit</strong>ます。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-139">On the Lync main window, select the <strong>Options</strong> button, then select <strong>File</strong> &gt; <strong>Exit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sign-in-to-lync-with-a-smart-card"></a><span data-ttu-id="3f3d3-140">スマートカードを使用して Lync にサインインする</span><span class="sxs-lookup"><span data-stu-id="3f3d3-140">Sign in to Lync with a Smart Card</span></span>

<span data-ttu-id="3f3d3-141">一部の組織では、2要素認証と呼ばれる複数ステップのサインインプロセスを使用して、Lync 2013 ユーザーのセキュリティを強化しています。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-141">Some organizations now use a multi-step sign-in process, called two-factor authentication, to increase security for their Lync 2013 users.</span></span> <span data-ttu-id="3f3d3-142">このオプションを使用する場合は、Lync にサインインするための "スマートカード" が必要です。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-142">If you’re expected to use this option, you’ll need a “smart card” to sign in to Lync.</span></span> <span data-ttu-id="3f3d3-143">スマートカードには、物理と仮想の2つの種類があります。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-143">Smart cards come in two varieties, physical and virtual:</span></span>

  - <span data-ttu-id="3f3d3-144">**物理**    クレジットカードのサイズについて。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-144">**Physical**   About the size of a credit card.</span></span> <span data-ttu-id="3f3d3-145">ログイン時にスマートカードリーダーに挿入します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-145">You insert it into a smart card reader when you log in.</span></span>

  - <span data-ttu-id="3f3d3-146">**仮想**    物理オブジェクトではなく、コンピューターの特殊なチップに書き込まれる電子識別子です。これにより、基本的にはコンピューターにスマートカードが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-146">**Virtual**   Not a physical object, but an electronic identifier that gets written to a special chip on your computer, which in essence builds the smart card into your computer.</span></span> <span data-ttu-id="3f3d3-147">TPM (トラステッドプラットフォームモジュール) チップを含む Windows 8 コンピューターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-147">Available only for use with Windows 8 computers that contain the TPM (Trusted Platform Module) chip.</span></span>

<div>

## <a name="enroll-your-smart-card"></a><span data-ttu-id="3f3d3-148">スマートカードを登録する</span><span class="sxs-lookup"><span data-stu-id="3f3d3-148">Enroll your smart card</span></span>

<span data-ttu-id="3f3d3-149">スマートカードを使用してサインインするには、カードが "登録済み" になっている必要があります。つまり、ユーザーの資格情報がカードで識別される必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-149">Before you can sign in with a smart card, the card must be “enrolled”—that is, your user credentials have to be identified with the card.</span></span> <span data-ttu-id="3f3d3-150">これは、カードが物理または仮想のどちらであるかによっても当てはまります。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-150">This is the case whether the card is physical or virtual.</span></span> <span data-ttu-id="3f3d3-151">このプロセスは、既に Lync Server 管理者によって実行されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-151">This process may already been carried out by your Lync Server administrator.</span></span> <span data-ttu-id="3f3d3-152">完了しているかどうかがわからない場合は、確認してください。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-152">Check with them if you’re not sure whether that has been done.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f3d3-153">各仮想スマートカードは、がインストールされているデバイスにのみ関連付けられているため、使用する Windows 8 コンピューターごとに個別のカードを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-153">Since each virtual smart card is associated only with the device it’s installed on, a separate card will need to be enrolled for each Windows 8 computer you use.</span></span>



</div>

<span data-ttu-id="3f3d3-154">**スマートカードを手動で登録するには**</span><span class="sxs-lookup"><span data-stu-id="3f3d3-154">**To manually enroll your smart card**</span></span>

1.  <span data-ttu-id="3f3d3-155">Lync を実行しているコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-155">Log on to the computer you’ll be running Lync on.</span></span>

2.  <span data-ttu-id="3f3d3-156">Internet Explorer を使用して、組織の証明機関 Web 登録ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-156">Using Internet Explorer, browse to your organization’s Certificate Authority Web Enrollment page.</span></span>
    
    <span data-ttu-id="3f3d3-157">まだお持ちでない場合は、このリソースの web アドレスを Lync Server 管理者に依頼してください。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-157">Ask your Lync Server administrator for the web address of this resource if you don’t already have it.</span></span> <span data-ttu-id="3f3d3-158">URL は、次のように表示されます。 https://MyCA.\ [会社名 \] . .com/certsrv]。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-158">The URL will look something like this: https://MyCA.\[yourcompanyname\].com/certsrv.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3f3d3-159">Internet Explorer 10 を使用している場合は、この web サイトを互換モードで表示する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-159">If you’re using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

3.  <span data-ttu-id="3f3d3-160">証明書ページにログオンするように求めるメッセージが表示されたら、(コンピューターの管理者としてではなく) ドメインアカウントを使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-160">When you’re prompted to log on to the certification page, log on using your domain account (rather than as administrator of your computer).</span></span>

4.  <span data-ttu-id="3f3d3-161">Web サイトのウェルカムページで、[ **証明書の要求**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-161">On the website Welcome Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="3f3d3-162">[ **要求の詳細設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-162">Select **Advanced Request**.</span></span>

6.  <span data-ttu-id="3f3d3-163">[ **この CA への要求を作成し送信**する] を選択し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-163">Select **Create and submit a request to this CA**, then click **Next**.</span></span>

7.  <span data-ttu-id="3f3d3-164">これで、スマートカード登録ステーションというページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-164">Now you’ll see a page called Smart Card Enrollment Station.</span></span> <span data-ttu-id="3f3d3-165">ActiveX コントロールをインストールする要求を承認し、次のように詳細証明書要求フォームを完成させます。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-165">Approve the request to install the ActiveX control, and then complete the Advanced Certificate Request form as follows:</span></span>
    
    1.  <span data-ttu-id="3f3d3-166">[**証明書テンプレート**] ドロップダウンリストから [**スマートカードユーザー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-166">Select **Smartcard user** from the **Certificate Template** dropdown list.</span></span>
    
    2.  <span data-ttu-id="3f3d3-167">[ **新しいキーセットの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-167">Select **Create new key set**.</span></span>
    
    3.  <span data-ttu-id="3f3d3-168">[スマートカード] のラベルで製造元の情報を検索し、 **CSP** のドロップダウンリストからその製造元を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-168">Find the manufacturer information on the label of your smart card and select that manufacturer from the **CSP** dropdown list.</span></span>
    
    4.  <span data-ttu-id="3f3d3-169">要求の形式がまだ選択されていない場合は、[ **CSP** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-169">Select **CSP** as the Request Format, if it’s not already selected.</span></span>
    
    5.  <span data-ttu-id="3f3d3-170">[ハッシュアルゴリズム] ドロップダウンリストから [ **sha1** ] を選択します (まだ選択されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-170">Select **sha1** from the Hash Algorithm dropdown list, if it’s not already selected.</span></span>
    
    6.  <span data-ttu-id="3f3d3-171">証明書にわかりやすい名前を付けて、[ **送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-171">Give your certificate a name you’ll recognize, and click **Submit**.</span></span>

8.  <span data-ttu-id="3f3d3-172">次に、登録ステーションに接続されたカードリーダーに空のスマートカードを挿入し、[ **登録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-172">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

9.  <span data-ttu-id="3f3d3-173">メッセージが表示されたら、暗証番号 (PIN) を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-173">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3f3d3-174">テクニカルサポート担当者がスマートカードを登録するために使用する特別な PIN を指定していない場合は、既定のスマートカード PIN の値を使用します。これは12345678です。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-174">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

10. <span data-ttu-id="3f3d3-175">スマートカードを初めて使用したときに PIN を変更するようにユーザーに強制するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-175">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

11. <span data-ttu-id="3f3d3-176">次に、登録ステーションに接続されたカードリーダーに空のスマートカードを挿入し、[ **登録**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-176">Now insert your blank smart card into the card reader attached to the enrollment station and click **Enroll**.</span></span>

12. <span data-ttu-id="3f3d3-177">メッセージが表示されたら、暗証番号 (PIN) を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-177">When prompted, enter your personal identification number (PIN), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3f3d3-178">テクニカルサポート担当者がスマートカードを登録するために使用する特別な PIN を指定していない場合は、既定のスマートカード PIN の値を使用します。これは12345678です。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-178">If your technical support person has not given you a special PIN to use to enroll your smart card, use the default smart card PIN value, which is 12345678.</span></span>

    
    </div>

13. <span data-ttu-id="3f3d3-179">スマートカードを初めて使用したときに PIN を変更するようにユーザーに強制するオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-179">Select the option to force the user (you) to change the PIN the first time the smart card is used.</span></span>

14. <span data-ttu-id="3f3d3-180">[ **OK]** をクリックして、表示されている証明書に情報が表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-180">Click **OK** to confirm that the certificate displayed has your information on it.</span></span>

15. <span data-ttu-id="3f3d3-181">証明書が発行されたことを示す通知が表示されたら、[ **この証明書のインストール** ] をクリックして登録プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-181">Once you see the notice that the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>

</div>

<div>

## <a name="sign-in-to-lync-with-your-smart-card-credentials"></a><span data-ttu-id="3f3d3-182">スマートカードの資格情報を使用して Lync にサインインする</span><span class="sxs-lookup"><span data-stu-id="3f3d3-182">Sign in to Lync with your smart card credentials</span></span>

<span data-ttu-id="3f3d3-183">スマートカードを初めて使用する前に、Lync サインインページで [ **サインイン情報の削除** ] をクリックすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-183">Before you use your smart card for the first time, it’s recommended that you click **Delete my sign-in info** on the Lync sign-in page.</span></span> <span data-ttu-id="3f3d3-184">この操作を実行すると、コンピューターに格納されているすべてのサインイン資格情報が削除され、発生する可能性のあるエラーの原因がなくなります。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-184">Doing this clears any sign-in credentials stored on your computer, and eliminates a possible source of error.</span></span>

<span data-ttu-id="3f3d3-185">**スマートカードの資格情報を使用して Lync にサインインするには**</span><span class="sxs-lookup"><span data-stu-id="3f3d3-185">**To sign in to Lync with your smart card credentials**</span></span>

1.  <span data-ttu-id="3f3d3-186">Lync クライアントを起動します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-186">Start the Lync client.</span></span>

2.  <span data-ttu-id="3f3d3-187">[サインイン] 画面の [ **サインインアドレス** ] ボックスに、サインインしているユーザーアカウント名を入力し、[ **サインイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-187">On the Sign in screen, type your sign in user account name in the **Sign-in address** box, and then click **Sign In**.</span></span>

3.  <span data-ttu-id="3f3d3-188">仮想スマートカードを使用している場合は、この手順を省略します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-188">If you are using a virtual smart card, skip this step.</span></span>
    
    <span data-ttu-id="3f3d3-189">物理スマートカードを使用している場合は、スマートカードリーダーにスマートカードを挿入し、カードが検出されたときに [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-189">If you are using a physical smart card, insert the smart card into your smart card reader and prompted to do so, and then click **OK** when the card is detected.</span></span>

4.  <span data-ttu-id="3f3d3-190">スマートカードの PIN 番号を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-190">Type in the PIN number you for your smart card and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3f3d3-191">サポート担当者がスマートカードの PIN 番号を割り当てられていない場合は、既定値の12345678を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f3d3-191">If you were not assigned a smart card PIN number by your support person, use the default value, which is 12345678.</span></span>

    
    </div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

