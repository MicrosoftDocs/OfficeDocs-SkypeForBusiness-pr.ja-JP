---
title: チームの更新
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
description: Teams デスクトップクライアントの更新方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ace50cc0f9c59375c5a182cf18559b0a449db109
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570258"
---
# <a name="teams-update-process"></a><span data-ttu-id="8482a-103">Teams の更新プロセス</span><span class="sxs-lookup"><span data-stu-id="8482a-103">Teams update process</span></span>

<span data-ttu-id="8482a-104">Teams web app が毎週更新されます。</span><span class="sxs-lookup"><span data-stu-id="8482a-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="8482a-105">Teams のデスクトップクライアントの更新プログラムは、skype の技術導入プログラムを通じて、社内の厳密なテストと検証の2週間ごとにリリースされます (タップ)。</span><span class="sxs-lookup"><span data-stu-id="8482a-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="8482a-106">通常、これは火曜日で行われます。</span><span class="sxs-lookup"><span data-stu-id="8482a-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="8482a-107">重要な更新が必要な場合は、チームはこのスケジュールを無視し、利用可能になったらすぐに更新プログラムをリリースします。</span><span class="sxs-lookup"><span data-stu-id="8482a-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="8482a-108">デスクトップクライアントは自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="8482a-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="8482a-109">チームは、バックグラウンドで数時間ごとに更新プログラムを確認し、それをダウンロードした後、更新プログラムをサイレントインストールする前にコンピューターがアイドル状態になるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="8482a-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="8482a-110">ユーザーは、アプリの右上にある [**プロファイル**] ドロップダウンメニューの [**更新プログラムの確認**] をクリックして、手動で更新プログラムをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8482a-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="8482a-111">更新プログラムが利用可能な場合は、コンピューターがアイドル状態になったときにダウンロードされ、黙ってインストールされます。</span><span class="sxs-lookup"><span data-stu-id="8482a-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="8482a-112">更新プログラムをダウンロードするには、ユーザーがサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8482a-112">Users need to be signed in for updates to be downloaded.</span></span> 

<span data-ttu-id="8482a-113">2019年7月31日から、Teams クライアントの更新では、更新中にネットワーク帯域幅が大幅に減少します。</span><span class="sxs-lookup"><span data-stu-id="8482a-113">Starting July 31, 2019, Teams client updates use significantly lower network bandwidth during the update.</span></span> <span data-ttu-id="8482a-114">これは既定でオンになっており、管理者またはユーザーが操作する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8482a-114">This is turned on by default and requires no action from admins or users.</span></span>

## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="8482a-115">Office 365 ProPlus の更新プログラムについて</span><span class="sxs-lookup"><span data-stu-id="8482a-115">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="8482a-116">Office は既定で、office 365 ProPlus の新しいインストールと共にインストールされます。詳しくは、「 [office 365 で Microsoft Teams を展開する ProPlus](https://docs.microsoft.com/DeployOffice/teams-install)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8482a-116">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="8482a-117">チームは、前に説明したように、独自の更新プロセスに従いますが、Word や Excel など、他のオフィスアプリの更新プロセスではありません。</span><span class="sxs-lookup"><span data-stu-id="8482a-117">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="8482a-118">詳細については、「 [Office 365 ProPlus の更新プログラムチャネルの概要」](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8482a-118">To learn more, read [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="8482a-119">VDI でのチームの更新について</span><span class="sxs-lookup"><span data-stu-id="8482a-119">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="8482a-120">仮想デスクトップインフラストラクチャ (VDI) 上の Teams クライアントは、非 VDI Teams クライアントのように自動的には更新されません。</span><span class="sxs-lookup"><span data-stu-id="8482a-120">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="8482a-121">「Team を[VDI にインストール](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)する」の手順に従って、新しい MSI をインストールして、VM イメージを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8482a-121">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="8482a-122">最新バージョンに更新するには、現在のバージョンをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8482a-122">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="8482a-123">管理者がチームの自動更新の代わりに更新プログラムを展開することはできますか?</span><span class="sxs-lookup"><span data-stu-id="8482a-123">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="8482a-124">チームは、任意の配信メカニズムを使用して更新プログラムを展開する権限を管理者に付与することはできません。</span><span class="sxs-lookup"><span data-stu-id="8482a-124">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>

