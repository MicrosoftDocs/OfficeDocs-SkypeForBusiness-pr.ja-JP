---
title: ダイヤルイン会議の暗証番号 (PIN) ルールを構成する
description: ダイヤルイン会議の暗証番号 (PIN) ルールを構成します。
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
ms.openlocfilehash: 799092ba57e9a85cd196840fc81c1f46b96e9900
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565053"
---
# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="3df91-103">Lync Server 2013 でダイヤルイン会議の暗証番号 (PIN) ルールを構成する</span><span class="sxs-lookup"><span data-stu-id="3df91-103">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3df91-104">_**トピックの最終更新日:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="3df91-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="3df91-105">Lync Server 2013 組織内の Active Directory ドメインサービス (AD DS) の資格情報を持つユーザーは、個人識別番号 (PIN) を使用して、認証されたユーザーとしてダイヤルイン会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="3df91-105">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="3df91-106">PIN ポリシーは、ダイヤルイン会議の Pin の動作規則を定義します。</span><span class="sxs-lookup"><span data-stu-id="3df91-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="3df91-107">特定のポリシーをサイトまたは特定のユーザーグループに適用する場合は、新しい PIN ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3df91-107">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span> <span data-ttu-id="3df91-108">組織全体で同じ PIN ポリシーを使用する場合は、グローバル PIN ポリシーを使用して、必要に応じて変更することができます。</span><span class="sxs-lookup"><span data-stu-id="3df91-108">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="3df91-109">PIN ポリシーは、最も狭いスコープから最も広いスコープへのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3df91-109">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="3df91-110">ユーザーレベルの PIN ポリシーをユーザーに割り当てると、それらの設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="3df91-110">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="3df91-111">ユーザーポリシーを割り当てない場合は、サイトレベルの PIN ポリシーが適用されます (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="3df91-111">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="3df91-112">ユーザーポリシーまたはサイトポリシーが適用されていない場合は、グローバル PIN ポリシーが既定の設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="3df91-112">If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3df91-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3df91-113">In This Section</span></span>

  - [<span data-ttu-id="3df91-114">Lync Server 2013 での既定のダイヤルイン会議の PIN 設定の変更</span><span class="sxs-lookup"><span data-stu-id="3df91-114">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="3df91-115">サイトまたはユーザーのグループに対して Lync Server 2013 でダイヤルイン会議の PIN 設定を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="3df91-115">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="3df91-116">Lync Server 2013 で、サイトまたはユーザーのグループのダイヤルイン会議の PIN 設定を削除する</span><span class="sxs-lookup"><span data-stu-id="3df91-116">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

