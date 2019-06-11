---
title: 'Lync Server 2013: 会議ポリシー'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing policies
ms:assetid: 8f92eb7c-ee66-4df6-a726-4bff93b122cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688133(v=OCS.15)
ms:contentKeyID: 49733732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b60b521c69b821dacfe8bd569a6300b4c21e0287
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-policies-in-lync-server-2013"></a><span data-ttu-id="ecc62-102">Lync Server 2013 の会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="ecc62-102">Conferencing policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecc62-103">_**最終更新日:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="ecc62-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="ecc62-104">会議ポリシーは、会議中にユーザーが利用できる機能 (会議とも呼ばれます) を定義します。</span><span class="sxs-lookup"><span data-stu-id="ecc62-104">Conferencing policy defines the features and capabilities that users have available during a conference (also known as a meeting).</span></span> <span data-ttu-id="ecc62-105">電話会議ポリシー設定には、会議に IP オーディオと IP ビデオを組み込むことができるかどうかということから、出席可能な最大参加者数に至るまでの、さまざまなスケジューリングおよび参加オプションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ecc62-105">Conferencing policy settings encompass a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="ecc62-106">管理者は会議ポリシーを使って、会議のセキュリティ、帯域幅、および法的情報を管理できます。</span><span class="sxs-lookup"><span data-stu-id="ecc62-106">Administrators can use conferencing policy to manage security, bandwidth, and legal aspects of meetings.</span></span>

<span data-ttu-id="ecc62-107">電話会議ポリシーは、グローバル スコープ、サイト スコープ、およびユーザー スコープの 3 つのレベルで定義できます。</span><span class="sxs-lookup"><span data-stu-id="ecc62-107">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="ecc62-108">設定の対象になるのは、最も狭いスコープから最も広いスコープまでのどのスコープでも、特定のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="ecc62-108">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="ecc62-109">ユーザーポリシーをユーザーに割り当てると、それらの設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="ecc62-109">If you assign a user policy to a user, those settings take precedence.</span></span> <span data-ttu-id="ecc62-110">ユーザー ポリシーを割り当てていない場合は、サイト設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ecc62-110">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="ecc62-111">ユーザー ポリシーもサイト ポリシーも適用されていない場合は、グローバル ポリシーが既定の設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="ecc62-111">If no user or site policies apply, global policy provides the default settings.</span></span>

<span data-ttu-id="ecc62-112">グローバル ポリシーは既定として存在するため、新しいグローバル ポリシーを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="ecc62-112">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="ecc62-113">また、既存のグローバル ポリシーを削除することはできませんが、既存のグローバル ポリシーを変更して既定の設定をカスタマイズすることはできます。</span><span class="sxs-lookup"><span data-stu-id="ecc62-113">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ecc62-114">このセクション中</span><span class="sxs-lookup"><span data-stu-id="ecc62-114">In This Section</span></span>

  - [<span data-ttu-id="ecc62-115">Lync Server 2013 で会議のポリシー情報を表示する</span><span class="sxs-lookup"><span data-stu-id="ecc62-115">View conferencing policy information in Lync Server 2013</span></span>](lync-server-2013-view-conferencing-policy-information.md)

  - [<span data-ttu-id="ecc62-116">Lync Server 2013 で会議ポリシーを作成または変更する</span><span class="sxs-lookup"><span data-stu-id="ecc62-116">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)

  - [<span data-ttu-id="ecc62-117">Lync Server 2013 で既存の会議ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="ecc62-117">Delete an existing conferencing policy in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-conferencing-policy.md)

  - [<span data-ttu-id="ecc62-118">Lync Server 2013 の会議ポリシー設定リファレンス</span><span class="sxs-lookup"><span data-stu-id="ecc62-118">Conferencing policy settings reference for Lync Server 2013</span></span>](lync-server-2013-conferencing-policy-settings-reference.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