## <a name="servicing-agreement"></a><span data-ttu-id="8482a-125">サービス契約</span><span class="sxs-lookup"><span data-stu-id="8482a-125">Servicing agreement</span></span>

<span data-ttu-id="8482a-126">最新のオンラインサービスとして、Teams クライアントは2週間ごとに自動更新されます。</span><span class="sxs-lookup"><span data-stu-id="8482a-126">As a modern online service, the Teams client auto-updates every two weeks.</span></span> <span data-ttu-id="8482a-127">Teams は最新のライフサイクルポリシーによって管理されるため、ユーザーは最新バージョンのデスクトップクライアントを維持している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8482a-127">Because Teams is governed by the Modern Lifecycle Policy, it's expected that users remain on the most up-to-date version of the desktop client.</span></span> <span data-ttu-id="8482a-128">これにより、ユーザーは最新の機能、パフォーマンスの拡張、セキュリティ、およびサービスの信頼性を確保することができます。</span><span class="sxs-lookup"><span data-stu-id="8482a-128">This ensures that users have the latest capabilities, performance enhancements, security, and service reliability.</span></span>

<span data-ttu-id="8482a-129">デスクトップクライアントが最新の状態になっているかどうかを特定するための支援を始めるには、ユーザーの現在のバージョンが 1 ~ 3 か月前であり、新しいバージョンが利用可能であるかどうかをアプリ内通知で確認します。</span><span class="sxs-lookup"><span data-stu-id="8482a-129">To begin assisting in identifying when desktop clients fall out of date, an in-app alert will be displayed if the user’s current version is between one and three months old, and if there's a new version available.</span></span> <span data-ttu-id="8482a-130">このアプリ内のメッセージは、ユーザーが最新バージョンの Teams に更新したり、必要に応じて IT 管理者に連絡したりすることを促します。</span><span class="sxs-lookup"><span data-stu-id="8482a-130">This in-app messaging encourages users to update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so.</span></span> <span data-ttu-id="8482a-131">3ヶ月以上前の Teams デスクトップクライアントのユーザーには、今すぐ更新、IT 管理者への連絡、web 上のチームへの参加などのオプションを提供するブロックページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8482a-131">Users on Teams desktop clients that are more than three months old will see a blocking page that gives the options to update now, reach out to their IT admin, or continue to Teams on the web.</span></span>

<span data-ttu-id="8482a-132">初めてインストールしたときから3ヶ月以上経過したデスクトップクライアントのバージョンについては、上記のサービス情報に遭遇する前に、28日間の猶予期間が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8482a-132">Desktop client versions that are more than three months old upon first install and/or first run of Teams have a 28-day grace period before encountering the above-mentioned servicing information.</span></span> <span data-ttu-id="8482a-133">この期間中、自動更新プロセスによって Teams クライアントが更新されます。</span><span class="sxs-lookup"><span data-stu-id="8482a-133">During this period, the auto-update process will update the Teams client.</span></span> <span data-ttu-id="8482a-134">更新されていない場合は、最新バージョンの Teams に手動で更新するか、必要に応じて IT 管理者に連絡するために、アプリ内警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8482a-134">If not updated, users will see an in-app alert encouraging them to manually update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so.</span></span> <span data-ttu-id="8482a-135">これには、Office 365 ProPlus バンドルの一部として Teams デスクトップクライアントを使用するユーザーも含まれます。</span><span class="sxs-lookup"><span data-stu-id="8482a-135">This includes users using the Teams desktop client as part of the Office 365 ProPlus bundle.</span></span>

<span data-ttu-id="8482a-136">政府機関向けの Teams デスクトップクライアントには、現時点で通知が表示されるまで、現在このサービス契約には例外があります。</span><span class="sxs-lookup"><span data-stu-id="8482a-136">Teams desktop clients on Government Clouds currently have an exception to this servicing agreement until further notice.</span></span>

<span data-ttu-id="8482a-137">新しいバージョンのリリースについては[、メッセージセンター](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)を確認**するか** > 、「クライアントの**新機能**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8482a-137">For information on new version releases, check [Message Center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) or go to **Help** > **What’s new** in the client.</span></span>
