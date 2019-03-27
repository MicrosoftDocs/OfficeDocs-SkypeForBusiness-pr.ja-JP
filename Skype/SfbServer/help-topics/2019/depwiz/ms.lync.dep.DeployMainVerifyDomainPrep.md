---
title: ドメイン内のレプリケーションの確認
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'ドメインの準備手順 1 で実行のレプリケーションを確認する: スキーマの準備、Skype からビジネス サーバー管理シェル Lync Server 管理シェルのコマンドレットを実行する必要があります。 Windows PowerShell コマンドレットを実行するには、Domain Admins グループのメンバーと、準備したドメインのメンバーであるコンピューターにログオンします。 次の手順を実行します。'
ms.openlocfilehash: 8adec80d9f0874e395150941cada02f58099bce9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884520"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="212ea-105">ドメイン内のレプリケーションの確認</span><span class="sxs-lookup"><span data-stu-id="212ea-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="212ea-106">ドメインの準備の実行のレプリケーションを確認するのには**ステップ 1: スキーマの準備**、Skype からビジネス サーバー管理シェル Lync Server 管理シェルのコマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="212ea-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="212ea-107">Windows PowerShell コマンドレットを実行するには、Domain Admins グループのメンバーと、準備したドメインのメンバーであるコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="212ea-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="212ea-108">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="212ea-108">Do the following:</span></span>
  
1. <span data-ttu-id="212ea-109">ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネスの Skype**をクリック**ビジネス サーバー管理シェルの Skype**です。</span><span class="sxs-lookup"><span data-stu-id="212ea-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="212ea-110">Windows PowerShell では、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="212ea-110">In Windows PowerShell, type the following:</span></span>
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="212ea-111">例:</span><span class="sxs-lookup"><span data-stu-id="212ea-111">For example:</span></span>
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="212ea-112">パラメーター GlobalSettingsDomainController を使用して、グローバル設定を保存する場所を指定できます。</span><span class="sxs-lookup"><span data-stu-id="212ea-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="212ea-113">システム コンテナーではよくあるアップグレードの展開、構成コンテナーに移行したグローバル設定が行われていない) では、設定が保存されている場合、Active Directory ドメイン サービス フォレストのルート ドメイン コント ローラーを定義します。</span><span class="sxs-lookup"><span data-stu-id="212ea-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="212ea-114">グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。</span><span class="sxs-lookup"><span data-stu-id="212ea-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="212ea-115">このパラメーターを指定しない場合、コマンドレットでは、設定が構成コンテナーに保存されていると見なして、Active Directory の任意のドメイン コントローラーを参照します。</span><span class="sxs-lookup"><span data-stu-id="212ea-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="212ea-116">Domain パラメーターを指定しない場合、値はローカル ドメインに設定されます。</span><span class="sxs-lookup"><span data-stu-id="212ea-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="212ea-117">ドメインの準備が成功した場合、このコマンドレットを実行すると、値 **LC_DOMAIN_SETTINGS_STATE_READY** が戻されます。</span><span class="sxs-lookup"><span data-stu-id="212ea-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

