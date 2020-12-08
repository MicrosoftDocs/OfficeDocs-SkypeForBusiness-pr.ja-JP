---
title: ダイレクトルーティング SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 詳細については、「構成」、「基本的な展開の決定事項」、「ボイスルーティングの考慮事項」などのダイレクトルーティングについて説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9e64dc908bafdd63b17e22716e76c4f04df1409
ms.sourcegitcommit: f122c078b6458754500f3cc68086d6ccfa62d183
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588601"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a><span data-ttu-id="13d4e-103">Survivable Branch Appliance (SBA) – Direct Routing-パブリックプレビュー</span><span class="sxs-lookup"><span data-stu-id="13d4e-103">Survivable Branch Appliance (SBA) for Direct Routing - Public Preview</span></span>


> [!NOTE]
> <span data-ttu-id="13d4e-104">これはパブリックプレビューのリリースです。</span><span class="sxs-lookup"><span data-stu-id="13d4e-104">This is a public preview release.</span></span>

<span data-ttu-id="13d4e-105">場合によっては、ダイレクトルーティングを使用して Microsoft 電話システムに接続すると、インターネットが停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="13d4e-105">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="13d4e-106">顧客サイト------------------------------------------</span><span class="sxs-lookup"><span data-stu-id="13d4e-106">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="13d4e-107">ただし、ブランチ内のイントラネットは完全に機能しているため、ユーザーは PSTN 接続を提供するセッションボーダーコントローラー (SBC) に接続できます。</span><span class="sxs-lookup"><span data-stu-id="13d4e-107">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="13d4e-108">この記事では、Survivable Branch Appliance (SBA) を使用して、停止時に Microsoft 電話システムが PSTN (公衆交換電話網) 通話の発信と受信を継続できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-108">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="13d4e-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="13d4e-109">Prerequisites</span></span>

<span data-ttu-id="13d4e-110">SBA は、Microsoft が、そのコードを SBCs のファームウェアに埋め込むために Microsoft が提供する配布可能なコードです。</span><span class="sxs-lookup"><span data-stu-id="13d4e-110">The SBA is distributable code provided by Microsoft to SBC vendors who then embed the code into the firmware of their SBCs.</span></span> 

<span data-ttu-id="13d4e-111">埋め込まれた Survivable Branch アプライアンスを使って、最新のセッションボーダーコントローラーのファームウェアを取得するには、SBC ベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="13d4e-111">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="13d4e-112">さらに、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="13d4e-112">In addition, the following is required:</span></span>

- <span data-ttu-id="13d4e-113">この SBC は、メディアをバイパスするように構成する必要があります。これにより、ブランチサイトの Microsoft Teams クライアントは、SBC でメディアに直接流れることができます。</span><span class="sxs-lookup"><span data-stu-id="13d4e-113">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="13d4e-114">SBA VM OS で TLS 1.2 を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="13d4e-114">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="13d4e-115">サポートされているチームクライアント</span><span class="sxs-lookup"><span data-stu-id="13d4e-115">Supported Teams clients</span></span>

<span data-ttu-id="13d4e-116">SBA 機能は、次の Microsoft Teams クライアントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="13d4e-116">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="13d4e-117">Microsoft Teams Windows デスクトップ</span><span class="sxs-lookup"><span data-stu-id="13d4e-117">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="13d4e-118">Microsoft Teams macOS デスクトップ</span><span class="sxs-lookup"><span data-stu-id="13d4e-118">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="13d4e-119">メカニズム</span><span class="sxs-lookup"><span data-stu-id="13d4e-119">How it works</span></span>

