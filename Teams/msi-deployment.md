---
title: MSI を使用して Microsoft Teams をインストールする
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 管理者は Teams MSI を使用して、Microsoft Teams を選択したユーザーまたはコンピューターに一括展開することができます。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78ceb6fa0cd70b5cf6fc25bc9537939beea99b7c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882039"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="5b330-103">MSI を使用して Microsoft Teams をインストールする</span><span class="sxs-lookup"><span data-stu-id="5b330-103">Install Microsoft Teams using MSI</span></span>
=================================

<span data-ttu-id="5b330-104">System Center Configuration Manager、またはグループ ポリシー、または任意のサードパーティの配布メカニズムを広範囲の展開に使用するために、マイクロソフトは管理者が選択したユーザーまたはコンピューターへの Teams の一括展開で使用することができる MSI ファイル ([32-bit](https://aka.ms/teams32bitmsi) と [64-bit](https://aka.ms/teams64bitmsi) の両方) を提供しています。</span><span class="sxs-lookup"><span data-stu-id="5b330-104">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="5b330-105">管理者はこれらのファイルを使用してリモートで Teams を展開することができます。このため、ユーザーは Teams アプリを手動でダウンロードする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="5b330-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="5b330-106">展開した場合、Teams はそのマシンにサインインするすべてのユーザーに対して自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="5b330-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="5b330-107">コンピューターにパッケージを展開して、マシンの新しいユーザー全員がこの展開のメリットを得られるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5b330-107">We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="5b330-108">SCCM の詳細については、「[System Center Configuration Manager の概要](https://docs.microsoft.com/sccm/core/understand/introduction)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5b330-108">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="5b330-109">展開の手順 (推奨)</span><span class="sxs-lookup"><span data-stu-id="5b330-109">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="5b330-110">最新のパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="5b330-110">Retrieve the latest package.</span></span>
2. <span data-ttu-id="5b330-111">MSI によって事前に入力された既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="5b330-111">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="5b330-112">可能な場合、コンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="5b330-112">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="5b330-113">Microsoft Teams MSI パッケージがどのように機能するか</span><span class="sxs-lookup"><span data-stu-id="5b330-113">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="5b330-114">Teams MSI はインストーラーを Program Files に配置します。</span><span class="sxs-lookup"><span data-stu-id="5b330-114">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="5b330-115">ユーザーが新しい Windows ユーザー プロファイルにサインインするときは常に、インストーラーが起動して Teams アプリケーションのコピーがそのユーザーのアプリデータ フォルダーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5b330-115">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="5b330-116">ユーザーが既にアプリデータ フォルダーに Teams アプリをインストール済みの場合、MSI インストーラーはそのユーザーについてはプロセスをスキップします。</span><span class="sxs-lookup"><span data-stu-id="5b330-116">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="5b330-117">更新プログラムを展開するのに MSI を使用しないでください。クライアントは、サービスから利用可能な新しいバージョンを見つけたら、自動更新します。</span><span class="sxs-lookup"><span data-stu-id="5b330-117">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="5b330-118">最新のインストーラーを再展開するには、以下に説明されている MSI の再展開のプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b330-118">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="5b330-119">MSI パッケージの以前のバージョンを展開すると、クライアントは自動更新をそのユーザーで可能なときに実行します。</span><span class="sxs-lookup"><span data-stu-id="5b330-119">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="5b330-120">かなり昔のバージョンが展開された場合、MSI はユーザーが Teams を使用できる状態になる前にアプリケーションの更新を開始します。</span><span class="sxs-lookup"><span data-stu-id="5b330-120">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="5b330-121">既定のインストール場所を変更することは、更新フローが崩れる可能性があるため、お勧めしません。</span><span class="sxs-lookup"><span data-stu-id="5b330-121">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="5b330-122">かなり昔のバージョンを利用すると、ユーザーがサービスにアクセスするのを妨げる結果になってしまいます。</span><span class="sxs-lookup"><span data-stu-id="5b330-122">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="5b330-123">ターゲット コンピューターの要件</span><span class="sxs-lookup"><span data-stu-id="5b330-123">Target computer requirements</span></span>

- <span data-ttu-id="5b330-124">.NET Framework 4.5 以降</span><span class="sxs-lookup"><span data-stu-id="5b330-124">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="5b330-125">Windows 7 以降</span><span class="sxs-lookup"><span data-stu-id="5b330-125">Windows 7 or later</span></span>
- <span data-ttu-id="5b330-126">各ユーザー プロファイルで 3 GB のディスク容量 (推奨)</span><span class="sxs-lookup"><span data-stu-id="5b330-126">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="5b330-127">クリーン アップと展開の手順</span><span class="sxs-lookup"><span data-stu-id="5b330-127">Clean up and redeployment procedure</span></span>
<span data-ttu-id="5b330-128">ユーザーがユーザー プロファイルから Teams をアンインストールすると、MSI のインストーラーは、そのユーザーが Teams アプリをアンインストールしたことと、そのユーザー プロファイルで今後 Teams をインストールする機会がないことを記録します。</span><span class="sxs-lookup"><span data-stu-id="5b330-128">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="5b330-129">このユーザーのために Teams がアンインストールされた特定のコンピューター上でユーザーを再展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5b330-129">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="5b330-130">それぞれのユーザー プロファイルでインストールされている Teams アプリをすべてアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="5b330-130">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="5b330-131">アンインストール後、%localappdata%\Microsoft\Teams\ 以下のディレクトリを再帰的に削除します。</span><span class="sxs-lookup"><span data-stu-id="5b330-131">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="5b330-132">MSI パッケージをその特定のコンピューターに再展開します。</span><span class="sxs-lookup"><span data-stu-id="5b330-132">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="5b330-133">[Microsoft Teams の展開のクリーン アップ](.\scripts\Powershell-script-teams-deployment-clean-up.md) スクリプトを使用して、SCCM を介して手順 1 と 2 を完了することができます。</span><span class="sxs-lookup"><span data-stu-id="5b330-133">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>                              

