---
title: 監視サーバーの関連付けの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 監視サーバーを削除するには、オフに関連付けられているフロント エンド プール、フロント エンド サーバー、リカバリ性に優れたブランチ アプライアンスおよび存続可能ブランチ サーバーへの依存関係を変更する必要があります。 依存関係を削除するのにはフロント エンド サーバー、リカバリ性に優れたブランチ アプライアンスおよび存続可能ブランチ サーバー、フロント エンド プールのプロパティを編集するとします。 依存関係をオフにし、トポロジ ビルダーでサーバーを削除した後、トポロジ ビルダーに関連付けられているデータベース ストアのオブジェクトも削除されることが通知されます。
ms.openlocfilehash: 854e95969d08d14d626bb374073091ae4ae39630
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231459"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="34733-105">監視サーバーの関連付けの削除</span><span class="sxs-lookup"><span data-stu-id="34733-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="34733-106">監視サーバーを削除するにはオフに、関連付けられているフロント エンド プール、フロント エンド サーバー、ブランチ アプライアンスのリカバリ性に優れた、および存続可能ブランチ サーバーへの依存関係を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34733-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="34733-107">フロント エンド プール、フロント エンド サーバー、ブランチ アプライアンスのリカバリ性に優れた、および依存関係を削除するのには、存続可能ブランチ サーバーのプロパティを編集するとします。</span><span class="sxs-lookup"><span data-stu-id="34733-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="34733-108">依存関係をオフにし、トポロジ ビルダーでサーバーを削除した後、トポロジ ビルダーに関連付けられているデータベース ストアのオブジェクトも削除されることが通知されます。</span><span class="sxs-lookup"><span data-stu-id="34733-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="34733-109">監視サーバーの関連付けを削除するのには</span><span class="sxs-lookup"><span data-stu-id="34733-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="34733-110">ビジネス 2019 フロント エンド サーバーの Skype、トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="34733-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="34733-111">バージョンのインストール] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="34733-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="34733-112">トポロジ ビルダーでは、監視サーバーが定義されているによって**エンタープライズ エディションのフロント エンド プール**、**標準的なフロント エンド サーバーのエディション**、または**ブランチ サイト**を展開します。</span><span class="sxs-lookup"><span data-stu-id="34733-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="34733-113">ある場合は、存続可能ブランチ サーバーが関連付けられている場合は、**ブランチ サイト**を展開し、支社のサイト名を展開して**ブランチ アプライアンスのリカバリ性に優れた**を展開してください。</span><span class="sxs-lookup"><span data-stu-id="34733-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="34733-114">**ブランチ アプライアンスのリカバリ性に優れた**ユーザー ・ インタ フェースは、存続可能ブランチ サーバーとブランチのリカバリ性に優れたアプライアンスの両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="34733-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="34733-115">プール、サーバー、または、サーバーの監視に関連付けられているデバイスを右クリックし、 **[プロパティの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34733-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="34733-116">**プロパティの編集**、 **[全般**] の下で > **の関連付け**では、**監視サーバーを関連付ける**] チェック ボックスをオフにし、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34733-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="34733-117">他のプール、サーバー、またはサーバーの監視に関連付けられているデバイスの前の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="34733-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="34733-118">監視サーバーを右クリックし、し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34733-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="34733-119">**依存するストアを削除する**には、[ **OK**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34733-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="34733-120">トポロジを公開、レプリケーション ・ ステータスを確認、Skype を必要に応じてビジネス サーバーの展開ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="34733-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

