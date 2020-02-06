---
title: 現在のドメインの準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Skype for Business Server 2015 または Skype for Business Server ユーザーを実行しているホストサーバーにドメインを準備するには、「セットアップを使用してドメインの準備を行う」の説明に従って、「手順 5: 現在のドメインを準備する」を完了する必要があります。 この手順を完了するには、準備するドメインの Domain Admins グループのメンバー、またはドメインが属するフォレストの Enterprise Admins グループのメンバーとしてログインする必要があります。 ドメインを準備するには、以下の操作を行います。'
ms.openlocfilehash: 2f3563c9a1c857e9d4828ca63cf2cb675f524e56
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823551"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="33f68-105">現在のドメインの準備</span><span class="sxs-lookup"><span data-stu-id="33f68-105">Prepare Current Domain</span></span>

<span data-ttu-id="33f68-106">Skype for Business Server 2015 または Skype for Business Server ユーザーを実行しているホストサーバーにドメインを準備するには、「[セットアップを使用してドメインの準備を](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)行う」の説明に従って、「**手順 5: 現在のドメインを準備**する」を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33f68-106">To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="33f68-107">この手順を完了するには、準備するドメインの Domain Admins グループのメンバー、またはドメインが属するフォレストの Enterprise Admins グループのメンバーとしてログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="33f68-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="33f68-108">ドメインを準備するには、以下の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="33f68-108">To prepare the domain:</span></span>

1. <span data-ttu-id="33f68-109">Skype for Business Server 2015 のインストールフォルダーまたはメディアから setup.exe を実行して、Skype for Business Server 展開ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="33f68-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="33f68-110">[**Active Directory の準備**] をクリックして、展開状態が判別されるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="33f68-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="33f68-111">[**手順 5: 現在のドメインの準備**] で、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33f68-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="33f68-112">[**コマンドの実行**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33f68-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="33f68-113">[**アクション**] 列で、[**ドメインの準備**] を展開し、各タスクの最後に\*\* \<成功\> **の実行結果を探して、ドメインの準備が正常に完了したことを確認します。次に、[**完了\*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33f68-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="33f68-114">Skype for Business Server 展開ウィザードによって作成されたログファイルを確認する必要がある場合は、この手順を実行した Active Directory ドメインサービスユーザーの Users ディレクトリで展開ウィザードが実行されたコンピューターで確認できます。</span><span class="sxs-lookup"><span data-stu-id="33f68-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="33f68-115">たとえば、ユーザーがドメイン Contoso.net のドメイン管理者としてログインしている場合、ログファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp. にあります。</span><span class="sxs-lookup"><span data-stu-id="33f68-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


