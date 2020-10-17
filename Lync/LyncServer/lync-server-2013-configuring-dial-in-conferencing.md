---
title: 'Lync Server 2013: ダイヤルイン会議の構成'
description: 'Lync Server 2013: ダイヤルイン会議の構成。'
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
ms.openlocfilehash: d9c3353caa1344b717b0f64c271149f078f194e5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557943"
---
# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="9a109-103">Lync Server 2013 でのダイヤルイン会議の構成</span><span class="sxs-lookup"><span data-stu-id="9a109-103">Configuring dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a109-104">_**トピックの最終更新日:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="9a109-104">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="9a109-105">このセクションでは、Lync Server 2013 ダイヤルイン会議の構成について手順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="9a109-105">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9a109-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9a109-106">In This Section</span></span>

  - [<span data-ttu-id="9a109-107">Lync Server 2013 でのダイヤルイン会議構成の前提条件とアクセス許可</span><span class="sxs-lookup"><span data-stu-id="9a109-107">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="9a109-108">Lync Server 2013 でのダイヤルイン会議の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="9a109-108">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="9a109-109">Lync Server 2013 でダイヤルイン会議のダイヤルプランを構成する</span><span class="sxs-lookup"><span data-stu-id="9a109-109">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="9a109-110">ダイヤルプラン Lync Server 2013 に地域が割り当てられていることを確認する</span><span class="sxs-lookup"><span data-stu-id="9a109-110">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="9a109-111">オプションLync Server 2013 での PIN ポリシー設定の確認</span><span class="sxs-lookup"><span data-stu-id="9a109-111">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="9a109-112">Lync Server 2013 でのダイヤルインの会議ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="9a109-112">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="9a109-113">Lync Server 2013 でのダイヤルイン会議アクセス番号の構成</span><span class="sxs-lookup"><span data-stu-id="9a109-113">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="9a109-114">オプションLync Server 2013 でダイヤルイン会議の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="9a109-114">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="9a109-115">オプションLync Server 2013 での DTMF コマンドのキーマッピングの変更</span><span class="sxs-lookup"><span data-stu-id="9a109-115">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="9a109-116">オプションLync Server 2013 での会議の参加と脱退のアナウンスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="9a109-116">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="9a109-117">オプションLync Server 2013 でのダイヤルイン会議の確認</span><span class="sxs-lookup"><span data-stu-id="9a109-117">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="9a109-118">Lync 2013 用オンライン ミーティング アドインの展開</span><span class="sxs-lookup"><span data-stu-id="9a109-118">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="9a109-119">Lync Server 2013 でユーザーアカウント設定を構成する</span><span class="sxs-lookup"><span data-stu-id="9a109-119">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="9a109-120">勧め会議ディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="9a109-120">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="9a109-121">オプションLync Server 2013 でのダイヤルイン会議へのユーザーのようこそ</span><span class="sxs-lookup"><span data-stu-id="9a109-121">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="9a109-122">関連情報</span><span class="sxs-lookup"><span data-stu-id="9a109-122">Related Sections</span></span>

[<span data-ttu-id="9a109-123">Lync Server 2013 の展開 </span><span class="sxs-lookup"><span data-stu-id="9a109-123">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

