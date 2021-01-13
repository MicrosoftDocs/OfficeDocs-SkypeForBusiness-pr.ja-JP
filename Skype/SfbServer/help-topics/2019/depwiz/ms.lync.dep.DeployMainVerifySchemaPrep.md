---
title: スキーマ パーティションのレプリケーションの確認
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: スキーマ拡張機能が Active Directory ドメイン サービス フォレストに正常にレプリケートされたことを確認するには、次の手順を実行します。
ms.openlocfilehash: 4e4bfdf4fb50366f831f029d8f331551ba906969
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801567"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="611eb-103">スキーマ パーティションのレプリケーションの確認</span><span class="sxs-lookup"><span data-stu-id="611eb-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="611eb-104">スキーマ拡張機能が Active Directory ドメイン サービス フォレストに正常にレプリケートされたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="611eb-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="611eb-105">スキーマ拡張機能が Enterprise Admins グループのメンバーとして適用された Active Directory ドメイン サービス フォレスト内のドメイン コントローラー (スキーマ マスターの役割を持つドメイン コントローラー以外) にログオンします。</span><span class="sxs-lookup"><span data-stu-id="611eb-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="611eb-106">[**スタート**] をクリックして [**管理ツール**] をクリックし、[**ADSI エディター**] をクリックして ADSI エディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="611eb-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="611eb-107">または [**スタート**] をクリックして [**ファイル名を指定して実行**] をクリックし、「**adsiedit.msc**」と入力して ADSI エディターを起動します。</span><span class="sxs-lookup"><span data-stu-id="611eb-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="611eb-108">Microsoft 管理コンソール (MMC) ツリーで、まだ選択されていない場合には [ADSI エディタ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="611eb-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="611eb-109">**[アクション]** メニューで、**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="611eb-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="611eb-110">[**接続の設定**] ダイアログ ボックスの [**既知の名前付けコンテキストを選択する**] で、[**スキーマ**] を選択して [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="611eb-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="611eb-p101">スキーマ コンテナーで、CN=ms-RTC-SIP-SchemaVersion を検索します。このオブジェクトが存在し、**rangeUpper** 属性の値が 1150 で、**rangeLower** 属性の値が 3 の場合、スキーマは正しく更新され、レプリケートされています。このオブジェクトが存在しないか、**rangeUpper** および **rangeLower** 属性の値が指定された値と異なる場合、スキーマは変更されていないか、レプリケートされていません。</span><span class="sxs-lookup"><span data-stu-id="611eb-p101">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion. If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated. If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="611eb-114">スキーマのレプリケーションが成功したことを確認できなかった場合は、およそ 15 分待ってからもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="611eb-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="611eb-115">Active Directory レプリケーションは、緩やかな一貫性モデルに基づいており、サーバーとインフラストラクチャの多くの要因に基づいて、一部のレプリケーション遅延が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="611eb-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

