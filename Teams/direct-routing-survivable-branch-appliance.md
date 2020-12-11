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
description: 構成、必要な主要な展開決定、音声ルーティングに関する考慮事項など、ダイレクト ルーティングの詳細について説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3204bc58b083f62feca3f878d2189558b69af6bd
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620732"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a><span data-ttu-id="df2fa-103">ダイレクト ルーティング用の分岐電気機器 (SBA) - パブリック プレビュー</span><span class="sxs-lookup"><span data-stu-id="df2fa-103">Survivable Branch Appliance (SBA) for Direct Routing - Public Preview</span></span>


> [!NOTE]
> <span data-ttu-id="df2fa-104">これはパブリック プレビュー リリースです。</span><span class="sxs-lookup"><span data-stu-id="df2fa-104">This is a public preview release.</span></span>

<span data-ttu-id="df2fa-105">場合によっては、Microsoft Phone System に接続するためにダイレクト ルーティングを使用しているお客様のサイトで、インターネットが停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="df2fa-105">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="df2fa-106">ブランチと呼ばれるお客様のサイトが、直接ルーティングを通じて Microsoft クラウドに一時的に接続できないことを想定します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-106">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="df2fa-107">ただし、ブランチ内のイントラネットは引き続き完全に機能し、ユーザーは PSTN 接続を提供しているセッション ボーダー コントローラー (SBC) に接続できます。</span><span class="sxs-lookup"><span data-stu-id="df2fa-107">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="df2fa-108">この記事では、停止した場合に Microsoft Phone System が公衆交換電話網 (PSTN) 通話を発信および受信し続け、発信および受信を行う場合に、SBA (不可不可) の分岐電気機器 (SBA) を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-108">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="df2fa-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="df2fa-109">Prerequisites</span></span>

<span data-ttu-id="df2fa-110">SBA は、Microsoft が SBC ベンダーに提供するコードを配布可能なコードで、その後、ファームウェアにコードを埋め込むか、別の VM またはハードウェアで SBA を実行するために個別に配布します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-110">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="df2fa-111">埋め込まれたEdvedable Branch Controller を使用して最新のセッション ボーダー コントローラーファームウェアを取得するには、SBC ベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="df2fa-111">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="df2fa-112">さらに、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="df2fa-112">In addition, the following is required:</span></span>

- <span data-ttu-id="df2fa-113">ブランチ サイトの Microsoft Teams クライアントが SBC で直接流れるメディアを使用するには、メディア バイパス用に SBC を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2fa-113">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="df2fa-114">SBA VM OS で TLS1.2 を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2fa-114">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="df2fa-115">サポートされている Teams クライアント</span><span class="sxs-lookup"><span data-stu-id="df2fa-115">Supported Teams clients</span></span>

<span data-ttu-id="df2fa-116">SBA 機能は、次の Microsoft Teams クライアントでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="df2fa-116">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="df2fa-117">Microsoft Teams Windows デスクトップ</span><span class="sxs-lookup"><span data-stu-id="df2fa-117">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="df2fa-118">Microsoft Teams macOS デスクトップ</span><span class="sxs-lookup"><span data-stu-id="df2fa-118">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="df2fa-119">メカニズム</span><span class="sxs-lookup"><span data-stu-id="df2fa-119">How it works</span></span>

<span data-ttu-id="df2fa-120">インターネットの停止中、Teams クライアントは自動的に SBA に切り替える必要があります。継続的な通話は中断することなく継続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2fa-120">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="df2fa-121">ユーザーからの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="df2fa-121">No action is required from the user.</span></span> <span data-ttu-id="df2fa-122">Teams クライアントがインターネットが正常に動作し、すべての発信通話が完了すると、クライアントは通常の操作モードに戻り、他の Teams サービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-122">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="df2fa-123">SBA は収集された通話データ レコードをクラウドにアップロードし、この情報をテナント管理者が確認するために通話履歴が更新されます。</span><span class="sxs-lookup"><span data-stu-id="df2fa-123">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="df2fa-124">Microsoft Teams クライアントがオフライン モードの場合、次の呼び出し関連機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="df2fa-124">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="df2fa-125">SBC を経由するメディアを使用して、ローカル SBA/SBC を介して PSTN 通話を行う。</span><span class="sxs-lookup"><span data-stu-id="df2fa-125">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="df2fa-126">SBC を経由するメディアを使用して、ローカル SBA/SBC 経由で PSTN 通話を受信する。</span><span class="sxs-lookup"><span data-stu-id="df2fa-126">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="df2fa-127">PSTN 通話の保留と再開。</span><span class="sxs-lookup"><span data-stu-id="df2fa-127">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="df2fa-128">構成</span><span class="sxs-lookup"><span data-stu-id="df2fa-128">Configuration</span></span>

