---
title: 'Lync Server 2013: Lync for Windows Phone のインストール'
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
ms.openlocfilehash: e2dcb2b1fdc41d1d4dd9a047eceaba8bcbc2c3ea
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a><span data-ttu-id="5722b-102">Lync Server 2013 での Lync for Windows Phone のインストール</span><span class="sxs-lookup"><span data-stu-id="5722b-102">Installing Lync for Windows Phone in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5722b-103">_**トピックの最終更新日:** 2014-02-03_</span><span class="sxs-lookup"><span data-stu-id="5722b-103">_**Topic Last Modified:** 2014-02-03_</span></span>

<span data-ttu-id="5722b-104">Windows phone 用 Lync 2013 は、ユーザーがインストールできるアプリケーションで、Windows Phone Marketplace で利用できます。</span><span class="sxs-lookup"><span data-stu-id="5722b-104">Lync 2013 for Windows Phone is a user-installable application that is available in the Windows Phone Marketplace.</span></span>

<div>

## <a name="installing-lync-for-windows-mobile"></a><span data-ttu-id="5722b-105">Lync for Windows Mobile のインストール</span><span class="sxs-lookup"><span data-stu-id="5722b-105">Installing Lync for Windows Mobile</span></span>

<span data-ttu-id="5722b-106">ユーザーに対して、Lync 2013 for Windows Phone をデバイスにインストールするように指示するには、を使用<https://go.microsoft.com/fwlink/p/?linkid=231901>します。</span><span class="sxs-lookup"><span data-stu-id="5722b-106">You can instruct your users to install Lync 2013 for Windows Phone on their devices by directing them to the Windows Phone Marketplace at <https://go.microsoft.com/fwlink/p/?linkid=231901>.</span></span>

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a><span data-ttu-id="5722b-107">DNS SRV レコードを使用して Exchange Web サービスを公開する場合</span><span class="sxs-lookup"><span data-stu-id="5722b-107">If You Use a DNS SRV Record to Publish Exchange Web Services</span></span>

<span data-ttu-id="5722b-108">Lync クライアントに対して Exchange 統合を有効にするために、一部の組織では、DNS SRV レコードを使用して Exchange Web サービスの URL を公開しています。</span><span class="sxs-lookup"><span data-stu-id="5722b-108">To enable Exchange integration for Lync clients, some organizations publish the Exchange Web Services URL by using a DNS SRV record.</span></span> <span data-ttu-id="5722b-109">「Microsoft ダウンロードセンター」に記載されている「Exchange 統合について[https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095)理解し、トラブルシューティングを行う」では、これが必要になるシナリオについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="5722b-109">The document "Understanding and Troubleshooting Exchange Integration," available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095), describes scenarios in which this might be necessary.</span></span> <span data-ttu-id="5722b-110">ただし、windows phone プラットフォームでは SRV 参照がサポートされていないため、Windows Phone ユーザーの Exchange 統合はこのシナリオでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="5722b-110">However, Exchange integration for Windows Phone users will not work in this scenario, because the Windows Phone platform does not support SRV lookups.</span></span> <span data-ttu-id="5722b-111">電話でサーバーを自動的に検出するのではなく、Windows Phone のユーザーに Exchange Web サービスの URL を指定するように指示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5722b-111">You will need to instruct Windows Phone users to specify the Exchange Web Services URL instead of allowing the phone to automatically detect the server.</span></span>

<span data-ttu-id="5722b-112">ユーザーに、Windows Phone で Lync の設定を次のように構成するように指示します。</span><span class="sxs-lookup"><span data-stu-id="5722b-112">Instruct your users to configure the Lync settings on their Windows Phones as follows:</span></span>

1.  <span data-ttu-id="5722b-113">Windows Phone の [Lync の設定] で、[ **Exchange** ] 画面を選択します。</span><span class="sxs-lookup"><span data-stu-id="5722b-113">In Windows Phone, in the Lync settings, select the **Exchange** screen.</span></span>

2.  <span data-ttu-id="5722b-114">**自動検出サーバー**を**オフ**に移動します。</span><span class="sxs-lookup"><span data-stu-id="5722b-114">Move **Auto-Detect Server** to **Off**.</span></span>

