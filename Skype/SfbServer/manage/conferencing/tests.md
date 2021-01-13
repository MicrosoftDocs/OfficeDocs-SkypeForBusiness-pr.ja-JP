---
title: Skype for Business Server でのダイヤルイン会議のテスト
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: '概要: Skype for Business Server でダイヤルイン会議をテストする方法について説明します。'
ms.openlocfilehash: 214ec05c49072825e6a8744cb92db66d864e3d34
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827937"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="06066-103">Skype for Business Server でのダイヤルイン会議のテスト</span><span class="sxs-lookup"><span data-stu-id="06066-103">Test dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="06066-104">**概要:** Skype for Business Server でダイヤルイン会議をテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="06066-104">**Summary:** Learn how to test dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="06066-105">ダイヤルイン会議構成の最後の確認作業として、どのアクセス番号も使用しないダイヤルイン会議の地域があるダイヤル プランやダイヤルイン会議の地域が指定されていないアクセス番号を検索します。</span><span class="sxs-lookup"><span data-stu-id="06066-105">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="06066-106">また、ダイヤルイン会議の設定 Web ページとダイヤルイン アクセス番号が正しく機能する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06066-106">You should also verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly.</span></span>
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="06066-107">アクセス番号で使用されないダイヤルイン会議地域のダイヤル プランを検索する</span><span class="sxs-lookup"><span data-stu-id="06066-107">Find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1. <span data-ttu-id="06066-108">RTCUniversalServerAdmins グループのメンバーか、Cs-ServerAdministrator または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="06066-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="06066-109">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06066-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="06066-110">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="06066-110">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    <span data-ttu-id="06066-111">このコマンドレットは、どのアクセス番号も使用していないダイヤルイン会議の地域がある、すべてのダイヤル プランを返します。</span><span class="sxs-lookup"><span data-stu-id="06066-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>
    
<span data-ttu-id="06066-112">詳細については [、「Get-CsDialInConferencingAccessNumber」を参照してください](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="06066-112">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="find-access-numbers-without-assigned-regions"></a><span data-ttu-id="06066-113">地域が割り当てられていないアクセス番号を検索する</span><span class="sxs-lookup"><span data-stu-id="06066-113">Find access numbers without assigned regions</span></span>

1. <span data-ttu-id="06066-114">RTCUniversalServerAdmins グループのメンバーか、Cs-ServerAdministrator または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="06066-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="06066-115">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06066-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="06066-116">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="06066-116">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    <span data-ttu-id="06066-117">このコマンドレットは、地域に関連付けられていないダイヤルイン会議のアクセス番号をすべて返します。</span><span class="sxs-lookup"><span data-stu-id="06066-117">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>
    
<span data-ttu-id="06066-118">詳細については [、「Get-CsDialInConferencingAccessNumber」を参照してください](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="06066-118">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="test-webpage-and-access-numbers"></a><span data-ttu-id="06066-119">Web ページとアクセス番号をテストする</span><span class="sxs-lookup"><span data-stu-id="06066-119">Test webpage and access numbers</span></span>

<span data-ttu-id="06066-120">ダイヤルイン会議の設定の Web ページとダイヤルイン アクセス番号が正しく動作していることを確認するには、以下を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06066-120">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>
  
- <span data-ttu-id="06066-121">簡単な URL にサインインして、ダイヤルイン会議の設定の Web ページをテストします。</span><span class="sxs-lookup"><span data-stu-id="06066-121">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>
    
- <span data-ttu-id="06066-p102">この後のスクリプトを実行して、特定のプールでそのアクセス番号が正しく動作することをテストします。 このスクリプトは、アクセス番号への通話をシミュレートします。 このスクリプトを使用するには、特定のプールでホストされている 1 つの統合コミュニケーション (UC) クライアントの SIP アドレスと資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="06066-p102">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="06066-125">特定のプールのアクセス番号をテストするには</span><span class="sxs-lookup"><span data-stu-id="06066-125">To test access numbers for a specific pool</span></span>

1. <span data-ttu-id="06066-126">RTCUniversalServerAdmins グループのメンバーか、Cs-ServerAdministrator または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="06066-126">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="06066-127">Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理シェル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06066-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="06066-128">コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="06066-128">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    <span data-ttu-id="06066-129">結果レポートに、コマンドの成否と特定の診断情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="06066-129">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="06066-130">-Verbose フラグは、検出されたアクセス番号の数と、その詳細に関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="06066-130">The -Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>
    
<span data-ttu-id="06066-131">詳細については [、「Test-CsDialInConferencing」を参照してください](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="06066-131">For more information, see [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span></span>
  

