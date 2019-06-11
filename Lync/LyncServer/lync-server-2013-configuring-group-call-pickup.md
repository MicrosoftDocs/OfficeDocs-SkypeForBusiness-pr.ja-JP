---
title: 'Lync Server 2013: グループ通話のピックアップの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Group Call Pickup
ms:assetid: b4b0a9a0-91c6-43a5-9e2b-a086caeb3f94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945645(v=OCS.15)
ms:contentKeyID: 51541505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d7f82d976d3e6e2594cecafe5634edfe0b52841
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="c6b2f-102">Lync Server 2013 でグループ通話のピックアップを構成する</span><span class="sxs-lookup"><span data-stu-id="c6b2f-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6b2f-103">_**最終更新日:** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="c6b2f-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="c6b2f-104">Lync Server 2013 の累積更新プログラム: 2013 年2月に、グループ通話のピックアップが新しいエンタープライズ Voip 機能として導入されています。</span><span class="sxs-lookup"><span data-stu-id="c6b2f-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="c6b2f-105">グループ通話のピックアップにより、ユーザーは、通話ピックアップグループ番号にダイヤルすることによって、他のユーザーが着信した通話を受け取れるようになります。</span><span class="sxs-lookup"><span data-stu-id="c6b2f-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="c6b2f-106">グループ通話のピックアップで使用されるコンポーネントは、エンタープライズボイスの展開時に、フロントエンドサーバーまたは Standard Edition サーバーに自動的にインストールされ、有効になります。</span><span class="sxs-lookup"><span data-stu-id="c6b2f-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="c6b2f-107">ただし、グループ通話のピックアップは、ユーザーが利用できるようになる前に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6b2f-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="c6b2f-108">このセクションでは、グループ通話のピックアップの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="c6b2f-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c6b2f-109">このセクション中</span><span class="sxs-lookup"><span data-stu-id="c6b2f-109">In This Section</span></span>

[<span data-ttu-id="c6b2f-110">グループ通話の集配構成の前提条件とユーザー権限 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6b2f-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="c6b2f-111">Lync Server 2013 でのグループ通話のピックアップの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="c6b2f-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="c6b2f-112">Deploy the SEFAUtil tool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6b2f-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="c6b2f-113">Lync Server 2013 での通話ピックアップグループ番号の設定</span><span class="sxs-lookup"><span data-stu-id="c6b2f-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="c6b2f-114">Lync Server 2013 のユーザーに対してグループ通話のピックアップを有効にし、グループ番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="c6b2f-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="c6b2f-115">グループ通話の集配の課題を Lync Server 2013 のユーザーに伝える</span><span class="sxs-lookup"><span data-stu-id="c6b2f-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="c6b2f-116">省略Lync Server 2013 でグループ通話のピックアップの展開を確認する</span><span class="sxs-lookup"><span data-stu-id="c6b2f-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

