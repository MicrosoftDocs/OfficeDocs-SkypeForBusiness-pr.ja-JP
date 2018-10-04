---
title: PowerShell を使用して、チームを管理するには
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: マイクロソフト チームの機能のすべてを管理する Windows PowerShell を使用するについて説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: eccd04023324256e40d9e06315fcd80081ffe565
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371351"
---
# <a name="using-powershell-to-manage-teams"></a><span data-ttu-id="1b1b9-103">PowerShell を使用して、チームを管理するには</span><span class="sxs-lookup"><span data-stu-id="1b1b9-103">Using PowerShell to manage Teams</span></span>
<span data-ttu-id="1b1b9-104">これをビジョン化、機能を設定するためのリファレンス トピックとして私は。</span><span class="sxs-lookup"><span data-stu-id="1b1b9-104">I would envision this as a reference topic that would set up as per feature.</span></span> <span data-ttu-id="1b1b9-105">各機能のセットでは、すべてのコマンドレットが Get ヘルプ トピックへのリンクを持つテーブルに記載されているがあります。</span><span class="sxs-lookup"><span data-stu-id="1b1b9-105">Then each feature set would have all of the cmdlets listed in the table with links to the Get-Help topic.</span></span>

# <a name="managing-teams-features-using-powershell"></a><span data-ttu-id="1b1b9-106">PowerShell を使用するチームの機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="1b1b9-106">Managing Teams features using PowerShell</span></span>

## <a name="admin-roles"></a><span data-ttu-id="1b1b9-107">管理者の役割</span><span class="sxs-lookup"><span data-stu-id="1b1b9-107">Admin roles</span></span>

|<span data-ttu-id="1b1b9-108">役割</span><span class="sxs-lookup"><span data-stu-id="1b1b9-108">Role</span></span> |<span data-ttu-id="1b1b9-109">例</span><span class="sxs-lookup"><span data-stu-id="1b1b9-109">Example</span></span> |<span data-ttu-id="1b1b9-110">コマンドレットのヘルプ リンク</span><span class="sxs-lookup"><span data-stu-id="1b1b9-110">Cmdlet Help link</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="1b1b9-111">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="1b1b9-111">Global admin</span></span>     |         |         |
|<span data-ttu-id="1b1b9-112">ヘルプデスク</span><span class="sxs-lookup"><span data-stu-id="1b1b9-112">HelpDesk</span></span>     |         |         |
|<span data-ttu-id="1b1b9-113">次に</span><span class="sxs-lookup"><span data-stu-id="1b1b9-113">Next</span></span>   |         |         |
|<span data-ttu-id="1b1b9-114">次に</span><span class="sxs-lookup"><span data-stu-id="1b1b9-114">Next</span></span>     |         |         |

<span data-ttu-id="1b1b9-115">イザベルのドキュメントへのリンクします。</span><span class="sxs-lookup"><span data-stu-id="1b1b9-115">link to Isabella's doc</span></span>

## <a name="audio-conferencing"></a><span data-ttu-id="1b1b9-116">オーディオ会議</span><span class="sxs-lookup"><span data-stu-id="1b1b9-116">Audio conferencing</span></span>