<span data-ttu-id="13d4e-120">インターネットの停止中は、チームクライアントが SBA に自動的に切り替える必要があります。進行中の通話は、引き続き中断されます。</span><span class="sxs-lookup"><span data-stu-id="13d4e-120">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="13d4e-121">ユーザーからの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="13d4e-121">No action is required from the user.</span></span> <span data-ttu-id="13d4e-122">チームクライアントがインターネットが稼働していることを検出し、発信通話が完了したら、クライアントは通常の操作モードに戻り、他の Teams サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-122">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="13d4e-123">SBA によって、収集された通話データレコードがクラウドにアップロードされ、通話履歴が更新され、テナント管理者がこの情報を確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="13d4e-123">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="13d4e-124">Microsoft Teams クライアントがオフラインモードの場合は、次のような呼び出しに関連する機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="13d4e-124">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="13d4e-125">ローカルの SBA/SBC 経由で、メディアを SBC を介して流れる PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="13d4e-125">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="13d4e-126">ローカルの SBA/SBC での PSTN 通話の受信。 SBC を介してメディアが流れます。</span><span class="sxs-lookup"><span data-stu-id="13d4e-126">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="13d4e-127">PSTN 通話を保留および再開します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-127">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="13d4e-128">構成</span><span class="sxs-lookup"><span data-stu-id="13d4e-128">Configuration</span></span>

<span data-ttu-id="13d4e-129">SBA 機能が機能するためには、チームクライアントは、どの SBAs が各ブランチサイトで利用可能で、どの SBAs がそのサイトのユーザーに割り当てられているかを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="13d4e-129">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="13d4e-130">構成の手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="13d4e-130">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="13d4e-131">SBAs を作成します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-131">Create the SBAs.</span></span>
2. <span data-ttu-id="13d4e-132">Teams ブランチ survivability ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-132">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="13d4e-133">ユーザーにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="13d4e-133">Assign the policy to users.</span></span>
4. <span data-ttu-id="13d4e-134">Azure Active Directory を使用して SBA にアプリケーションを登録します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-134">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="13d4e-135">すべての構成は、Skype for Business Online PowerShell コマンドレットを使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="13d4e-135">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="13d4e-136">(Teams 管理センターでは、ダイレクトルーティング SBA 機能はまだサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="13d4e-136">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="13d4e-137">(SBC の設定方法については、「SBC ベンダーのドキュメントへのリンク」を参照してください)。この記事の最後にある「セッション境界コントローラーの構成」をご覧ください。)</span><span class="sxs-lookup"><span data-stu-id="13d4e-137">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="13d4e-138">SBAs を作成する</span><span class="sxs-lookup"><span data-stu-id="13d4e-138">Create the SBAs</span></span>

<span data-ttu-id="13d4e-139">SBAs を作成するには、New-CsTeamsSurvivableBranchAppliance コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-139">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="13d4e-140">このコマンドレットには、次のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="13d4e-140">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="13d4e-141">パラメーター</span><span class="sxs-lookup"><span data-stu-id="13d4e-141">Parameter</span></span>| <span data-ttu-id="13d4e-142">説明</span><span class="sxs-lookup"><span data-stu-id="13d4e-142">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="13d4e-143">Identity</span><span class="sxs-lookup"><span data-stu-id="13d4e-143">Identity</span></span>  | <span data-ttu-id="13d4e-144">SBA の FQDN</span><span class="sxs-lookup"><span data-stu-id="13d4e-144">The FQDN of the SBA</span></span>  |
| <span data-ttu-id="13d4e-145">Fqdn</span><span class="sxs-lookup"><span data-stu-id="13d4e-145">Fqdn</span></span> | <span data-ttu-id="13d4e-146">SBA の FQDN</span><span class="sxs-lookup"><span data-stu-id="13d4e-146">The FQDN of the SBA</span></span> |
| <span data-ttu-id="13d4e-147">サイト</span><span class="sxs-lookup"><span data-stu-id="13d4e-147">Site</span></span> | <span data-ttu-id="13d4e-148">SBA が配置されている TenantNetworkSite</span><span class="sxs-lookup"><span data-stu-id="13d4e-148">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="13d4e-149">説明</span><span class="sxs-lookup"><span data-stu-id="13d4e-149">Description</span></span> | <span data-ttu-id="13d4e-150">テキストを無料で表示</span><span class="sxs-lookup"><span data-stu-id="13d4e-150">Free format text</span></span> |
|||

