---
title: 'Lync Server 2013: 統合連絡先ストアへのユーザーの移行'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd0ec64192f1aa83eb9c076976c20a9e87ab9115
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="fc06d-102">Lync Server 2013 での統合連絡先ストアへのユーザーの移行</span><span class="sxs-lookup"><span data-stu-id="fc06d-102">Migrate users to unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc06d-103">_**最終更新日:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="fc06d-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="fc06d-104">ユーザーの連絡先は、ユーザーが次のように Exchange 2013 サーバーに自動的に移行されます。</span><span class="sxs-lookup"><span data-stu-id="fc06d-104">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>

  - <span data-ttu-id="fc06d-105">UcsAllowed が True に設定されたユーザー サービス ポリシーがユーザーに割り当てられている場合。</span><span class="sxs-lookup"><span data-stu-id="fc06d-105">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>

  - <span data-ttu-id="fc06d-106">は Exchange 2013 メールボックスでプロビジョニングされ、少なくとも1回はメールボックスにサインインしています。</span><span class="sxs-lookup"><span data-stu-id="fc06d-106">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>

  - <span data-ttu-id="fc06d-107">Lync 2013 リッチクライアントを使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="fc06d-107">Logs in by using a Lync 2013 rich client.</span></span>

<span data-ttu-id="fc06d-108">ユーザーが Lync 2010 以前のクライアントでログインしている場合、またはユーザーが Exchange 2013 サーバーに接続されていない場合、ユーザーサービスポリシーは無視され、ユーザーの連絡先は Lync Server に残ります。</span><span class="sxs-lookup"><span data-stu-id="fc06d-108">If the user logs in with a Lync 2010 or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Lync Server.</span></span>

<span data-ttu-id="fc06d-109">ユーザーの連絡先が移行されているかどうかは、次のいずれかの方法で確認できます。</span><span class="sxs-lookup"><span data-stu-id="fc06d-109">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span>

  - <span data-ttu-id="fc06d-110">クライアント コンピューターで次のレジストリ キーを調べます。</span><span class="sxs-lookup"><span data-stu-id="fc06d-110">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="fc06d-111">HKEY\_現在\_の\\ユーザー\\ソフトウェア\\Microsoft\\Office\\15.0\\\<Lync SIP\>\\URL UCS</span><span class="sxs-lookup"><span data-stu-id="fc06d-111">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span></span>
    
    <span data-ttu-id="fc06d-112">ユーザーの連絡先が Exchange 2013 に保存されている場合、このキーには2165の値を持つ InUCSMode の値が格納されます。</span><span class="sxs-lookup"><span data-stu-id="fc06d-112">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>

  - <span data-ttu-id="fc06d-113">**Test-CsUnifiedContactStore** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fc06d-113">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="fc06d-114">Lync Server 管理シェルコマンドラインで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fc06d-114">At the Lync Server Management Shell command line, type:</span></span>
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="fc06d-115">**Test-CsUnifiedContactStore** が成功した場合は、ユーザーの連絡先が統合連絡先ストアに移行されています。</span><span class="sxs-lookup"><span data-stu-id="fc06d-115">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

