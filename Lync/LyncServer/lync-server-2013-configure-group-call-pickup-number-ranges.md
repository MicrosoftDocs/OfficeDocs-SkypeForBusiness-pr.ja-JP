---
title: 'Lync Server 2013: グループ通話ピックアップ番号の範囲の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Group Call Pickup number ranges
ms:assetid: f15f75f6-f965-4558-b612-f40cecdd5d8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945657(v=OCS.15)
ms:contentKeyID: 51541529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d63ec2dcd4190be810d6296ffdafe58759efb68
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507684"
---
# <a name="configure-group-call-pickup-number-ranges-in-lync-server-2013"></a><span data-ttu-id="35b5f-102">Lync Server 2013 でグループ通話ピックアップ番号の範囲を構成する</span><span class="sxs-lookup"><span data-stu-id="35b5f-102">Configure Group Call Pickup number ranges in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35b5f-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="35b5f-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="35b5f-104">グループ通話ピックアップは、コールパークアプリケーションに基づいています。</span><span class="sxs-lookup"><span data-stu-id="35b5f-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="35b5f-105">グループ通話ピックアップを展開する場合は、通話ピックアップグループ番号として指定された電話番号の範囲をコールパークオービットテーブルに設定します。</span><span class="sxs-lookup"><span data-stu-id="35b5f-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="35b5f-106">これらのグループ番号は、ユーザーが別のユーザーの通話を取得するためにダイヤルする番号です。</span><span class="sxs-lookup"><span data-stu-id="35b5f-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="35b5f-107">コールパークオービット番号と同様に、通話ピックアップグループ番号は、ユーザーまたは電話が割り当てられていない仮想内線である必要があります。</span><span class="sxs-lookup"><span data-stu-id="35b5f-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="35b5f-108">グループ通話ピックアップを展開する各フロントエンドプールには、1つまたは複数の通話ピックアップグループ番号範囲を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="35b5f-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="35b5f-109">グループ番号の範囲は、Lync Server 展開間でグローバルに一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="35b5f-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="35b5f-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="35b5f-110">In This Section</span></span>

  - [<span data-ttu-id="35b5f-111">Lync Server 2013 でグループ通話ピックアップ番号の範囲を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="35b5f-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

  - [<span data-ttu-id="35b5f-112">Lync Server 2013 でグループ通話ピックアップ番号の範囲を削除する</span><span class="sxs-lookup"><span data-stu-id="35b5f-112">Delete a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-delete-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