3.  <span data-ttu-id="5722b-115">空のフィールドをタップして、Exchange Web サービスの完全修飾ドメイン名 (FQDN) または URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="5722b-115">Tap the empty field and enter the fully qualified domain name (FQDN) or URL for Exchange Web Services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5722b-116">完全修飾ドメイン名 (FQDN) または Exchange Web サービスサーバーの完全な URL のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5722b-116">You can specify either the fully qualified domain name (FQDN) or the full URL of your Exchange Web Services server.</span></span> <span data-ttu-id="5722b-117">FQDN を指定すると、プロトコル (https://) と Exchange Web サービスパス (/ews/exchange.asmx) が自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5722b-117">If you specify the FQDN, the protocol (https://) and the Exchange Web Services path (/ews/exchange.asmx) are added automatically.</span></span> <span data-ttu-id="5722b-118">Exchange Web サービスのパスが異なる場合は、完全な URL を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5722b-118">If your Exchange Web Services path is different, you can specify the full URL.</span></span>

    
    </div>

4.  <span data-ttu-id="5722b-119">画面を閉じます。</span><span class="sxs-lookup"><span data-stu-id="5722b-119">Close the screen.</span></span>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a><span data-ttu-id="5722b-120">モバイル クライアント インストールの検証</span><span class="sxs-lookup"><span data-stu-id="5722b-120">Verifying Mobile Client Installation</span></span>

<span data-ttu-id="5722b-121">クライアントを構成して正常にサインインしたら、次のテストを使用して、Lync 2013 のインストールがモバイルデバイスで正しく動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="5722b-121">After you configure the client and sign in successfully, use the following tests to verify that your installation of Lync 2013 is working correctly on your mobile device.</span></span>

<span data-ttu-id="5722b-122">**会社のディレクトリにある連絡先の検索**</span><span class="sxs-lookup"><span data-stu-id="5722b-122">**Search for a contact in the corporate directory**</span></span>

1.  <span data-ttu-id="5722b-123">連絡先一覧で、下部にある [**検索**] をタップします。</span><span class="sxs-lookup"><span data-stu-id="5722b-123">In the Contacts list, tap **Search** at the bottom.</span></span>

2.  <span data-ttu-id="5722b-124">グローバルアドレス一覧にのみ存在する連絡先を検索します。</span><span class="sxs-lookup"><span data-stu-id="5722b-124">Search for a contact that exists only in the global address list.</span></span>

3.  <span data-ttu-id="5722b-125">連絡先名が検索結果に表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5722b-125">Verify that the contact name appears in the search results.</span></span>

<span data-ttu-id="5722b-126">**インスタントメッセージングとプレゼンスのテスト**</span><span class="sxs-lookup"><span data-stu-id="5722b-126">**Test instant messaging and presence**</span></span>

1.  <span data-ttu-id="5722b-127">連絡先一覧で、連絡先をタップします。</span><span class="sxs-lookup"><span data-stu-id="5722b-127">In the Contacts list, tap a contact.</span></span>

2.  <span data-ttu-id="5722b-128">連絡先カードで、[**IM**] アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="5722b-128">In the contact card, tap the **IM** icon.</span></span>

3.  <span data-ttu-id="5722b-129">インスタントメッセージング (IM) ウィンドウが表示され、IM の入力と送信が可能であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5722b-129">Verify that an instant messaging (IM) window appears and that you can type and send an IM.</span></span>

<span data-ttu-id="5722b-130">**ダイヤルアウト会議のテスト**</span><span class="sxs-lookup"><span data-stu-id="5722b-130">**Test dial-out conferencing**</span></span>

1.  <span data-ttu-id="5722b-131">Outlook で、Lync 会議をスケジューリングします。</span><span class="sxs-lookup"><span data-stu-id="5722b-131">In Outlook, schedule a Lync meeting.</span></span>

2.  <span data-ttu-id="5722b-132">モバイル デバイスで、会議の招待状を開きます。</span><span class="sxs-lookup"><span data-stu-id="5722b-132">On the mobile device, open the meeting invitation.</span></span>

3.  <span data-ttu-id="5722b-133">参加する会議のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5722b-133">Click the link in the meeting to join.</span></span>

4.  <span data-ttu-id="5722b-134">電話会議サービスからの呼び出しに応答し、会議のオーディオに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5722b-134">Answer the call from the conference service and verify that you are connected to meeting audio.</span></span>

<span data-ttu-id="5722b-135">**プッシュ通知のテスト**</span><span class="sxs-lookup"><span data-stu-id="5722b-135">**Test push notifications**</span></span>

1.  <span data-ttu-id="5722b-136">ユーザー A のモバイル デバイスで、ユーザー A のアカウントを使用して Lync にサインインします。</span><span class="sxs-lookup"><span data-stu-id="5722b-136">On user A’s mobile device, sign in to Lync with user A’s account.</span></span>

2.  <span data-ttu-id="5722b-137">モバイル デバイスで別のアプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="5722b-137">Open another application on the mobile device.</span></span>

3.  <span data-ttu-id="5722b-138">異なるクライアントで、ユーザー B のアカウントを使用して Lync にサインインします。</span><span class="sxs-lookup"><span data-stu-id="5722b-138">On a different client, sign in to Lync with user B’s account.</span></span>

4.  <span data-ttu-id="5722b-139">IM をユーザー B からユーザー A に送信します。</span><span class="sxs-lookup"><span data-stu-id="5722b-139">Send an IM from user B to user A.</span></span>

5.  <span data-ttu-id="5722b-140">IM 通知がユーザー A のモバイル デバイスに表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5722b-140">Verify that the IM notification appears on user A’s mobile device.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

