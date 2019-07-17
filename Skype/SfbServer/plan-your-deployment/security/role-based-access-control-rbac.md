---
title: Skype for Business Server の役割ベースのアクセス制御 (RBAC)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d01fba36-eb7e-4de9-9bba-5102ae157820
description: Skype for Business Server には役割ベースのアクセス制御 (RBAC) グループが含まれているので、セキュリティの高い標準を維持しながら、管理タスクを委任できます。 これらのグループはフォレストの準備の際に作成されます。 フォレストの準備の詳細については、「Skype for Business Server の Active Directory ドメインサービス」を参照してください。 フォレストの準備によって作成される特定のグループの詳細については、展開ドキュメントの「Skype for Business Server でのフォレストの準備による変更」を参照してください。
ms.openlocfilehash: d5f31d7c53c743e4b2d001b00abec7ec93ef8d91
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2019
ms.locfileid: "35759016"
---
# <a name="role-based-access-control-rbac-for-skype-for-business-server"></a><span data-ttu-id="9770a-106">Skype for Business Server の役割ベースのアクセス制御 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="9770a-106">Role-based access control (RBAC) for Skype for Business Server</span></span>
 
<span data-ttu-id="9770a-107">Skype for Business Server には役割ベースのアクセス制御 (RBAC) グループが含まれているので、セキュリティの高い標準を維持しながら、管理タスクを委任できます。</span><span class="sxs-lookup"><span data-stu-id="9770a-107">Skype for Business Server includes Role-Based Access Control (RBAC) groups to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="9770a-108">これらのグループはフォレストの準備の際に作成されます。</span><span class="sxs-lookup"><span data-stu-id="9770a-108">These groups are created during forest preparation.</span></span> <span data-ttu-id="9770a-109">フォレストの準備の詳細については、「 [Skype For Business Server の Active Directory ドメインサービス](active-directory-domain-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9770a-109">For details about forest preparation, see [Active Directory Domain Services for Skype for Business Server](active-directory-domain-services.md).</span></span> <span data-ttu-id="9770a-110">フォレストの準備によって作成される特定のグループの詳細については、展開ドキュメントの「 [Skype For Business Server でのフォレストの準備による変更](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9770a-110">For details about the specific groups created by forest preparation, see [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>
  
<span data-ttu-id="9770a-111">RBAC では、管理者特権が与えられているのは、事前に定義された管理者ロールにユーザーを割り当てることによって、多くの一般的な管理タスクに適用される11定義済みのロールを含むことです</span><span class="sxs-lookup"><span data-stu-id="9770a-111">With RBAC, administrative privilege is granted by assigning users to pre-defined administrative roles, including the 11 predefined roles that cover many common administrative tasks.</span></span> <span data-ttu-id="9770a-112">各役割は、その役割のユーザーが実行できる Skype for Business Server 管理シェルコマンドレットの特定のリストに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="9770a-112">Each role is associated with a specific list of Skype for Business Server Management Shell cmdlets that users in that role are allowed to run.</span></span> <span data-ttu-id="9770a-113">RBAC を使うと、ユーザーに対して、自分のジョブで必要な管理機能のみが与えられる、"最低限の権限" の原則に従うことができます。</span><span class="sxs-lookup"><span data-stu-id="9770a-113">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative abilities that their jobs require.</span></span> 
  
<span data-ttu-id="9770a-114">RBAC ロールの詳細については[、「ロールベースのアクセス制御の計画」を](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control)参照してください。</span><span class="sxs-lookup"><span data-stu-id="9770a-114">More details on RBAC roles can be found at [Planning for role-based access control](https://docs.microsoft.com/lyncserver/lync-server-2013-planning-for-role-based-access-control).</span></span>
