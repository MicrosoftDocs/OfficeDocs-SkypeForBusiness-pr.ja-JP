---
title: ダイヤルイン会議の暗証番号 (PIN) ルールを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aef41f14b37d2a21fa747bb14132bd6e9ba93ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="b09bc-102">Lync Server 2013 でダイヤルイン会議の暗証番号 (PIN) ルールを構成する</span><span class="sxs-lookup"><span data-stu-id="b09bc-102">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b09bc-103">_**最終更新日:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="b09bc-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="b09bc-104">組織内の Active Directory ドメインサービス (AD DS) の資格情報を持つ Lync Server 2013 ユーザーは、暗証番号 (PIN) を使って、認証されたユーザーとしてダイヤルイン会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="b09bc-104">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="b09bc-105">PIN ポリシーは、ダイヤルイン会議 PIN がどのように機能するかについてのルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="b09bc-105">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="b09bc-106">特定のポリシーをサイトまたは特定のユーザー グループに適用する場合は、新しい PIN ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b09bc-106">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span> <span data-ttu-id="b09bc-107">組織全体で同じ PIN ポリシーを使用する場合は、グローバル PIN ポリシーを使用でき、必要に応じて変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="b09bc-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="b09bc-108">PIN ポリシーは、最も狭いスコープから最も広いスコープまでのどのスコープでも、ユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b09bc-108">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="b09bc-109">ユーザーレベルの PIN ポリシーをユーザーに割り当てると、それらの設定は優先権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="b09bc-109">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="b09bc-110">ユーザー ポリシーを割り当てない場合は、サイトレベルの PIN ポリシーがあれば、そのポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="b09bc-110">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="b09bc-111">ユーザー ポリシーもサイト ポリシーも適用されていない場合は、グローバル PIN ポリシーが既定の設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="b09bc-111">If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b09bc-112">このセクション中</span><span class="sxs-lookup"><span data-stu-id="b09bc-112">In This Section</span></span>

  - [<span data-ttu-id="b09bc-113">Lync Server 2013 での既定のダイヤルイン会議の PIN 設定の変更</span><span class="sxs-lookup"><span data-stu-id="b09bc-113">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="b09bc-114">サイトまたはユーザーのグループ向けに Lync Server 2013 でダイヤルイン会議の PIN 設定を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="b09bc-114">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="b09bc-115">Lync Server 2013 でサイトまたはユーザーのグループのダイヤルイン会議の PIN 設定を削除する</span><span class="sxs-lookup"><span data-stu-id="b09bc-115">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

