---
title: 'Lync Server 2013: Lync for iPhone および iPad のインストール'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for iPhone and iPad
ms:assetid: 88d1c149-5842-4ecf-a15e-fcda0330325b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690987(v=OCS.15)
ms:contentKeyID: 51541496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42d83536b3fac3f4050ce76015ce69a6a28522a9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514194"
---
# <a name="installing-lync-for-iphone-and-ipad-in-lync-server-2013"></a><span data-ttu-id="245d7-102">Lync Server 2013 で Lync for iPhone および iPad をインストールする</span><span class="sxs-lookup"><span data-stu-id="245d7-102">Installing Lync for iPhone and iPad in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="245d7-103">_**トピックの最終更新日:** 2014-03-10_</span><span class="sxs-lookup"><span data-stu-id="245d7-103">_**Topic Last Modified:** 2014-03-10_</span></span>

<span data-ttu-id="245d7-104">Lync 2013 for iPhone および Lync 2013 for iPad は、ユーザーがインストール可能なアプリケーションであり、Apple App Store で利用できます。</span><span class="sxs-lookup"><span data-stu-id="245d7-104">Lync 2013 for iPhone and Lync 2013 for iPad are user-installable applications that are available in the Apple App Store.</span></span>

<div>

## <a name="installing-lync-for-iphone-and-lync-for-ipad"></a><span data-ttu-id="245d7-105">Lync for iPhone および Lync for iPad のインストール</span><span class="sxs-lookup"><span data-stu-id="245d7-105">Installing Lync for iPhone and Lync for iPad</span></span>

<span data-ttu-id="245d7-106">ユーザーに対して、Lync 2013 for iPhone および Lync 2013 for iPad をデバイスからアプリストアに送信するように指示することができます。</span><span class="sxs-lookup"><span data-stu-id="245d7-106">You can instruct your users to install Lync 2013 for iPhone and Lync 2013 for iPad by directing them to the App Store from their devices.</span></span> <span data-ttu-id="245d7-107">各デバイスの App Store もオンラインで利用できます。</span><span class="sxs-lookup"><span data-stu-id="245d7-107">The App Store for each device is also available online.</span></span>

  - <span data-ttu-id="245d7-108">Lync for iPhone は、ttp://www.apple.com/iphone/from-the-app-store/のアプリストアで利用でき \< h<span> </span> ></span><span class="sxs-lookup"><span data-stu-id="245d7-108">Lync for iPhone is available in the App Store at \< h<span></span>ttp://www.apple.com/iphone/from-the-app-store/></span></span>

  - <span data-ttu-id="245d7-109">Lync for iPad は、tp://www.apple.com/ipad/from-the-app-store/のアプリストアで利用でき \< ht<span> </span> ></span><span class="sxs-lookup"><span data-stu-id="245d7-109">Lync for iPad is available in the App Store at \< ht<span></span>tp://www.apple.com/ipad/from-the-app-store/></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="245d7-110">Lync 2013 アプリをインストールしていない場合や、会議出席依頼から Lync 会議に参加しようとしている場合、iPhone のユーザーは [参加ツール] ページにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="245d7-110">iPhone users who have not installed the Lync 2013 app and who try to join a Lync meeting from a meeting invitation will be redirected to a Join Launcher page.</span></span> <span data-ttu-id="245d7-111">このページには、Lync 2013 アプリをインストールするためのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="245d7-111">This page contains a link for installing the Lync 2013 app.</span></span> <span data-ttu-id="245d7-112">ただし、このリンクを指定すると、ユーザーはアプリストアに誘導されるのではなく、空の Safari ブラウザーページが開きます。</span><span class="sxs-lookup"><span data-stu-id="245d7-112">However, instead of directing the user to the App Store, this link opens a blank Safari browser page.</span></span> <span data-ttu-id="245d7-113">ユーザーは、この問題を回避するために、次の2つのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="245d7-113">The user can do one of two things to work around this issue:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="245d7-114">[ <STRONG>ホーム</STRONG> ] ボタンを使用して safari ページをバックグラウンドに送信し、再び safari を開きます。</span><span class="sxs-lookup"><span data-stu-id="245d7-114">Use the <STRONG>Home</STRONG> button to send the Safari page to the background, and then reopen Safari.</span></span> <span data-ttu-id="245d7-115">通知 "このページをアプリストアで開く" というメッセージが表示されたら、[ <STRONG>開く</STRONG> ] をタップして、アプリストアで Lync 2013 download に転送されるようにします。</span><span class="sxs-lookup"><span data-stu-id="245d7-115">When the notification “Open this page in App Store” appears, tap <STRONG>Open</STRONG> to be directed to Lync 2013 download in the App Store.</span></span></P>
