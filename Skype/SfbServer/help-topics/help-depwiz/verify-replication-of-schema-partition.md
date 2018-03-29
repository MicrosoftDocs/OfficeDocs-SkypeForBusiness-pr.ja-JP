---
title: スキーマ パーティションのレプリケーションを確認します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: Active Directory ドメイン サービス フォレストでスキーマ拡張機能が正常にレプリケートされていることを確認するには、次の操作を行います。
ms.openlocfilehash: a5628e369ffc796affe9984cef8ecb1ba044ec8a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="7caea-103">スキーマ パーティションのレプリケーションを確認します。</span><span class="sxs-lookup"><span data-stu-id="7caea-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="7caea-104">Active Directory ドメイン サービス フォレストでスキーマ拡張機能が正常にレプリケートされていることを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7caea-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="7caea-105">Enterprise Admins グループのメンバーとして、スキーマの拡張機能が適用された場所、Active Directory ドメイン サービス フォレスト内ドメイン コント ローラー (ただし、スキーマ マスターの役割を保持しているドメイン コント ローラー) にログオンします。</span><span class="sxs-lookup"><span data-stu-id="7caea-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="7caea-106">ADSI 編集を開く: [**スタート**] ボタン、 **[管理ツール**] をクリックし、[ **ADSI Edit**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7caea-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7caea-107">または、**開始**] をクリックし、**実行**、ADSI Edit を起動するのには入力**ファイル名を指定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7caea-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="7caea-108">Microsoft 管理コンソール (MMC) ツリーで、選択されていない場合は、ADSI Edit] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7caea-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="7caea-109">[**アクション**] メニューで、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7caea-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="7caea-110">[**接続の設定**] ダイアログ ボックスの [**既知の名前付けコンテキストを選択する**] で、[**スキーマ**] を選択して [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7caea-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="7caea-111">[スキーマ] コンテナーを探します CN = ms の RTC の SIP を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="7caea-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="7caea-112">、このオブジェクトが存在し、 **rangeUpper**属性の値は、1150、 **rangeLower**属性の値は 3、スキーマが正常に更新し、レプリケートします。</span><span class="sxs-lookup"><span data-stu-id="7caea-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="7caea-113">**RangeLower**し、 **rangeUpper**属性の値として使用されてない場合またはこのオブジェクトが存在しない場合を指定し、スキーマが変更されていないまたはレプリケートされていません。</span><span class="sxs-lookup"><span data-stu-id="7caea-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7caea-114">スキーマのレプリケーションのチェックが正常に複製をまだ表示されていない場合は、約 15 分間待機し、再び確認します。</span><span class="sxs-lookup"><span data-stu-id="7caea-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="7caea-115">Active Directory のレプリケーションはゆるやかな一貫性モデルに基づくし、いくつかのサーバーとインフラストラクチャの要因に基づくいくつかのレプリケーションの遅延が発生することが。</span><span class="sxs-lookup"><span data-stu-id="7caea-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

