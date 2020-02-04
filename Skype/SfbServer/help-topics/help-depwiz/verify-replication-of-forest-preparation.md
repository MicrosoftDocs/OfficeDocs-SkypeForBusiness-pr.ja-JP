---
title: フォレスト準備のレプリケーションの確認
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: グローバルカタログの複製と、フォレストの準備中のオブジェクトの作成が正常に完了したことを確認するには、次の操作を行います。
ms.openlocfilehash: 4f17b62fd0756019bab105df323215571557dce2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700652"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="442a3-103">フォレスト準備のレプリケーションの確認</span><span class="sxs-lookup"><span data-stu-id="442a3-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="442a3-104">グローバルカタログの複製と、フォレストの準備中のオブジェクトの作成が正常に完了したことを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="442a3-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="442a3-105">フォレストの準備を実行したフォレスト内のドメイン コントローラー (他のドメイン コントローラーからリモート サイトにあるドメイン コントローラーを推奨) で、[**Active Directory ユーザーとコンピューター**] を開きます。</span><span class="sxs-lookup"><span data-stu-id="442a3-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="442a3-106">[**Active Directory ユーザーとコンピューター**] で、フォレストまたは子ドメインのドメイン名を展開します。</span><span class="sxs-lookup"><span data-stu-id="442a3-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="442a3-107">左側のウィンドウで [**ユーザー** ] コンテナーをクリックし、右側のウィンドウでユニバーサルグループ csadministrator を探します。</span><span class="sxs-lookup"><span data-stu-id="442a3-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="442a3-108">CsAdministrator (Cs で始まる8つの新しいユニバーサルグループの一部) が表示されている場合は、フォレストの準備の複製が正常に完了しています。</span><span class="sxs-lookup"><span data-stu-id="442a3-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="442a3-109">グループがまだ存在していない場合は、複製を強制するか、15分間待ってから右側のウィンドウを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="442a3-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="442a3-110">グループが表示されている場合、レプリケーションは完了しています。</span><span class="sxs-lookup"><span data-stu-id="442a3-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="442a3-111">Skype for Business Server 展開ウィザードによって作成されたログファイルを確認する場合は、その手順を実行した Active Directory ドメインサービスユーザーの Users ディレクトリで展開ウィザードが実行されているコンピューターで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="442a3-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="442a3-112">たとえば、ユーザーがドメイン Contoso.net のドメイン管理者としてログインしている場合、ログファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。</span><span class="sxs-lookup"><span data-stu-id="442a3-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