> <LI>
> <P><span data-ttu-id="245d7-116">アプリストアを手動で開き、「Lync 2013」を検索して、アプリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="245d7-116">Manually open the App Store, search for "Lync 2013," and download the app.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="245d7-117">モバイル クライアント インストールの検証</span><span class="sxs-lookup"><span data-stu-id="245d7-117">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="245d7-118">クライアントを構成し、サインインに成功した後、次のテストを行って、Lync のインストールがモバイル デバイスで正しく動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="245d7-118">After you configure the client and sign in successfully, use the following tests to verify that your Lync installation is working correctly on your mobile device.</span></span>

<span data-ttu-id="245d7-119">**会社のディレクトリにある連絡先の検索**</span><span class="sxs-lookup"><span data-stu-id="245d7-119">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="245d7-120">連絡先リストの最上部にある検索バーの内側をタップし、グローバル アドレス一覧 (GAL) のみに存在する連絡先の名前の入力を開始します。</span><span class="sxs-lookup"><span data-stu-id="245d7-120">In the Contacts list, tap inside the search bar at the top, and begin typing the name of a contact that exists only in the global address list (GAL).</span></span>

2.  <span data-ttu-id="245d7-121">連絡先名が検索結果に表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="245d7-121">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="245d7-122">**インスタントメッセージングとプレゼンスのテスト**</span><span class="sxs-lookup"><span data-stu-id="245d7-122">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="245d7-123">連絡先一覧で、連絡先をタップします。</span><span class="sxs-lookup"><span data-stu-id="245d7-123">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="245d7-124">連絡先カードで、[**IM**] アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="245d7-124">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="245d7-125">インスタントメッセージング (IM) ウィンドウが表示され、IM の入力と送信が可能であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="245d7-125">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="245d7-126">**ダイヤルアウト会議のテスト**</span><span class="sxs-lookup"><span data-stu-id="245d7-126">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="245d7-127">Outlook で、Lync 会議をスケジューリングします。</span><span class="sxs-lookup"><span data-stu-id="245d7-127">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="245d7-128">モバイル デバイスで、会議の招待状を開きます。</span><span class="sxs-lookup"><span data-stu-id="245d7-128">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="245d7-129">参加する会議のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="245d7-129">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="245d7-130">会議サービスからの呼び出しに応答し、会議のオーディオに接続されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="245d7-130">Answer the call from the conference service and verify that you are connected to the meeting audio.</span></span>

<span data-ttu-id="245d7-131">**プッシュ通知のテスト**</span><span class="sxs-lookup"><span data-stu-id="245d7-131">**Test push notifications**</span></span>

1.  <span data-ttu-id="245d7-132">ユーザー A のモバイル デバイスで、ユーザー A のアカウントを使用して Lync にサインインします。</span><span class="sxs-lookup"><span data-stu-id="245d7-132">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="245d7-133">モバイル デバイスで別のアプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="245d7-133">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="245d7-134">異なるクライアントで、ユーザー B のアカウントを使用して Lync にサインインします。</span><span class="sxs-lookup"><span data-stu-id="245d7-134">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="245d7-135">IM をユーザー B からユーザー A に送信します。</span><span class="sxs-lookup"><span data-stu-id="245d7-135">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="245d7-136">IM 通知がユーザー A のモバイル デバイスに表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="245d7-136">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

