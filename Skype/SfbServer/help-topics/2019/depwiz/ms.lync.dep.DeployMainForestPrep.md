---
title: 現在のフォレストの準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Active Directory ドメインサービスフォレストを準備するには、「スキーマの準備を実行する」のトピックで説明されているように、スキーマを正常に拡張し、スキーマがレプリケートされていることを確認する必要があります。
ms.openlocfilehash: 810bfae1fd308ef943f41846a8baef774f4f724e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303398"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="1cb9c-103">現在のフォレストの準備</span><span class="sxs-lookup"><span data-stu-id="1cb9c-103">Prepare Current Forest</span></span>

<span data-ttu-id="1cb9c-104">Active Directory ドメインサービスフォレストを準備するには、「[スキーマの準備を実行](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)する」のトピックで説明されているように、スキーマを正常に拡張し、スキーマがレプリケートされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cb9c-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="1cb9c-p101">これらの前提条件を満たしたら、[**手順 3: 現在のフォレストの準備**] を開始できます。フォレストを準備するには、フォレスト ルートのコンピューターに、フォレスト ルートの Domain Admins のメンバーとして、または準備しているフォレストの Enterprise Admins のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="1cb9c-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="1cb9c-107">[**手順 3: 現在のフォレストの準備**] で、展開ウィザードから [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb9c-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="1cb9c-108">[**フォレストの準備**] ページから、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1cb9c-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1cb9c-109">フォレストの準備 Skype for Business Server のユニバーサルグループを配置する場所を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="1cb9c-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server.</span></span> <span data-ttu-id="1cb9c-110">組織の要件と一致する配置先を選択してください。</span><span class="sxs-lookup"><span data-stu-id="1cb9c-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="1cb9c-p103">[**コマンドを実行しています**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。エラーがないことを確認します。警告を確認して、それらの警告が予期されるものであり、インフラストラクチャにとって通常のものであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1cb9c-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="1cb9c-114">ログの [**アクション**] 列で、[**フォレスト**の準備] を展開して、各タスクの最後の\*\* \<成功\> \*\*の実行結果を確認し、フォレストの準備が正常に完了したことを確認します。次に、[完了] をクリックします。 \*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="1cb9c-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="1cb9c-115">Active Directory ドメインサービスのレプリケーションが完了するまで待ちます。または、ドメインの準備を実行する前に、フォレストルートドメインコントローラーの [ **Active Directory サイトとサービス**] スナップインに記載されているすべてのドメインコントローラーに対して強制的にレプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="1cb9c-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="1cb9c-116">すべての Active Directory サイトのドメインコントローラー間で強制的にレプリケーションを実行して、サイト内での複製が分単位で行われるようにします。</span><span class="sxs-lookup"><span data-stu-id="1cb9c-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="1cb9c-117">Skype for Business Server 展開ウィザードによって作成されたログファイルを確認する必要がある場合は、展開ウィザードが実行されているコンピューターで、手順を実行した Active Directory ドメインサービスユーザーの Users ディレクトリで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="1cb9c-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="1cb9c-118">たとえば、ユーザーがドメイン Contoso.net のドメイン管理者としてログインしている場合、ログファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。</span><span class="sxs-lookup"><span data-stu-id="1cb9c-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>


