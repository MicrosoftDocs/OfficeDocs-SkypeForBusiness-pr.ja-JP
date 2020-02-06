---
title: Skype for Business Server コンポーネントのセットアップまたは削除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Skype for Business Server コンポーネントのインストール、ライセンス認証、または非アクティブ化、またはアンインストールを行うには、「手順 2: Skype Server コンポーネントをセットアップまたは削除する」をご覧ください。 インストールまたは変更するコンピューターのローカル管理者としてログインしている必要があります。また、現在のドメインで Active Directory ドメインサービスのユーザーとグループを読み取ることができる必要があります。 開始するには、[実行] をクリックします。 この操作を行うと、中央管理ストアベースのトポロジ定義が読み取られます。 中央管理ストアに定義されている役割に従って、必要なソフトウェア コンポーネントがインストールされて構成されます。 インストールが完了したら、概要を確認して、[完了] をクリックします。'
ms.openlocfilehash: d19d4946af48f96066d01cea33f0a5c04c22f816
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798364"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a><span data-ttu-id="34f7f-108">Skype for Business Server コンポーネントのセットアップまたは削除</span><span class="sxs-lookup"><span data-stu-id="34f7f-108">Setup or Remove Skype for Business Server Components</span></span>
 
<span data-ttu-id="34f7f-109">Skype for Business Server コンポーネントのインストール、ライセンス認証、または非アクティブ化、またはアンインストールを行うには、 **「手順 2: Skype Server コンポーネントをセットアップまたは削除**する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="34f7f-109">To install and activate, or deactivate or uninstall Skype for Business Server components, you use **Step 2: Setup or Remove Skype Server Components**.</span></span> <span data-ttu-id="34f7f-110">インストールまたは変更するコンピューターのローカル管理者としてログインしている必要があります。また、現在のドメインで Active Directory ドメインサービスのユーザーとグループを読み取ることができる必要があります。</span><span class="sxs-lookup"><span data-stu-id="34f7f-110">You must be logged in as a local administrator on the computer that you are installing or modifying and must be able to read Active Directory Domain Services users and groups in the current domain.</span></span> <span data-ttu-id="34f7f-111">開始するには、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34f7f-111">To begin, click **Run**.</span></span> <span data-ttu-id="34f7f-112">この操作を行うと、中央管理ストアベースのトポロジ定義が読み取られます。</span><span class="sxs-lookup"><span data-stu-id="34f7f-112">When you do this, the Central Management store-based topology definition is read.</span></span> <span data-ttu-id="34f7f-113">中央管理ストアに定義されている役割に従って、必要なソフトウェア コンポーネントがインストールされて構成されます。</span><span class="sxs-lookup"><span data-stu-id="34f7f-113">Necessary software components are installed and configured, according to the role as defined in the Central Management store.</span></span> <span data-ttu-id="34f7f-114">インストールが完了したら、概要を確認して、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34f7f-114">When the installation is complete, review the Summary, and click **Finish**.</span></span>
  
> [!TIP]
> <span data-ttu-id="34f7f-115">展開ウィザードによって作成されたログファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューター上で、そのステップを実行した Active Directory ユーザーの Users ディレクトリで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="34f7f-115">If you need to review the log files that are created by the Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="34f7f-116">たとえば、ユーザーがドメイン Contoso.net のドメイン管理者としてログインしている場合、ログファイルは次の場所に保存されてい > ます。 C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="34f7f-116">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  
> [!NOTE]
> <span data-ttu-id="34f7f-117">このコンピューターに Skype for Business Server コンポーネントを以前インストールしたことがある場合は、展開ウィザードでそのコンポーネントが認識され、手順2のボタンは**再度実行**として表示されます。</span><span class="sxs-lookup"><span data-stu-id="34f7f-117">If you have previously installed Skype for Business Server components on this computer, the Deployment Wizard will recognize this, and the button in step 2 will be displayed as **Run Again**.</span></span> <span data-ttu-id="34f7f-118">このため、サーバーを適切に構成または変更するために、必要に応じて何度でも手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="34f7f-118">This enables you to run the step as many times as needed to correctly configure or modify the server.</span></span> 
  

