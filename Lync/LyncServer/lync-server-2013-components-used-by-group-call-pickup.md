---
title: 'Lync Server 2013: グループ通話ピックアップで使用されるコンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e868ecc20dcafbb5da12c91deb26a91f4efacb2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="00c58-102">Lync Server 2013 のグループ通話ピックアップで使用されるコンポーネント</span><span class="sxs-lookup"><span data-stu-id="00c58-102">Components used by Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00c58-103">_**トピックの最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="00c58-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="00c58-104">グループ通話ピックアップは、エンタープライズ Voip およびコールパークアプリケーションを展開するときに自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="00c58-104">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="00c58-105">グループ通話ピックアップを有効にするには、通話ピックアップグループ番号として指定された別の番号の範囲を使用してコールパークオービットテーブルを構成し、ユーザーを割り当ててグループ通話ピックアップのユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="00c58-105">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span> <span data-ttu-id="00c58-106">グループ通話ピックアップをサポートする Lync Server コンポーネントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="00c58-106">The following Lync Server components support Group Call Pickup:</span></span>

  - <span data-ttu-id="00c58-107">**Application service**   アプリケーションサービスは、コールパークアプリケーションなどの統合コミュニケーションアプリケーションを展開、ホスト、および管理するためのプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="00c58-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="00c58-108">アプリケーションサービスは、フロントエンドプール内のすべてのフロントエンドサーバーとすべての Standard Edition サーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="00c58-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="00c58-109">**コールパークアプリケーション**   コールパークアプリケーションは、アプリケーションサービスによってホストされている統合コミュニケーションアプリケーションの1つです。</span><span class="sxs-lookup"><span data-stu-id="00c58-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="00c58-110">グループ通話ピックアップは、コールパークアプリケーションに基づいています。</span><span class="sxs-lookup"><span data-stu-id="00c58-110">Group Call Pickup is based on the Call Park application.</span></span>

  - <span data-ttu-id="00c58-111">**Lync server 管理シェル**   lync server 管理シェルを使用して、グループ通話ピックアップグループを管理します。</span><span class="sxs-lookup"><span data-stu-id="00c58-111">**Lync Server Management Shell**   You use Lync Server Management Shell to manage Group Call Pickup groups.</span></span>

  - <span data-ttu-id="00c58-112">**SEFAUtil resource kit tool**   セカンダリ拡張機能のアクティブ化ユーティリティ (SEFAUtil) を使用して、ユーザーを通話ピックアップグループに割り当て、ユーザーの通話ピックアップを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="00c58-112">**SEFAUtil resource kit tool**   You use the secondary extension feature activation utility (SEFAUtil) to assign users to a call pickup group and to enable or disable call pickup for users.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

