---
title: Skype for Business Server コンポーネントのセットアップまたは削除
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
description: 'ステップ 2 を使用してアクティブ化、または非アクティブ化またはサーバー 2015 のビジネス コンポーネントの Skype をアンインストール、: セットアップまたは Skype のサーバー コンポーネントを削除します。 ログオンしなければなりませんでコンピューター上のローカル管理者としてインストールすると変更、および必要としている、現在のドメインの Active Directory ドメイン サービスのユーザーとグループを読み取ることができません。 開始するには、[実行] をクリックします。 この操作を行うと、中央管理ストアベースのトポロジ定義が読み取られます。 中央管理ストアに定義されている役割に従って、必要なソフトウェア コンポーネントがインストールされて構成されます。 インストールが完了したら、概要を確認して、[完了] をクリックします。'
ms.openlocfilehash: c8845f34b09513c47b3332a751ae17e93cc655ee
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201210"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a><span data-ttu-id="a46d3-108">Skype for Business Server コンポーネントのセットアップまたは削除</span><span class="sxs-lookup"><span data-stu-id="a46d3-108">Setup or Remove Skype for Business Server Components</span></span>
 
<span data-ttu-id="a46d3-109">使用してアクティブ化、または非アクティブ化またはサーバー 2015 のビジネス コンポーネントの Skype をアンインストール、**手順 2: セットアップまたは Skype のサーバー コンポーネントを削除する**です。</span><span class="sxs-lookup"><span data-stu-id="a46d3-109">To install and activate, or deactivate or uninstall Skype for Business Server 2015 components, you use **Step 2: Setup or Remove Skype Server Components**.</span></span> <span data-ttu-id="a46d3-110">ログオンしなければなりませんでコンピューター上のローカル管理者としてインストールすると変更、および必要としている、現在のドメインの Active Directory ドメイン サービスのユーザーとグループを読み取ることができません。</span><span class="sxs-lookup"><span data-stu-id="a46d3-110">You must be logged in as a local administrator on the computer that you are installing or modifying and must be able to read Active Directory Domain Services users and groups in the current domain.</span></span> <span data-ttu-id="a46d3-111">開始するには、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a46d3-111">To begin, click **Run**.</span></span> <span data-ttu-id="a46d3-112">この操作を行うと、中央管理ストアベースのトポロジ定義が読み取られます。</span><span class="sxs-lookup"><span data-stu-id="a46d3-112">When you do this, the Central Management store-based topology definition is read.</span></span> <span data-ttu-id="a46d3-113">中央管理ストアに定義されている役割に従って、必要なソフトウェア コンポーネントがインストールされて構成されます。</span><span class="sxs-lookup"><span data-stu-id="a46d3-113">Necessary software components are installed and configured, according to the role as defined in the Central Management store.</span></span> <span data-ttu-id="a46d3-114">インストールが完了したら、概要を確認して、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a46d3-114">When the installation is complete, review the Summary, and click **Finish**.</span></span>
  
> [!TIP]
> <span data-ttu-id="a46d3-115">展開ウィザードによって作成されるログ ファイルを確認する必要がある場合、は、展開ウィザードが実行しているコンピューターの手順を実行した Active Directory ユーザーのユーザー ディレクトリ内にそれらを検索できます。</span><span class="sxs-lookup"><span data-stu-id="a46d3-115">If you need to review the log files that are created by the Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="a46d3-116">たとえば、ユーザー Contoso.net のドメインのドメイン管理者としてログインしている場合、ログ ・ ファイル内にある: _gt C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="a46d3-116">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a46d3-117">サーバー 2015 のビジネス コンポーネントをこのコンピューター上の過去に Skype をインストールしている場合は、展開ウィザードは、これを認識し、として**の再実行**、手順 2 でボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a46d3-117">If you have previously installed Skype for Business Server 2015 components on this computer, the Deployment Wizard will recognize this, and the button in step 2 will be displayed as **Run Again**.</span></span> <span data-ttu-id="a46d3-118">このため、サーバーを適切に構成または変更するために、必要に応じて何度でも手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="a46d3-118">This enables you to run the step as many times as needed to correctly configure or modify the server.</span></span> 
  

