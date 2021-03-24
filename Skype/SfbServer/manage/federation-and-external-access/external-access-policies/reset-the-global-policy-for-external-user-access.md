---
title: 外部ユーザー アクセスに関するグローバル ポリシーのリセット
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: グローバル ポリシーを完全に削除することはできません。 グローバル ポリシーに対して [**削除**] オプションを使用すると、外部ユーザー アクセス オプションのサポートが含まれていない既定の設定に、グローバル ポリシーがリセットされるだけです。
ms.openlocfilehash: 6c74690d86f7a300b79b755db7c6111eec7810f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098973"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="b503e-104">Skype for Business Server の外部ユーザー アクセスのグローバル ポリシーをリセットする</span><span class="sxs-lookup"><span data-stu-id="b503e-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="b503e-105">使用しなくなった外部ユーザー アクセス ポリシーを作成または構成済みの場合は、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b503e-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="b503e-106">作成したサイトやユーザー ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b503e-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="b503e-p102">グローバル ポリシーを既定の設定にリセットします。 既定のグローバル ポリシー設定では、外部ユーザー アクセスが許可されません。 グローバル ポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="b503e-p102">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>

<span data-ttu-id="b503e-p103">グローバル ポリシーを完全に削除することはできません。 グローバル ポリシーに対して [**削除**] オプションを使用すると、外部ユーザー アクセス オプションのサポートが含まれていない既定の設定に、グローバル ポリシーがリセットされるだけです。</span><span class="sxs-lookup"><span data-stu-id="b503e-p103">You cannot completely delete a global policy. Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="b503e-112">グローバル ポリシーを既定の設定にリセットするには</span><span class="sxs-lookup"><span data-stu-id="b503e-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="b503e-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b503e-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b503e-114">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b503e-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="b503e-115">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b503e-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="b503e-116">[**外部アクセス ポリシー**] タブでグローバル ポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b503e-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="b503e-p104">削除について確認するメッセージが表示されたら、[**OK**] をクリックします。 ページの先頭に、グローバル ポリシーがリセットされたことを知らせるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b503e-p104">When prompted to confirm the deletion, click **OK**. A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b503e-119">コマンドレットを使用したグローバル外部アクセス ポリシー Windows PowerShellする</span><span class="sxs-lookup"><span data-stu-id="b503e-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b503e-120">グローバル外部アクセス ポリシーは、ユーザーのコマンドレットとWindows PowerShell使用してRemove-CsExternalAccessPolicyできます。</span><span class="sxs-lookup"><span data-stu-id="b503e-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="b503e-121">このコマンドレットは、Skype for Business Server 管理シェルから、またはリモート セッション から実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b503e-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="b503e-122">グローバル外部アクセス ポリシーをリセットするには</span><span class="sxs-lookup"><span data-stu-id="b503e-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="b503e-123">次のコマンドは、グローバル外部アクセス ポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="b503e-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="b503e-124">詳細については [、Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b503e-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>