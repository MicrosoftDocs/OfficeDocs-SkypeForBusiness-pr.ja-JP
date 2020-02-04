---
title: 証明書の要求、インストール、または割り当て
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
description: '手順 3: [実行] をクリックすると、証明書ウィザードが開始されます。 ウィザードを使用して構成される証明書は、トポロジビルダーで構成され、中央管理ストアに公開されている Skype for Business Server 2015 トポロジの定義に基づいています。 組織内のオンライン証明機関 (CA) に対して証明書ウィザードを正常に実行するには、コンピューターのローカル管理者グループのメンバーであるユーザーとしてコンピューターにログオンしている必要があります。 また、コンピューターと CA が存在するドメインで、認証されたドメインユーザーである必要があります。 証明書ウィザードでは、組織の CA にアクセスするための代替資格情報を指定することができます。'
ms.openlocfilehash: b5d3c224142d4e457f584faa440b4fd4000497b3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687290"
---
# <a name="request-install-or-assign-certificates"></a><span data-ttu-id="90aca-107">証明書の要求、インストール、または割り当て</span><span class="sxs-lookup"><span data-stu-id="90aca-107">Request, Install, or Assign Certificates</span></span>
 
 <span data-ttu-id="90aca-108">**手順 3:** [**実行**] をクリックすると、証明書ウィザードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="90aca-108">**Step 3: Request, Install or Assign Certificates** starts the Certificate Wizard when you click **Run**.</span></span> <span data-ttu-id="90aca-109">ウィザードを使用して構成される証明書は、トポロジビルダーで構成され、中央管理ストアに公開されている Skype for Business Server 2015 トポロジの定義に基づいています。</span><span class="sxs-lookup"><span data-stu-id="90aca-109">The certificates that are configured through the wizard are based on the definition of the Skype for Business Server 2015 topology that is configured and published by Topology Builder to the Central Management store.</span></span> <span data-ttu-id="90aca-110">組織内のオンライン証明機関 (CA) に対して証明書ウィザードを正常に実行するには、コンピューターのローカル管理者グループのメンバーであるユーザーとしてコンピューターにログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="90aca-110">To successfully run the Certificate Wizard for an online certification authority (CA) in your organization, you must be logged on to the computer as a user who is a member of the computer local administrators group.</span></span> <span data-ttu-id="90aca-111">また、コンピューターと CA が存在するドメインで、認証されたドメインユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="90aca-111">You must also be an authenticated Domain User in the domain where the computer and the CA exist.</span></span> <span data-ttu-id="90aca-112">証明書ウィザードでは、組織の CA にアクセスするための代替資格情報を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="90aca-112">The certificate wizard does provide the ability to specify alternate credentials for access your organization's CA.</span></span>
  
> [!NOTE]
> <span data-ttu-id="90aca-p103">また、証明書ウィザードを使用して、パブリック CA や他のオフライン公開キー基盤 (PKI) に送信されるオフライン証明書要求を要求して処理することはできません。コンピューターへのログオンで必要なメンバーシップ以外に、オフライン要求を生成するために必要な特定のグループ メンバーシップはありません。パブリック CA の応答を処理し、証明書をコンピューターと役割に割り当てるには、ローカルの Administrators グループのメンバーかそれと同等のユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="90aca-p103">You can also use the Certificate Wizard to request and process offline certificate requests that are sent to a public CA or other offline public key infrastructure (PKI). There are no specific group memberships, other than those needed to log on to the computer, to generate an offline request. To process the public CA response and to assign the certificate to the computer and role, you must be logged on as a member of the local Administrators group or equivalent.</span></span> 
  

