---
title: CMS 設定の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.CmsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4b882923-ed6f-44f3-ad9c-aabad5a3bc00
description: 中央管理サーバーを、ある定義済みのフロントエンドのプールから別の定義済みのフロントエンドのプールに変更できます。 中央管理サーバーの場所を変更するには、[中央管理サーバーをインストールするフロントエンド サーバー] の下のドロップダウン リストからフロントエンド プールを選択します。 フロントエンド サーバーは、Enterprise Edition フロントエンドのプールまたは Standard Edition フロントエンド サーバーのいずれかにできます。
ms.openlocfilehash: 741bbee4d913066c0fb64fa30f4bfad2ced4d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833107"
---
# <a name="cms-settings-expander"></a><span data-ttu-id="6005e-105">CMS 設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="6005e-105">CMS Settings Expander</span></span>
 
<span data-ttu-id="6005e-p102">中央管理サーバーを、ある定義済みのフロントエンドのプールから別の定義済みのフロントエンドのプールに変更できます。中央管理サーバーの場所を変更するには、[**中央管理サーバーをインストールするフロントエンド サーバー**] の下のドロップダウン リストからフロントエンド プールを選択します。フロントエンド サーバーは、Enterprise Edition フロントエンドのプールまたは Standard Edition フロントエンド サーバーのいずれかにできます。</span><span class="sxs-lookup"><span data-stu-id="6005e-p102">The Central Management Server can be changed from one defined Front End pool to another defined Front End pool. To change the location of the Central Management Server, select the Front End pool from the drop-down list under **Front End server to install Central Management Server on**. A Front End Server can be an Enterprise Edition Front End pool or a Standard Edition Front End Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6005e-109">インフラストラクチャに中央管理ストアを定義、公開、および展開している場合は、外部処理によって中央管理ストアを別のフロントエンドに再配置しないと、中央管理ストアの場所を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6005e-109">If you have defined, published, and deployed the Central Management store for the infrastructure, you cannot change the location of the Central Management store without relocating the Central Management store to another Front End by an external process.</span></span> 
  
<span data-ttu-id="6005e-110">中央管理サーバー ストアの移動の詳細については、次のコマンドレット リファレンスの [「Move-CsManagementServer」Windows PowerShell](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="6005e-110">For details about moving the Central Management Server store, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps) in the Windows PowerShell cmdlet reference.</span></span>
  

