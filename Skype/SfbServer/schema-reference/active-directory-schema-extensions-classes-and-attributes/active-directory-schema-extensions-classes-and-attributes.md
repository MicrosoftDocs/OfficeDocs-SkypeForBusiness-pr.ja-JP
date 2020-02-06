---
title: ディレクトリ スキーマの拡張、クラスおよび属性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: このリファレンスセクションには、次の情報が含まれています。
ms.openlocfilehash: 98ce04f38d9ee6c572f517441a370823ab7647d5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815555"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="4c637-103">ディレクトリ スキーマの拡張、クラスおよび属性</span><span class="sxs-lookup"><span data-stu-id="4c637-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="4c637-104">このリファレンスセクションには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4c637-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="4c637-105">Skype for Business Server の新規または変更された Active Directory スキーマの拡張機能</span><span class="sxs-lookup"><span data-stu-id="4c637-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="4c637-106">Active Directory のスキーマには、Active Directory フォレストで作成できるすべてのオブジェクトクラスの正式な定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4c637-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="4c637-107">また、スキーマには、Active Directory オブジェクトに存在できるすべての属性の正式な定義も含まれています。</span><span class="sxs-lookup"><span data-stu-id="4c637-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="4c637-108">Active Directory のグローバルカタログには、フォレストのすべてのオブジェクトのレプリカと、各オブジェクトの属性のサブセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4c637-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="4c637-109">このセクションでは、Skype for Business Server で新規または変更されたクラスと属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c637-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="4c637-110">Skype for Business Server で使用されるすべてのクラスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4c637-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="4c637-111">Skype for Business Server で使用されるすべての属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c637-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="4c637-112">Skype for Business Server で使用されるクラスの一覧と、それぞれに含まれる可能性のある属性</span><span class="sxs-lookup"><span data-stu-id="4c637-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="4c637-113">グローバル設定とオブジェクト、およびフォレストの準備の際に作成されるユニバーサルサービスと管理グループに加えて、</span><span class="sxs-lookup"><span data-stu-id="4c637-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="4c637-114">ドメインの準備中にドメインルートと組み込みのコンテナー上に作成されるアクセス制御エントリ (Ace)</span><span class="sxs-lookup"><span data-stu-id="4c637-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="4c637-115">Active Directory 組織単位 (OU) で行われた変更は、Grant_CsSetupPermission コマンドレットによって変更されます。</span><span class="sxs-lookup"><span data-stu-id="4c637-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="4c637-116">Grant_CsOUPermission コマンドレットによって Active Directory OU で行われる変更</span><span class="sxs-lookup"><span data-stu-id="4c637-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="4c637-117">このセクション中</span><span class="sxs-lookup"><span data-stu-id="4c637-117">In This Section</span></span>

- [<span data-ttu-id="4c637-118">Skype for Business Server でのスキーマの変更</span><span class="sxs-lookup"><span data-stu-id="4c637-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="4c637-119">Skype for Business Server のスキーマクラスと説明</span><span class="sxs-lookup"><span data-stu-id="4c637-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="4c637-120">Skype for Business Server のスキーマ属性と説明</span><span class="sxs-lookup"><span data-stu-id="4c637-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="4c637-121">Skype for Business Server のクラス別のスキーマ属性</span><span class="sxs-lookup"><span data-stu-id="4c637-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="4c637-122">Skype for Business Server でのフォレストの準備によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="4c637-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="4c637-123">Skype for Business Server のドメイン準備によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="4c637-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="4c637-124">Skype for Business Server で付与されたアクセス許可によって行われる変更</span><span class="sxs-lookup"><span data-stu-id="4c637-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="4c637-125">Skype for Business Server の権限付与によって行われた変更</span><span class="sxs-lookup"><span data-stu-id="4c637-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

