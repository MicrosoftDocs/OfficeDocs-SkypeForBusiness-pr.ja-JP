---
title: Teams の更新プログラム
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams デスクトップ クライアントの更新方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8058fa1e79b7d415d03c08500213206579029042
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832617"
---
# <a name="teams-update-process"></a><span data-ttu-id="15d82-103">Teams の更新プロセス</span><span class="sxs-lookup"><span data-stu-id="15d82-103">Teams update process</span></span>

<span data-ttu-id="15d82-104">Teams Web アプリは毎週更新されます。</span><span class="sxs-lookup"><span data-stu-id="15d82-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="15d82-105">Teams デスクトップ クライアントの更新プログラムは、TAP (Technology Adoption Program) を使用した厳格な内部テストと検証の後、2 週間ごとにリリースされます。</span><span class="sxs-lookup"><span data-stu-id="15d82-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="15d82-106">通常は火曜日にリリースされます。</span><span class="sxs-lookup"><span data-stu-id="15d82-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="15d82-107">緊急更新プログラムが必要な場合、Teams ではこのスケジュールをバイパスし、利用可能になり次第更新プログラムをリリースします。</span><span class="sxs-lookup"><span data-stu-id="15d82-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="15d82-108">デスクトップ クライアントは自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="15d82-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="15d82-109">Teams は、数時間ごとにバックグラウンドで更新プログラムを確認します。更新プログラムをダウンロードすると、コンピューターがアイドル状態になるまで待機してから、更新プログラムをサイレント インストールします。</span><span class="sxs-lookup"><span data-stu-id="15d82-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="15d82-110">ユーザーは、アプリの右上にある **[プロファイル]** ドロップダウン メニューの **[更新プログラムの確認]** をクリックして、更新プログラムを手動でダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="15d82-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="15d82-111">更新プログラムが入手可能であれば、ダウンロードが実行されて、コンピューターがアイドル状態のときにサイレント インストールされます。</span><span class="sxs-lookup"><span data-stu-id="15d82-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="15d82-112">更新プログラムがダウンロードされるには、ユーザーがサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="15d82-112">Users need to be signed in for updates to be downloaded.</span></span> 

<span data-ttu-id="15d82-113">2019 年 7 月 31 日以降、Teams クライアントの更新プログラムで更新時に使用されるネットワーク帯域幅が大幅に減少されます。</span><span class="sxs-lookup"><span data-stu-id="15d82-113">Starting July 31, 2019, Teams client updates use significantly lower network bandwidth during the update.</span></span> <span data-ttu-id="15d82-114">これは既定でオンになっているため、管理者もユーザーも特別な操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="15d82-114">This is turned on by default and requires no action from admins or users.</span></span>

## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="15d82-115">Office 365 ProPlus の更新について</span><span class="sxs-lookup"><span data-stu-id="15d82-115">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="15d82-116">「[Office 365 ProPlus と同時に Microsoft Teams を展開する](https://docs.microsoft.com/DeployOffice/teams-install)」で説明されているように、Teams は、既定で Office 365 ProPlus の新しいインストールと一緒にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="15d82-116">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="15d82-117">上で説明したとおり、Teams は、Word や Excel などの他の Office アプリの更新プロセスではなく、独自の更新プロセスに従います。</span><span class="sxs-lookup"><span data-stu-id="15d82-117">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="15d82-118">詳細については、「[Office 365 ProPlus 更新プログラムのチャネルの概要](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15d82-118">To learn more, read [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="15d82-119">VDI 上の Teams の更新について</span><span class="sxs-lookup"><span data-stu-id="15d82-119">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="15d82-120">仮想デスクトップ インフラストラクチャ (VDI) 上の Teams クライアントは、VDI 以外の Teams クライアントのように自動的には更新されません。</span><span class="sxs-lookup"><span data-stu-id="15d82-120">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="15d82-121">[VDI 上に Teams をインストールする](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)ための手順に従って、新しい MSI をインストールして、VM イメージを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15d82-121">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="15d82-122">新しいバージョンに更新するには、現在のバージョンをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="15d82-122">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="15d82-123">Teams の自動更新の代わりに、管理者が更新プログラムを展開することはできますか?</span><span class="sxs-lookup"><span data-stu-id="15d82-123">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="15d82-124">Teams では、どんな配信メカニズムを使用してであれ、管理者が更新プログラムを展開することはできません。</span><span class="sxs-lookup"><span data-stu-id="15d82-124">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>

