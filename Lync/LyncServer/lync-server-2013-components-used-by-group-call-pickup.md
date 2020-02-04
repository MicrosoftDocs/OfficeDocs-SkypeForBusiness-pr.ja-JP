---
title: 'Lync Server 2013: グループ通話のピックアップで使用されるコンポーネント'
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
ms.openlocfilehash: 7b9c810d5835d113a26bd3a15295f75a71552590
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="700bc-102">Lync Server 2013 でグループ通話のピックアップによって使用されるコンポーネント</span><span class="sxs-lookup"><span data-stu-id="700bc-102">Components used by Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="700bc-103">_**最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="700bc-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="700bc-104">グループ通話のピックアップは、エンタープライズボイスと Call パークアプリケーションを展開したときに自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="700bc-104">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="700bc-105">グループ通話のピックアップを有効にするには、通話ピックアップグループ番号として指定された別の範囲の番号を使用して、ユーザーをピックアップグループに発信し、グループ通話のピックアップを許可するようにユーザーを割り当てることで、グループ通話のピックアップを有効にします。</span><span class="sxs-lookup"><span data-stu-id="700bc-105">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span> <span data-ttu-id="700bc-106">グループ通話のピックアップは、次の Lync Server コンポーネントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="700bc-106">The following Lync Server components support Group Call Pickup:</span></span>

  - <span data-ttu-id="700bc-107">**アプリケーションサービス**   アプリケーションサービスは、コールパークアプリケーションなどのユニファイドコミュニケーションアプリケーションを展開、ホスティング、および管理するためのプラットフォームを提供します。</span><span class="sxs-lookup"><span data-stu-id="700bc-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="700bc-108">アプリケーションサービスは、フロントエンドプールのすべてのフロントエンドサーバーと、すべての Standard Edition サーバーに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="700bc-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="700bc-109">**コールパーク**   アプリケーションは、アプリケーションサービスによってホストされるユニファイドコミュニケーションアプリケーションの1つです。</span><span class="sxs-lookup"><span data-stu-id="700bc-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="700bc-110">グループ通話のピックアップは、コールパークアプリケーションに基づいています。</span><span class="sxs-lookup"><span data-stu-id="700bc-110">Group Call Pickup is based on the Call Park application.</span></span>

  - <span data-ttu-id="700bc-111">**Lync server 管理**   シェル lync server 管理シェルを使ってグループ通話のピックアップグループを管理します。</span><span class="sxs-lookup"><span data-stu-id="700bc-111">**Lync Server Management Shell**   You use Lync Server Management Shell to manage Group Call Pickup groups.</span></span>

  - <span data-ttu-id="700bc-112">**SEFAUtil リソースキットツール**   セカンダリ拡張機能のアクティブ化ユーティリティ (SEFAUtil) を使って、ユーザーを通話ピックアップグループに割り当て、ユーザーに対して通話集配を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="700bc-112">**SEFAUtil resource kit tool**   You use the secondary extension feature activation utility (SEFAUtil) to assign users to a call pickup group and to enable or disable call pickup for users.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

