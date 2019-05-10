---
title: チーム プロセスを更新します。
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/08/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: チームのデスクトップ クライアントを更新する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04b7d1e66905e7859139605b90b3093a48e8afbd
ms.sourcegitcommit: b072148ea13f4d4f6035204a48bedd287fb90ebd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "33829097"
---
# <a name="teams-update-process"></a><span data-ttu-id="e8a32-103">チーム プロセスを更新します。</span><span class="sxs-lookup"><span data-stu-id="e8a32-103">Teams update process</span></span>

<span data-ttu-id="e8a32-104">チームの Web アプリケーションは、毎週更新されます。</span><span class="sxs-lookup"><span data-stu-id="e8a32-104">The Teams Web App is updated weekly.</span></span>

<span data-ttu-id="e8a32-105">チーム デスクトップ クライアント更新がリリースされた内部の厳格なテストおよび検証した後は 2 週間ごと、技術導入プログラム (タップ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e8a32-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="e8a32-106">これは通常、火曜日にします。</span><span class="sxs-lookup"><span data-stu-id="e8a32-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="e8a32-107">重要な更新が必要な場合は、チームはこのスケジュールを使用しないし、使用可能になるとすぐに更新プログラムをリリースします。</span><span class="sxs-lookup"><span data-stu-id="e8a32-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="e8a32-108">デスクトップ クライアント自体が自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="e8a32-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="e8a32-109">チームのチェックは、バック グラウンドでいくつかの時間ごとの更新、ダウンロード、および、コンピューターに更新プログラムをサイレント モードでインストールする前にアイドル状態になるを待ちます。</span><span class="sxs-lookup"><span data-stu-id="e8a32-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="e8a32-110">上に**プロファイル**のドロップ ダウン メニューで [**更新プログラムの確認**] をクリックしてユーザーが更新プログラムを手動でダウンロード、アプリケーションの右です。</span><span class="sxs-lookup"><span data-stu-id="e8a32-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="e8a32-111">更新が利用可能な場合は、それがダウンロードされ、コンピューターがアイドル状態のときにサイレント モードでインストールされています。</span><span class="sxs-lookup"><span data-stu-id="e8a32-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="e8a32-112">ユーザーは、ダウンロードする更新プログラム署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8a32-112">Users need to be signed in for updates to be downloaded.</span></span>

## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="e8a32-113">Office 365 用リソースへの更新について教えてください。</span><span class="sxs-lookup"><span data-stu-id="e8a32-113">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="e8a32-114">チームは Office 365 用リソースの新規インストールでは既定でインストールされている[Office 365 用リソースを持つマイクロソフト チームの展開](https://docs.microsoft.com/DeployOffice/teams-install)で説明したようです。</span><span class="sxs-lookup"><span data-stu-id="e8a32-114">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="e8a32-115">チームは、上記で説明した、独自の更新プロセスと、更新プロセスではなく Word や Excel など、他のオフィス アプリケーションに依存します。</span><span class="sxs-lookup"><span data-stu-id="e8a32-115">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="e8a32-116">VDI のチームへの更新について教えてください。</span><span class="sxs-lookup"><span data-stu-id="e8a32-116">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="e8a32-117">チーム クライアント仮想デスクトップ インフラストラクチャ (VDI) では、VDI 以外のチームのクライアントがいることを自動的に更新されません。</span><span class="sxs-lookup"><span data-stu-id="e8a32-117">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="e8a32-118">[VDI のチームをインストール](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)する手順の説明に従って、新しい MSI をインストールすると、VM イメージを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8a32-118">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="e8a32-119">新しいバージョンに更新する現在のバージョンをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8a32-119">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="e8a32-120">管理者は、チームではなく更新プログラムを展開できる自動更新しますか?</span><span class="sxs-lookup"><span data-stu-id="e8a32-120">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="e8a32-121">チームは、管理者が任意のデリバリ メカニズムを通じて更新プログラムを展開することを得られないは。</span><span class="sxs-lookup"><span data-stu-id="e8a32-121">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>