## <a name="servicing-agreement"></a><span data-ttu-id="15d82-125">サービス契約</span><span class="sxs-lookup"><span data-stu-id="15d82-125">Servicing agreement</span></span>

<span data-ttu-id="15d82-126">最新のオンライン サービスとして、Teams クライアントは 2 週間ごとに自動更新されます。</span><span class="sxs-lookup"><span data-stu-id="15d82-126">As a modern online service, the Teams client auto-updates every two weeks.</span></span> <span data-ttu-id="15d82-127">Teams には最新のライフサイクル ポリシーが適用されるため、ユーザーには最新バージョンのデスクトップ クライアントを使用し続けることが期待されています。</span><span class="sxs-lookup"><span data-stu-id="15d82-127">Because Teams is governed by the Modern Lifecycle Policy, it's expected that users remain on the most up-to-date version of the desktop client.</span></span> <span data-ttu-id="15d82-128">そうすることにより、ユーザーは最新の機能、パフォーマンス強化、セキュリティ、サービスの信頼性を確保することができます。</span><span class="sxs-lookup"><span data-stu-id="15d82-128">This ensures that users have the latest capabilities, performance enhancements, security, and service reliability.</span></span>

<span data-ttu-id="15d82-129">デスクトップ クライアントが最新ではなくなったタイミングを特定する助けとして、ユーザーの現在のバージョンが 1 か月から 3 か月前のものである場合、および新しいバージョンが使用できる場合に、アプリ内アラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="15d82-129">To begin assisting in identifying when desktop clients fall out of date, an in-app alert will be displayed if the user’s current version is between one and three months old, and if there's a new version available.</span></span> <span data-ttu-id="15d82-130">このアプリ内のメッセージ機能により、ユーザーは最新バージョンの Teams に更新するか、必要に応じて IT 管理者に連絡してそうしてもらうように促されます。</span><span class="sxs-lookup"><span data-stu-id="15d82-130">This in-app messaging encourages users to update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so.</span></span> <span data-ttu-id="15d82-131">3 か月より前の Teams デスクトップ クライアントを使用しているユーザーには、ブロック ページが表示されます。このページには、すぐに更新するか、IT 管理者に連絡するか、Teams on the web に移動するかを選択するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="15d82-131">Users on Teams desktop clients that are more than three months old will see a blocking page that gives the options to update now, reach out to their IT admin, or continue to Teams on the web.</span></span>

<span data-ttu-id="15d82-132">デスクトップ クライアント バージョンが、最初のインストールまたは Teams を初めて実行した時点で 3 か月より前のものである場合は、上述のサービス情報が表示されるまで 28 日間の猶予期間が設定されています。</span><span class="sxs-lookup"><span data-stu-id="15d82-132">Desktop client versions that are more than three months old upon first install and/or first run of Teams have a 28-day grace period before encountering the above-mentioned servicing information.</span></span> <span data-ttu-id="15d82-133">この期間中に、自動更新プロセスによって Teams クライアントが更新されます。</span><span class="sxs-lookup"><span data-stu-id="15d82-133">During this period, the auto-update process will update the Teams client.</span></span> <span data-ttu-id="15d82-134">更新されない場合は、最新バージョンの Teams に手動で更新するか、必要に応じて IT 管理者に連絡してそうしてもらうように促すアプリ内アラートがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="15d82-134">If not updated, users will see an in-app alert encouraging them to manually update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so.</span></span> <span data-ttu-id="15d82-135">これには、Office 365 ProPlus バンドルの一部として Teams デスクトップ クライアントを使用するユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="15d82-135">This includes users using the Teams desktop client as part of the Office 365 ProPlus bundle.</span></span>

<span data-ttu-id="15d82-136">政府機関向けクラウドの Teams デスクトップ クライアントについては、現在のところ、別途お知らせするまでこのサービス契約の例外です。</span><span class="sxs-lookup"><span data-stu-id="15d82-136">Teams desktop clients on Government Clouds currently have an exception to this servicing agreement until further notice.</span></span>

<span data-ttu-id="15d82-137">新しいバージョンのリリースの詳細については、[メッセージ センター](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)で確認するか、クライアントの **[ヘルプ]** > **[What’s new](新機能)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15d82-137">For information on new version releases, check [Message Center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) or go to **Help** > **What’s new** in the client.</span></span>
