---
title: 'Lync Server 2013: 統合連絡先ストアの展開'
description: 'Lync Server 2013: 統合連絡先ストアの展開。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 056792d2e4ea66699b276d0d571e83c8a0256483
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557753"
---
# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="ff313-103">Lync Server 2013 での統合連絡先ストアの展開</span><span class="sxs-lookup"><span data-stu-id="ff313-103">Deploying unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff313-104">_**トピックの最終更新日:** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="ff313-104">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="ff313-105">Lync Server 2013 での統合連絡先ストアの有効化では、トポロジ設定は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ff313-105">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="ff313-106">ユーザーに対して統合連絡先ストアを有効にするためには、次のことが必要です。</span><span class="sxs-lookup"><span data-stu-id="ff313-106">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="ff313-107">統合連絡先ストア ポリシーが有効であること (既定では有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="ff313-107">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="ff313-108">ユーザーが Lync 2013 を使用して少なくとも1回ログインします。</span><span class="sxs-lookup"><span data-stu-id="ff313-108">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="ff313-109">ユーザーの連絡先が移行され、ユーザーが Lync 2013 を使用してログインすると、ユーザーは lync 2013、Outlook 2013、または Outlook Web Access から Lync の連絡先にアクセスして管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ff313-109">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="ff313-110">ユーザーは、Outlook または Outlook Web Access から連絡先を管理するために Lync にログインする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ff313-110">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ff313-111">ユーザーが移行後に Lync 2010 からログインした場合、連絡先とグループは利用できますが、ユーザーはその連絡先を管理 (追加、削除、移動、タグ付け、タグの削除、または変更) できません。</span><span class="sxs-lookup"><span data-stu-id="ff313-111">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ff313-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ff313-112">In This Section</span></span>

  - [<span data-ttu-id="ff313-113">Lync Server 2013 で統合連絡先ストアに対してユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="ff313-113">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="ff313-114">Lync Server 2013 でユーザーを統合連絡先ストアに移行する</span><span class="sxs-lookup"><span data-stu-id="ff313-114">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="ff313-115">Lync Server 2013 で移行されたユーザーのロールバック</span><span class="sxs-lookup"><span data-stu-id="ff313-115">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

