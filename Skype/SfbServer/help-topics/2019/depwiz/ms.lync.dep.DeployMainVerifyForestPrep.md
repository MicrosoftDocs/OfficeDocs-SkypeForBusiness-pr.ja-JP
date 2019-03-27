---
title: フォレスト準備のレプリケーションの確認
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: グローバル カタログのレプリケーションとフォレストの準備時にオブジェクトの作成であることを確認するのには成功して、次の操作を行います。
ms.openlocfilehash: 77b7265ce101b7428f6bfde1ed5840dac9e0a99e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880652"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="cba77-103">フォレスト準備のレプリケーションの確認</span><span class="sxs-lookup"><span data-stu-id="cba77-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="cba77-104">グローバル カタログのレプリケーションとフォレストの準備時にオブジェクトの作成であることを確認するのには成功して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cba77-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="cba77-105">フォレストの準備を実行したフォレスト内のドメイン コントローラー (他のドメイン コントローラーからリモート サイトにあるドメイン コントローラーを推奨) で、[**Active Directory ユーザーとコンピューター**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="cba77-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="cba77-106">[**Active Directory ユーザーとコンピューター**] で、フォレストまたは子ドメインのドメイン名を展開します。</span><span class="sxs-lookup"><span data-stu-id="cba77-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="cba77-107">左側のウィンドウで [ **Users** ] コンテナーをクリックし、右側のペインでのユニバーサル グループ CsAdministrator を探します。</span><span class="sxs-lookup"><span data-stu-id="cba77-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="cba77-108">CsAdministrator (8 つの他の新しいユニバーサル ・ グループ間で Cs で始まる) が存在する場合は、フォレストの準備のレプリケーションが成功しています。</span><span class="sxs-lookup"><span data-stu-id="cba77-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="cba77-109">グループがまだ存在しない場合は、レプリケーションを強制的にまたは 15 分間待機して右側のウィンドウを更新できます。</span><span class="sxs-lookup"><span data-stu-id="cba77-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="cba77-110">グループが表示されている場合、レプリケーションは完了しています。</span><span class="sxs-lookup"><span data-stu-id="cba77-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="cba77-111">ビジネス サーバーの展開ウィザードは、Skype によって作成されるログ ファイルを確認するには場合、は、展開ウィザードが実行しているコンピューターの手順を実行した Active Directory ドメイン サービスのユーザーのユーザー ディレクトリ内にそれらを検索できます。</span><span class="sxs-lookup"><span data-stu-id="cba77-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="cba77-112">たとえば、ユーザー Contoso.net のドメインのドメイン管理者としてログインしている場合、ログ ・ ファイル内にある: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="cba77-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

