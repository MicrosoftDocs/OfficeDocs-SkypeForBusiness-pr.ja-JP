---
title: アーカイブ サーバーの関連付けの削除
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: アーカイブサーバーを削除するには、関連付けられているフロントエンドプール、フロントエンドサーバー、存続可能ブランチアプライアンス、および存続可能ブランチサーバーの依存関係を変更またはクリアする必要があります。 依存関係を削除するには、フロントエンドプール、フロントエンドサーバー、存続可能 Branch Appliance、存続可能 Branch Server の各プロパティを編集します。 依存関係をクリアし、トポロジビルダーでサーバーを削除すると、トポロジビルダー内の関連付けられたデータベースストアオブジェクトも削除されることが通知されます。
ms.openlocfilehash: bba21dadc70f5c9f62fea5073ef5bf815c8b35a1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752139"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="e50d0-105">アーカイブ サーバーの関連付けの削除</span><span class="sxs-lookup"><span data-stu-id="e50d0-105">Remove the Archiving server association</span></span>

<span data-ttu-id="e50d0-106">アーカイブサーバーを削除するには、関連付けられているフロントエンドプール、フロントエンドサーバー、存続可能ブランチアプライアンス、および存続可能ブランチサーバーの依存関係を変更またはクリアする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e50d0-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="e50d0-107">依存関係を削除するには、フロントエンドプール、フロントエンドサーバー、存続可能 Branch Appliance、存続可能 Branch Server の各プロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="e50d0-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="e50d0-108">トポロジビルダーで依存関係をクリアし、サーバーを削除すると、トポロジビルダー内の関連付けられたデータベースストアオブジェクトも削除されることが通知されます。</span><span class="sxs-lookup"><span data-stu-id="e50d0-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="e50d0-109">アーカイブサーバーの関連付けを削除するには</span><span class="sxs-lookup"><span data-stu-id="e50d0-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="e50d0-110">Skype for Business Server 2019 フロントエンドサーバーで、トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="e50d0-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="e50d0-111">従来のインストールノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="e50d0-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="e50d0-112">トポロジビルダーで、アーカイブサーバーが定義されている場所に応じて、 **Enterprise Edition フロントエンドプール**、 **Standard Edition フロントエンドサーバー**、または**ブランチサイト**を展開します。</span><span class="sxs-lookup"><span data-stu-id="e50d0-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="e50d0-113">存続可能 Branch Server が関連付けられている場合は、[**ブランチサイト**] を展開し、[ブランチサイト] を展開して、[**存続可能ブランチアプライアンス**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="e50d0-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e50d0-114">ユーザーインターフェイスの**存続可能 Branch アプライアンス**は、存続可能 branch Server と存続可能 branch Appliance の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e50d0-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="e50d0-115">アーカイブサーバーに関連付けられているプール、サーバー、またはデバイスを右クリックし、[**プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e50d0-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="e50d0-116">[**プロパティの編集**] の [**一般的な**関連付け] で、[  >  **Associations\*\*\*\*アーカイブサーバーの関連付け**] チェックボックスをオフにして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e50d0-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="e50d0-117">削除するアーカイブサーバーに関連付けられているその他のプール、サーバー、またはデバイスに対して、前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e50d0-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="e50d0-118">アーカイブサーバーを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e50d0-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="e50d0-119">[**依存ストアの削除**] で、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e50d0-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="e50d0-120">トポロジを公開し、レプリケーションの状態を確認してから、必要に応じて Skype for Business Server 展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="e50d0-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