<span data-ttu-id="df2fa-129">SBA 機能を機能するには、Teams クライアントは、各ブランチ サイトで使用できる SBA と、そのサイト内のユーザーに割り当てられている SBA を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2fa-129">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="df2fa-130">構成手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df2fa-130">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="df2fa-131">SA を作成します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-131">Create the SBAs.</span></span>
2. <span data-ttu-id="df2fa-132">Teams ブランチのアクセス可能性ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-132">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="df2fa-133">ユーザーにポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="df2fa-133">Assign the policy to users.</span></span>
4. <span data-ttu-id="df2fa-134">Azure Active Directory で SBA のアプリケーションを登録します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-134">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="df2fa-135">すべての構成は、Skype for Business Online PowerShell コマンドレットを使用して行います。</span><span class="sxs-lookup"><span data-stu-id="df2fa-135">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="df2fa-136">(Teams 管理センターは、ダイレクト ルーティング SBA 機能をまだサポートしていません)。</span><span class="sxs-lookup"><span data-stu-id="df2fa-136">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="df2fa-137">(SBC ベンダーのドキュメントへのリンクを含む SBC の構成については、この記事の最後にあるセッション ボーダー コントローラーの構成を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="df2fa-137">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="df2fa-138">SA を作成する</span><span class="sxs-lookup"><span data-stu-id="df2fa-138">Create the SBAs</span></span>

<span data-ttu-id="df2fa-139">SA を作成するには、次のコマンドレットNew-CsTeamsSurvivableBranchApplianceします。</span><span class="sxs-lookup"><span data-stu-id="df2fa-139">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="df2fa-140">このコマンドレットには、次のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="df2fa-140">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="df2fa-141">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df2fa-141">Parameter</span></span>| <span data-ttu-id="df2fa-142">説明</span><span class="sxs-lookup"><span data-stu-id="df2fa-142">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="df2fa-143">Identity</span><span class="sxs-lookup"><span data-stu-id="df2fa-143">Identity</span></span>  | <span data-ttu-id="df2fa-144">SBA の ID</span><span class="sxs-lookup"><span data-stu-id="df2fa-144">The identity of the SBA</span></span>  |
| <span data-ttu-id="df2fa-145">Fqdn</span><span class="sxs-lookup"><span data-stu-id="df2fa-145">Fqdn</span></span> | <span data-ttu-id="df2fa-146">SBA の FQDN</span><span class="sxs-lookup"><span data-stu-id="df2fa-146">The FQDN of the SBA</span></span> |
| <span data-ttu-id="df2fa-147">サイト</span><span class="sxs-lookup"><span data-stu-id="df2fa-147">Site</span></span> | <span data-ttu-id="df2fa-148">SBA が保存されている TenantNetworkSite</span><span class="sxs-lookup"><span data-stu-id="df2fa-148">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="df2fa-149">説明</span><span class="sxs-lookup"><span data-stu-id="df2fa-149">Description</span></span> | <span data-ttu-id="df2fa-150">無料の書式テキスト</span><span class="sxs-lookup"><span data-stu-id="df2fa-150">Free format text</span></span> |
|||

