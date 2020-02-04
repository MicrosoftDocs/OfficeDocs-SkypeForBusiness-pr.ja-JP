---
title: 'Lync Server 2013: ダイヤルイン会議の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring dial-in conferencing
ms:assetid: 79a98c5d-a0a8-4729-828d-b9166842432c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398600(v=OCS.15)
ms:contentKeyID: 48184587
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d722abaf76ef915b7587039cb7732cb281a06308
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="bbe88-102">Lync Server 2013 でのダイヤルイン会議の構成</span><span class="sxs-lookup"><span data-stu-id="bbe88-102">Configuring dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbe88-103">_**最終更新日:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="bbe88-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="bbe88-104">このセクションでは、Lync Server 2013 ダイヤルイン会議の構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe88-104">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bbe88-105">このセクション中</span><span class="sxs-lookup"><span data-stu-id="bbe88-105">In This Section</span></span>

  - [<span data-ttu-id="bbe88-106">Lync Server 2013 のダイヤルイン会議の前提条件とアクセス許可</span><span class="sxs-lookup"><span data-stu-id="bbe88-106">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="bbe88-107">Lync Server 2013 のダイヤルイン会議の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="bbe88-107">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="bbe88-108">Lync Server 2013 でのダイヤルイン会議のダイヤル プランの構成</span><span class="sxs-lookup"><span data-stu-id="bbe88-108">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="bbe88-109">「ダイヤルプラン Lync Server 2013 に地域が割り当てられていることを確認する」</span><span class="sxs-lookup"><span data-stu-id="bbe88-109">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="bbe88-110">(オプション) Lync Server 2013 での PIN ポリシー設定の確認</span><span class="sxs-lookup"><span data-stu-id="bbe88-110">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="bbe88-111">Lync Server 2013 でダイヤルインの会議ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="bbe88-111">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="bbe88-112">Lync Server 2013 でのダイヤルイン会議アクセス番号の構成</span><span class="sxs-lookup"><span data-stu-id="bbe88-112">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="bbe88-113">(オプション) Lync Server 2013 でのダイヤルイン会議の設定の検証</span><span class="sxs-lookup"><span data-stu-id="bbe88-113">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="bbe88-114">(オプション) Lync Server 2013 で DTMF コマンドの主要なマッピングを変更する</span><span class="sxs-lookup"><span data-stu-id="bbe88-114">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="bbe88-115">(オプション) Lync Server 2013 での会議への入退出のアナウンスの有効化および無効化</span><span class="sxs-lookup"><span data-stu-id="bbe88-115">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="bbe88-116">(オプション) Lync Server 2013 でのダイヤルイン会議の検証</span><span class="sxs-lookup"><span data-stu-id="bbe88-116">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="bbe88-117">Lync 2013 用オンライン会議アドインの展開</span><span class="sxs-lookup"><span data-stu-id="bbe88-117">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="bbe88-118">Lync Server 2013 でのユーザー アカウント設定の構成</span><span class="sxs-lookup"><span data-stu-id="bbe88-118">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="bbe88-119">(Recommended) Create Conference Directories</span><span class="sxs-lookup"><span data-stu-id="bbe88-119">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="bbe88-120">(オプション) Lync Server 2013 でのダイヤルイン会議へのユーザーの受け入れ</span><span class="sxs-lookup"><span data-stu-id="bbe88-120">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="bbe88-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbe88-121">Related Sections</span></span>

[<span data-ttu-id="bbe88-122">Lync Server 2013 の展開</span><span class="sxs-lookup"><span data-stu-id="bbe88-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

