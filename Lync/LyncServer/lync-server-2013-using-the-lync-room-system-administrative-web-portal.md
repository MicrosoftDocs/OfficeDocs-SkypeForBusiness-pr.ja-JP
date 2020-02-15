---
title: 'Lync Server 2013: Lync Room System 管理 Web ポータルの使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3871002fc07c0129c1caa2cb6b86734548b20a66
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="8f303-102">Lync Server 2013 での Lync Room System 管理 Web ポータルの使用</span><span class="sxs-lookup"><span data-stu-id="8f303-102">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f303-103">_**トピックの最終更新日:** 2014-11-10_</span><span class="sxs-lookup"><span data-stu-id="8f303-103">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="8f303-104">サーバーに LRS を展開した後、ブラウザーから LRS 管理 Web ポータルにサインインして、すべての LRS ルームの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8f303-104">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="8f303-105">サインイン</span><span class="sxs-lookup"><span data-stu-id="8f303-105">Sign in</span></span>

1.  <span data-ttu-id="8f303-106">次の URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="8f303-106">Browse to the following URL:</span></span>
    
    <span data-ttu-id="8f303-107">https://\<fe-サーバー\>/lrs</span><span class="sxs-lookup"><span data-stu-id="8f303-107">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="8f303-108">LRSSupport アカウントの資格情報、または LRSSupportAdminGroup セキュリティグループに追加されているアカウントを入力します。</span><span class="sxs-lookup"><span data-stu-id="8f303-108">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="8f303-109">![Lync Room System 管理者ポータルのサインイン画面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System 管理者ポータルのサインイン画面")</span><span class="sxs-lookup"><span data-stu-id="8f303-109">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="8f303-110">LRS 管理 Web ポータルの概要ページ</span><span class="sxs-lookup"><span data-stu-id="8f303-110">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="8f303-111">概要ページには、サーバーに展開されているすべての LRS ルームに関する次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f303-111">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="8f303-112">**タグ**   管理者がルームに付与するカスタム名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8f303-112">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="8f303-113">タグは、ルーム名をクリックすることで、ポータルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="8f303-113">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="8f303-114">**[正常性**   ] 会議室の正常性の状態を示します。これは、会議室の設定ページの [正常性] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f303-114">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="8f303-115">**[次の会議**   ] 次の会議がスケジュールされた日時です。</span><span class="sxs-lookup"><span data-stu-id="8f303-115">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="8f303-116">**LRS Version, Manufacturer, Model**   これらの値は、LRS で事前に設定されています。</span><span class="sxs-lookup"><span data-stu-id="8f303-116">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="8f303-117">製造元によっては、これらのフィールドが空白のままになっている場合があります。</span><span class="sxs-lookup"><span data-stu-id="8f303-117">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="8f303-118">**最終更新**   web ページが最後に更新された日時が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f303-118">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="8f303-119">![Lync Room System 管理ポータルの概要ビュー](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System 管理ポータルの概要ビュー")</span><span class="sxs-lookup"><span data-stu-id="8f303-119">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="8f303-120">LRS ルーム情報</span><span class="sxs-lookup"><span data-stu-id="8f303-120">LRS Room Information</span></span>

<span data-ttu-id="8f303-121">ポータルの [Room Info] セクションでは、個々の LRS ルームを表示および構成できます。</span><span class="sxs-lookup"><span data-stu-id="8f303-121">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="8f303-122">これには、[設定]、[詳細]、[トラブルシューティング]、[正常性] の4つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="8f303-122">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="8f303-123">設定</span><span class="sxs-lookup"><span data-stu-id="8f303-123">Settings</span></span>