<span data-ttu-id="df2fa-151">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-151">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="df2fa-152">Teams ブランチの分けやすさに関するポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="df2fa-152">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="df2fa-153">ポリシーを作成するには、次のコマンドレットNew-CsTeamsSurvivableBranchAppliancePolicyします。</span><span class="sxs-lookup"><span data-stu-id="df2fa-153">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="df2fa-154">このコマンドレットには、次のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="df2fa-154">This cmdlet has the following parameters.</span></span> <span data-ttu-id="df2fa-155">ポリシーには、1 つ以上の SA を含めできます。</span><span class="sxs-lookup"><span data-stu-id="df2fa-155">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="df2fa-156">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df2fa-156">Parameter</span></span>| <span data-ttu-id="df2fa-157">説明</span><span class="sxs-lookup"><span data-stu-id="df2fa-157">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="df2fa-158">Identity</span><span class="sxs-lookup"><span data-stu-id="df2fa-158">Identity</span></span> | <span data-ttu-id="df2fa-159">ポリシーの ID</span><span class="sxs-lookup"><span data-stu-id="df2fa-159">The identity of the policy</span></span> |
| <span data-ttu-id="df2fa-160">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="df2fa-160">BranchApplianceFqdns</span></span>  | <span data-ttu-id="df2fa-161">サイト内の SBA の FQDN</span><span class="sxs-lookup"><span data-stu-id="df2fa-161">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="df2fa-162">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-162">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="df2fa-163">このコマンドレットを使用して、ポリシーの SA を追加またはSet-CsTeamsSurvivableBranchAppliancePolicyできます。</span><span class="sxs-lookup"><span data-stu-id="df2fa-163">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="df2fa-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-164">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="df2fa-165">ユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="df2fa-165">Assign a policy to a user</span></span>

<span data-ttu-id="df2fa-166">ポリシーを個々のユーザーに割り当てるには、次のコマンドレットGrant-CsTeamsSurvivableBranchAppliancePolicyします。</span><span class="sxs-lookup"><span data-stu-id="df2fa-166">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="df2fa-167">このコマンドレットには、次のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="df2fa-167">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="df2fa-168">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df2fa-168">Parameter</span></span>| <span data-ttu-id="df2fa-169">説明</span><span class="sxs-lookup"><span data-stu-id="df2fa-169">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="df2fa-170">Identity</span><span class="sxs-lookup"><span data-stu-id="df2fa-170">Identity</span></span> | <span data-ttu-id="df2fa-171">ユーザーの ID</span><span class="sxs-lookup"><span data-stu-id="df2fa-171">The identity of the user</span></span> |
| <span data-ttu-id="df2fa-172">PolicyName</span><span class="sxs-lookup"><span data-stu-id="df2fa-172">PolicyName</span></span> | <span data-ttu-id="df2fa-173">ポリシーの ID</span><span class="sxs-lookup"><span data-stu-id="df2fa-173">The identity of the policy</span></span> |
||

<span data-ttu-id="df2fa-174">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-174">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="df2fa-175">次の例に示すように、ポリシー$Nullユーザーからポリシーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="df2fa-175">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="df2fa-176">Azure Active Directory で SBA のアプリケーションを登録する</span><span class="sxs-lookup"><span data-stu-id="df2fa-176">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="df2fa-177">テナント内で使用される異なる SBA が Microsoft 365 から必要なデータを読み取り込むには、Azure Active Directory で SBA 用のアプリケーションを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2fa-177">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="df2fa-178">アプリケーションの登録の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df2fa-178">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="df2fa-179">Azure Active Directory 用の業務用アプリを開発する</span><span class="sxs-lookup"><span data-stu-id="df2fa-179">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="df2fa-180">[Microsoft ID プラットフォームでアプリケーションを登録します](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。</span><span class="sxs-lookup"><span data-stu-id="df2fa-180">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="df2fa-181">テナント内のすべての SA で使用するために 1 つのアプリケーションのみを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df2fa-181">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="df2fa-182">SBA 登録には、登録によって作成された次の値が必要です。</span><span class="sxs-lookup"><span data-stu-id="df2fa-182">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="df2fa-183">アプリケーション (クライアント) ID</span><span class="sxs-lookup"><span data-stu-id="df2fa-183">Application (client) ID</span></span> 
- <span data-ttu-id="df2fa-184">クライアント シークレット</span><span class="sxs-lookup"><span data-stu-id="df2fa-184">Client secret</span></span> 