<span data-ttu-id="13d4e-151">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-151">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.dk -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="13d4e-152">Teams ブランチ Survivability ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="13d4e-152">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="13d4e-153">ポリシーを作成するには、New-CsTeamsSurvivableBranchAppliancePolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-153">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="13d4e-154">このコマンドレットには、次のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="13d4e-154">This cmdlet has the following parameters.</span></span> <span data-ttu-id="13d4e-155">ポリシーには1つ以上の SBAs を含めることができることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="13d4e-155">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="13d4e-156">パラメーター</span><span class="sxs-lookup"><span data-stu-id="13d4e-156">Parameter</span></span>| <span data-ttu-id="13d4e-157">説明</span><span class="sxs-lookup"><span data-stu-id="13d4e-157">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="13d4e-158">Identity</span><span class="sxs-lookup"><span data-stu-id="13d4e-158">Identity</span></span> | <span data-ttu-id="13d4e-159">ポリシーの id</span><span class="sxs-lookup"><span data-stu-id="13d4e-159">The identity of the policy</span></span> |
| <span data-ttu-id="13d4e-160">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="13d4e-160">BranchApplianceFqdns</span></span>  | <span data-ttu-id="13d4e-161">サイト内の SBA の FQDN。</span><span class="sxs-lookup"><span data-stu-id="13d4e-161">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="13d4e-162">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-162">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.dk, sba2.contoso.com} 
```

<span data-ttu-id="13d4e-163">Set-CsTeamsSurvivableBranchAppliancePolicy コマンドレットを使用して、ポリシーから SBAs を追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="13d4e-163">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="13d4e-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-164">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="13d4e-165">ユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="13d4e-165">Assign a policy to a user</span></span>

<span data-ttu-id="13d4e-166">個々のユーザーにポリシーを割り当てるには、Grant-CsTeamsSurvivableBranchAppliancePolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-166">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="13d4e-167">このコマンドレットには、次のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="13d4e-167">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="13d4e-168">パラメーター</span><span class="sxs-lookup"><span data-stu-id="13d4e-168">Parameter</span></span>| <span data-ttu-id="13d4e-169">説明</span><span class="sxs-lookup"><span data-stu-id="13d4e-169">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="13d4e-170">Identity</span><span class="sxs-lookup"><span data-stu-id="13d4e-170">Identity</span></span> | <span data-ttu-id="13d4e-171">ユーザーの id</span><span class="sxs-lookup"><span data-stu-id="13d4e-171">The identity of the user</span></span> |
| <span data-ttu-id="13d4e-172">PolicyName</span><span class="sxs-lookup"><span data-stu-id="13d4e-172">PolicyName</span></span> | <span data-ttu-id="13d4e-173">ポリシーの id</span><span class="sxs-lookup"><span data-stu-id="13d4e-173">The identity of the policy</span></span> |
||

<span data-ttu-id="13d4e-174">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-174">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="13d4e-175">次の例に示すように、$Null ポリシーを付与することで、ユーザーからポリシーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="13d4e-175">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="13d4e-176">Azure Active Directory を使用して SBA にアプリケーションを登録する</span><span class="sxs-lookup"><span data-stu-id="13d4e-176">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="13d4e-177">テナント内で別の SBAs を使用して、Microsoft 365 から必要なデータを読み取ることができるようにするには、SBA 用のアプリケーションを Azure Active Directory と共に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13d4e-177">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="13d4e-178">アプリケーションの登録の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13d4e-178">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="13d4e-179">Azure Active Directory 用の基幹業務アプリの開発</span><span class="sxs-lookup"><span data-stu-id="13d4e-179">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="13d4e-180">[Microsoft identity platform にアプリケーションを登録](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-180">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="13d4e-181">テナント内のすべての SBAs で使用する1つのアプリケーションのみ登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13d4e-181">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="13d4e-182">SBA の登録では、登録によって作成される次の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13d4e-182">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="13d4e-183">アプリケーション (クライアント) ID</span><span class="sxs-lookup"><span data-stu-id="13d4e-183">Application (client) ID</span></span> 
- <span data-ttu-id="13d4e-184">クライアントシークレット</span><span class="sxs-lookup"><span data-stu-id="13d4e-184">Client secret</span></span> 

<span data-ttu-id="13d4e-185">SBA アプリケーションの場合は、次の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="13d4e-185">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="13d4e-186">名前は任意の名前にすることができます。</span><span class="sxs-lookup"><span data-stu-id="13d4e-186">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="13d4e-187">サポートされているアカウントの種類 = この組織ディレクトリのアカウントのみ。</span><span class="sxs-lookup"><span data-stu-id="13d4e-187">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="13d4e-188">Web リダイレクト Uri = https://login.microsoftonline.com/common/oauth2/nativeclient 。</span><span class="sxs-lookup"><span data-stu-id="13d4e-188">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="13d4e-189">暗黙的な許可トークン = アクセストークンと ID トークン。</span><span class="sxs-lookup"><span data-stu-id="13d4e-189">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="13d4e-190">API 権限 = Skype および Teams のテナント管理者アクセス-> アプリケーションのアクセス許可 > application_access_custom_sba_appliance。</span><span class="sxs-lookup"><span data-stu-id="13d4e-190">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="13d4e-191">クライアントシークレット: 任意の説明と有効期限を使用できます。</span><span class="sxs-lookup"><span data-stu-id="13d4e-191">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="13d4e-192">クライアントシークレットは、作成した後すぐにコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="13d4e-192">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="13d4e-193">アプリケーション (クライアント) ID は [概要] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="13d4e-193">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="13d4e-194">次に、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-194">Then follow these steps:</span></span>

1. <span data-ttu-id="13d4e-195">アプリケーションを登録します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-195">Register the application.</span></span>
2. <span data-ttu-id="13d4e-196">暗黙的な grant トークンを設定します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-196">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="13d4e-197">API のアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-197">Set the API permissions.</span></span>
4. <span data-ttu-id="13d4e-198">クライアントシークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-198">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="13d4e-199">セッション境界コントローラー構成</span><span class="sxs-lookup"><span data-stu-id="13d4e-199">Session Border Controller configuration</span></span> 

<span data-ttu-id="13d4e-200">埋め込まれた Survivable Branch Appliance を使ってセッション境界コントローラーを構成する方法については、「SBC ベンダーから提供されるドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13d4e-200">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="13d4e-201">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="13d4e-201">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="13d4e-202">リボン</span><span class="sxs-lookup"><span data-stu-id="13d4e-202">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="13d4e-203">Oracle</span><span class="sxs-lookup"><span data-stu-id="13d4e-203">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="13d4e-204">TE (システム)</span><span class="sxs-lookup"><span data-stu-id="13d4e-204">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="13d4e-205">問題の報告</span><span class="sxs-lookup"><span data-stu-id="13d4e-205">Reporting issues</span></span>

<span data-ttu-id="13d4e-206">問題が SBC ベンダーのサポート組織に報告されます。</span><span class="sxs-lookup"><span data-stu-id="13d4e-206">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="13d4e-207">問題を報告するときに、Survivable Branch アプライアンスが構成されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="13d4e-207">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="13d4e-208">既知の問題</span><span class="sxs-lookup"><span data-stu-id="13d4e-208">Known issues</span></span>

- <span data-ttu-id="13d4e-209">新しい Survivable Branch アプライアンスを追加した場合、Survivable Branch Appliance のポリシーで使用できるようになるまでに少し時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="13d4e-209">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="13d4e-210">Survivable Branch Appliance のポリシーをユーザーに割り当てる場合は、SBA が Get Csonline ユーザーの出力に表示されるまでに少し時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="13d4e-210">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="13d4e-211">Azure AD の連絡先に対して数値のルックアップを逆に実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="13d4e-211">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="13d4e-212">SBA は、着信の転送設定をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="13d4e-212">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="13d4e-213">動的な緊急通報 (E911) 用に設定された緊急電話番号への緊急通話の発信はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="13d4e-213">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="13d4e-214">Get-CsOnlineUser の出力に TeamsBranchSurvivabilityPolicy が表示されます。</span><span class="sxs-lookup"><span data-stu-id="13d4e-214">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
