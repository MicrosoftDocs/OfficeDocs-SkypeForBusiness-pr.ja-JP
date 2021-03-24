---
title: 現在のフォレストの準備
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Active Directory ドメイン サービス フォレストを準備するには、「スキーマの準備の実行」の説明に従ってスキーマを正常に拡張し、スキーマがレプリケートされたことを確認する必要があります。
ms.openlocfilehash: 94d41a993b2fe976ef7ede885d277c00417ff7dc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103463"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="318c7-103">現在のフォレストの準備</span><span class="sxs-lookup"><span data-stu-id="318c7-103">Prepare Current Forest</span></span>

<span data-ttu-id="318c7-104">Active Directory ドメイン サービス フォレストを準備するには、「スキーマの準備を実行する」の説明[](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema)に従ってスキーマを正常に拡張し、スキーマがレプリケートされたことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="318c7-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="318c7-p101">これらの前提条件を満たしたら、[**手順 3: 現在のフォレストの準備**] を開始できます。フォレストを準備するには、フォレスト ルートのコンピューターに、フォレスト ルートの Domain Admins のメンバーとして、または準備しているフォレストの Enterprise Admins のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="318c7-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="318c7-107">[**手順 3: 現在のフォレストの準備**] で、展開ウィザードから [**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="318c7-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="318c7-108">**[フォレストの準備]** ページから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="318c7-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="318c7-109">フォレストの準備では、Skype for Business Server 2015 のユニバーサル グループを配置する場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="318c7-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server 2015.</span></span> <span data-ttu-id="318c7-110">組織の要件と一致する配置先を選択してください。</span><span class="sxs-lookup"><span data-stu-id="318c7-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="318c7-p103">[**コマンドを実行しています**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。エラーがないことを確認します。警告を確認して、それらの警告が予期されるものであり、インフラストラクチャにとって通常のものであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="318c7-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="318c7-114">ログの **[アクション**] 列で、[フォレスト準備] を展開し、各タスクの最後に実行結果を探して、フォレストの準備が正常に完了したと確認し、ログを閉じて、[完了] を **\<Success\>** クリックします。 </span><span class="sxs-lookup"><span data-stu-id="318c7-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="318c7-115">Active Directory ドメイン サービスのレプリケーションが完了するのを待つか、フォレスト ルート ドメイン コントローラーの Active Directory Sites **and Services** スナップインに記載されているすべてのドメイン コントローラーへのレプリケーションを強制的に実行してから、ドメインの準備を実行します。</span><span class="sxs-lookup"><span data-stu-id="318c7-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="318c7-116">サイト内でレプリケーションが数分以内に開始されるよう、すべての Active Directory サイト内のドメイン コントローラ間でレプリケーションを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="318c7-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="318c7-117">Skype for Business Server 展開ウィザードによって作成されたログ ファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューターで、手順を実行した Active Directory ドメイン サービス ユーザーの Users ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="318c7-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="318c7-118">たとえば、ユーザーがドメイン Contoso.net でドメイン管理者としてログインした場合、ログ ファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。</span><span class="sxs-lookup"><span data-stu-id="318c7-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>