---
title: ダイレクト ルーティング SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
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
description: 構成、必要なコア デプロイの決定、音声ルーティングに関する考慮事項など、ダイレクト ルーティングの詳細について説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: edf2c2a97bec2b167f1218d983d3c9f7fa4bd667
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096427"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a><span data-ttu-id="7f9d0-103">ダイレクト ルーティングのための存続可能ブランチ アプライアンス (SBA)</span><span class="sxs-lookup"><span data-stu-id="7f9d0-103">Survivable Branch Appliance (SBA) for Direct Routing</span></span>


<span data-ttu-id="7f9d0-104">場合によっては、ダイレクト ルーティングを使用してシステムに接続する顧客サイトMicrosoft 電話インターネットが停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-104">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="7f9d0-105">ブランチと呼ばれるお客様のサイトが、直接ルーティングを介して一時的に Microsoft クラウドに接続できないとします。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-105">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="7f9d0-106">ただし、ブランチ内のイントラネットは引き続き完全に機能し、ユーザーは PSTN 接続を提供するセッション ボーダー コントローラー (SBC) に接続できます。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-106">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="7f9d0-107">この記事では、存続可能ブランチ アプライアンス (SBA) を使用して、障害が発生した場合に Microsoft 電話 System が引き続き公衆交換電話網 (PSTN) 通話を発信および受信できる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-107">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7f9d0-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="7f9d0-108">Prerequisites</span></span>

<span data-ttu-id="7f9d0-109">SBA は、Microsoft が SBC ベンダーに提供する再配布可能なコードです。その後、コードをファームウェアに埋め込むか、別の VM またはハードウェアで SBA を実行するために個別に配布します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-109">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="7f9d0-110">組み込みの存続可能ブランチ アプライアンスを使用して最新のセッション ボーダー コントローラー ファームウェアを取得するには、SBC ベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-110">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="7f9d0-111">さらに、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-111">In addition, the following is required:</span></span>

- <span data-ttu-id="7f9d0-112">ブランチ サイト内の Microsoft Teams クライアントが SBC と直接流れるメディアを確保するには、メディア バイパス用に SBC を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-112">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="7f9d0-113">SBA VM OS で TLS1.2 を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-113">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="7f9d0-114">サポートされているTeams クライアント</span><span class="sxs-lookup"><span data-stu-id="7f9d0-114">Supported Teams clients</span></span>

<span data-ttu-id="7f9d0-115">SBA 機能は、次のクライアントでMicrosoft Teamsされます。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-115">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="7f9d0-116">Microsoft Teams Windows デスクトップ</span><span class="sxs-lookup"><span data-stu-id="7f9d0-116">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="7f9d0-117">Microsoft Teams macOS デスクトップ</span><span class="sxs-lookup"><span data-stu-id="7f9d0-117">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="7f9d0-118">メカニズム</span><span class="sxs-lookup"><span data-stu-id="7f9d0-118">How it works</span></span>

<span data-ttu-id="7f9d0-119">インターネットの停止中、クライアントTeams自動的に SBA に切り替える必要があります。また、継続的な呼び出しは中断することなく続行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-119">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="7f9d0-120">ユーザーからのアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-120">No action is required from the user.</span></span> <span data-ttu-id="7f9d0-121">Teams クライアントがインターネットが稼働し、すべての発信呼び出しが完了するとすぐに、クライアントは通常の操作モードに戻り、他の Teams サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-121">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="7f9d0-122">SBA は収集された通話データ レコードをクラウドにアップロードし、通話履歴が更新され、テナント管理者がこの情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-122">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="7f9d0-123">クライアントがMicrosoft Teamsモードの場合、次の呼び出し関連機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-123">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="7f9d0-124">ローカル SBA/SBC 経由で PSTN 通話を行い、SBC を通過するメディアを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-124">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="7f9d0-125">SBC を通過するメディアを使用してローカル SBA/SBC 経由で PSTN 通話を受信する。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-125">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="7f9d0-126">PSTN 通話の保留と再開。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-126">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="7f9d0-127">構成</span><span class="sxs-lookup"><span data-stu-id="7f9d0-127">Configuration</span></span>

