---
title: 現在のドメインの準備
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'ビジネス サーバーのユーザーのビジネス サーバーまたは Skype の Skype を実行しているホスト サーバーにドメインを準備するには、手順 5 を完了する必要があります: 準備現在のドメイン、ドメインの準備の実行に使用するセットアップのトピックで説明されているようです。 この手順を完了するには、準備するドメインの Domain Admins グループのメンバー、またはドメインが属するフォレストの Enterprise Admins グループのメンバーとしてログインする必要があります。 ドメインを準備するには、以下の操作を行います。'
ms.openlocfilehash: 7b67521cef97efd2bdfc0da344a8619272899340
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19979891"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="53bb6-105">現在のドメインの準備</span><span class="sxs-lookup"><span data-stu-id="53bb6-105">Prepare Current Domain</span></span>
 
<span data-ttu-id="53bb6-106">ビジネス サーバーのユーザーのビジネス サーバーまたは Skype の Skype を実行しているホスト サーバーにドメインを準備するのには行う必要があります**手順 5: 現在のドメインを準備する**、[ドメインの準備を実行するセットアップを使用して](http://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)トピックの説明します。</span><span class="sxs-lookup"><span data-stu-id="53bb6-106">To prepare a domain to host servers running Skype for Business Server or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](http://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="53bb6-107">この手順を完了するには、準備するドメインの Domain Admins グループのメンバー、またはドメインが属するフォレストの Enterprise Admins グループのメンバーとしてログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="53bb6-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="53bb6-108">ドメインを準備するには、以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="53bb6-108">To prepare the domain:</span></span>
  
1. <span data-ttu-id="53bb6-109">ビジネス サーバー 2015 インストール フォルダーまたはメディアの Skype、ビジネス サーバーの展開ウィザードは、Skype を起動するのには、Setup.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="53bb6-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>
    
2. <span data-ttu-id="53bb6-110">[**Active Directory の準備**] をクリックして、展開状態が判別されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="53bb6-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>
    
3. <span data-ttu-id="53bb6-111">[**手順 5: 現在のドメインの準備**] で、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb6-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>
    
4. <span data-ttu-id="53bb6-112">[**コマンドの実行**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53bb6-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>
    
5. <span data-ttu-id="53bb6-113">[**アクション**] 列で、**ドメインの準備**] を探して、**\<成功\>** ドメインの準備が正常に完了したことを確認して、ログを閉じるし、[**完了**] をクリックする各タスクの最後に実行の結果です。</span><span class="sxs-lookup"><span data-stu-id="53bb6-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>
    
> [!TIP]
> <span data-ttu-id="53bb6-114">ビジネス サーバーの展開ウィザードは、Skype によって作成されるログ ファイルを確認する必要がある場合、は、展開ウィザードの実行の手順を実行した Active Directory ドメイン サービスのユーザーのユーザー ディレクトリ内のコンピューターでそれらを検索できます。</span><span class="sxs-lookup"><span data-stu-id="53bb6-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="53bb6-115">たとえば、ユーザー Contoso.net のドメインのドメイン管理者としてログインしている場合、ログ ・ ファイル内にある: C:\Users\Administrator.Contoso\AppData\Local\Temp。</span><span class="sxs-lookup"><span data-stu-id="53bb6-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span> 
  

