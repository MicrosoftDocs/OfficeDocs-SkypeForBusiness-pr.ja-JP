---
title: 現在のフォレストの準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Active Directory ドメイン サービス フォレストを準備するには、正常にスキーマの準備の実行中のトピックで説明したように、スキーマを拡張して、スキーマがレプリケートされたことを確認する必要があります。
ms.openlocfilehash: 51f3a4bd643ce4d3102d1d0e0c6810fae951c5f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888794"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="70766-103">現在のフォレストの準備</span><span class="sxs-lookup"><span data-stu-id="70766-103">Prepare Current Forest</span></span>

<span data-ttu-id="70766-104">Active Directory ドメイン サービス フォレストを準備するには、正常に[スキーマの準備を実行して](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)、トピックで説明したように、スキーマを拡張して、スキーマがレプリケートされたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70766-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="70766-p101">これらの前提条件を満たしたら、[**手順 3: 現在のフォレストの準備**] を開始できます。フォレストを準備するには、フォレスト ルートのコンピューターに、フォレスト ルートの Domain Admins のメンバーとして、または準備しているフォレストの Enterprise Admins のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="70766-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="70766-107">[**手順 3: 現在のフォレストの準備**] で、展開ウィザードから [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70766-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="70766-108">[**フォレストの準備**] ページから、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70766-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="70766-109">フォレストの準備では、Skype のビジネス サーバー 2015 のユニバーサル グループを配置する場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="70766-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server 2015.</span></span> <span data-ttu-id="70766-110">組織の要件と一致する配置先を選択してください。</span><span class="sxs-lookup"><span data-stu-id="70766-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="70766-p103">[**コマンドを実行しています**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。エラーがないことを確認します。警告を確認して、それらの警告が予期されるものであり、インフラストラクチャにとって通常のものであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="70766-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="70766-114">ログの [**アクション**] 列の下には、**フォレストの準備**を展開、検索、**\<成功\>** フォレストの準備が正常に完了したことを確認し、ログを閉じるし、 **[完了] をクリックし、各タスクの最後に実行の結果**.</span><span class="sxs-lookup"><span data-stu-id="70766-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="70766-115">完了するには Active Directory ドメイン サービスのレプリケーションを待つか、ドメインの準備を実行する前に、 **Active Directory サイトとサービス**スナップインで、フォレスト ルート ドメイン コント ローラーに表示されているすべてのドメイン コント ローラーへのレプリケーションを強制的に。</span><span class="sxs-lookup"><span data-stu-id="70766-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="70766-116">分以内にサイト内でのレプリケーションが発生するすべての Active Directory サイト内のドメイン コント ローラー間のレプリケーションを強制します。</span><span class="sxs-lookup"><span data-stu-id="70766-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="70766-117">ビジネス サーバーの展開ウィザードは、Skype によって作成されるログ ファイルを確認する必要がある場合、は、展開ウィザードが実行しているコンピューターの手順を実行した Active Directory ドメイン サービスのユーザーのユーザー ディレクトリ内にそれらを検索できます。</span><span class="sxs-lookup"><span data-stu-id="70766-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="70766-118">たとえば、ユーザー Contoso.net のドメインのドメイン管理者としてログインしている場合、ログ ・ ファイル内にある: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="70766-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>