<span data-ttu-id="7f9d0-128">SBA 機能を機能するには、Teams クライアントは、各ブランチ サイトで使用できる SBA と、そのサイト内のユーザーに割り当てられている SBA を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-128">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="7f9d0-129">構成手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-129">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="7f9d0-130">SBA を作成します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-130">Create the SBAs.</span></span>
2. <span data-ttu-id="7f9d0-131">ブランチの存続Teamsポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-131">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="7f9d0-132">ポリシーをユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-132">Assign the policy to users.</span></span>
4. <span data-ttu-id="7f9d0-133">SBA のアプリケーションをアプリケーションに登録Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-133">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="7f9d0-134">すべての構成は、オンライン PowerShell コマンドレットSkype for Business使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-134">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="7f9d0-135">(Teams センターでは、直接ルーティング SBA 機能はまだサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-135">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="7f9d0-136">(SBC ベンダーのドキュメントへのリンクを含む SBC の構成については、この記事の最後にある「セッション ボーダー コントローラーの構成」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-136">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="7f9d0-137">SBA を作成する</span><span class="sxs-lookup"><span data-stu-id="7f9d0-137">Create the SBAs</span></span>

<span data-ttu-id="7f9d0-138">SA を作成するには、次のコマンドレットNew-CsTeamsSurvivableBranchApplianceします。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-138">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="7f9d0-139">このコマンドレットには、次のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-139">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="7f9d0-140">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7f9d0-140">Parameter</span></span>| <span data-ttu-id="7f9d0-141">説明</span><span class="sxs-lookup"><span data-stu-id="7f9d0-141">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="7f9d0-142">Identity</span><span class="sxs-lookup"><span data-stu-id="7f9d0-142">Identity</span></span>  | <span data-ttu-id="7f9d0-143">SBA の ID</span><span class="sxs-lookup"><span data-stu-id="7f9d0-143">The identity of the SBA</span></span>  |
| <span data-ttu-id="7f9d0-144">Fqdn</span><span class="sxs-lookup"><span data-stu-id="7f9d0-144">Fqdn</span></span> | <span data-ttu-id="7f9d0-145">SBA の FQDN</span><span class="sxs-lookup"><span data-stu-id="7f9d0-145">The FQDN of the SBA</span></span> |
| <span data-ttu-id="7f9d0-146">サイト</span><span class="sxs-lookup"><span data-stu-id="7f9d0-146">Site</span></span> | <span data-ttu-id="7f9d0-147">SBA がある TenantNetworkSite</span><span class="sxs-lookup"><span data-stu-id="7f9d0-147">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="7f9d0-148">説明</span><span class="sxs-lookup"><span data-stu-id="7f9d0-148">Description</span></span> | <span data-ttu-id="7f9d0-149">自由形式のテキスト</span><span class="sxs-lookup"><span data-stu-id="7f9d0-149">Free format text</span></span> |
|||

<span data-ttu-id="7f9d0-150">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-150">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="7f9d0-151">ブランチの存続Teamsポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="7f9d0-151">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="7f9d0-152">ポリシーを作成するには、次のコマンドレットNew-CsTeamsSurvivableBranchAppliancePolicyします。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-152">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="7f9d0-153">このコマンドレットには、次のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-153">This cmdlet has the following parameters.</span></span> <span data-ttu-id="7f9d0-154">ポリシーには、1 つ以上の SBA を含め得る点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-154">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="7f9d0-155">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7f9d0-155">Parameter</span></span>| <span data-ttu-id="7f9d0-156">説明</span><span class="sxs-lookup"><span data-stu-id="7f9d0-156">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="7f9d0-157">Identity</span><span class="sxs-lookup"><span data-stu-id="7f9d0-157">Identity</span></span> | <span data-ttu-id="7f9d0-158">ポリシーの ID</span><span class="sxs-lookup"><span data-stu-id="7f9d0-158">The identity of the policy</span></span> |
| <span data-ttu-id="7f9d0-159">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="7f9d0-159">BranchApplianceFqdns</span></span>  | <span data-ttu-id="7f9d0-160">サイト内の SBA の FQDN</span><span class="sxs-lookup"><span data-stu-id="7f9d0-160">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="7f9d0-161">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-161">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="7f9d0-162">次のコマンドレットを使用して、ポリシーの SBA を追加Set-CsTeamsSurvivableBranchAppliancePolicyできます。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-162">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="7f9d0-163">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-163">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="7f9d0-164">ユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="7f9d0-164">Assign a policy to a user</span></span>

<span data-ttu-id="7f9d0-165">ポリシーを個々のユーザーに割り当てるには、次のコマンドレットGrant-CsTeamsSurvivableBranchAppliancePolicyします。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-165">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="7f9d0-166">このコマンドレットには、次のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-166">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="7f9d0-167">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7f9d0-167">Parameter</span></span>| <span data-ttu-id="7f9d0-168">説明</span><span class="sxs-lookup"><span data-stu-id="7f9d0-168">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="7f9d0-169">Identity</span><span class="sxs-lookup"><span data-stu-id="7f9d0-169">Identity</span></span> | <span data-ttu-id="7f9d0-170">ユーザーの ID</span><span class="sxs-lookup"><span data-stu-id="7f9d0-170">The identity of the user</span></span> |
| <span data-ttu-id="7f9d0-171">PolicyName</span><span class="sxs-lookup"><span data-stu-id="7f9d0-171">PolicyName</span></span> | <span data-ttu-id="7f9d0-172">ポリシーの ID</span><span class="sxs-lookup"><span data-stu-id="7f9d0-172">The identity of the policy</span></span> |
||

<span data-ttu-id="7f9d0-173">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-173">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="7f9d0-174">ユーザーからポリシーを削除するには、次の例に$Nullポリシーを付与します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-174">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="7f9d0-175">SBA のアプリケーションをアプリケーションに登録Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7f9d0-175">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="7f9d0-176">テナント内で使用される異なる SBA が Microsoft 365 から必要なデータを読み取るのを許可するには、SBA のアプリケーションを Azure Active Directory に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-176">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="7f9d0-177">アプリケーションの登録の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-177">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="7f9d0-178">新しいビジネス アプリを開発Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7f9d0-178">Develop line-of-business apps for Azure Active Directory</span></span>](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="7f9d0-179">[アプリケーションを Microsoft ID プラットフォーム に登録します](/azure/active-directory/develop/quickstart-register-app)。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-179">[Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="7f9d0-180">登録する必要があるアプリケーションは、テナント内のすべての SBA で使用するために 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-180">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="7f9d0-181">SBA 登録には、登録によって作成された次の値が必要です。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-181">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="7f9d0-182">アプリケーション (クライアント) ID</span><span class="sxs-lookup"><span data-stu-id="7f9d0-182">Application (client) ID</span></span> 
- <span data-ttu-id="7f9d0-183">クライアント シークレット</span><span class="sxs-lookup"><span data-stu-id="7f9d0-183">Client secret</span></span> 

<span data-ttu-id="7f9d0-184">SBA アプリケーションの場合は、次の注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-184">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="7f9d0-185">名前は、ユーザーが決定した名前にできます。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-185">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="7f9d0-186">サポートされているアカウントの種類 = この組織のディレクトリ内のアカウントのみ。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-186">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="7f9d0-187">Web リダイレクト URI = https://login.microsoftonline.com/common/oauth2/nativeclient 。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-187">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="7f9d0-188">暗黙的な付与トークン = アクセス トークンと ID トークン。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-188">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="7f9d0-189">API のアクセス許可 = SkypeテナントTeamsアクセス -> アプリケーションのアクセス許可 -> application_access_custom_sba_appliance。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-189">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="7f9d0-190">クライアント シークレット: 任意の説明と有効期限を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-190">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="7f9d0-191">クライアント シークレットは、作成後すぐにコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-191">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="7f9d0-192">アプリケーション (クライアント) ID が [概要] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-192">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="7f9d0-193">その後、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-193">Then follow these steps:</span></span>

1. <span data-ttu-id="7f9d0-194">アプリケーションを登録します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-194">Register the application.</span></span>
2. <span data-ttu-id="7f9d0-195">暗黙的な付与トークンを設定します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-195">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="7f9d0-196">API のアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-196">Set the API permissions.</span></span>
4. <span data-ttu-id="7f9d0-197">クライアント シークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-197">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="7f9d0-198">セッション ボーダー コントローラーの構成</span><span class="sxs-lookup"><span data-stu-id="7f9d0-198">Session Border Controller configuration</span></span> 

<span data-ttu-id="7f9d0-199">組み込みの Survivable Branch Appliance を使用してセッション ボーダー コントローラーを構成する方法の詳細なガイダンスについては、SBC ベンダーが提供するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-199">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="7f9d0-200">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="7f9d0-200">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="7f9d0-201">リボン</span><span class="sxs-lookup"><span data-stu-id="7f9d0-201">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="7f9d0-202">Oracle</span><span class="sxs-lookup"><span data-stu-id="7f9d0-202">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="7f9d0-203">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="7f9d0-203">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="7f9d0-204">問題の報告</span><span class="sxs-lookup"><span data-stu-id="7f9d0-204">Reporting issues</span></span>

<span data-ttu-id="7f9d0-205">SBC ベンダーのサポート組織に問題を報告します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-205">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="7f9d0-206">問題を報告する場合は、存続可能ブランチ アプライアンスが構成されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-206">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="7f9d0-207">既知の問題</span><span class="sxs-lookup"><span data-stu-id="7f9d0-207">Known issues</span></span>

- <span data-ttu-id="7f9d0-208">新しい存続可能ブランチ アプライアンスを追加する場合は、存続可能ブランチ アプライアンス ポリシーで使用できるまで時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-208">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="7f9d0-209">ユーザーに存続可能ブランチ アプライアンス ポリシーを割り当てると、Get-CsOnlineUser の出力に SBA が表示されるまで時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-209">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="7f9d0-210">Azure ADに対する逆引き番号参照は実行されません。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-210">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="7f9d0-211">SBA では、通話の転送設定はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-211">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="7f9d0-212">動的緊急通話 (E911) 用に構成された緊急電話番号への緊急通話はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-212">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="7f9d0-213">このコマンドの出力Get-CsOnlineUser TeamsBranchSurvivabilityPolicy が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7f9d0-213">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>