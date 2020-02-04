---
title: 'Lync Server 2013: Lync for Windows Phone をインストールする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75e42f9fd2b954e943050fc9877706ae53a1143c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="2072a-102">Lync Server 2013 での Lync for Windows Phone のインストール</span><span class="sxs-lookup"><span data-stu-id="2072a-102">Installing Lync for Windows Phone in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2072a-103">_**最終更新日:** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="2072a-103">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="2072a-104">Windows Phone 用の Lync 2013 は、Windows Phone Marketplace で利用できる、ユーザーがインストールできるアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="2072a-104">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="2072a-105">Lync for Windows Mobile をインストールする</span><span class="sxs-lookup"><span data-stu-id="2072a-105">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="2072a-106">ユーザーに windows phone 用の Lync 2013 をインストールするように指示するには、Windows Phone Marketplace を使用<http://go.microsoft.com/fwlink/p/?linkid=231901>します。</span><span class="sxs-lookup"><span data-stu-id="2072a-106">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <http://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="2072a-107">DNS SRV レコードを使用して Exchange Web サービスを公開している場合</span><span class="sxs-lookup"><span data-stu-id="2072a-107">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="2072a-108">Lync クライアントで Exchange の統合を有効にするには、一部の組織では DNS SRV レコードを使用して Exchange Web サービスの URL を公開します。</span><span class="sxs-lookup"><span data-stu-id="2072a-108">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="2072a-109">Microsoft ダウンロードセンターで利用可能な、「Exchange の統合について理解し[http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)、トラブルシューティングする」のドキュメントでは、これが必要になる可能性のあるシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2072a-109">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="2072a-110">ただし、windows phone プラットフォームでは、SRV 参照がサポートされていないため、Windows Phone ユーザー向けの Exchange との統合は動作しません。</span><span class="sxs-lookup"><span data-stu-id="2072a-110">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="2072a-111">電話で自動的にサーバーを検出する代わりに、Windows Phone ユーザーに Exchange Web サービスの URL を指定するように指示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2072a-111">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="2072a-112">次のようにして、Windows Phone で Lync の設定を構成するようにユーザーに指示します。</span><span class="sxs-lookup"><span data-stu-id="2072a-112">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="2072a-113">Windows Phone の Lync の [設定] で、[ **Exchange** ] 画面を選択します。</span><span class="sxs-lookup"><span data-stu-id="2072a-113">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="2072a-114">**自動検出サーバー**を**オフ**にします。</span><span class="sxs-lookup"><span data-stu-id="2072a-114">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="2072a-115">空のフィールドをタップして、Exchange Web Services の完全修飾ドメイン名 (FQDN) または URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="2072a-115">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2072a-116">完全修飾ドメイン名 (FQDN) または Exchange Web サービスサーバーの完全な URL のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2072a-116">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="2072a-117">FQDN を指定すると、プロトコル (https://) と Exchange Web サービスのパス (/ews/exchange.asmx) が自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="2072a-117">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="2072a-118">Exchange Web Services のパスが異なる場合は、完全な URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2072a-118">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="2072a-119">画面を閉じます。</span><span class="sxs-lookup"><span data-stu-id="2072a-119">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="2072a-120">モバイルクライアントのインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="2072a-120">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="2072a-121">クライアントを構成して正常にサインインしたら、次のテストを行って、お使いのモバイルデバイスで Lync 2013 が正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2072a-121">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="2072a-122">**会社のディレクトリにある連絡先の検索**</span><span class="sxs-lookup"><span data-stu-id="2072a-122">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="2072a-123">連絡先リストで、下部にある [**検索**] をタップします。</span><span class="sxs-lookup"><span data-stu-id="2072a-123">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="2072a-124">グローバル アドレス一覧にだけ含まれる連絡先を検索します。</span><span class="sxs-lookup"><span data-stu-id="2072a-124">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="2072a-125">連絡先名が検索結果に表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2072a-125">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="2072a-126">**インスタント メッセージングおよびプレゼンスのテスト**</span><span class="sxs-lookup"><span data-stu-id="2072a-126">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="2072a-127">連絡先リストで、連絡先をタップします。</span><span class="sxs-lookup"><span data-stu-id="2072a-127">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="2072a-128">連絡先カードで、[ **IM** ] をタップします。</span><span class="sxs-lookup"><span data-stu-id="2072a-128">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="2072a-129">インスタント メッセージング (IM) ウィンドウが表示され、IM の入力と送信が可能であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2072a-129">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="2072a-130">**ダイヤルアウト会議のテスト**</span><span class="sxs-lookup"><span data-stu-id="2072a-130">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="2072a-131">Outlook で Lync 会議をスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="2072a-131">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="2072a-132">モバイル デバイスで、会議の招待状を開きます。</span><span class="sxs-lookup"><span data-stu-id="2072a-132">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="2072a-133">参加する会議のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2072a-133">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="2072a-134">会議サービスからの通話に応答し、会議のオーディオに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2072a-134">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="2072a-135">**プッシュ通知のテスト**</span><span class="sxs-lookup"><span data-stu-id="2072a-135">**Test push notifications**</span></span>

1.  <span data-ttu-id="2072a-136">ユーザー A のモバイルデバイスで、ユーザー A のアカウントで Lync にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2072a-136">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="2072a-137">モバイル デバイスで別のアプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="2072a-137">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="2072a-138">別のクライアントでは、ユーザー B のアカウントで Lync にサインインします。</span><span class="sxs-lookup"><span data-stu-id="2072a-138">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="2072a-139">IM をユーザー B からユーザー A に送信します。</span><span class="sxs-lookup"><span data-stu-id="2072a-139">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="2072a-140">IM 通知がユーザー A のモバイル デバイスに表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2072a-140">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

