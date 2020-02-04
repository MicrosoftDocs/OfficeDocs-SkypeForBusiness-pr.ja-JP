---
title: スキーマ パーティションのレプリケーションの確認
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: Active Directory ドメインサービスフォレストでスキーマ拡張が正常にレプリケートされたことを確認するには、次の手順を実行します。
ms.openlocfilehash: 0b90f61849e66e78c49d7d00783133198bab6b54
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687320"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="0ac05-103">スキーマ パーティションのレプリケーションの確認</span><span class="sxs-lookup"><span data-stu-id="0ac05-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="0ac05-104">Active Directory ドメインサービスフォレストでスキーマ拡張が正常にレプリケートされたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0ac05-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="0ac05-105">Active Directory ドメインサービスフォレストのドメインコントローラー (スキーママスターの役割を保持しているドメインコントローラー以外) にログオンします。ここでは、スキーマの拡張機能が Enterprise Admins グループのメンバーとして適用されています。</span><span class="sxs-lookup"><span data-stu-id="0ac05-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="0ac05-106">ADSI の編集を開く: [**スタート**] をクリックし、[**管理ツール**] をクリックして、[ **adsi の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ac05-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="0ac05-107">または、[**スタート**] をクリックし、[**実行**] をクリックします。次に、「 **adsiedit** 」と入力して ADSI エディターを起動します。</span><span class="sxs-lookup"><span data-stu-id="0ac05-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="0ac05-108">Microsoft 管理コンソール (MMC) ツリーでまだ選択されていない場合は、[ADSI Edit] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ac05-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="0ac05-109">[**アクション**] メニューで、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ac05-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="0ac05-110">[**接続の設定**] ダイアログ ボックスの [**既知の名前付けコンテキストを選択する**] で、[**スキーマ**] を選択して [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ac05-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="0ac05-111">スキーマ コンテナーで、CN=ms-RTC-SIP-SchemaVersion を検索します。</span><span class="sxs-lookup"><span data-stu-id="0ac05-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="0ac05-112">このオブジェクトが存在し、 **Rangeupper**属性の値が1150であり、 **rangeupper**属性の値が3の場合は、スキーマが正常に更新され、複製されています。</span><span class="sxs-lookup"><span data-stu-id="0ac05-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="0ac05-113">このオブジェクトが存在しない場合、または**Rangeupper**属性と**rangeupper**属性の値が指定されていない場合は、スキーマが変更されていないか、複製されていません。</span><span class="sxs-lookup"><span data-stu-id="0ac05-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0ac05-114">スキーマの複製を確認しても正常な複製が表示されない場合は、約15分待ってからもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="0ac05-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="0ac05-115">Active Directory のレプリケーションは、緩やかな一貫性モデルに基づいており、サーバーとインフラストラクチャのさまざまな要因に基づいて、いくつかのレプリケーション待ち時間が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ac05-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