<span data-ttu-id="df2fa-185">SBA アプリケーションの場合は、次の注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="df2fa-185">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="df2fa-186">名前は、ユーザーが決めたものにできます。</span><span class="sxs-lookup"><span data-stu-id="df2fa-186">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="df2fa-187">サポートされているアカウントの種類 = この組織のディレクトリのアカウントのみ。</span><span class="sxs-lookup"><span data-stu-id="df2fa-187">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="df2fa-188">Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="df2fa-188">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="df2fa-189">暗黙的な付与トークン = Access トークンと ID トークン。</span><span class="sxs-lookup"><span data-stu-id="df2fa-189">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="df2fa-190">API のアクセス許可 = Skype と Teams テナント管理者アクセス -> アプリケーションのアクセス許可 -> application_access_custom_sba_appliance。</span><span class="sxs-lookup"><span data-stu-id="df2fa-190">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="df2fa-191">クライアント シークレット: 任意の説明と有効期限を使用できます。</span><span class="sxs-lookup"><span data-stu-id="df2fa-191">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="df2fa-192">クライアント シークレットは、作成後すぐにコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="df2fa-192">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="df2fa-193">アプリケーション (クライアント) ID が [概要] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="df2fa-193">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="df2fa-194">次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="df2fa-194">Then follow these steps:</span></span>

1. <span data-ttu-id="df2fa-195">アプリケーションを登録します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-195">Register the application.</span></span>
2. <span data-ttu-id="df2fa-196">暗黙的な付与トークンを設定します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-196">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="df2fa-197">API のアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-197">Set the API permissions.</span></span>
4. <span data-ttu-id="df2fa-198">クライアント シークレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-198">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="df2fa-199">セッション ボーダー コントローラーの構成</span><span class="sxs-lookup"><span data-stu-id="df2fa-199">Session Border Controller configuration</span></span> 

<span data-ttu-id="df2fa-200">埋め込まれたEdEdしおり分岐電気機器を使用してセッション ボーダー コントローラーを構成する方法の詳細なガイダンスについては、SBC ベンダーが提供するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="df2fa-200">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="df2fa-201">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="df2fa-201">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="df2fa-202">リボン</span><span class="sxs-lookup"><span data-stu-id="df2fa-202">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="df2fa-203">Oracle</span><span class="sxs-lookup"><span data-stu-id="df2fa-203">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="df2fa-204">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="df2fa-204">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="df2fa-205">問題の報告</span><span class="sxs-lookup"><span data-stu-id="df2fa-205">Reporting issues</span></span>

<span data-ttu-id="df2fa-206">問題がある場合は、SBC ベンダーのサポート組織に報告してください。</span><span class="sxs-lookup"><span data-stu-id="df2fa-206">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="df2fa-207">問題を報告する場合は、変更可能なブランチ 電気機器が構成されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="df2fa-207">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="df2fa-208">既知の問題</span><span class="sxs-lookup"><span data-stu-id="df2fa-208">Known issues</span></span>

- <span data-ttu-id="df2fa-209">新しい変更可能な分岐機器を追加する場合、そのブランチ の分岐の分岐の利用に関するポリシーでそれらを使用するには、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="df2fa-209">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="df2fa-210">ユーザーに変更可能な分岐ポリシーを割り当てると、SBA が Get-CsOnlineUser の出力に表示されるまで時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="df2fa-210">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="df2fa-211">Azure の連絡先に対する逆ADの参照は実行されません。</span><span class="sxs-lookup"><span data-stu-id="df2fa-211">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="df2fa-212">SBA では、通話の転送設定はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="df2fa-212">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="df2fa-213">動的緊急通話 (E911) 用に構成された緊急電話番号への緊急通話の発信はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="df2fa-213">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="df2fa-214">この値の出力Get-CsOnlineUser TeamsBranchSurvivabilityPolicy が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df2fa-214">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