|<span data-ttu-id="1b1b9-117">コマンドレット名</span><span class="sxs-lookup"><span data-stu-id="1b1b9-117">Cmdlet name</span></span> |<span data-ttu-id="1b1b9-118">説明</span><span class="sxs-lookup"><span data-stu-id="1b1b9-118">Description</span></span> |<span data-ttu-id="1b1b9-119">コマンドレットのヘルプ リンク</span><span class="sxs-lookup"><span data-stu-id="1b1b9-119">Cmdlet Help link</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="1b1b9-120">コマンドレット名</span><span class="sxs-lookup"><span data-stu-id="1b1b9-120">Cmdlet name</span></span>   |    <span data-ttu-id="1b1b9-121">機能</span><span class="sxs-lookup"><span data-stu-id="1b1b9-121">What it does</span></span>  |    <span data-ttu-id="1b1b9-122">Get-help PS コマンドレットへのリンクします。</span><span class="sxs-lookup"><span data-stu-id="1b1b9-122">Link to the Get-Help PS cmdlet</span></span>     |
|<span data-ttu-id="1b1b9-123">コマンドレット名</span><span class="sxs-lookup"><span data-stu-id="1b1b9-123">Cmdlet name</span></span>   |    <span data-ttu-id="1b1b9-124">機能</span><span class="sxs-lookup"><span data-stu-id="1b1b9-124">What it does</span></span>  |    <span data-ttu-id="1b1b9-125">Get-help PS コマンドレットへのリンクします。</span><span class="sxs-lookup"><span data-stu-id="1b1b9-125">Link to the Get-Help PS cmdlet</span></span>     |
|<span data-ttu-id="1b1b9-126">コマンドレット名</span><span class="sxs-lookup"><span data-stu-id="1b1b9-126">Cmdlet name</span></span>   |    <span data-ttu-id="1b1b9-127">機能</span><span class="sxs-lookup"><span data-stu-id="1b1b9-127">What it does</span></span>  |    <span data-ttu-id="1b1b9-128">Get-help PS コマンドレットへのリンクします。</span><span class="sxs-lookup"><span data-stu-id="1b1b9-128">Link to the Get-Help PS cmdlet</span></span>     |
|<span data-ttu-id="1b1b9-129">コマンドレット名</span><span class="sxs-lookup"><span data-stu-id="1b1b9-129">Cmdlet name</span></span>   |    <span data-ttu-id="1b1b9-130">機能</span><span class="sxs-lookup"><span data-stu-id="1b1b9-130">What it does</span></span>  |    <span data-ttu-id="1b1b9-131">Get-help PS コマンドレットへのリンクします。</span><span class="sxs-lookup"><span data-stu-id="1b1b9-131">Link to the Get-Help PS cmdlet</span></span>     |

## <a name="meeting-policies"></a><span data-ttu-id="1b1b9-132">ミーティングのポリシー</span><span class="sxs-lookup"><span data-stu-id="1b1b9-132">Meeting policies</span></span>
<span data-ttu-id="1b1b9-133">|コマンドレット名 |   何 |   Get-help PS コマンドレットへのリンク。コマンドレット名 |   何 |   Get-help PS コマンドレットへのリンク。コマンドレット名 |   何 |   Get-help PS コマンドレットへのリンク。コマンドレット名 |   何 |   Get-help PS コマンドレットへのリンク。コマンドレット名 |   何 |   Get-help PS コマンドレットへのリンク |</span><span class="sxs-lookup"><span data-stu-id="1b1b9-133">|Cmdlet name   |    What it does  |    Link to the Get-Help PS cmdlet     | |Cmdlet name   |    What it does  |    Link to the Get-Help PS cmdlet     | |Cmdlet name   |    What it does  |    Link to the Get-Help PS cmdlet     | |Cmdlet name   |    What it does  |    Link to the Get-Help PS cmdlet     | |Cmdlet name   |    What it does  |    Link to the Get-Help PS cmdlet     |</span></span>

## <a name="messaging-policies"></a><span data-ttu-id="1b1b9-134">メッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="1b1b9-134">Messaging policies</span></span>
<span data-ttu-id="1b1b9-135">|コマンドレット名 |   何 |   Get-help PS コマンドレットへのリンク。コマンドレット名 |   何 |   Get-help PS コマンドレットへのリンク。コマンドレット名 |   何 |   Get-help PS コマンドレットへのリンク。コマンドレット名 |   何 |   Get-help PS コマンドレットへのリンク |</span><span class="sxs-lookup"><span data-stu-id="1b1b9-135">|Cmdlet name   |    What it does  |    Link to the Get-Help PS cmdlet     | |Cmdlet name   |    What it does  |    Link to the Get-Help PS cmdlet     | |Cmdlet name   |    What it does  |    Link to the Get-Help PS cmdlet     | |Cmdlet name   |    What it does  |    Link to the Get-Help PS cmdlet     |</span></span>

### <a name="related-topics"></a><span data-ttu-id="1b1b9-136">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1b1b9-136">Related topics</span></span>