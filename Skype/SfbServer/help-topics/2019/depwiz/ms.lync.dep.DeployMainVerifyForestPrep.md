---
title: フォレスト準備のレプリケーションの確認
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: フォレストの準備中にグローバル カタログのレプリケーションとオブジェクトの作成が正常に行されたことを確認するには、次の手順を実行します。
ms.openlocfilehash: 299b738bbfa14ad13825e5c08e87c03167c9f4cc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801597"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="d4a4e-103">フォレスト準備のレプリケーションの確認</span><span class="sxs-lookup"><span data-stu-id="d4a4e-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="d4a4e-104">フォレストの準備中にグローバル カタログのレプリケーションとオブジェクトの作成が正常に行されたことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4a4e-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="d4a4e-105">ドメイン コントローラー (他のドメイン コントローラーからのリモート サイトが望ましい) で、フォレストの準備が実行されたフォレストで、Active Directory ユーザーとコンピューター **を開きます**。</span><span class="sxs-lookup"><span data-stu-id="d4a4e-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="d4a4e-106">**[Active Directory ユーザーとコンピューター]** で、フォレストまたは子ドメインのドメイン名を展開します。</span><span class="sxs-lookup"><span data-stu-id="d4a4e-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="d4a4e-107">左側の **ウィンドウで Users** コンテナーをクリックし、右側のウィンドウでユニバーサル グループ CsAdministrator を探します。</span><span class="sxs-lookup"><span data-stu-id="d4a4e-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="d4a4e-108">CsAdministrator (Cs で始まる他の 8 つの新しいユニバーサル グループ間) が存在する場合、フォレストの準備のレプリケーションは成功しています。</span><span class="sxs-lookup"><span data-stu-id="d4a4e-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="d4a4e-p102">グループが表示されていない場合、レプリケーションを強制的に実行するか、15 分待ってから右側のウィンドウを更新することができます。グループが表示されている場合、レプリケーションは完了しています。</span><span class="sxs-lookup"><span data-stu-id="d4a4e-p102">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane. When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="d4a4e-111">Skype for Business Server 展開ウィザードによって作成されたログ ファイルを確認する場合は、展開ウィザードが実行されたコンピューターの手順を実行した Active Directory ドメイン サービス ユーザーの Users ディレクトリでログ ファイルを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4a4e-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="d4a4e-112">たとえば、ユーザーがドメイン Contoso.net でドメイン管理者としてログインした場合、ログ ファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。</span><span class="sxs-lookup"><span data-stu-id="d4a4e-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

