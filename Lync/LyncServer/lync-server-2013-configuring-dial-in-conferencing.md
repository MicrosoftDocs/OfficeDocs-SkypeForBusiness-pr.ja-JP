---
title: 'Lync Server 2013: ダイヤルイン会議の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring dial-in conferencing
ms:assetid: 79a98c5d-a0a8-4729-828d-b9166842432c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398600(v=OCS.15)
ms:contentKeyID: 48184587
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ca8b82fe77e578f1ac513d00583c42dd56162a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="f4a71-102">Lync Server 2013 でのダイヤルイン会議の構成</span><span class="sxs-lookup"><span data-stu-id="f4a71-102">Configuring dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4a71-103">_**最終更新日:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="f4a71-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="f4a71-104">このセクションでは、Lync Server 2013 ダイヤルイン会議の構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="f4a71-104">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f4a71-105">このセクション中</span><span class="sxs-lookup"><span data-stu-id="f4a71-105">In This Section</span></span>

  - [<span data-ttu-id="f4a71-106">Lync Server 2013 のダイヤルイン会議の前提条件とアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f4a71-106">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="f4a71-107">Lync Server 2013 のダイヤルイン会議の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="f4a71-107">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="f4a71-108">Lync Server 2013 でのダイヤルイン会議のダイヤル プランの構成</span><span class="sxs-lookup"><span data-stu-id="f4a71-108">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="f4a71-109">「ダイヤルプラン Lync Server 2013 に地域が割り当てられていることを確認する」</span><span class="sxs-lookup"><span data-stu-id="f4a71-109">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="f4a71-110">(オプション) Lync Server 2013 での PIN ポリシー設定の確認</span><span class="sxs-lookup"><span data-stu-id="f4a71-110">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="f4a71-111">Lync Server 2013 でダイヤルインの会議ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="f4a71-111">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="f4a71-112">Lync Server 2013 でのダイヤルイン会議アクセス番号の構成</span><span class="sxs-lookup"><span data-stu-id="f4a71-112">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="f4a71-113">(オプション) Lync Server 2013 でのダイヤルイン会議の設定の検証</span><span class="sxs-lookup"><span data-stu-id="f4a71-113">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="f4a71-114">(オプション) Lync Server 2013 で DTMF コマンドの主要なマッピングを変更する</span><span class="sxs-lookup"><span data-stu-id="f4a71-114">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="f4a71-115">(オプション) Lync Server 2013 での会議への入退出のアナウンスの有効化および無効化</span><span class="sxs-lookup"><span data-stu-id="f4a71-115">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="f4a71-116">(オプション) Lync Server 2013 でのダイヤルイン会議の検証</span><span class="sxs-lookup"><span data-stu-id="f4a71-116">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="f4a71-117">Lync 2013 用オンライン会議アドインの展開</span><span class="sxs-lookup"><span data-stu-id="f4a71-117">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="f4a71-118">Lync Server 2013 でのユーザー アカウント設定の構成</span><span class="sxs-lookup"><span data-stu-id="f4a71-118">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="f4a71-119">(Recommended) Create Conference Directories</span><span class="sxs-lookup"><span data-stu-id="f4a71-119">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="f4a71-120">(オプション) Lync Server 2013 でのダイヤルイン会議へのユーザーの受け入れ</span><span class="sxs-lookup"><span data-stu-id="f4a71-120">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="f4a71-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4a71-121">Related Sections</span></span>

[<span data-ttu-id="f4a71-122">Lync Server 2013 の展開</span><span class="sxs-lookup"><span data-stu-id="f4a71-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

