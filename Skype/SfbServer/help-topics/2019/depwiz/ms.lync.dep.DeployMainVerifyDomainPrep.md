---
title: ドメイン内のレプリケーションの確認
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: '「手順 1: スキーマを準備する」で実行したドメイン準備のレプリケーションを確認するには、Skype for Business Server 管理シェル Lync Server 管理シェルからコマンドレットを実行する必要があります。 Windows PowerShell コマンドレットを実行するには、準備したドメインのメンバーであるコンピューターに Domain Admins グループのメンバーとしてログオンします。 次の操作を行ってください。'
ms.openlocfilehash: 9ec39551702e0f3480671787536929863cb61f6b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801657"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="82888-105">ドメイン内のレプリケーションの確認</span><span class="sxs-lookup"><span data-stu-id="82888-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="82888-106">「手順 **1:** スキーマを準備する」で実行したドメイン準備のレプリケーションを確認するには、Skype for Business Server 管理シェル Lync Server 管理シェルからコマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82888-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="82888-107">Windows PowerShell コマンドレットを実行するには、準備したドメインのメンバーであるコンピューターに Domain Admins グループのメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="82888-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="82888-108">次の操作を行ってください。</span><span class="sxs-lookup"><span data-stu-id="82888-108">Do the following:</span></span>
  
1. <span data-ttu-id="82888-109">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82888-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="82888-110">次Windows PowerShell入力します。</span><span class="sxs-lookup"><span data-stu-id="82888-110">In Windows PowerShell, type the following:</span></span>
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="82888-111">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="82888-111">For example:</span></span>
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="82888-112">パラメーター GlobalSettingsDomainController を使用して、グローバル設定を保存する場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="82888-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="82888-113">設定がシステム コンテナーに格納されている場合 (グローバル設定が構成コンテナーに移行されていないアップグレード展開で一般的)、Active Directory ドメイン サービス フォレストのルートにドメイン コントローラーを定義します。</span><span class="sxs-lookup"><span data-stu-id="82888-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="82888-114">グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。</span><span class="sxs-lookup"><span data-stu-id="82888-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="82888-115">このパラメーターを指定しない場合、コマンドレットは設定が構成コンテナーに格納され、Active Directory 内の任意のドメイン コントローラーを参照すると想定します。</span><span class="sxs-lookup"><span data-stu-id="82888-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="82888-116">Domain パラメーターを指定しない場合、値はローカル ドメインに設定されます。</span><span class="sxs-lookup"><span data-stu-id="82888-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="82888-117">ドメインの準備が成功した場合、このコマンドレットを実行すると、値 **LC_DOMAIN_SETTINGS_STATE_READY** が戻されます。</span><span class="sxs-lookup"><span data-stu-id="82888-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

