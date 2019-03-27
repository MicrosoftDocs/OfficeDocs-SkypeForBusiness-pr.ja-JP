---
title: 外部ユーザー アクセスに関するグローバル ポリシーのリセット
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: グローバル ポリシーを完全に削除することはできません。 外部ユーザー アクセス オプションのサポートが含まれていない既定の設定をグローバル ポリシーをリセットすることがのみグローバル ポリシーを**削除**する] オプションを使用します。
ms.openlocfilehash: 048d1f1aabd2e188cefa25358068ea6ec150b8f3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877875"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="e5671-104">ビジネス サーバーの Skype での外部ユーザー アクセスのグローバル ポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="e5671-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="e5671-105">作成または、外部ユーザー アクセス ポリシーを使用する必要がなくなったように構成した場合は、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e5671-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="e5671-106">作成したサイトまたはユーザーのポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="e5671-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="e5671-107">グローバル ポリシーを既定の設定にリセットします。</span><span class="sxs-lookup"><span data-stu-id="e5671-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="e5671-108">既定のグローバル ポリシー設定は、すべての外部ユーザー アクセスを拒否します。</span><span class="sxs-lookup"><span data-stu-id="e5671-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="e5671-109">グローバル ポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="e5671-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="e5671-110">グローバル ポリシーを完全に削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e5671-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="e5671-111">外部ユーザー アクセス オプションのサポートが含まれていない既定の設定をグローバル ポリシーをリセットすることがのみグローバル ポリシーを**削除**する] オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e5671-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="e5671-112">グローバル ポリシーを既定の設定にリセットするには</span><span class="sxs-lookup"><span data-stu-id="e5671-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="e5671-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e5671-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e5671-114">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="e5671-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="e5671-115">左側のナビゲーション バーで [**外部ユーザー アクセス**] をクリックして、[**外部アクセス ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5671-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="e5671-116">[**外部アクセス ポリシー** ] タブで、[グローバル ポリシー] をクリック**を編集**する、し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5671-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="e5671-117">削除の確認メッセージが表示されたら、[ **OK**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5671-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="e5671-118">グローバル ポリシーがリセットされたことを通知するページの上部にあるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5671-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e5671-119">Windows PowerShell コマンドレットを使用して、グローバル外部アクセス ポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="e5671-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e5671-120">グローバル外部アクセス ポリシーは、Windows PowerShell と削除 CsExternalAccessPolicy コマンドレットを使用してリセットできます。</span><span class="sxs-lookup"><span data-stu-id="e5671-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="e5671-121">ビジネス サーバー管理シェルの Skype から、または Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e5671-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="e5671-122">グローバル外部アクセス ポリシーをリセットするのには</span><span class="sxs-lookup"><span data-stu-id="e5671-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="e5671-123">このコマンドは、グローバル外部アクセス ポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="e5671-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="e5671-124">詳細については、[削除 CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5671-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


