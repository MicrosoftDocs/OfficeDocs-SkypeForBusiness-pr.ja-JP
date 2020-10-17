---
title: 'Lync Server 2013: エンタープライズ Voip のユーザーの無効化'
description: 'Lync Server 2013: エンタープライズ Voip に対してユーザーを無効にします。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d99916444e2b1c984e251f6e6289d88e31a538a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568213"
---
# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="29ab7-103">Lync Server 2013 でのエンタープライズ Voip のユーザーの無効化</span><span class="sxs-lookup"><span data-stu-id="29ab7-103">Disable a user for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29ab7-104">_**トピックの最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="29ab7-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="29ab7-105">Lync Server 2013 に対して有効になっているユーザーアカウントのエンタープライズ Voip を無効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="29ab7-105">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Lync Server 2013.</span></span>

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="29ab7-106">エンタープライズ Voip のユーザーアカウントを無効にするには</span><span class="sxs-lookup"><span data-stu-id="29ab7-106">To disable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="29ab7-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="29ab7-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="29ab7-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="29ab7-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="29ab7-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29ab7-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="29ab7-110">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29ab7-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="29ab7-111">**[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29ab7-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="29ab7-112">表で、エンタープライズ Voip を有効にするユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="29ab7-112">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="29ab7-113">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29ab7-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="29ab7-114">[**Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ VoIP**] 以外のオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="29ab7-114">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="29ab7-115">ユーザーが Lync を使用して音声またはビデオ通話を行うことを制限するには、[ <STRONG>テレフォニー</STRONG>] で [ <STRONG>音声ビデオを無効</STRONG>にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29ab7-115">To restrict a user from making audio or video calls by using Lync, under <STRONG>Telephony</STRONG>, click <STRONG>Audio/video disabled</STRONG>.</span></span>

    
    </div>

8.  <span data-ttu-id="29ab7-116">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29ab7-116">Click **Commit**.</span></span>

<span data-ttu-id="29ab7-117">これで、ユーザーはエンタープライズ Voip 機能を使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="29ab7-117">The user is now unable to use the Enterprise Voice feature.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29ab7-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="29ab7-118">See Also</span></span>


[<span data-ttu-id="29ab7-119">Lync Server 2013 のエンタープライズ Voip でユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="29ab7-119">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  


[<span data-ttu-id="29ab7-120">Lync Server 2013 でのユーザーのエンタープライズ Voip の管理</span><span class="sxs-lookup"><span data-stu-id="29ab7-120">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)  
[<span data-ttu-id="29ab7-121">Lync Server 2013 管理シェル</span><span class="sxs-lookup"><span data-stu-id="29ab7-121">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

