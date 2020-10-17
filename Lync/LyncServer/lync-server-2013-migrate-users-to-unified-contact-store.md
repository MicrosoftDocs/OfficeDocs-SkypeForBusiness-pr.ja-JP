---
title: 'Lync Server 2013: ユーザーを統合連絡先ストアに移行する'
description: 'Lync Server 2013: ユーザーを統合連絡先ストアに移行します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e9ee9850cc723ae132f15d7c0c6b3769e1240ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568593"
---
# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="d0110-103">Lync Server 2013 でユーザーを統合連絡先ストアに移行する</span><span class="sxs-lookup"><span data-stu-id="d0110-103">Migrate users to unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0110-104">_**トピックの最終更新日:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="d0110-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="d0110-105">次の場合、ユーザーの連絡先は Exchange 2013 サーバーに自動的に移行されます。</span><span class="sxs-lookup"><span data-stu-id="d0110-105">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>

  - <span data-ttu-id="d0110-106">UcsAllowed が True に設定されたユーザー サービス ポリシーがユーザーに割り当てられている場合。</span><span class="sxs-lookup"><span data-stu-id="d0110-106">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>

  - <span data-ttu-id="d0110-107">Exchange 2013 メールボックスでプロビジョニングされ、少なくとも1回はメールボックスにサインインしています。</span><span class="sxs-lookup"><span data-stu-id="d0110-107">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>

  - <span data-ttu-id="d0110-108">Lync 2013 リッチクライアントを使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="d0110-108">Logs in by using a Lync 2013 rich client.</span></span>

<span data-ttu-id="d0110-109">ユーザーが Lync 2010 またはそれ以前のクライアントを使用してログインしている場合、またはユーザーが Exchange 2013 サーバーに接続されていない場合、ユーザーサービスポリシーは無視され、ユーザーの連絡先は Lync Server に残ります。</span><span class="sxs-lookup"><span data-stu-id="d0110-109">If the user logs in with a Lync 2010 or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Lync Server.</span></span>

<span data-ttu-id="d0110-110">ユーザーの連絡先が移行されているかどうかは、次のどちらかの方法で確認できます。</span><span class="sxs-lookup"><span data-stu-id="d0110-110">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span>

  - <span data-ttu-id="d0110-111">クライアント コンピューターで次のレジストリ キーを調べます。</span><span class="sxs-lookup"><span data-stu-id="d0110-111">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="d0110-112">HKEY \_ CURRENT \_ USER \\ Software \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ \<SIP URL\> \\ UCS</span><span class="sxs-lookup"><span data-stu-id="d0110-112">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span></span>
    
    <span data-ttu-id="d0110-113">ユーザーの連絡先が Exchange 2013 に格納されている場合、このキーには2165という値を持つ InUCSMode の値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0110-113">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>

  - <span data-ttu-id="d0110-114">**Test-CsUnifiedContactStore** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="d0110-114">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="d0110-115">Lync Server 管理シェルコマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d0110-115">At the Lync Server Management Shell command line, type:</span></span>
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="d0110-116">**Test-CsUnifiedContactStore** が成功した場合は、ユーザーの連絡先が統合連絡先ストアに移行されています。</span><span class="sxs-lookup"><span data-stu-id="d0110-116">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

