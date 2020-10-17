---
title: 'Lync Server 2013: 会議ポリシー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing policies
ms:assetid: 8f92eb7c-ee66-4df6-a726-4bff93b122cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688133(v=OCS.15)
ms:contentKeyID: 49733732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 681dbf0d6786656afcee12120e1b26d95bee41df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502304"
---
# <a name="conferencing-policies-in-lync-server-2013"></a><span data-ttu-id="82f2f-102">Lync Server 2013 の会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="82f2f-102">Conferencing policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82f2f-103">_**トピックの最終更新日:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="82f2f-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="82f2f-p101">会議ポリシーにより、会議 (ミーティングとも呼ばれます) でユーザーが使用できる機能が定義されます。 会議ポリシー設定には、会議に IP オーディオと IP ビデオを組み込むことができるかどうかということから、出席可能な最大参加者数に至るまでの、さまざまなスケジューリングおよび参加オプションが含まれます。 管理者は、会議ポリシーを使用して、セキュリティ、帯域幅、および会議の法的側面を管理できます。</span><span class="sxs-lookup"><span data-stu-id="82f2f-p101">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting). Conferencing policy settings encompass a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend. Administrators can use conferencing policy to manage security, bandwidth, and legal aspects of meetings.</span></span>

<span data-ttu-id="82f2f-p102">会議ポリシーは、グローバル スコープ、サイト スコープ、およびユーザー スコープの 3 つのレベルで定義できます。 設定の対象になるのは、最も狭いスコープから最も広いスコープまでのどのスコープでも、特定のユーザーです。 ユーザー ポリシーをユーザーに割り当てると、それらの設定は優先権を持ちます。 ユーザー ポリシーを割り当てていない場合は、サイト設定が適用されます。 ユーザー ポリシーもサイト ポリシーも適用されていない場合は、グローバル ポリシーが既定の設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="82f2f-p102">You can define conferencing policy on three levels: global scope, site scope, and user scope. Settings apply to a specific user from the narrowest scope to the widest scope. If you assign a user policy to a user, those settings take precedence. If you do not assign a user policy, site settings apply. If no user or site policies apply, global policy provides the default settings.</span></span>

<span data-ttu-id="82f2f-p103">グローバル ポリシーは既定として存在するため、新しいグローバル ポリシーを作成することはできません。 また、既存のグローバル ポリシーを削除することはできませんが、既存のグローバル ポリシーを変更して既定の設定をカスタマイズすることはできます。</span><span class="sxs-lookup"><span data-stu-id="82f2f-p103">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="82f2f-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="82f2f-114">In This Section</span></span>

  - [<span data-ttu-id="82f2f-115">Lync Server 2013 での会議ポリシー情報の表示</span><span class="sxs-lookup"><span data-stu-id="82f2f-115">View conferencing policy information in Lync Server 2013</span></span>](lync-server-2013-view-conferencing-policy-information.md)

  - [<span data-ttu-id="82f2f-116">Lync Server 2013 での会議ポリシーの作成または変更</span><span class="sxs-lookup"><span data-stu-id="82f2f-116">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)

  - [<span data-ttu-id="82f2f-117">Lync Server 2013 で既存の会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="82f2f-117">Delete an existing conferencing policy in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-conferencing-policy.md)

  - [<span data-ttu-id="82f2f-118">Lync Server 2013 の会議ポリシー設定のリファレンス</span><span class="sxs-lookup"><span data-stu-id="82f2f-118">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