<span data-ttu-id="8f303-124">[設定] セクションでは、ルームのパスワード、会議室タグ、および既定の音量レベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8f303-124">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="8f303-125">これらの設定を構成すると、LRS コンソールを再起動した後にのみ変更がレプリケートされます。</span><span class="sxs-lookup"><span data-stu-id="8f303-125">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="8f303-126">Lync Room システムでは、バージョン15.12 以降のシステム更新設定のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f303-126">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="8f303-127">![Lync Room System 管理ポータルルームの設定](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System 管理ポータルルームの設定")</span><span class="sxs-lookup"><span data-stu-id="8f303-127">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="8f303-128">詳細</span><span class="sxs-lookup"><span data-stu-id="8f303-128">Details</span></span>

<span data-ttu-id="8f303-129">[詳細] セクションには、LRS ルームの設定の読み取り専用の概要が表示されます。これには、最終更新日時が含まれます。次の会議。最終更新、メンテナンス、調整、既定のスピーカー、マイク、および着信音の設定。4.0SIP URI。画面の数と各画面の詳細。状態、およびアクティビティ。</span><span class="sxs-lookup"><span data-stu-id="8f303-129">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="8f303-130">![Lync Room System 管理ポータル詳細ビュー](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System 管理ポータル詳細ビュー")</span><span class="sxs-lookup"><span data-stu-id="8f303-130">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="8f303-131">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8f303-131">Troubleshooting</span></span>

<span data-ttu-id="8f303-132">トラブルシューティングのセクションは、ログをリモートで収集し、指定した場所に保存するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f303-132">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="8f303-133">LRS コンソール (LRS ユーザーインターフェイス) を再起動したり、システム全体を再起動したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8f303-133">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="8f303-134">ログを収集するには、指定された形式のフォルダーパスを指定し、LRS コンピューターアカウントに指定された書き込み権限がフォルダーにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8f303-134">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="8f303-135">ログサイズが大きすぎる場合は、ログの収集が完了するまでに最大5分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8f303-135">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="8f303-136">ページを更新すると、最新の状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f303-136">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="8f303-137">![Lync Room System 管理ポータルルームのログ記録](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System 管理ポータルルームのログ記録")</span><span class="sxs-lookup"><span data-stu-id="8f303-137">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="8f303-138">正常性</span><span class="sxs-lookup"><span data-stu-id="8f303-138">Health</span></span>

<span data-ttu-id="8f303-139">[正常性] セクションは、Lync Server の接続、オーディオデバイス、ビデオデバイス、復元状態、および画面デバイスの正常性を視覚的に示します。</span><span class="sxs-lookup"><span data-stu-id="8f303-139">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="8f303-140">![Lync Room System 管理ポータルルームの正常性](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System 管理ポータルルームの正常性")</span><span class="sxs-lookup"><span data-stu-id="8f303-140">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="8f303-141">管理 Web ポータルに関するその他の注意事項</span><span class="sxs-lookup"><span data-stu-id="8f303-141">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="8f303-142">設定変更は、LRS システムが再起動された後にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="8f303-142">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="8f303-143">LRSApp アカウントのパスワードが期限切れになると、ルームの状態を表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="8f303-143">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="8f303-144">LRSAppuser アカウントのパスワードを有効期限切れにならないように構成するか、有効期限が近づいたときにパスワードを更新してください。</span><span class="sxs-lookup"><span data-stu-id="8f303-144">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="8f303-145">LRS 管理 web ポータルは、オンプレミスの展開でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8f303-145">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="8f303-146">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="8f303-146">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="8f303-147">管理 web ポータルにサインインできないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="8f303-147">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="8f303-148">を開くhttps://localhost/lrsと、サインインページを表示できるようになりますが、サインイン情報を入力するときにサインインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8f303-148">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="8f303-149">この場合は、を開いhttps://FQDNofFEserver/lrsて、管理 web ポータルにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f303-149">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="8f303-150">管理 web ポータルにアクセスするコンピューターがワークグループ内にある場合、"http://" は機能しません。</span><span class="sxs-lookup"><span data-stu-id="8f303-150">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="8f303-151">代わりに "https" を使用します。</span><span class="sxs-lookup"><span data-stu-id="8f303-151">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="8f303-152">管理 web ポータルで LRS が表示されないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="8f303-152">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="8f303-153">展開に LRS アカウントがあること、および LRS 管理 Web ポータルの展開に関する推奨事項に従って作成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8f303-153">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="8f303-154">Lync server で、LRS アカウントが、[有効-CsUser] ではなく [Enable-Csの会議室] を使用してプロビジョニングされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8f303-154">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="8f303-155">LRS アカウントを作成済みで、管理 web ポータルにアカウントが表示されていない場合は、「Lync Server Logging tool を使用して**会議ポータル**コンポーネントを選択して、サーバーログを収集し、それらを LRS サポート連絡先に送信します。</span><span class="sxs-lookup"><span data-stu-id="8f303-155">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="8f303-156">管理 web ポータルで LRS の状態を確認できないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="8f303-156">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="8f303-157">LRSApp ユーザーアカウントの SIP が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8f303-157">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="8f303-158">それでも問題が解決しない場合は、D:\\Tracing\\lrsadminlogs\\から LRS システムの**TRACE .log**ファイルを収集し、LRS サポート連絡先に送信します。</span><span class="sxs-lookup"><span data-stu-id="8f303-158">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

