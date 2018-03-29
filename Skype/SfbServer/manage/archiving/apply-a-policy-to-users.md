---
title: Skype for Business Server 2015 でのユーザーへのアーカイブ ポリシーの適用
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: '概要: ビジネス サーバー 2015 の Skype のユーザーのアーカイブ ポリシーを割り当てる方法を説明します。'
ms.openlocfilehash: fc9811aa57a1ba397dedce325f03ea2d77e4413b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server-2015"></a><span data-ttu-id="dcbe6-103">Skype for Business Server 2015 でのユーザーへのアーカイブ ポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="dcbe6-103">Apply an archiving policy to users in Skype for Business Server 2015</span></span>

<span data-ttu-id="dcbe6-104">**の概要:**ビジネス サーバー 2015 の Skype のユーザーのアーカイブ ポリシーを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-104">**Summary:** Learn how to assign an archiving policy to users in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="dcbe6-105">1 つを作成した、またはユーザーのアーカイブのための複数のユーザー ポリシーは、Skype ビジネス サーバー 2015 のホーム、それらのユーザーまたはユーザー グループに適切なポリシーを適用することによって特定のユーザーのアーカイブのサポートを実装できます。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-105">If you have created one or more user policies for archiving for users homed on Skype for Business Server 2015, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups.</span></span> <span data-ttu-id="dcbe6-106">たとえば、内部通信のアーカイブをサポートするためにポリシーを作成する場合は、ビジネス サーバー 2015 通信のためのユーザーの Skype のアーカイブをサポートするために少なくとも 1 つのユーザーまたはユーザー ・ グループに適用できます。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-106">For example, if you create a policy to support archiving of internal communications, you can apply it to at least one user or user group to support archiving of the user's Skype for Business Server 2015 communications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dcbe6-107">場合は有効にする Microsoft Exchange の統合、展開、Exchange インプレース保持ポリシーの管理に Exchange のホーム サーバーはユーザーのアーカイブが有効になっているし、インプレース保持に自分のメールボックスを配置するかどうか。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-107">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="dcbe6-108">詳細については、[ビジネス サーバー 2015 の Skype でアーカイブするための計画](../../plan-your-deployment/archiving/archiving.md)と[構成との統合ビジネス サーバー 2015 の Skype の Exchange の記憶域](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-108">For details, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server 2015](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a><span data-ttu-id="dcbe6-109">コントロール パネルを使用したユーザー ポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="dcbe6-109">Apply a user policy by using the Control Panel</span></span>

<span data-ttu-id="dcbe6-110">コントロール パネルを使用してユーザー ポリシーを適用するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-110">To apply a user policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="dcbe6-111">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="dcbe6-112">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="dcbe6-113">左側のナビゲーション バーで [**ユーザー**] をクリックして、構成するユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-113">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span> 
    
4. <span data-ttu-id="dcbe6-114">検索結果一覧の表でユーザー アカウントをクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="dcbe6-115">**アーカイブ**ポリシーでは、 **Lync Server ユーザーの編集**では、アーカイブ ユーザー ポリシーを適用するを選択します。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-115">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dcbe6-116">**\<自動\>**の設定は、サーバー インストールの既定の設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-116">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="dcbe6-117">これらの設定はサーバーによって自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-117">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="dcbe6-118">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-118">Click **Commit**.</span></span>
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a><span data-ttu-id="dcbe6-119">Windows PowerShell を使用してユーザー ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-119">Apply a user policy by using Windows PowerShell</span></span>

<span data-ttu-id="dcbe6-120">**与える CsArchivingPolicy**の Windows PowerShell コマンドレットを使用してユーザー ポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-120">You can also apply a user policy by using the Windows PowerShell **Grant-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="dcbe6-121">次のコマンドは、ユーザー単位のアーカイブ ポリシー RedmondArchivingPolicy をユーザー Ken Myer に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-121">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

<span data-ttu-id="dcbe6-122">このコマンドに割り当て、ユーザーごとのアーカイブ ポリシー RedmondArchivingPolicy をすべてのユーザーにユーザーがアカウントが置かれている、レジストラー プール atl の cs-001.contoso.com です。詳細については、このコマンドで使用されるフィルター パラメーターは、 [Get CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-122">This command assigns the per-user archiving policy RedmondArchivingPolicy to all users who have accounts homed on the Registrar pool atl-cs-001.contoso.com. For details about the Filter parameter used in this command, see the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet documentation.</span></span>
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

```

<span data-ttu-id="dcbe6-p104">次のコマンドは、Ken Myer に割り当てられたユーザー単位のアーカイブ ポリシーを削除します。ユーザー単位のポリシーが削除された後、Ken Myer は、グローバル ポリシー、または存在する場合は Ken Myer のローカル サイト ポリシーによって、自動的に管理されます。サイト ポリシーは、グローバル ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-p104">The following command removes any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is removed, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

<span data-ttu-id="dcbe6-126">詳細については、[補助金 CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps)コマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcbe6-126">For details, see the [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet documentation.</span></span>
  

