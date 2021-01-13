---
title: Skype for Business Server コンポーネントのセットアップまたは削除
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype for Business Server コンポーネントのインストールとアクティブ化、または非アクティブ化またはアンインストールを行う場合は、「手順 2: Skype Server コンポーネントをセットアップまたは削除する」を使用します。 インストールまたは変更するコンピューターにローカル管理者としてログインし、現在のドメイン内の Active Directory ドメイン サービスのユーザーとグループを読み取る必要があります。 開始するには、[実行] をクリックします。 これにより、中央管理ストアベースのトポロジ定義が読み取られます。 中央管理ストアに定義されている役割に従って、必要なソフトウェア コンポーネントがインストールされて構成されます。 インストールが完了したら、概要を確認し、[完了] をクリックします。'
ms.openlocfilehash: 8a004e17984a927d08b7c814f8a4ba435c98971e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825056"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a><span data-ttu-id="4f808-108">Skype for Business Server コンポーネントのセットアップまたは削除</span><span class="sxs-lookup"><span data-stu-id="4f808-108">Setup or Remove Skype for Business Server Components</span></span>
 
<span data-ttu-id="4f808-109">Skype for Business Server コンポーネントをインストールしてアクティブ化または非アクティブ化またはアンインストールするには、「手順 2: Skype Server コンポーネントをセットアップまたは削除する **」を使用します**。</span><span class="sxs-lookup"><span data-stu-id="4f808-109">To install and activate, or deactivate or uninstall Skype for Business Server components, you use **Step 2: Setup or Remove Skype Server Components**.</span></span> <span data-ttu-id="4f808-110">インストールまたは変更するコンピューターにローカル管理者としてログインし、現在のドメイン内の Active Directory ドメイン サービスのユーザーとグループを読み取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f808-110">You must be logged in as a local administrator on the computer that you are installing or modifying and must be able to read Active Directory Domain Services users and groups in the current domain.</span></span> <span data-ttu-id="4f808-111">開始するには、**[実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f808-111">To begin, click **Run**.</span></span> <span data-ttu-id="4f808-112">これにより、中央管理ストアベースのトポロジ定義が読み取られます。</span><span class="sxs-lookup"><span data-stu-id="4f808-112">When you do this, the Central Management store-based topology definition is read.</span></span> <span data-ttu-id="4f808-113">中央管理ストアに定義されている役割に従って、必要なソフトウェア コンポーネントがインストールされて構成されます。</span><span class="sxs-lookup"><span data-stu-id="4f808-113">Necessary software components are installed and configured, according to the role as defined in the Central Management store.</span></span> <span data-ttu-id="4f808-114">インストールが完了したら、概要を確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f808-114">When the installation is complete, review the Summary, and click **Finish**.</span></span>
  
> [!TIP]
> <span data-ttu-id="4f808-115">展開ウィザードで作成されたログ ファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューターの手順を実行した Active Directory ユーザーの Users ディレクトリでログ ファイルを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f808-115">If you need to review the log files that are created by the Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="4f808-116">たとえば、ユーザーがドメイン Contoso.net でドメイン管理者としてログインした場合、ログ ファイルは > C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。</span><span class="sxs-lookup"><span data-stu-id="4f808-116">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4f808-117">このコンピューターに Skype for Business Server コンポーネントを以前にインストールした場合は、展開ウィザードによってこの認識が行い、手順 2 のボタンが [再び実行] として **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="4f808-117">If you have previously installed Skype for Business Server components on this computer, the Deployment Wizard will recognize this, and the button in step 2 will be displayed as **Run Again**.</span></span> <span data-ttu-id="4f808-118">これにより、サーバーを適切に構成または変更するために、必要に応じて何度でも手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="4f808-118">This enables you to run the step as many times as needed to correctly configure or modify the server.</span></span> 
  

