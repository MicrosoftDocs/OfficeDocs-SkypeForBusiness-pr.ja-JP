---
title: 'Lync Server 2013: グループ通話ピックアップの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Group Call Pickup
ms:assetid: b4b0a9a0-91c6-43a5-9e2b-a086caeb3f94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945645(v=OCS.15)
ms:contentKeyID: 51541505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef62fc903e70c0ff60cd86d124fbd092d9b394c1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="2badc-102">Lync Server 2013 でグループ通話ピックアップを構成する</span><span class="sxs-lookup"><span data-stu-id="2badc-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2badc-103">_**トピックの最終更新日:** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="2badc-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="2badc-104">Lync Server 2013 の累積的な更新プログラム: 2 月2013は、新しいエンタープライズ Voip 機能としてグループ通話ピックアップを導入しました。</span><span class="sxs-lookup"><span data-stu-id="2badc-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="2badc-105">グループ通話ピックアップでは、通話ピックアップグループ番号をダイヤルすることによって、他のユーザーに対して着信する通話を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2badc-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="2badc-106">エンタープライズ Voip を展開するときに、グループ通話ピックアップが使用するコンポーネントは、フロントエンドサーバーまたは Standard Edition サーバーに自動的にインストールされ、有効になります。</span><span class="sxs-lookup"><span data-stu-id="2badc-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="2badc-107">ただし、ユーザーが使用できるようにするには、グループ通話ピックアップを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2badc-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="2badc-108">このセクションでは、グループ通話ピックアップの構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="2badc-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2badc-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2badc-109">In This Section</span></span>

[<span data-ttu-id="2badc-110">Lync Server 2013 でのグループ通話ピックアップ構成の前提条件とユーザー権限</span><span class="sxs-lookup"><span data-stu-id="2badc-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="2badc-111">Lync Server 2013 でのグループ通話ピックアップの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="2badc-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="2badc-112">SEFAUtil ツールを Lync Server 2013 に展開する</span><span class="sxs-lookup"><span data-stu-id="2badc-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="2badc-113">Lync Server 2013 での通話ピックアップグループ番号の構成</span><span class="sxs-lookup"><span data-stu-id="2badc-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="2badc-114">Lync Server 2013 のユーザーのグループ通話ピックアップを有効にし、グループ番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="2badc-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="2badc-115">グループ通話ピックアップの割り当てを Lync Server 2013 のユーザーに伝達する</span><span class="sxs-lookup"><span data-stu-id="2badc-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="2badc-116">オプションLync Server 2013 でのグループ通話ピックアップの展開の確認</span><span class="sxs-lookup"><span data-stu-id="2badc-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

