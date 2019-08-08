---
title: チームの更新
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Teams デスクトップクライアントの更新方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0fe542c6df89946ad73f14cf9104f973e292aa3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243844"
---
# <a name="teams-update-process"></a><span data-ttu-id="e09c6-103">Teams の更新プロセス</span><span class="sxs-lookup"><span data-stu-id="e09c6-103">Teams update process</span></span>

<span data-ttu-id="e09c6-104">Teams web app が毎週更新されます。</span><span class="sxs-lookup"><span data-stu-id="e09c6-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="e09c6-105">Teams のデスクトップクライアントの更新プログラムは、skype の技術導入プログラムを通じて、社内の厳密なテストと検証の2週間ごとにリリースされます (タップ)。</span><span class="sxs-lookup"><span data-stu-id="e09c6-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="e09c6-106">通常、これは火曜日で行われます。</span><span class="sxs-lookup"><span data-stu-id="e09c6-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="e09c6-107">重要な更新が必要な場合は、チームはこのスケジュールを無視し、利用可能になったらすぐに更新プログラムをリリースします。</span><span class="sxs-lookup"><span data-stu-id="e09c6-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="e09c6-108">デスクトップクライアントは自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="e09c6-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="e09c6-109">チームは、バックグラウンドで数時間ごとに更新プログラムを確認し、それをダウンロードした後、更新プログラムをサイレントインストールする前にコンピューターがアイドル状態になるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="e09c6-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="e09c6-110">ユーザーは、アプリの右上にある [**プロファイル**] ドロップダウンメニューの [**更新プログラムの確認**] をクリックして、手動で更新プログラムをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e09c6-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="e09c6-111">更新プログラムが利用可能な場合は、コンピューターがアイドル状態になったときにダウンロードされ、黙ってインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e09c6-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="e09c6-112">更新プログラムをダウンロードするには、ユーザーがサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e09c6-112">Users need to be signed in for updates to be downloaded.</span></span> 

<span data-ttu-id="e09c6-113">2019年7月9日に、Teams クライアントの更新では、更新中にネットワーク帯域幅が大幅に減少します。</span><span class="sxs-lookup"><span data-stu-id="e09c6-113">Starting July 9, 2019, Teams client updates use significantly lower network bandwidth during the update.</span></span> <span data-ttu-id="e09c6-114">これは既定でオンになっており、管理者またはユーザーが操作する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e09c6-114">This is turned on by default and requires no action from admins or users.</span></span>


## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="e09c6-115">Office 365 ProPlus の更新プログラムについて</span><span class="sxs-lookup"><span data-stu-id="e09c6-115">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="e09c6-116">Office は既定で、office 365 ProPlus の新しいインストールと共にインストールされます。詳しくは、「 [office 365 で Microsoft Teams を展開する ProPlus](https://docs.microsoft.com/DeployOffice/teams-install)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e09c6-116">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="e09c6-117">チームは、前に説明したように、独自の更新プロセスに従いますが、Word や Excel など、他のオフィスアプリの更新プロセスではありません。</span><span class="sxs-lookup"><span data-stu-id="e09c6-117">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="e09c6-118">詳細については、「 [Office 365 ProPlus の更新プログラムチャネルの概要」](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e09c6-118">To learn more, read [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="e09c6-119">VDI でのチームの更新について</span><span class="sxs-lookup"><span data-stu-id="e09c6-119">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="e09c6-120">仮想デスクトップインフラストラクチャ (VDI) 上の Teams クライアントは、非 VDI Teams クライアントのように自動的には更新されません。</span><span class="sxs-lookup"><span data-stu-id="e09c6-120">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="e09c6-121">「Team を[VDI にインストール](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)する」の手順に従って、新しい MSI をインストールして、VM イメージを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e09c6-121">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="e09c6-122">最新バージョンに更新するには、現在のバージョンをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e09c6-122">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="e09c6-123">管理者がチームの自動更新の代わりに更新プログラムを展開することはできますか?</span><span class="sxs-lookup"><span data-stu-id="e09c6-123">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="e09c6-124">チームは、任意の配信メカニズムを使用して更新プログラムを展開する権限を管理者に付与することはできません。</span><span class="sxs-lookup"><span data-stu-id="e09c6-124">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>
