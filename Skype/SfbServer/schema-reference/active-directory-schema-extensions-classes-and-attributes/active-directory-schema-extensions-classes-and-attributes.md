---
title: ディレクトリ スキーマの拡張、クラスおよび属性
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: このリファレンス セクションには、次の情報が含まれています。
ms.openlocfilehash: 37dee1a029a0d8872452082aebb9b8f0fcf2f072
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213404"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="6df57-103">ディレクトリ スキーマの拡張、クラスおよび属性</span><span class="sxs-lookup"><span data-stu-id="6df57-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="6df57-104">このリファレンス セクションには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6df57-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="6df57-105">新規または Skype のビジネス サーバーの変更は、アクティブなディレクトリ スキーマの拡張</span><span class="sxs-lookup"><span data-stu-id="6df57-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="6df57-106">Active Directory スキーマには、Active Directory フォレスト内に作成できるすべてのオブジェクト クラスの正式な定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6df57-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="6df57-107">スキーマには、Active Directory オブジェクト上に存在できるすべての属性の正式な定義も含まれています。</span><span class="sxs-lookup"><span data-stu-id="6df57-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="6df57-108">Active Directory グローバル カタログには、各オブジェクトの属性のサブセットのほかに、フォレストのすべてのオブジェクトのレプリカが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6df57-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="6df57-109">このセクションでは、クラスと属性を追加または変更された Skype のビジネス サーバーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6df57-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="6df57-110">Skype サーバーの使用ビジネス、それぞれの説明を持つすべてのクラス</span><span class="sxs-lookup"><span data-stu-id="6df57-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="6df57-111">Skype サーバーの使用ビジネス、それぞれの説明を持つすべての属性</span><span class="sxs-lookup"><span data-stu-id="6df57-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="6df57-112">Skype サーバーの使用ビジネス、それぞれの属性を持つクラスのリストが含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6df57-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="6df57-113">グローバル設定とオブジェクトの間に作成されたユニバーサル サービスと管理グループだけでなく、フォレストの準備</span><span class="sxs-lookup"><span data-stu-id="6df57-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="6df57-114">ドメインの準備中にドメイン ルートおよび組み込みコンテナーに作成されるアクセス制御エントリ (Ace)</span><span class="sxs-lookup"><span data-stu-id="6df57-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="6df57-115">Grant_CsSetupPermission コマンドレットによって、Active Directory の組織単位 (OU) に行われた変更です。</span><span class="sxs-lookup"><span data-stu-id="6df57-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="6df57-116">Grant_CsOUPermission コマンドレットで Active Directory OU に加えた変更ができます。</span><span class="sxs-lookup"><span data-stu-id="6df57-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="6df57-117">このセクション中</span><span class="sxs-lookup"><span data-stu-id="6df57-117">In This Section</span></span>

- [<span data-ttu-id="6df57-118">Skype ビジネス サーバーのスキーマの変更</span><span class="sxs-lookup"><span data-stu-id="6df57-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="6df57-119">スキーマのクラスおよび Skype のビジネス サーバー用の説明</span><span class="sxs-lookup"><span data-stu-id="6df57-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="6df57-120">スキーマの属性および Skype ビジネス サーバーの説明</span><span class="sxs-lookup"><span data-stu-id="6df57-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="6df57-121">Skype ビジネス サーバー用のクラスでのスキーマの属性</span><span class="sxs-lookup"><span data-stu-id="6df57-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="6df57-122">Skype でビジネス サーバーは、フォレストの準備によって加えられた変更</span><span class="sxs-lookup"><span data-stu-id="6df57-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="6df57-123">Skype のビジネス サーバー用のドメインの準備によって加えられた変更</span><span class="sxs-lookup"><span data-stu-id="6df57-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="6df57-124">Skype の許可-CsSetupPermission によるビジネス サーバーの変更</span><span class="sxs-lookup"><span data-stu-id="6df57-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="6df57-125">Skype の許可-CsOUPermission によるビジネス サーバーの変更</span><span class="sxs-lookup"><span data-stu-id="6df57-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

