---
title: 'Lync Server 2013: エンタープライズ Voip のユーザーを無効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dabe378f07cbca263ba3b32257c310b01bd922c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="87e2b-102">Lync Server 2013 でエンタープライズ Voip のユーザーを無効にする</span><span class="sxs-lookup"><span data-stu-id="87e2b-102">Disable a user for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87e2b-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="87e2b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="87e2b-104">Lync Server 2013 用に有効になっているユーザーアカウントのエンタープライズボイスを無効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="87e2b-104">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Lync Server 2013.</span></span>

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="87e2b-105">エンタープライズ Voip のユーザーアカウントを無効にするには</span><span class="sxs-lookup"><span data-stu-id="87e2b-105">To disable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="87e2b-106">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="87e2b-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="87e2b-107">ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="87e2b-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="87e2b-108">Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="87e2b-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="87e2b-109">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87e2b-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="87e2b-110">[**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87e2b-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="87e2b-111">表で、エンタープライズ Voip を有効にするユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="87e2b-111">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="87e2b-112">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87e2b-112">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="87e2b-113">[ **Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ voip**] 以外のオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="87e2b-113">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="87e2b-114">ユーザーが Lync を使って音声またはビデオ通話を発信することを制限するには、[<STRONG>テレフォニー</STRONG>] で [<STRONG>オーディオ/ビデオを無効</STRONG>にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87e2b-114">To restrict a user from making audio or video calls by using Lync, under <STRONG>Telephony</STRONG>, click <STRONG>Audio/video disabled</STRONG>.</span></span>

    
    </div>

8.  <span data-ttu-id="87e2b-115">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87e2b-115">Click **Commit**.</span></span>

<span data-ttu-id="87e2b-116">これで、ユーザーはエンタープライズ Voip 機能を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="87e2b-116">The user is now unable to use the Enterprise Voice feature.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="87e2b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="87e2b-117">See Also</span></span>


[<span data-ttu-id="87e2b-118">Lync Server 2013 でのエンタープライズ Voip のユーザーの有効化</span><span class="sxs-lookup"><span data-stu-id="87e2b-118">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  


[<span data-ttu-id="87e2b-119">Lync Server 2013 でのユーザーのエンタープライズボイスの管理</span><span class="sxs-lookup"><span data-stu-id="87e2b-119">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)  
[<span data-ttu-id="87e2b-120">Lync Server 2013 管理シェル</span><span class="sxs-lookup"><span data-stu-id="87e2b-120">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

