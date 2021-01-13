---
title: 証明書の要求、インストール、または割り当て
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
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
description: '手順 3: [実行] をクリックすると、証明書の要求、インストール、または割り当てによって証明書ウィザードが起動します。 ウィザードを使用して構成される証明書は、トポロジ ビルダーによって構成および中央管理ストアに公開される Skype for Business Server 2015 トポロジの定義に基づいて行います。 組織内のオンライン証明機関 (CA) の証明書ウィザードを正常に実行するには、コンピューターのローカル管理者グループのメンバーであるユーザーとしてコンピューターにログオンする必要があります。 コンピューターと CA が存在するドメインの認証されたドメイン ユーザーである必要があります。 証明書ウィザードは、組織の CA にアクセスするための代替資格情報を指定する機能を提供します。'
ms.openlocfilehash: 278aea23430d2fad39c355f03c7512a76ab9cbee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829717"
---
# <a name="request-install-or-assign-certificates"></a><span data-ttu-id="01225-107">証明書の要求、インストール、または割り当て</span><span class="sxs-lookup"><span data-stu-id="01225-107">Request, Install, or Assign Certificates</span></span>
 
 <span data-ttu-id="01225-108">**手順 3: [実行] をクリックすると** 、証明書の要求、インストール、または割り当てによって証明書ウィザードが **起動します**。</span><span class="sxs-lookup"><span data-stu-id="01225-108">**Step 3: Request, Install or Assign Certificates** starts the Certificate Wizard when you click **Run**.</span></span> <span data-ttu-id="01225-109">ウィザードを使用して構成される証明書は、トポロジ ビルダーによって構成および中央管理ストアに公開される Skype for Business Server 2015 トポロジの定義に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="01225-109">The certificates that are configured through the wizard are based on the definition of the Skype for Business Server 2015 topology that is configured and published by Topology Builder to the Central Management store.</span></span> <span data-ttu-id="01225-110">組織内のオンライン証明機関 (CA) の証明書ウィザードを正常に実行するには、コンピューターのローカル管理者グループのメンバーであるユーザーとしてコンピューターにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01225-110">To successfully run the Certificate Wizard for an online certification authority (CA) in your organization, you must be logged on to the computer as a user who is a member of the computer local administrators group.</span></span> <span data-ttu-id="01225-111">コンピューターと CA が存在するドメインの認証されたドメイン ユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="01225-111">You must also be an authenticated Domain User in the domain where the computer and the CA exist.</span></span> <span data-ttu-id="01225-112">証明書ウィザードでは、組織の CA にアクセスするための代替資格情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="01225-112">The certificate wizard does provide the ability to specify alternate credentials for access your organization's CA.</span></span>
  
> [!NOTE]
> <span data-ttu-id="01225-p103">また、証明書ウィザードを使用して、パブリック CA や他のオフライン公開キー基盤 (PKI) に送信されるオフライン証明書要求を要求して処理することはできません。コンピューターへのログオンで必要なメンバーシップ以外に、オフライン要求を生成するために必要な特定のグループ メンバーシップはありません。パブリック CA の応答を処理し、証明書をコンピューターと役割に割り当てるには、ローカル管理者グループのメンバーかそれと同等のユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01225-p103">You can also use the Certificate Wizard to request and process offline certificate requests that are sent to a public CA or other offline public key infrastructure (PKI). There are no specific group memberships, other than those needed to log on to the computer, to generate an offline request. To process the public CA response and to assign the certificate to the computer and role, you must be logged on as a member of the local Administrators group or equivalent.</span></span> 
  

