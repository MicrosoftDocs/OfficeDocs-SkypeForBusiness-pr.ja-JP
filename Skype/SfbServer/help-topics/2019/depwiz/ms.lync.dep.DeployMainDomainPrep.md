---
title: 現在のドメインの準備
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype for Business Server または Skype for Business Server ユーザーを実行しているサーバーをホストするドメインを準備するには、「セットアップを使用してドメインの準備を実行する」の説明に従って、手順 5: 現在のドメインを準備する必要があります。 この手順を完了するには、準備するドメインの Domain Admins グループのメンバー、またはドメインが属するフォレストの Enterprise Admins グループのメンバーとしてログインする必要があります。 ドメインを準備するには、以下の操作を行います。'
ms.openlocfilehash: d6e2efb774d7cad653c0a95e0e2863b97efe55ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824937"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="7bb02-105">現在のドメインの準備</span><span class="sxs-lookup"><span data-stu-id="7bb02-105">Prepare Current Domain</span></span>

<span data-ttu-id="7bb02-106">Skype for Business Server または Skype for Business Server ユーザーを実行しているサーバーをホストするドメインを準備するには、「セットアップを使用してドメインの準備を実行する」の説明に従って、手順 **5:** 現在のドメインを準備する必要 [があります。](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)</span><span class="sxs-lookup"><span data-stu-id="7bb02-106">To prepare a domain to host servers running Skype for Business Server or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="7bb02-107">この手順を完了するには、準備するドメインの Domain Admins グループのメンバー、またはドメインが属するフォレストの Enterprise Admins グループのメンバーとしてログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bb02-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="7bb02-108">ドメインを準備するには、以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7bb02-108">To prepare the domain:</span></span>

1. <span data-ttu-id="7bb02-109">Skype for Business Server のインストール フォルダーまたはメディアから、Setup.exeを実行して Skype for Business Server 展開ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="7bb02-109">From the Skype for Business Server installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="7bb02-110">[**Active Directory の準備**] をクリックし、展開状態が判別されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="7bb02-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="7bb02-111">[**手順 5: 現在のドメインの準備**] で、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bb02-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="7bb02-112">[**コマンドを実行しています**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7bb02-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="7bb02-113">[操作 **]** 列で[ **ドメイン** の準備] を展開し、各タスクの最後に実行結果を探して、ドメインの準備が正常に完了したのを確認し、ログを閉じて、[完了] を **\<Success\>** クリック **します**。</span><span class="sxs-lookup"><span data-stu-id="7bb02-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="7bb02-114">Skype for Business Server 展開ウィザードで作成されたログ ファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューターの手順を実行した Active Directory ドメイン サービス ユーザーの Users ディレクトリでログ ファイルを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bb02-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="7bb02-115">たとえば、ユーザーがドメイン Contoso.net でドメイン管理者としてログインした場合、ログ ファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。</span><span class="sxs-lookup"><span data-stu-id="7bb02-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


