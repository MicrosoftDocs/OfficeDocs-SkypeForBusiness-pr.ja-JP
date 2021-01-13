---
title: Skype for Business Server で外部ユーザーのアーカイブ免責事項を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: '概要: このトピックでは、Skype for Business Server のアーカイブについての免責事項を構成する方法について説明します。'
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820667"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="77025-103">Skype for Business Server で外部ユーザーのアーカイブ免責事項を構成する</span><span class="sxs-lookup"><span data-stu-id="77025-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="77025-104">**概要:** このトピックでは、Skype for Business Server のアーカイブについての免責事項を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="77025-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="77025-105">組織が外部パートナーと通信する場合は、外部パートナーとの通信をアーカイブ中と知らせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="77025-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="77025-106">エッジ サーバーを展開し、組織のフェデレーションを有効にするときに、アーカイブについての免責事項を外部パートナーに自動的に送信するかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="77025-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="77025-107">この構成を変更する必要がある場合は、Skype for Business Server コントロール パネルまたは Windows PowerShell **Set-CsAccessEdgeConfiguration** コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="77025-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="77025-108">コマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="77025-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="77025-109">外部ユーザーが Skype for Business Server 展開のユーザーと共同作業を行うのを有効にするには、外部ユーザー アクセスをサポートするために、少なくとも 1 つの外部アクセス ポリシーも構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="77025-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="77025-110">詳細については、「組織の XMPP フェデレーション パートナーの管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77025-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="77025-111">特定のフェデレーション ドメインのアクセス制御の詳細については、「個々のフェデレーション ドメインによるアクセスの制御」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77025-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="77025-112">コントロール パネルを使用してアーカイブ免責事項を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="77025-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="77025-113">RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="77025-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="77025-114">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="77025-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="77025-115">左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="77025-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="77025-116">[**アクセス エッジ構成**] タブで、[**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="77025-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="77025-117">[**アクセス** エッジ構成の編集] の [フェデレーションとパブリック **IM** 接続の有効化] で、[フェデレーション パートナーにアーカイブについての免責事項を送信する] チェック ボックスをオンまたはオフにして、アーカイブについての免責事項の自動送信を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="77025-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="77025-118">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="77025-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="77025-119">アーカイブ免責事項を有効または無効にするには、次のWindows PowerShell</span><span class="sxs-lookup"><span data-stu-id="77025-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="77025-120">アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="77025-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="77025-121">アーカイブについての免責事項を有効にするには、**EnableArchivingDisclaimer** プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="77025-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


