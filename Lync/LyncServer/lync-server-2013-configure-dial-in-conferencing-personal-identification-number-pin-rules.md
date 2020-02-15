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
ms.openlocfilehash: 243e8d44cb5d6e3662c51c643a86cc9379ee958b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="f0a04-102">Lync Server 2013 でダイヤルイン会議の暗証番号 (PIN) ルールを構成する</span><span class="sxs-lookup"><span data-stu-id="f0a04-102">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0a04-103">_**トピックの最終更新日:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="f0a04-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="f0a04-104">Lync Server 2013 組織内の Active Directory ドメインサービス (AD DS) の資格情報を持つユーザーは、個人識別番号 (PIN) を使用して、認証されたユーザーとしてダイヤルイン会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="f0a04-104">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="f0a04-105">PIN ポリシーは、ダイヤルイン会議の Pin の動作規則を定義します。</span><span class="sxs-lookup"><span data-stu-id="f0a04-105">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="f0a04-106">特定のポリシーをサイトまたは特定のユーザーグループに適用する場合は、新しい PIN ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f0a04-106">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span> <span data-ttu-id="f0a04-107">組織全体で同じ PIN ポリシーを使用する場合は、グローバル PIN ポリシーを使用して、必要に応じて変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f0a04-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="f0a04-108">PIN ポリシーは、最も狭いスコープから最も広いスコープへのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0a04-108">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="f0a04-109">ユーザーレベルの PIN ポリシーをユーザーに割り当てると、それらの設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="f0a04-109">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="f0a04-110">ユーザーポリシーを割り当てない場合は、サイトレベルの PIN ポリシーが適用されます (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="f0a04-110">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="f0a04-111">ユーザーポリシーまたはサイトポリシーが適用されていない場合は、グローバル PIN ポリシーが既定の設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="f0a04-111">If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f0a04-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f0a04-112">In This Section</span></span>

  - [<span data-ttu-id="f0a04-113">Lync Server 2013 での既定のダイヤルイン会議の PIN 設定の変更</span><span class="sxs-lookup"><span data-stu-id="f0a04-113">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="f0a04-114">サイトまたはユーザーのグループに対して Lync Server 2013 でダイヤルイン会議の PIN 設定を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="f0a04-114">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="f0a04-115">Lync Server 2013 で、サイトまたはユーザーのグループのダイヤルイン会議の PIN 設定を削除する</span><span class="sxs-lookup"><span data-stu-id="f0a04-115">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

