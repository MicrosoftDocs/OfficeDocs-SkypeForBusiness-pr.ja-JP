---
title: Skype for Business Server システムのインストールまたは更新
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainDeploySystem
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6ea5158-aaa0-4c2f-aeac-c0dfa1718d7c
description: インストールを開始するには、または Skype for Business Server 2015 の既存の展開を更新するには、[Skype for Business Server のインストールまたは更新] をクリックします。 このセクションの手順では、トポロジ ビルダー ドキュメントに基づいて、特定のサーバーの役割に固有のコンポーネントをインストールします。 この一連の手順を開始する前に、トポロジ ビルダーで展開を定義する必要があります。 展開先のコンピューターに、ローカル管理者として、およびサーバーが配置されているドメインの Domain Admins グループのメンバーとしてログインすることも必要です。 コンピューターは、この手順を完了する前にドメインに参加させる必要があります。
ms.openlocfilehash: 21e614e700d366273dd81edc405171216d338aa0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108713"
---
# <a name="install-or-update-skype-for-business-server-system"></a><span data-ttu-id="cdc27-107">Skype for Business Server システムのインストールまたは更新</span><span class="sxs-lookup"><span data-stu-id="cdc27-107">Install or Update Skype for Business Server System</span></span>

<span data-ttu-id="cdc27-108">インストールを開始するには、または Skype for Business Server 2015 の既存の展開を更新するには、[Skype for Business Server のインストールまたは更新] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cdc27-108">To begin the installation, or to update an existing deployment of Skype for Business Server 2015, click **Install or Update Skype for Business Server**.</span></span> <span data-ttu-id="cdc27-109">このセクションの手順では、トポロジ ビルダー ドキュメントに基づいて、特定のサーバーの役割に固有のコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cdc27-109">The steps in this section will install components specific to a given server role, based on the Topology Builder document.</span></span> <span data-ttu-id="cdc27-110">この一連の手順を開始する前に、トポロジ ビルダーで展開を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdc27-110">Before you begin this series of steps, you must define the deployment in Topology Builder.</span></span> <span data-ttu-id="cdc27-111">展開先のコンピューターに、ローカル管理者として、およびサーバーが配置されているドメインの Domain Admins グループのメンバーとしてログインすることも必要です。</span><span class="sxs-lookup"><span data-stu-id="cdc27-111">You must be logged into the computer that you are deploying as the local administrator and as a member of the Domain Admins group in the domain where the server is located.</span></span> <span data-ttu-id="cdc27-112">コンピューターは、この手順を完了する前にドメインに参加させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdc27-112">The computer must be joined to the domain prior to completing this step.</span></span>

<span data-ttu-id="cdc27-113">現在展開されているサーバーを更新する場合は、トポロジ ビルダーで行う予定の変更を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdc27-113">If you are updating a currently deployed server, you must make the changes that you intend to make in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="cdc27-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="cdc27-114">See also</span></span>

[<span data-ttu-id="cdc27-115">展開</span><span class="sxs-lookup"><span data-stu-id="cdc27-115">Deployment</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deployment)