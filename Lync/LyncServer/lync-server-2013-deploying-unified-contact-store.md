---
title: 'Lync Server 2013: 統合連絡先ストアの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94f4c52eb3adda31f32de410f139154788fa37e9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="7f677-102">Lync Server 2013 統合連絡先ストアの展開</span><span class="sxs-lookup"><span data-stu-id="7f677-102">Deploying unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f677-103">_**最終更新日:** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="7f677-103">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="7f677-104">Lync Server 2013 で統合連絡先ストアを有効にする場合、トポロジの設定は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7f677-104">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="7f677-105">ユーザーに対して統合連絡先ストアを有効にするには、次のことが必要です。</span><span class="sxs-lookup"><span data-stu-id="7f677-105">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="7f677-106">統合連絡先ストア ポリシーが有効であること (既定では有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="7f677-106">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="7f677-107">ユーザーは、少なくとも1回は Lync 2013 でログインします。</span><span class="sxs-lookup"><span data-stu-id="7f677-107">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="7f677-108">ユーザーが Lync 2013 を使ってログインしたときに自動的に実行されるユーザーの連絡先が移行された後、ユーザーは lync 2013、Outlook 2013、または Outlook Web Access から Lync の連絡先にアクセスして管理することができます。</span><span class="sxs-lookup"><span data-stu-id="7f677-108">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="7f677-109">ユーザーは、Outlook または Outlook Web Access から連絡先を管理するために Lync にログインする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7f677-109">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7f677-110">ユーザーが移行後に Lync 2010 からログインしている場合、連絡先とグループは最新の状態になっていますが、ユーザーはその連絡先を管理 (追加、削除、移動、タグ付け、解除、または変更) することはできません。</span><span class="sxs-lookup"><span data-stu-id="7f677-110">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7f677-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="7f677-111">In This Section</span></span>

  - [<span data-ttu-id="7f677-112">Lync Server 2013 の統合連絡先ストアでユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="7f677-112">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="7f677-113">Lync Server 2013 での統合連絡先ストアへのユーザーの移行</span><span class="sxs-lookup"><span data-stu-id="7f677-113">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="7f677-114">Lync Server 2013 での移行したユーザーのロールバック</span><span class="sxs-lookup"><span data-stu-id="7f677-114">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

