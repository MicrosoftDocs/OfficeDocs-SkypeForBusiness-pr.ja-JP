---
title: Skype for Business Server システムのインストールまたは更新
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDeploySystem
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6ea5158-aaa0-4c2f-aeac-c0dfa1718d7c
description: インストールを開始する、またはビジネス サーバー 2015 の Skype の既存の配置を更新するには、ビジネスのサーバーのインストールまたは Skype の更新をクリックします。 このセクションの手順では、トポロジ ビルダー ドキュメントに基づいて、特定のサーバー ロールに特定のコンポーネントがインストールされます。 この一連の手順を開始する前に、トポロジ ビルダーで、配置を定義する必要があります。 展開先のコンピューターに、ローカル管理者として、およびサーバーが配置されているドメインの Domain Admins グループのメンバーとしてログインすることも必要です。 コンピューターは、この手順を完了する前にドメインに参加させる必要があります。
ms.openlocfilehash: ef6b9cd31340d96b2cb989e7a9db5b6851932d4b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23263845"
---
# <a name="install-or-update-skype-for-business-server-system"></a><span data-ttu-id="4f37c-107">Skype for Business Server システムのインストールまたは更新</span><span class="sxs-lookup"><span data-stu-id="4f37c-107">Install or Update Skype for Business Server System</span></span>

<span data-ttu-id="4f37c-108">インストールを開始する、またはビジネス サーバー 2015 の Skype の既存の配置を更新するには、**ビジネスのサーバーの更新の Skype をインストールまたは**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f37c-108">To begin the installation, or to update an existing deployment of Skype for Business Server 2015, click **Install or Update Skype for Business Server**.</span></span> <span data-ttu-id="4f37c-109">このセクションの手順では、トポロジ ビルダー ドキュメントに基づいて、特定のサーバー ロールに特定のコンポーネントがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4f37c-109">The steps in this section will install components specific to a given server role, based on the Topology Builder document.</span></span> <span data-ttu-id="4f37c-110">この一連の手順を開始する前に、トポロジ ビルダーで、配置を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f37c-110">Before you begin this series of steps, you must define the deployment in Topology Builder.</span></span> <span data-ttu-id="4f37c-111">展開先のコンピューターに、ローカル管理者として、およびサーバーが配置されているドメインの Domain Admins グループのメンバーとしてログインすることも必要です。</span><span class="sxs-lookup"><span data-stu-id="4f37c-111">You must be logged into the computer that you are deploying as the local administrator and as a member of the Domain Admins group in the domain where the server is located.</span></span> <span data-ttu-id="4f37c-112">コンピューターは、この手順を完了する前にドメインに参加させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f37c-112">The computer must be joined to the domain prior to completing this step.</span></span>

<span data-ttu-id="4f37c-113">展開済みのサーバーを更新する場合は、トポロジ ビルダーで作成する変更を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f37c-113">If you are updating a currently deployed server, you must make the changes that you intend to make in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f37c-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f37c-114">See also</span></span>

[<span data-ttu-id="4f37c-115">展開</span><span class="sxs-lookup"><span data-stu-id="4f37c-115">Deployment</span></span>](https://technet.microsoft.com/library/83bd43ee-c1fe-4b38-bfa7-3eb382817bf9.aspx)