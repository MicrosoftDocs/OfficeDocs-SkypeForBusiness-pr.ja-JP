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
ms.openlocfilehash: bd86bcbe34e1cd3510fcbf5f257504a2316f3d14
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="8a44c-102">Lync Server 2013 でのダイヤルイン会議の構成</span><span class="sxs-lookup"><span data-stu-id="8a44c-102">Configuring dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a44c-103">_**トピックの最終更新日:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="8a44c-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="8a44c-104">このセクションでは、Lync Server 2013 ダイヤルイン会議の構成について手順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="8a44c-104">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8a44c-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8a44c-105">In This Section</span></span>

  - [<span data-ttu-id="8a44c-106">Lync Server 2013 でのダイヤルイン会議構成の前提条件とアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8a44c-106">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="8a44c-107">Lync Server 2013 でのダイヤルイン会議の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="8a44c-107">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="8a44c-108">Lync Server 2013 でダイヤルイン会議のダイヤルプランを構成する</span><span class="sxs-lookup"><span data-stu-id="8a44c-108">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="8a44c-109">ダイヤルプラン Lync Server 2013 に地域が割り当てられていることを確認する</span><span class="sxs-lookup"><span data-stu-id="8a44c-109">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="8a44c-110">オプションLync Server 2013 での PIN ポリシー設定の確認</span><span class="sxs-lookup"><span data-stu-id="8a44c-110">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="8a44c-111">Lync Server 2013 でのダイヤルインの会議ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="8a44c-111">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="8a44c-112">Lync Server 2013 でのダイヤルイン会議アクセス番号の構成</span><span class="sxs-lookup"><span data-stu-id="8a44c-112">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="8a44c-113">オプションLync Server 2013 でダイヤルイン会議の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="8a44c-113">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="8a44c-114">オプションLync Server 2013 での DTMF コマンドのキーマッピングの変更</span><span class="sxs-lookup"><span data-stu-id="8a44c-114">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="8a44c-115">オプションLync Server 2013 での会議の参加と脱退のアナウンスを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="8a44c-115">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="8a44c-116">オプションLync Server 2013 でのダイヤルイン会議の確認</span><span class="sxs-lookup"><span data-stu-id="8a44c-116">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="8a44c-117">Lync 2013 用オンライン ミーティング アドインの展開</span><span class="sxs-lookup"><span data-stu-id="8a44c-117">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="8a44c-118">Lync Server 2013 でユーザーアカウント設定を構成する</span><span class="sxs-lookup"><span data-stu-id="8a44c-118">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="8a44c-119">勧め会議ディレクトリを作成する</span><span class="sxs-lookup"><span data-stu-id="8a44c-119">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="8a44c-120">オプションLync Server 2013 でのダイヤルイン会議へのユーザーのようこそ</span><span class="sxs-lookup"><span data-stu-id="8a44c-120">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="8a44c-121">関連情報</span><span class="sxs-lookup"><span data-stu-id="8a44c-121">Related Sections</span></span>

[<span data-ttu-id="8a44c-122">Lync Server 2013 の展開 </span><span class="sxs-lookup"><span data-stu-id="8a44c-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

