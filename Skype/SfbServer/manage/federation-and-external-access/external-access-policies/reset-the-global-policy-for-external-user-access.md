---
title: 外部ユーザー アクセスに関するグローバル ポリシーのリセット
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: グローバルポリシーを完全に削除することはできません。 グローバルポリシーの [**削除**] オプションを使うと、グローバルポリシーは既定の設定にリセットされます。これには、外部ユーザーアクセスオプションのサポートは含まれません。
ms.openlocfilehash: 339ad22e1d049510416bfc3433c6c8a104455504
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280146"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="dbdd8-104">Skype for Business Server で外部ユーザーアクセスのグローバルポリシーをリセットする</span><span class="sxs-lookup"><span data-stu-id="dbdd8-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="dbdd8-105">使用しない外部ユーザーアクセスポリシーを作成または構成している場合は、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="dbdd8-106">作成したサイトまたはユーザーのポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="dbdd8-107">グローバルポリシーを既定の設定にリセットします。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="dbdd8-108">既定のグローバルポリシー設定では、外部ユーザーのアクセスを拒否します。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="dbdd8-109">グローバルポリシーは削除できません。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="dbdd8-110">グローバルポリシーを完全に削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="dbdd8-111">グローバルポリシーの [**削除**] オプションを使うと、グローバルポリシーは既定の設定にリセットされます。これには、外部ユーザーアクセスオプションのサポートは含まれません。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="dbdd8-112">グローバルポリシーを既定の設定にリセットするには</span><span class="sxs-lookup"><span data-stu-id="dbdd8-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="dbdd8-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dbdd8-114">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="dbdd8-115">左側のナビゲーションバーで、[**外部ユーザーアクセス**]、[**外部アクセスポリシー**] の順番にクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="dbdd8-116">[**外部アクセスポリシー** ] タブで、グローバルポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="dbdd8-117">削除を確認するメッセージが表示されたら、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="dbdd8-118">ページの上部に、グローバルポリシーがリセットされたことを通知するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dbdd8-119">Windows PowerShell コマンドレットを使用してグローバル外部アクセスポリシーをリセットする</span><span class="sxs-lookup"><span data-stu-id="dbdd8-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dbdd8-120">グローバル外部アクセスポリシーをリセットするには、Windows PowerShell と CsExternalAccessPolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="dbdd8-121">このコマンドレットは、Skype for Business Server 管理シェルから、またはリモートセッション Windows PowerShell から実行できます。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="dbdd8-122">グローバル外部アクセスポリシーをリセットするには</span><span class="sxs-lookup"><span data-stu-id="dbdd8-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="dbdd8-123">このコマンドは、グローバル外部アクセスポリシーをリセットします。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="dbdd8-124">詳細については、 [CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dbdd8-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


