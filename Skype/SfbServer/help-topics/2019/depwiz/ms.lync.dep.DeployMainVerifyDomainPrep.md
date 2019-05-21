---
title: ドメイン内のレプリケーションの確認
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: '「手順 1: スキーマの準備」で行われたドメインの準備の複製を確認するには、Skype for Business Server 管理シェル Lync Server Management Shell からコマンドレットを実行する必要があります。 Windows PowerShell コマンドレットを実行するには、準備したドメインのメンバーであるコンピューター、および Domain Admins グループのメンバーとしてログオンします。 次の手順を実行します。'
ms.openlocfilehash: 0b853a071116525ad313cf351685124bf92782a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303355"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="34a7f-105">ドメイン内のレプリケーションの確認</span><span class="sxs-lookup"><span data-stu-id="34a7f-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="34a7f-106">**「手順 1: スキーマの準備**」で行われたドメインの準備の複製を確認するには、Skype For Business Server 管理シェル Lync Server management shell からコマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="34a7f-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="34a7f-107">Windows PowerShell コマンドレットを実行するには、準備したドメインのメンバーであるコンピューター、および Domain Admins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="34a7f-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="34a7f-108">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="34a7f-108">Do the following:</span></span>
  
1. <span data-ttu-id="34a7f-109">Skype for Business Server 管理シェルを開始します。 [**スタート**]、[**すべてのプログラム**]、[ **skype For business**]、[ **skype for business server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="34a7f-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="34a7f-110">Windows PowerShell で、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="34a7f-110">In Windows PowerShell, type the following:</span></span>
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="34a7f-111">例:</span><span class="sxs-lookup"><span data-stu-id="34a7f-111">For example:</span></span>
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="34a7f-112">パラメーター GlobalSettingsDomainController を使用して、グローバル設定を保存する場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="34a7f-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="34a7f-113">設定がシステムコンテナーに保存されている場合 (つまり、グローバル設定が構成コンテナーに移行されていないアップグレード展開で一般的)、Active Directory ドメインサービスフォレストのルートでドメインコントローラーを定義します。</span><span class="sxs-lookup"><span data-stu-id="34a7f-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="34a7f-114">グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。</span><span class="sxs-lookup"><span data-stu-id="34a7f-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="34a7f-115">このパラメーターを指定しない場合、コマンドレットでは、設定が構成コンテナーに保存されていると見なして、Active Directory の任意のドメイン コントローラーを参照します。</span><span class="sxs-lookup"><span data-stu-id="34a7f-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="34a7f-116">Domain パラメーターを指定しない場合、値はローカル ドメインに設定されます。</span><span class="sxs-lookup"><span data-stu-id="34a7f-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="34a7f-117">ドメインの準備が成功した場合、このコマンドレットを実行すると、値 **LC_DOMAIN_SETTINGS_STATE_READY** が戻されます。</span><span class="sxs-lookup"><span data-stu-id="34a7f-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

