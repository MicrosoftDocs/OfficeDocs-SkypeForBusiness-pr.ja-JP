---
title: Skype for Business Server 2015 Stress and Performance Tool の使用
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: Skype for Business Server 2015 Stress and Performance Tool を実行するには、ユーザー、連絡先、およびユーザー プロファイルの両方を管理し、ツールを実行用に構成してから、ツールによって生成された出力または結果を確認できる必要があります。
ms.openlocfilehash: e008a85d22753a4e649da8501bd387675bb9b536
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814947"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="1fa6a-103">Skype for Business Server 2015 Stress and Performance Tool の使用</span><span class="sxs-lookup"><span data-stu-id="1fa6a-103">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="1fa6a-104">Skype for Business Server 2015 Stress and Performance Tool を実行するには、ユーザー、連絡先、およびユーザー プロファイルの両方を管理し、ツールを実行用に構成してから、ツールによって生成された出力または結果を確認できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-104">To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.</span></span>
  
<span data-ttu-id="1fa6a-105">Skype for Business Server 2015 Stress and Performance Tool の実行には、次の 4 つの領域があります (実行可能ファイルは次LyncPerfTool.exe。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-105">There are four areas involved with running the Skype for Business Server 2015 Stress and Performance Tool (the executable is LyncPerfTool.exe):</span></span>
  
- [<span data-ttu-id="1fa6a-106">ユーザーと連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="1fa6a-106">Create Users and Contacts</span></span>](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [<span data-ttu-id="1fa6a-107">ユーザー プロファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="1fa6a-107">Configure User Profile</span></span>](using-the-tool.md#BKMK_UserProfile)
    
- [<span data-ttu-id="1fa6a-108">LyncPerfTool の実行</span><span class="sxs-lookup"><span data-stu-id="1fa6a-108">Run LyncPerfTool</span></span>](using-the-tool.md#BKMK_RunTool)
    
- [<span data-ttu-id="1fa6a-109">結果の解釈</span><span class="sxs-lookup"><span data-stu-id="1fa6a-109">Interpreting the Results</span></span>](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a><span data-ttu-id="1fa6a-110">ユーザーと連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="1fa6a-110">Create Users and Contacts</span></span>
<span data-ttu-id="1fa6a-111"><a name="BKMK_CreateUsersAndContacts"> </a></span><span class="sxs-lookup"><span data-stu-id="1fa6a-111"><a name="BKMK_CreateUsersAndContacts"> </a></span></span>

<span data-ttu-id="1fa6a-112">Skype for Business Server 2015 (SB 2015) ユーザー プロビジョニング ツール (UserProvisioningTool.exe) を使用して、ストレスおよびパフォーマンス テスト用のユーザーと連絡先を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-112">You need to use the Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts for your stress and performance testing.</span></span>
  
<span data-ttu-id="1fa6a-113">トピックを読む上で役立つ可能性がある便利な用語の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-113">This is a list of helpful terms that might be useful as you read through the topics:</span></span>
  
- <span data-ttu-id="1fa6a-114">**組織単位** - Active Directory ドメイン サービス (AD DS) 組織単位 (OU)。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-114">**Organizational Unit** - The Active Directory Domain Services (AD DS) organizational unit (OU).</span></span>
    
- <span data-ttu-id="1fa6a-115">**フェデレーション/クロス プール** - 他のインスタント メッセージング (IM) サービスのユーザーと通信できるユーザー。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-115">**Federated / Cross Pool** - Users who can communicate with users from other Instant Messaging (IM) services.</span></span>
    
- <span data-ttu-id="1fa6a-116">**配布リスト** - または配布リスト。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-116">**Distribution Lists** - Or DLs.</span></span> <span data-ttu-id="1fa6a-117">これらは、DS ユーザー ADリストを含む AD DS 内のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-117">These are objects in AD DS that contain a list of AD DS users.</span></span> <span data-ttu-id="1fa6a-118">これらは、ユーザーのグループ間の通信を容易にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-118">They're used to facilitate communications across groups of people.</span></span>
    
- <span data-ttu-id="1fa6a-119">**位置情報** サービス - Skype for Business Server 2015 サービス。電話ごとに有効にし、構成すると、Enhanced 911 (E911) サービスの物理的な場所を取得できます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-119">**Location Info Service** - The Skype for Business Server 2015 service that, when it's enabled and configured per phone, allows for the retrieval of physical location for Enhanced 911 (E911) services.</span></span>
    
- <span data-ttu-id="1fa6a-120">**米国の電話番号** - 逆引き番号検索 (RNL) で着信および発信通話をルーティングするために使用される SIP URI に加えて、ユーザーに割り当てられた電話番号。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-120">**U.S. Phone Numbers** - Phone numbers assigned to user in addition to the SIP URI that's used for routing inbound and outbound calls in Reverse Number Lookup (RNL).</span></span>
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="1fa6a-121">ユーザーと連絡先を使用してユーザーと連絡先をUserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="1fa6a-121">Create Users and Contacts by using UserProvisioningTool.exe</span></span>

> [!NOTE]
> <span data-ttu-id="1fa6a-122">始める前に、このツールを実行するために Domain Admins セキュリティ グループのメンバーとしてログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-122">Before you even begin, be absolutely sure you're logged in as a member of the Domain Admins security group to run this tool.</span></span> <span data-ttu-id="1fa6a-123">Active Directory ユーザーを作成する場合は、これを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-123">You need to do this, because you're going to be creating Active Directory users.</span></span> 
  
<span data-ttu-id="1fa6a-124">読み込みシミュレーション用のユーザーと連絡先を作成するには、Skype for Business Server ユーザー プロビジョニング ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-124">You have to use the Skype for Business Server User Provisioning Tool to create users and contacts for load simulation.</span></span>
  
<span data-ttu-id="1fa6a-125">**Skype for Business Server ユーザー プロビジョニング ツール** は **、Skype for Business Server Stress and Performance Tool パッケージと一緒にインストール** されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-125">The **Skype for Business Server User Provisioning Tool** is installed with the **Skype for Business Server Stress and Performance Tool** package.</span></span> <span data-ttu-id="1fa6a-126">テストするフロントエンド サーバーまたは Standard Edition サーバーで、パッケージ インストーラー (CapacityPlanningTool.msi) が実行済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-126">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server you intend to test.</span></span>
  
<span data-ttu-id="1fa6a-127">Skype for Business Server ユーザー プロビジョニング ツールを起動するには、フロントエンド サーバーまたは Standard Edition サーバー上でファイル UserProvisioningTool.exe (%InstalledDirectory%LyncStressAndPerfTool\LyncStress にあります) を実行します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-127">You can start the Skype for Business Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1fa6a-128">多数のユーザー (たとえば、10,000 以上) を作成する場合は、次のコマンドUserProvisioningTool.exe。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-128">When you create a large number of users (for example, 10,000 or more), run the UserProvisioningTool.exe.</span></span> <span data-ttu-id="1fa6a-129">ツールは新しいユーザーを作成および構成するために、  *これを行う*  ADがあります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-129">You'll need to do this because the tool will be creating and configuring  *new*  AD users.</span></span>
  
<span data-ttu-id="1fa6a-130">ユーザー プロビジョニング ツールが開いたら、[構成] をクリックし、[構成の読み込み] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-130">When the User Provisioning Tool opens, click Configuration and select the Load Configuration.</span></span> 
  
<span data-ttu-id="1fa6a-131">ユーザーと連絡先の構成を開始するには、パッケージに含まれている既定のファイル ("SampleData.xml" と呼ばれる) を読み込SampleData.xml。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-131">To begin configuring users and contacts, load the default file included with the package, called "SampleData.xml".</span></span> <span data-ttu-id="1fa6a-132">これにより、展開に関連付けするために変更が必要なサンプル データがフィールドに事前に入力されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-132">This will prepopulate fields with sample data that you'll need to change to make it relevant for your deployment.</span></span>
  
<span data-ttu-id="1fa6a-133">カスタマイズした設定が既に含まれている構成済みの XML ファイルがある場合は、代わりにそのファイルを読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-133">If you have a preconfigured XML file that already contains your customized settings, you can load that file instead.</span></span> <span data-ttu-id="1fa6a-134">以下のセクションで説明するように、ユーザー プロビジョニング ツールのフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-134">Fill in the fields in the User Provisioning Tool, as described in the sections below.</span></span>
  
### <a name="to-configure-server-options"></a><span data-ttu-id="1fa6a-135">サーバー オプションを構成するには:</span><span class="sxs-lookup"><span data-stu-id="1fa6a-135">To configure server options:</span></span>

1. <span data-ttu-id="1fa6a-136">[ **フロントエンド プールの FQDN]** フィールドに、Standard Edition サーバーの完全修飾ドメイン名 (FQDN) またはユーザーをホストするフロントエンド プールを入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-136">In the **Front End Pool FQDN** field, type the fully qualified domain name (FQDN) of the Standard Edition server, or the Front End pool where you want to host the users.</span></span>
    
2. <span data-ttu-id="1fa6a-137">[ **ユーザー名のプレフィックス** ] フィールドに、テスト目的でユーザー名を変更するために使用するプレフィックス ("TestUser" など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-137">In the **User Name Prefix** field, type a prefix that you want to use to bust your user names for testing purposes (such as "TestUser").</span></span>
    
3. <span data-ttu-id="1fa6a-138">[ **パスワード] フィールド** に、すべてのテスト ユーザー アカウントで使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-138">In the **Password** field, type a password that will be used across all the test user accounts.</span></span>
    
4. <span data-ttu-id="1fa6a-139">[ **アカウント ドメイン]** フィールドに、現在のドメイン ドメインAD (テスト ユーザーを作成するドメイン) を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-139">In the **Account Domain** field, type the domain name of your current AD domain (the one in which you want to create your test users).</span></span>
    
5. <span data-ttu-id="1fa6a-140">[組織 **単位]** フィールドに、これらのテスト ユーザーをADドメインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-140">In the **Organizational Unit** field, type the name of the AD domain where you want to create these test users.</span></span> <span data-ttu-id="1fa6a-141">(OU が存在しない場合は、作成されます)。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-141">(If the OU doesn't already exist, it'll be created for you).</span></span>
    
6. <span data-ttu-id="1fa6a-142">[電話エリア **コード]** フィールドに、すべてのテスト ユーザー アカウントで使用する 3 桁のエリア コードを入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-142">In the **Phone Area Code** field, type the three-digit area code to be used across all test user accounts.</span></span> <span data-ttu-id="1fa6a-143">選択したエリア コードが、他のユーザーのエリア コードと競合しないことをAD。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-143">Make certain that the area code you chose doesn't conflict with other users' area codes in AD.</span></span>
    
7. <span data-ttu-id="1fa6a-144">テスト ユーザーの音声を **有効** にする場合は、[音声が有効] チェック ボックスをオンエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-144">Click to select the **Voice Enabled** check box, if you want to enable the test users for Enterprise Voice.</span></span>
    
8. <span data-ttu-id="1fa6a-145">[ユーザー **数] フィールド** に、作成するテスト ユーザーの総数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-145">In the **Number of Users** field, give the total number of test users you want to create.</span></span>
    
9. <span data-ttu-id="1fa6a-146">[開始 **インデックス** ] フィールドで、ユーザー名のプレフィックスのサフィックスとして使用される開始番号を指定します (たとえば、プレフィックスが "TestUser" で、下の例では名の末尾が "0" になります)。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-146">In the **Start Index** field, give the starting number that'll be used as a suffix to the user name prefix (for example, the prefix is "TestUser", and the first name will end in "0" in the example below.)</span></span>
    
     ![ユーザー作成タブを表示するユーザー プロビジョニング ツール。](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a><span data-ttu-id="1fa6a-148">[ユーザーの作成] ボタン</span><span class="sxs-lookup"><span data-stu-id="1fa6a-148">Create Users button</span></span>

<span data-ttu-id="1fa6a-149">[ユーザーの作成] ボタン **を** クリックすると、入力した入力パラメーターが検証されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-149">When you click on the **Create Users** button, the input parameters you've entered are validated.</span></span> <span data-ttu-id="1fa6a-150">検証エラーがある場合は、修正を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-150">If there are any validation errors, you'll be prompted to fix them.</span></span> <span data-ttu-id="1fa6a-151">または、すべての値が正しい場合、(指定した OU 内の) ADにユーザーが表示され始める可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-151">Or, if all the values are correct, users will start appearing in AD (in whichever OU you specified).</span></span> <span data-ttu-id="1fa6a-152">ツールの実行時に、ツールの下部に進行状況バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-152">You'll see a progress bar at the bottom of the tool as it runs.</span></span> <span data-ttu-id="1fa6a-153">進行状況バーがアクティブな間はアプリケーションを閉じない。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-153">Don't close the application while the progress bar is active.</span></span>
  
<span data-ttu-id="1fa6a-154">ユーザーの作成には時間がかかるので、必要に応じて計画してください。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-154">User creation takes time, so please plan accordingly.</span></span> <span data-ttu-id="1fa6a-155">このプロセスは、数分間のユーザーの場合は任意の時間、多数のユーザーの場合は数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-155">This process can take anywhere from several minutes for a few users, to a few hours for a large number of users.</span></span>
  
<span data-ttu-id="1fa6a-156">テスト環境で AD ドメイン コントローラーにアクセスできない場合でも、作成するユーザー範囲のユーザーの 1 人としてログインすることで、ユーザーの作成を検証できます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-156">If you don't have access to the AD Domain Controller in your test environment, you can still validate user creation by logging in as one of the users in the range of users you specified to create.</span></span> <span data-ttu-id="1fa6a-157">ユーザー名には、プレフィックスとサフィックスを@sipDomainしてください。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-157">Remember to use the prefix, and the suffix, along with the @sipDomain as the username.</span></span> <span data-ttu-id="1fa6a-158">次に例を示します: <em>TestUser20@contoso.net。</em></span><span class="sxs-lookup"><span data-stu-id="1fa6a-158">Here is an example:  <em>TestUser20@contoso.net</em>  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fa6a-159">ユーザーが既に存在する場合は、[ユーザーの作成] ボタンをクリックすると、構成の変更によってユーザーが更新されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-159">If the users already exist, clicking the Create Users button will update them with any configuration changes.</span></span> 
  
#### <a name="delete-users-button"></a><span data-ttu-id="1fa6a-160">[ユーザーの削除] ボタン</span><span class="sxs-lookup"><span data-stu-id="1fa6a-160">Delete Users button</span></span>

<span data-ttu-id="1fa6a-161">[ユーザーの削除] **ボタンをクリック** すると、タブの入力パラメーターが検証されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-161">When you click on the **Delete Users** button, the tab's input parameters will be validated.</span></span> <span data-ttu-id="1fa6a-162">検証エラーがある場合は、修正を求めるメッセージが表示され、入力値が正しい場合は、指定したテスト ユーザーが無効になり、Active Directory から削除されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-162">If there are validation errors, you'll be prompted to fix them, and if the input values are correct, the specified test users will be disabled and deleted from Active Directory.</span></span> <span data-ttu-id="1fa6a-163">この場合も、このタブの下部に進行状況バーが表示され、進行状況バーがアクティブな間はアプリケーションを閉じてはならない。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-163">Again, a progress bar will appear on the bottom of this tab, and you shouldn't close the application while the progress bar is active.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fa6a-164">サポートされているのは、米国形式の電話番号のみです。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-164">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="1fa6a-165">電話番号は常にユーザーに割り当てられます。電話番号によって作成UserProvisioningTool.exeユーザーは、既定エンタープライズ VoIP有効になっています。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-165">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice by default.</span></span> <span data-ttu-id="1fa6a-166">電話会議や UC-PSTN 通話など、自動応答を使用するシナリオでは、この電話番号を使用して通話を適切にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-166">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="1fa6a-167">このため、すべてのユーザーは  *一意*  の電話番号 *を持っている必要があります*  。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-167">For this reason,  *every user*  must have a *unique phone number*  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fa6a-168">**ユーザーを 2 回作成する必要がある場合は、別のエリア コードを使用しない限り、または以前のユーザーが Disable-CsUser コマンドレットを使用して無効になっている場合、コマンドは失敗します。**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-168">**If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the Disable-CsUser cmdlet.**</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1fa6a-169">連絡先を作成する前に、まずユーザーのレプリケーションを完了する必要があります (これは [ユーザー] タブから実行します)。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-169">Before you create contacts, you first need to complete user replication (which is done from the Users tab).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1fa6a-170">ユーザーを作成したばかりである場合は、Skype for Business Server のレプリケーションが完了し、データベースにユーザー アカウントが設定されるまで待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-170">If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="1fa6a-171">**ユーザーがレプリケートを完了していない場合は、エラーが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-171">**If the users haven't finished replicating, you'll see an error.**</span></span> <span data-ttu-id="1fa6a-172">Skype for Business Server 2015 フロントエンド サービスが開始した場合、または指定した総数の最後のユーザーに対して Get-CsUser コマンドレットを正常に実行することで、ユーザーがレプリケートを完了した時間が分かっています。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-172">You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.</span></span>
  
#### <a name="contacts-creation-tab"></a><span data-ttu-id="1fa6a-173">[連絡先の作成] タブ</span><span class="sxs-lookup"><span data-stu-id="1fa6a-173">Contacts Creation tab</span></span>

<span data-ttu-id="1fa6a-174">このタブでは、テスト用にユーザーの連絡先の詳細を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-174">This tab lets you give users' contacts details for your testing.</span></span>
  
![[コンテンツの作成] タブを表示するユーザー プロビジョニング ツール。](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a><span data-ttu-id="1fa6a-176">ユーザーの連絡先を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-176">To configure users' contacts, do the following:</span></span>

1. <span data-ttu-id="1fa6a-177">[Average **Contacts per User]** フィールドに、各ユーザーの連絡先リストに入力する連絡先の平均数を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-177">In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.</span></span>
    
2. <span data-ttu-id="1fa6a-178">すべてのユーザー **に対** して同じ数の連絡先を作成する場合は、[固定] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-178">Select the **Fixed** check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="1fa6a-179">ユーザー用に作成された連絡先の数を変更する場合は、そのチェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-179">If you want to vary the number of contacts created for users, clear that check box.</span></span>
    
3. <span data-ttu-id="1fa6a-180">[ユーザーあたりの **平均連絡先グループ数]** フィールドに、ユーザーごとの連絡先グループの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-180">In the **Average Contact Groups per User** field, enter the number of contact groups per user.</span></span> <span data-ttu-id="1fa6a-181">この数は、ユーザーごとの平均連絡先 **よりも小さくする必要があります**。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-181">This number needs to be smaller than **Average Contacts per User**.</span></span>
    
4. <span data-ttu-id="1fa6a-182">[フェデレーション/ **クロス プールの連絡先の割合** ] フィールドで、0 ~ 100 の数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-182">In the **Federated / Cross Pool Contacts Percentage** field, give a number between 0 and 100.</span></span> <span data-ttu-id="1fa6a-183">この割合の連絡先は、フェデレーション ユーザーと一緒に作成されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-183">This percentage of contacts will be created with the federated users.</span></span>
    
5. <span data-ttu-id="1fa6a-184">[ **フェデレーション/ クロス プール** ユーザー プレフィックス] フィールドで、ローカル ユーザーの連絡先リストに追加されるフェデレーション ユーザーのユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-184">In the **Federated / Cross Pool User Prefix** field, give the username for federated users that will be added to the contact lists of local users.</span></span>
    
6. <span data-ttu-id="1fa6a-185">[フェデレーション **/クロス プール ユーザー SIP ドメイン** ] フィールドで、フェデレーション ユーザーの SIP ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-185">In the **Federated / Cross Pool User SIP Domain** field, give the SIP Domain Name of the federated users.</span></span>
    
7. <span data-ttu-id="1fa6a-186">[ **ユーザーの作成]** タブで、情報が正しいか確認します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-186">In **User Creation** tab make sure the information is correct.</span></span> <span data-ttu-id="1fa6a-187">連絡先は、[ユーザーの作成] タブの値から作成されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-187">Your contacts will be created from values on the User Creation tab.</span></span>
    
8. <span data-ttu-id="1fa6a-188">[連絡先 **の作成] を** クリックして連絡先の作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-188">Click **Create Contacts** to begin the contact creation.</span></span> <span data-ttu-id="1fa6a-189">このプロセスには数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-189">This process can take several minutes.</span></span> <span data-ttu-id="1fa6a-190">完了すると、"Operation Completed Successfully" というメッセージが表示されたダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-190">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="1fa6a-191">作成された連絡先は、[ユーザーの作成] タブから作成されたユーザーとしてログオンすることで検証できます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-191">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1fa6a-192">連絡先が作成されると、このツールはターゲット プール内のすべてのフロントエンド サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-192">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="1fa6a-193">この操作によって作成された連絡先の数によっては、フロントエンド サーバーの起動に時間がかかる場合があります (最大 2 時間)。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-193">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span> 
  
#### <a name="distribution-list"></a><span data-ttu-id="1fa6a-194">配布リスト</span><span class="sxs-lookup"><span data-stu-id="1fa6a-194">Distribution List</span></span>

<span data-ttu-id="1fa6a-195">Skype for Business Server 2015 Stress and Performance Tool は、Skype for Business 2015 クライアントの配布リスト (DL) 拡張機能をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-195">The Skype for Business Server 2015 Stress and Performance Tool can simulate the Distribution List (DL) expansion feature in the Skype for Business 2015 client.</span></span> <span data-ttu-id="1fa6a-196">ユーザー プロビジョニング ツールで DL 拡張を有効にしない場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-196">You can skip this step if you don't intend to enable DL expansion in the User Provisioning tool.</span></span>
  
![[配布リストの作成] タブを表示するユーザー プロビジョニング ツール。](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
<span data-ttu-id="1fa6a-198">[配布リスト] タブでは、Stress and Performance Tool が配布リスト拡張機能に使用する配布リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-198">The Distribution List tab allows you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="1fa6a-199">DLL を作成する前に、ForestPrep の実行を含め、Skype for Business Server 2015 を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-199">Before creating DLs, Skype for Business Server 2015 needs to be deployed, including having run ForestPrep.</span></span> <span data-ttu-id="1fa6a-200">これが行われなかった場合、DL 属性は AD スキーマに存在しないので、ツールは DL を作成できません。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-200">If this isn't done, the DL attributes will not exist in the AD schema, so the tool won't be able to create DLs.</span></span>
  
### <a name="to-configure-distribution-lists"></a><span data-ttu-id="1fa6a-201">配布リストを構成するには:</span><span class="sxs-lookup"><span data-stu-id="1fa6a-201">To configure Distribution Lists:</span></span>

1. <span data-ttu-id="1fa6a-202">[配布 **リスト** の数] フィールドに、作成する配布リストの総数を指定します (ここでの推奨事項は、ユーザー数の 2 倍の値から始めるという方法です)。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-202">In the **Number of Distribution Lists** field, give the total number of DLs you want to create (The recommendation here is that you start with a value that is double the number of users you have.).</span></span>
    
2. <span data-ttu-id="1fa6a-203">[Distribution **List Prefix]** フィールドに、作成する DLL のプレフィックス *(testDL*  など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-203">In the **Distribution List Prefix** field, enter a prefix that all the DLs you create will have, for example *testDL*  .</span></span> <span data-ttu-id="1fa6a-204">つまり、100 DL では、DL 名は testDL0、testDL1、testDL99 までのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-204">That means, at 100 DLs, your DL names will look like: testDL0, testDL1, up to testDL99.</span></span>
    
3. <span data-ttu-id="1fa6a-205">**[Dist. List]** フィールドの [Minimum Members] に、各 DL に入力する最小ユーザー数を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-205">In the **Minimum Members in a Dist. List** field, enter the minimum number of users to put in each DL.</span></span>
    
4. <span data-ttu-id="1fa6a-206">**[Dist の最大メンバー** 数] フィールドに、各 DL に追加する最大ユーザー数を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-206">In the **Maximum Members in a Dist. List** field, enter the maximum number of users to add in each DL.</span></span>
    
#### <a name="create-distribution-lists-button"></a><span data-ttu-id="1fa6a-207">[配布リストの作成] ボタン</span><span class="sxs-lookup"><span data-stu-id="1fa6a-207">Create Distribution Lists button</span></span>

<span data-ttu-id="1fa6a-208">[配布リストの作成] ボタンをクリックすると、このツールは Active Directory を照会して、プレフィックスと番号に一致する配布リストが既に存在していないか確認します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-208">When you click the Create Distribution Lists button, the tool queries Active Directory to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="1fa6a-209">このツールは、まだ存在していない DLL を作成します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-209">The tool creates any DLs that don't already exist.</span></span> <span data-ttu-id="1fa6a-210">これらの新しく作成した配布リストにメンバーを追加するときに、[ユーザーの作成] タブで指定した範囲からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-210">When adding members to these newly created Distribution Lists, it'll choose the users from the range specified on the User Creation tab.</span></span>
  
#### <a name="location-info-service-config-tab"></a><span data-ttu-id="1fa6a-211">[場所情報サービス構成] タブ</span><span class="sxs-lookup"><span data-stu-id="1fa6a-211">Location Info Service Config tab</span></span>

<span data-ttu-id="1fa6a-212">Skype for Business Server 2015 Stress and Performance Tool では、場所情報サービスのダミー構成ファイルを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-212">The Skype for Business Server 2015 Stress and Performance Tool can also generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="1fa6a-213">通常、場所情報サービスは、サーバーのパフォーマンスに大きな影響を与える点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-213">Note that the Location Information Service typically doesn't have significant performance impact on the servers.</span></span> 
  
![[場所情報サービス構成] タブを表示するユーザー プロビジョニング ツール。](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
<span data-ttu-id="1fa6a-215">If you choose to test this feature, fill in the values in the form and click the Generate LIS Config Files button, which will create .CSV ファイルの呼び出し:</span><span class="sxs-lookup"><span data-stu-id="1fa6a-215">If you choose to test this feature, fill in the values in the form and click the Generate LIS Config Files button, which will create .CSV files called:</span></span>
  
- <span data-ttu-id="1fa6a-216">LIS_Subnet.csv</span><span class="sxs-lookup"><span data-stu-id="1fa6a-216">LIS_Subnet.csv</span></span>
    
- <span data-ttu-id="1fa6a-217">LIS_Switches.csv</span><span class="sxs-lookup"><span data-stu-id="1fa6a-217">LIS_Switches.csv</span></span>
    
- <span data-ttu-id="1fa6a-218">LIS_Ports.csv</span><span class="sxs-lookup"><span data-stu-id="1fa6a-218">LIS_Ports.csv</span></span>
    
- <span data-ttu-id="1fa6a-219">LIS_WAP.csv</span><span class="sxs-lookup"><span data-stu-id="1fa6a-219">LIS_WAP.csv</span></span>
    
<span data-ttu-id="1fa6a-220">これらのファイルを LIS データベースにインポートするには、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-220">To import these files into the LIS database use these PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="1fa6a-221">Set-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="1fa6a-221">Set-CsLisSubnet</span></span>
    
- <span data-ttu-id="1fa6a-222">Set-CsLisSwitch</span><span class="sxs-lookup"><span data-stu-id="1fa6a-222">Set-CsLisSwitch</span></span>
    
- <span data-ttu-id="1fa6a-223">Set-CsLisPort</span><span class="sxs-lookup"><span data-stu-id="1fa6a-223">Set-CsLisPort</span></span>
    
- <span data-ttu-id="1fa6a-224">Set-CsWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="1fa6a-224">Set-CsWirelessAccessPoint</span></span>
    
## <a name="configure-user-profile"></a><span data-ttu-id="1fa6a-225">ユーザー プロファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="1fa6a-225">Configure User Profile</span></span>
<span data-ttu-id="1fa6a-226"><a name="BKMK_UserProfile"> </a></span><span class="sxs-lookup"><span data-stu-id="1fa6a-226"><a name="BKMK_UserProfile"> </a></span></span>

<span data-ttu-id="1fa6a-227">(ユーザー作成ツールを使用して) ユーザーを作成した後、Skype for Business Server 2015 Load Configuration ツール (UserProfileGenerator.exe) を使用してユーザー プロファイルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-227">After your users are created (via the User Creation Tool) you can configure user profiles with the Skype for Business Server 2015 Load Configuration tool (UserProfileGenerator.exe).</span></span>
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a><span data-ttu-id="1fa6a-228">Skype for Business Server 2015 Load Configuration ツールの実行</span><span class="sxs-lookup"><span data-stu-id="1fa6a-228">Running the Skype for Business Server 2015 Load Configuration tool</span></span>

<span data-ttu-id="1fa6a-229">構成の読み込みツール (UserProfileGenerator.exe) を起動し、タブに入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-229">Start the Load Configuration tool (UserProfileGenerator.exe) and fill in the tabs.</span></span> <span data-ttu-id="1fa6a-230">このツールは、シミュレーションの実行に必要なクライアント コンピューターごとにディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-230">This tool creates a directory for each of the client computers that you'll need to run your simulations.</span></span> <span data-ttu-id="1fa6a-231">各クライアント ディレクトリには、Skype for Business Server 2015 Stress and Performance ツール (LyncPerfTool.exe) を起動するスクリプトが付属しています。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-231">Each client directory comes with a script to start the Skype for Business Server 2015 Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="1fa6a-232">以下のセクションでは、Skype for Business Server 2015 Load Configuration ツールの各タブのフィールドに入力する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-232">The sections below will give examples of how to fill in the fields on each tab of the Skype for Business Server 2015 Load Configuration tool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1fa6a-233">読み込み構成ツール (UserProfileGenerator.exe) で使用されるユーザー固有の値は、プールの Skype for Business Server 2015 ユーザー作成ツール (UserProvisioningTool.exe) で指定された値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-233">The user-specific values used in the Load Configuration tool (UserProfileGenerator.exe) must match the values specified in the Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) for the pool.</span></span> 
  
#### <a name="common-configuration-tab"></a><span data-ttu-id="1fa6a-234">[共通の構成] タブ</span><span class="sxs-lookup"><span data-stu-id="1fa6a-234">Common Configuration tab</span></span>

<span data-ttu-id="1fa6a-235">Load Configuration Tool の [Common **Configuration]** タブを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-235">The **Common Configuration** tab of the Load Configuration Tool is shown below.</span></span> <span data-ttu-id="1fa6a-236">次の手順で説明するように、[共通の構成] タブのフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-236">Fill in the fields of the Common Configuration tab, as described in the following steps.</span></span>
  
![[共通の構成] タブを表示する [ユーザー プロビジョニング] タブ。](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. <span data-ttu-id="1fa6a-238">[利用可能 **なコンピューター** の数] フィールドに、Stress and Performance ツールの実行に使用するコンピューターの数を入力します (LyncPerfTool.exe)。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-238">In the **Number of Available Machines** field, type the number of computers you want to use to run the Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="1fa6a-239">シミュレートする 4,500 ユーザーごとに 1 台のコンピューターを用意することをお勧めしますが、負荷レベルを下げるか、ツールの使用可能な機能のサブセットのみを使用する場合は、その数が異なる場合があります ([一般的なシナリオ] タブで読み込みレベルが設定されます)。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-239">We recommend that you have one computer for every 4500 users you'll be simulating, but that number may vary if you reduce the load level, or use only a subset of the tool's available features (Load levels are set on the General Scenarios tab).</span></span>
    
2. <span data-ttu-id="1fa6a-240">[ユーザー **名のプレフィックス]** フィールドに、すべてのユーザーのユーザー名フィールドのプレフィックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-240">In the **Prefix for User Names** field, enter a prefix for the user name field of all users.</span></span> <span data-ttu-id="1fa6a-241">Uri (Uniform Resource Identifier) にログインするには *、UserPrefix[User Start Index...(ユーザー数-1)]@Userドメイン*  (たとえば、myUser009@Contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-241">To log in the Uniform Resource Identifier (URI) will be: *UserPrefix[User Start Index…(Number Of Users-1)]@User Domain*  , for example, myUser009@Contoso.com.</span></span>
    
3. <span data-ttu-id="1fa6a-242">[すべての **ユーザーのパスワード] フィールドに** 、ユーザーの作成時に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-242">In the **Password for All Users** field, enter the password used during creation of the users.</span></span> <span data-ttu-id="1fa6a-243">このフィールドを空のままにすると、ユーザー名はパスワードとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-243">If you leave this field empty the username will be set as the password.</span></span>
    
4. <span data-ttu-id="1fa6a-244">[ユーザー **の開始インデックス]** フィールドに、構成する最初のユーザーのインデックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-244">In the **User Start Index** field, enter the index of the first user to be configured.</span></span> <span data-ttu-id="1fa6a-245">異なる種類または負荷レベルに対して異なる範囲を構成できますが、構成する範囲ごとに 1 回、Load Configuration ツール (UserProfileGenerator.exe) を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-245">You can configure different ranges for different types or levels of load, but you must run the Load Configuration tool (UserProfileGenerator.exe) once per the range you want to configure.</span></span>
    
5. <span data-ttu-id="1fa6a-246">[ **ユーザー数] フィールド** に、構成するユーザーの総数を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-246">In the **Number of Users** field, enter the total number of users you're going to configure.</span></span>
    
6. <span data-ttu-id="1fa6a-247">[ユーザー **ドメイン] フィールド** に、SIP URI に使用するドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-247">In the **User Domain** field, enter the domain used for the SIP URI.</span></span> <span data-ttu-id="1fa6a-248">これは、Skype for Business Server 2015 フロントエンド サーバーまたは Standard Edition サーバーにログオンする各ユーザーの SIP URI を作成するために使用され、アカウント ドメインとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-248">This is used to construct the SIP URI of each user to log on to the Skype for Business Server 2015 Front End Server or Standard Edition server, and may be different from the Account Domain.</span></span>
    
7. <span data-ttu-id="1fa6a-249">[アカウント **ドメイン] フィールド** に、DS ドメイン ログオンAD入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-249">In the **Account Domain** field, enter the AD DS domain logon.</span></span>
    
8. <span data-ttu-id="1fa6a-250">**[MPOP の割合**] (複数のプレゼンス ポイントの割合) フィールドで、複数のコンピューターまたはデバイスからログオンしているユーザーの割合 (たとえば 10%) の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-250">In the **MPOP Percentage** (Multiple Point of Presence percentage) field, give a value for the percentage of users that are logged on from multiple machines or devices, for example 10 percent.</span></span>
    
9. <span data-ttu-id="1fa6a-251">[サインイン/秒] (インスタンスごとに) フィールドに同時 **エンドポイントの最大数を入力** します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-251">Enter the maximum number of concurrent endpoints in the **Sign in Per Second (per Instance)** field.</span></span> <span data-ttu-id="1fa6a-252">これはユーザーのログインの最大数であり、推奨される割合は 1 秒あたり 2 以下 (<=2) です。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-252">This is the maximum number of log ins for your users, and the recommendation is a rate of less than/equal to 2 per second (<=2).</span></span>
    
10. <span data-ttu-id="1fa6a-253">[アクセス プロキシ] または [プール **の FQDN]** フィールドに、クライアントが接続するサーバーの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-253">In the **Access Proxy or Pool FQDN** field, enter the fully qualified domain name (FQDN) of the server you want the clients to connect to.</span></span> <span data-ttu-id="1fa6a-254">ユーザーが外部でログオンしている場合は、アクセス プロキシを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-254">If the users are logging on externally, you'll need to type the access proxy.</span></span> <span data-ttu-id="1fa6a-255">ユーザーが内部の場合は、エンタープライズ プールまたは Standard Edition サーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-255">If the users are internal, give the FQDN of their Enterprise Pool or Standard Edition server.</span></span>
    
11. <span data-ttu-id="1fa6a-256">[ **ポート] フィールド** に、ユーザーが SIP に使用するポートを入力します (既定値は 5061 です)。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-256">In the **Port** field, enter the port that you want users to use for SIP (the default here is 5061).</span></span>
    
12. <span data-ttu-id="1fa6a-257">[外部 **ネットワーク サーバーの設定** ] フィールドで、アクセス プロキシまたはプールの FQDN を指定し、ここでもポートを指定 **します**。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-257">For the **External Network Server Settings** field, give the Access Proxy or Pool FQDN and, again, the **Port**.</span></span> <span data-ttu-id="1fa6a-258">これらの設定は、外部エンドポイントの負荷シミュレーションにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-258">These settings are used only for External endpoints load simulation.</span></span>
    
#### <a name="general-scenarios-tab"></a><span data-ttu-id="1fa6a-259">[一般的なシナリオ] タブ</span><span class="sxs-lookup"><span data-stu-id="1fa6a-259">General Scenarios tab</span></span>

![[一般的なシナリオ] タブを表示する構成ツールの読み込み。](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
<span data-ttu-id="1fa6a-261">実行または無効のままにする処理を決定することで、提供される一般的な各シナリオの負荷レベルとパラメーターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-261">You can configure the load levels and parameters for each of the general scenarios offered by determining what you want to run or leave disabled.</span></span> <span data-ttu-id="1fa6a-262">一般的なオプションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-262">Here are your general options:</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fa6a-263">ローカル 情報サービスを含むすべてのフィールドの読み込みレベルの値は **、無効**、**低**、**中、\*\*\*\*高、** または **ユーザー設定です**。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-263">Load level values for all fields but Local Information Services are **Disabled**, **Low**, **Medium**, **High**, or **Custom**.</span></span> <span data-ttu-id="1fa6a-264">[無効] を選択した場合は、クライアントごとに構成が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-264">If you select any setting but Disabled, then configurations are generated for each client.</span></span> <span data-ttu-id="1fa6a-265">この値が高い場合、サーバーでサポートされる負荷は最大になります。medium は高負荷の 60% です。low は 30% です。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-265">High results in the max supported load on the server; medium is 60% of high load; low is 30%.</span></span> 
  
- <span data-ttu-id="1fa6a-266">**インスタント メッセージング -** これにはピアツーピアおよび会議が含まれます。読み込みレベルに適した値を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-266">**Instant Messaging -** This includes peer-to-peer and conferencing; choose the appropriate value for Load Level.</span></span>
    
- <span data-ttu-id="1fa6a-267">**電話会議 -** 電話会議専用の負荷レベルを選択 *します*  。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-267">**Audio Conferencing -** Choose a load level for audio conferencing *only*  .</span></span> <span data-ttu-id="1fa6a-268">ピアツーピア通話については、「音声シナリオ」セクションで少し **後で取り組む予定** です。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-268">Peer-to-peer calls will be tackled a little later in the **Voice Scenarios** section.</span></span> <span data-ttu-id="1fa6a-269">MultiView を **有効にするには** 、[詳細設定] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-269">Open the **Advanced** tab to enable MultiView.</span></span>
    
- <span data-ttu-id="1fa6a-270">**アプリケーション共有 -** アプリケーション共有の負荷レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-270">**Application Sharing -** Choose a load level for application sharing.</span></span>
    
- <span data-ttu-id="1fa6a-271">**データ コラボレーション -** データ会議を含むデータ コラボレーションの負荷レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-271">**Data Collaboration -** Choose a load level for data collaboration, which includes data conferencing.</span></span>
    
- <span data-ttu-id="1fa6a-272">**配布リストの展開 -** [詳細設定 **]** ボタンをクリックし、ユーザー作成ツール (UserProvisioningTool.exe) の [DL] タブで構成されている値と同じ値をフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-272">**Distribution List Expansion -** Click the **Advanced** button and fill in the field with the same values configured on the DL tab of the User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="1fa6a-273">負荷レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-273">Choose a load level.</span></span>
    
- <span data-ttu-id="1fa6a-274">**アドレス帳 Web クエリ -** これは、アドレス帳ファイルのダウンロードではなく、アドレス帳参照サービスです。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-274">**Address Book Web Query -** This is the address book lookup service rather than the address book file download.</span></span> <span data-ttu-id="1fa6a-275">アドレス帳ファイルのダウンロードに対してこれを有効にする場合は、[詳細設定] ボタンをクリックし **、EnableABSDownload** を True に設定します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-275">If you want to enable this for address book file downloads, click the **Advanced** button and set **EnableABSDownload** to True.</span></span> <span data-ttu-id="1fa6a-276">読み込みレベルの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-276">Give a value for load level.</span></span>
    
- <span data-ttu-id="1fa6a-277">**応答グループ サービス -** [詳細設定 **] ボタン** をクリックし、応答グループ サービス エージェントの準備時に既に作成した応答グループの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-277">**Response Group Service -** Click the **Advanced** button and specify the URIs of the response groups you already created when you provisioned Response Group Service agents.</span></span> <span data-ttu-id="1fa6a-278">少なくとも 1 つの応答グループを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-278">You must choose at least one response group.</span></span> <span data-ttu-id="1fa6a-279">さらに多くの値を使用するには、応答グループをセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-279">To use more, separate the response groups with semicolons.</span></span> <span data-ttu-id="1fa6a-280">**RGSUriSuffixStartIndex** と **RGSUriSuffixEndIndex** を実際の値に更新します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-280">Update **RGSUriSuffixStartIndex** and **RGSUriSuffixEndIndex** to the actual values.</span></span> <span data-ttu-id="1fa6a-281">負荷レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-281">Choose a load level.</span></span>
    
- <span data-ttu-id="1fa6a-282">**場所情報サービス -** [有効] または [無効] の読み込みレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-282">**Location Information Services -** Select a load level of either Enabled or Disabled.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1fa6a-283">各シナリオには、横に [詳細設定] ボタンがあります。また、既定の設定へのバリエーションを有効にする一連のチェック ボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-283">Each of the scenarios has an Advanced button located next to it, and a set of check boxes that enable variations to the default setting.</span></span> 
  
- <span data-ttu-id="1fa6a-284">*アドホックを選択* すると、ツールは 1 時間を通して作成される会議のシミュレーションを生成できます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-284">Choosing  *Ad-hoc*  will allow the tool to generate simulation of conferences that will be created throughout the hour.</span></span>
    
- <span data-ttu-id="1fa6a-285">大きな  *Conf を選択*  すると、大規模な会議シナリオがシミュレートされます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-285">Choosing  *Large Conf*  means that a Large Conference Scenario will be simulated.</span></span>
    
-  <span data-ttu-id="1fa6a-286">*External*  は、外部ユーザーもシミュレートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-286">*External*  tells the tool to also simulate external users.</span></span>
    
<span data-ttu-id="1fa6a-287">これらのボタンとチェック ボックスは、各シナリオに固有の追加の値であり、Stress and Performance Tool の動作を変更し、カスタマイズを可能にします。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-287">These buttons and check boxes are extra values specific to each scenario and will change the behavior of the Stress and Performance Tool and make customization possible.</span></span>
  
<span data-ttu-id="1fa6a-288">[一般シナリオ] タブのシナリオごとに (場所情報サービスを除く)、読み込みレベルの値がユーザー設定の場合、[詳細設定] ダイアログ ボックスの対応するフィールドを使用して会話速度が計算されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-288">For each scenario on the General Scenarios tab (except for Location Information Services), if the value of Load Level is **Custom**, then the conversation rate will be calculated using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="1fa6a-289">シナリオによってフィールド名が異なる場合がありますが、フィールドの説明は次の状態になります。メモ この番号は、ドロップダウン メニューから [ユーザー設定] が選択されている場合にのみ  *使用されます*  。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-289">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
<span data-ttu-id="1fa6a-290">値 **High、Medium、\*\*\*\*および** **Low** は、すべてのシナリオのバランスが取れたユーザー モデルに合ったモダリティごとの会話レートを変更します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-290">The values **High**, **Medium**, and **Low**, will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="1fa6a-291">期待される使用量の違いによりモダリティごとの負荷レベルを変更する必要がある場合は、カスタム会話レートを使用します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-291">If there's a need to change the load level per modality due to a difference in expected usage, use a Custom conversation rate.</span></span>
  
#### <a name="voice-scenarios-tab"></a><span data-ttu-id="1fa6a-292">[音声シナリオ] タブ</span><span class="sxs-lookup"><span data-stu-id="1fa6a-292">Voice Scenarios tab</span></span>

<span data-ttu-id="1fa6a-293">これは、音声関連のすべてのシナリオを構成するタブです。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-293">This is the tab for configuration of all your voice-related scenarios.</span></span>
  
![[構成ツールの音声シナリオの読み込み] タブ](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
<span data-ttu-id="1fa6a-295">選択肢は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-295">Your options are:</span></span>
  
- <span data-ttu-id="1fa6a-296">**VoIP -** [詳細設定 **] ボタン** をクリックし、PhoneAreaCode フィールドと LocationProfile (ダイヤル プラン) フィールドの値を追加します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-296">**VoIP -** Click the **Advanced** button and add values for the PhoneAreaCode and LocationProfile (dial plan) fields.</span></span> <span data-ttu-id="1fa6a-297">また、読み込みレベルの値も指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-297">You'll also give a value for Load Level.</span></span> <span data-ttu-id="1fa6a-298">VoIP または UC/PSTN ゲートウェイの負荷レベルを有効にした場合、外部通話をシミュレートするために公衆交換電話網 (PSTN) から統合コミュニケーション (UC) への構成ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-298">If you choose a load level for VoIP or UC/PSTN Gateway enabled, then a public-switched telephone network (PSTN) to unified communications (UC) configuration file will be generated to simulate external calls.</span></span>
    
- <span data-ttu-id="1fa6a-299">**UC/PSTN ゲートウェイ -** 負荷レベルの値を選択する必要があります。無効以外の値を選択する場合は、[詳細設定] ボタンをクリックして PSTN エリア コードの値も **指定する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-299">**UC/PSTN Gateway -** You need to choose a Load Level value, and when you choose anything other than Disabled, you've also got to supply a value for PSTN area code by clicking the **Advanced** button.</span></span> <span data-ttu-id="1fa6a-300">仲介 **サーバーと** PSTN の下の [追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-300">Click **Add** under the Mediation Server and PSTN.</span></span> <span data-ttu-id="1fa6a-301">エリア コード用にルートが構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-301">Make sure you have a route configured for the area code.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="1fa6a-302">Skype for Business コントロール パネルまたは Skype for Business 管理シェルを使用して、ボイス ルートの構成を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-302">You can use either the Skype for Business Control Panel or Skype for Business Management Shell to verify your voice route configuration.</span></span> 
  
- <span data-ttu-id="1fa6a-303">**会議アテンダント -** 読み込みレベルの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-303">**Conferencing Attendant -** Supply a value for Load Level.</span></span> <span data-ttu-id="1fa6a-304">Disabled 以外の値を指定すると、[電話番号] **フィールドが有効** になります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-304">Any value other than Disabled will enable the **Telephone Number** field.</span></span> <span data-ttu-id="1fa6a-305">使用する電話番号を自動応答入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-305">Enter the phone number of the Auto Attendant you want to use.</span></span> <span data-ttu-id="1fa6a-306">[ **詳細設定] を** クリックし **、[LocationProfile] フィールドの値を指定** します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-306">Click **Advanced** and give a value for the **LocationProfile** field.</span></span>
    
- <span data-ttu-id="1fa6a-307">**Call Parking Service -** ここでは、負荷レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-307">**Call Parking Service -** Here, supply a Load Level.</span></span>
    
- <span data-ttu-id="1fa6a-308">**仲介サーバーと PSTN -** 使用する仲介サーバーごとに、独自の PSTN シミュレーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-308">**Mediation Server and PSTN -** Each Mediation Server that you want to use needs its own PSTN simulator.</span></span> <span data-ttu-id="1fa6a-309">シミュレーターに使用するクライアントを決定した後、構成した PSTN シミュレーターで通話をそのコンピューターにルーティングするように仲介サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-309">After you've determined which client you're going to use for the simulator, configuration your Mediation Server to route calls to that computer on the PSTN Simulator you configured.</span></span> <span data-ttu-id="1fa6a-310">[追加 **] ボタン** をクリックして、仲介サーバーの値を構成します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-310">Click the **Add** button to configure a value for the Mediation Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1fa6a-311">各シナリオの横に [詳細設定] ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-311">Each scenario has an Advanced button located next to it.</span></span> <span data-ttu-id="1fa6a-312">[詳細] ダイアログ ボックスには、Stress and Performance Tool の動作を変更し、カスタマイズを有効にする各シナリオに固有の設定が含まれる。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-312">Advanced dialog boxes contain settings specific to each scenario that change the behavior of the Stress and Performance Tool and enable customization.</span></span> <span data-ttu-id="1fa6a-313">> [音声シナリオ] タブのシナリオごとに、読み込みレベルの値が **カスタム** の場合、[詳細設定] ダイアログ ボックスの対応するフィールドを使用して会話速度が計算されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-313">> For each scenario on the Voice Scenarios tab, if the value of Load Level is **Custom**, then the conversation rate will be calculated by using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="1fa6a-314">シナリオによってフィールド名が異なる場合がありますが、フィールドの説明は次の状態になります。メモ この番号は、ドロップダウン メニューから [ユーザー設定] が選択されている場合にのみ  *使用されます*  。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-314">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
#### <a name="web-app-tab"></a><span data-ttu-id="1fa6a-315">[Web App] タブ</span><span class="sxs-lookup"><span data-stu-id="1fa6a-315">Web App tab</span></span>

![構成ツールの [Web アプリ] タブを読み込む。](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
<span data-ttu-id="1fa6a-317">Web App は、フロントエンド サーバーにインストールされている Unified Communications Web API (UCWA) サーバーを介した会議シナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-317">Web App supports conferencing scenarios through the Unified Communications Web API (UCWA) server that's installed on a Front End server.</span></span> <span data-ttu-id="1fa6a-318">[Web アプリ] タブを使用して、すべての Web アプリ関連のシナリオを構成します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-318">Use the Web App tab to configure all web app-related scenarios.</span></span> <span data-ttu-id="1fa6a-319">オプションは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-319">Options are:</span></span>
  
- <span data-ttu-id="1fa6a-320">**一般的な Web アプリの設定 -** [追加 **設定]** ボタンをクリックし **、ReachTargetServerUrl** をフロントエンド プールの VIP のディレクトリ プール仮想 IP (VIP) に設定します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-320">**General Web App Settings -** Click the **Additional Settings** button and set the **ReachTargetServerUrl** to the Directory Pool virtual IP (VIP) of the Front End pool VIP.</span></span>
    
- <span data-ttu-id="1fa6a-321">**アプリケーション共有 -** 読み込みレベルの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-321">**Application Sharing -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="1fa6a-322">**データ コラボレーション -** 読み込みレベルの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-322">**Data Collaboration -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="1fa6a-323">**インスタント メッセージング -** 読み込みレベルの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-323">**Instant Messaging -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="1fa6a-324">**音声会議 -** 読み込みレベルの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-324">**Voice Conferencing -** Select a value for Load Level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1fa6a-325">各シナリオの横に **[詳細設定** ] ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-325">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="1fa6a-326">詳細ダイアログには、Stress and Performance Tool の動作を変更し、カスタマイズを有効にする各シナリオに固有の値が含まれます。> Web App の各シナリオで、読み込みレベルが **カスタム** の場合は **、ConversationsPerHour** フィールドで指定された値が既定ではなく使用されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-326">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Web App scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="mobility-tab"></a><span data-ttu-id="1fa6a-327">[モビリティ] タブ</span><span class="sxs-lookup"><span data-stu-id="1fa6a-327">Mobility tab</span></span>

<span data-ttu-id="1fa6a-328">モビリティ関連のすべてのシナリオを構成するには、このタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-328">Use this tab to configure all of the mobility-related scenarios.</span></span>
  
![[構成ツールのモビリティの読み込み] タブ](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
<span data-ttu-id="1fa6a-330">オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-330">The options here are:</span></span>
  
- <span data-ttu-id="1fa6a-331">**General Mobility Settings -** [ **追加設定]** をクリックし、フィールド UcwaTargetServerUrl をディレクター プール仮想 IP (VIP) またはフロントエンド プールの VIP に設定します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-331">**General Mobility Settings -** Click **Additional Settings** and set the field UcwaTargetServerUrl to the Director Pool virtual IP (VIP) or the Front End pool VIP.</span></span>
    
- <span data-ttu-id="1fa6a-332">**プレゼンスと P2P インスタント メッセージング/オーディオ -** モビリティ シミュレーションを有効にするには、負荷レベルの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-332">**Presence and P2P Instant Messaging/Audio -** Select a value for Load Level to enable the Mobility simulation.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1fa6a-333">各シナリオの横に **[詳細設定** ] ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-333">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="1fa6a-334">詳細ダイアログには、Stress and Performance Tool の動作を変更し、カスタマイズを有効にする各シナリオに固有の値が含まれます。> 各モビリティ シナリオで、負荷レベルが **カスタム** の場合は **、ConversationsPerHour** フィールドで指定された値が既定ではなく使用されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-334">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Mobility scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="summary-tab"></a><span data-ttu-id="1fa6a-335">[概要] タブ</span><span class="sxs-lookup"><span data-stu-id="1fa6a-335">Summary tab</span></span>

<span data-ttu-id="1fa6a-336">[概要] タブは、各シナリオで使用するユーザーを示します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-336">The Summary tab indicates which users to use for each of the scenarios.</span></span>
  
![[構成ツールの概要] タブを読み込む。](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
<span data-ttu-id="1fa6a-338">[概要] タブは、各シナリオで使用するユーザーを示します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-338">The Summary tab indicates which users to use for each of the scenarios.</span></span> 
  
<span data-ttu-id="1fa6a-339">ユーザー番号の範囲を手動で構成するには、[ユーザー範囲の生成を有効にする] チェック ボックスをオンにし、カスタマイズするユーザー範囲を含む表のシナリオをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-339">It's possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the User Range that you want to customize.</span></span>
  
<span data-ttu-id="1fa6a-340">**(RunClient.bat) サインイン** 速度に対応する生成されたバッチ ファイルに遅延を含めるには、開始時にサインインの遅延を追加します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-340">Check **(RunClient.bat) Add sign-in delay when starting** in order to include delays in the generated batch files to correspond to the sign-in rate.</span></span> <span data-ttu-id="1fa6a-341">これは、多数のユーザーをサインインするときにサーバーの過負荷を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-341">This is useful to prevent server overload when signing in a large number of users.</span></span>
  
<span data-ttu-id="1fa6a-342">[ **ファイルの生成]** をクリックし、構成を生成するフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-342">Click **Generate Files** and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="1fa6a-343">ファイルが正常に作成されると、ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-343">A dialog box will appear when your files have been successfully created.</span></span>
  
![[正常に生成された構成ファイルの読み込み] メッセージ ボックス。](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a><span data-ttu-id="1fa6a-346">LyncPerfTool の実行</span><span class="sxs-lookup"><span data-stu-id="1fa6a-346">Run LyncPerfTool</span></span>
<span data-ttu-id="1fa6a-347"><a name="BKMK_RunTool"> </a></span><span class="sxs-lookup"><span data-stu-id="1fa6a-347"><a name="BKMK_RunTool"> </a></span></span>

<span data-ttu-id="1fa6a-348">Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe) を実行する前に、ユーザー、連絡先、およびシナリオを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-348">You'll need to create users, contacts, and scenarios before running the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="1fa6a-349">ツールを使用してこれらのアクションを実行する方法の詳細[](using-the-tool.md#BKMK_CreateUsersAndContacts)については、この記事で[](using-the-tool.md#BKMK_UserProfile)前に説明した「ユーザーと連絡先の作成とユーザー プロファイルの構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-349">For details about using the tools to perform these actions, see [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) and [Configure User Profile](using-the-tool.md#BKMK_UserProfile) previously in this article.</span></span> <span data-ttu-id="1fa6a-350">これらのツールを実行すると、必要なパラメーターを含むバッチ ファイルの一部として Stress and Performance ツールで実行されるファイルも生成されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-350">Running these tools will also generate a file that will run with the Stress and Performance tool as part of a batch file with the required parameters included.</span></span>
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="1fa6a-351">Skype for Business Server 2015 Stress and Performance ツールの実行</span><span class="sxs-lookup"><span data-stu-id="1fa6a-351">Running the Skype for Business Server 2015 Stress and Performance tool</span></span>

<span data-ttu-id="1fa6a-352">Load Configuration ツール (UserProfileGenerator.exe) は、パフォーマンス カウンターを登録し、XML 構成ファイルを読み込み、Stress and Performance Tool (LyncPerfTool.exe) を実行できるバッチ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-352">The Load Configuration tool (UserProfileGenerator.exe) creates a batch file that enables you to run the Stress and Performance tool (LyncPerfTool.exe) by registering performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="1fa6a-353">バッチ ファイルは、構成ファイルごとに 1 LyncPerfTool.exeインスタンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-353">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="1fa6a-354">バッチ ファイルを実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-354">To run the batch file follow these steps:</span></span>
  
### <a name="run-the-stress-and-performance-test"></a><span data-ttu-id="1fa6a-355">ストレスとパフォーマンスのテストを実行する</span><span class="sxs-lookup"><span data-stu-id="1fa6a-355">Run the Stress and Performance test</span></span>

1. <span data-ttu-id="1fa6a-356">構成フォルダーとファイルを含むフォルダーを、各クライアント コンピューター上にLyncPerfTool.exeディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-356">Copy the folder with the configuration folders and files inside to the directory that has LyncPerfTool.exe on each client computer.</span></span> <span data-ttu-id="1fa6a-357">(たとえば、1.28_13.16.16 という名前のフォルダーに構成ファイルを生成した場合は、そのフォルダーを LyncPerfTool.exe が含むフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-357">(For example, if you generated the configuration files in the folder named 1.28_13.16.16, copy that folder to the folder with LyncPerfTool.exe in it.</span></span> <span data-ttu-id="1fa6a-358">これを各クライアントで行います)。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-358">Do this on each client.)</span></span>
    
2. <span data-ttu-id="1fa6a-359">クライアント フォルダーに移動し **、RunClient** バッチ スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-359">Navigate to the client folder and run the **RunClient** batch script.</span></span> <span data-ttu-id="1fa6a-360">エクスプローラーでバッチ ファイルをダブルクリックすると、そのクライアントのすべての構成ファイルが実行されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-360">You can double-click the batch file in Windows Explorer and it will run all of the configuration files for that client.</span></span> <span data-ttu-id="1fa6a-361">次の構文を使用して、クライアント フォルダーからスクリプトを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-361">You can also run the script from a client folder by using the following syntax:</span></span>
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

<span data-ttu-id="1fa6a-362">Stress and Performance ツールを直接実行するには、コマンド プロンプトを開き、コマンド ラインで次のコマンドを入力します (初めて実行する場合は、このトピックの後半のメモに示すように、必ずパフォーマンス カウンターを登録してください)。 `regsvr32 /i /n /s LyncPerfToolPerf.dll`</span><span class="sxs-lookup"><span data-stu-id="1fa6a-362">To run the Stress and Performance tool directly, open a command prompt and type the following command at the command line (and when doing this for the first time, be sure to register the performance counters  `regsvr32 /i /n /s LyncPerfToolPerf.dll`, as shown in the note later in this topic):</span></span>
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

<span data-ttu-id="1fa6a-363">ツールで構成ファイルの値を表示するには、前のコマンドにパラメーターを含め、次のように  `/displayfile` します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-363">To have the tool display the values in the configuration file, include the  `/displayfile` parameter on the preceding command, so that it looks like this:</span></span>
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

<span data-ttu-id="1fa6a-364">プロセス  *を終了*  するには、Ctrl + C キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-364">To  *end*  the process, press Ctrl+C.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fa6a-365">Stress and Performance ツールを直接実行する前に、次のコマンドを使用してパフォーマンス カウンターを登録する必要があります。  `regsvr32 /i /n /s LyncPerfToolPerf.dll`</span><span class="sxs-lookup"><span data-stu-id="1fa6a-365">Before running the Stress and Performance tool directly, you must register the performance counters via the following command:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`</span></span>
  
> [!NOTE]
> <span data-ttu-id="1fa6a-366">開始する Stress and Performance ツールのすべてのインスタンスは、すぐにユーザーのサインインを開始します。通常は、1 秒あたり 1 ユーザーの割合でサインインします。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-366">Every instance of the Stress and Performance tool that you start will immediately begin signing in users, usually at a rate of one user per second.</span></span> 
  
<span data-ttu-id="1fa6a-367">プールのユーザー サインイン率のピークは、1 秒あたり約 12 です。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-367">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="1fa6a-368">つまり、ユーザーがサインインしている間、同時に 12 LyncPerfTool.exeを超えるインスタンスを開始してはならないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-368">This means that you shouldn't start more than 12 LyncPerfTool.exe instances at the same time while users are still signing in.</span></span> <span data-ttu-id="1fa6a-369">1 秒あたり 1 人のユーザーが完全にサインインするには、約 20 分かかります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-369">One thousand users will take about 20 minutes to fully sign in at one per second.</span></span>
  
## <a name="interpreting-the-results"></a><span data-ttu-id="1fa6a-370">結果の解釈</span><span class="sxs-lookup"><span data-stu-id="1fa6a-370">Interpreting the Results</span></span>
<span data-ttu-id="1fa6a-371"><a name="BKMK_Interpret"> </a></span><span class="sxs-lookup"><span data-stu-id="1fa6a-371"><a name="BKMK_Interpret"> </a></span></span>

<span data-ttu-id="1fa6a-372">Skype for Business Server 2015 Stress and Performance Tool には、クライアントが何を行い、問題が発生しているのかを理解するのに役立つカウンターが多数含まれています。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-372">The Skype for Business Server 2015 Stress and Performance Tool has many counters that can help you understand what the client is doing, and whether it's encountering issues.</span></span>
  
### <a name="client-counters"></a><span data-ttu-id="1fa6a-373">クライアント カウンター</span><span class="sxs-lookup"><span data-stu-id="1fa6a-373">Client Counters</span></span>

<span data-ttu-id="1fa6a-374">実行中のインスタンスLyncPerfTool.exeカウンターのインスタンスが個別に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-374">Each instance of LyncPerfTool.exe running has a separate instance of the counters.</span></span> <span data-ttu-id="1fa6a-375">各インスタンスの名前は、プロセス ID によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-375">Each instance is named by its process ID.</span></span> <span data-ttu-id="1fa6a-376">クライアントが過負荷の場合は、他の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-376">If clients are overloaded other issues can occur.</span></span> <span data-ttu-id="1fa6a-377">これらの問題を回避するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-377">To prevent these issues:</span></span>
  
- <span data-ttu-id="1fa6a-378">クライアント コンピューターの CPU とメモリの使用状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-378">Monitor CPU and Memory usage on the client computers.</span></span> <span data-ttu-id="1fa6a-379">CPU が一貫して 90% を超える場合は、ユーザーの数を減らします。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-379">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>
    
- <span data-ttu-id="1fa6a-380">メモリ使用量が高い場合は、ページ ファイルの領域が足りなから始まると、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-380">When the Memory footprint is high, you may run into issues if the Page File begins to run out of space.</span></span> <span data-ttu-id="1fa6a-381">コミット チャージがコンピューターの制限に達していないのを確認します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-381">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="1fa6a-382">メモリ制限に達している場合は、ページ ファイルのサイズを大きくするか、ユーザー数を減らすことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-382">If you are running into Memory limits consider increasing the Page File size or reducing the number of users.</span></span>
    
<span data-ttu-id="1fa6a-383">主要なパフォーマンス カウンターの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-383">Here's a list of key performance counters:</span></span>
  
<span data-ttu-id="1fa6a-384">**一般的な情報**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-384">**General Information**</span></span>

|<span data-ttu-id="1fa6a-385">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-385">**Performance Counter**</span></span>|<span data-ttu-id="1fa6a-386">**説明**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-386">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fa6a-387">時間 (分)</span><span class="sxs-lookup"><span data-stu-id="1fa6a-387">Time Spent in Minutes</span></span>  <br/> |<span data-ttu-id="1fa6a-388">プロセスが開始された後に費やされた時間。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-388">Time spent since the process was started.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-389">アクティブなエンドポイント</span><span class="sxs-lookup"><span data-stu-id="1fa6a-389">Active Endpoints</span></span>  <br/> |<span data-ttu-id="1fa6a-390">サーバーに現在接続されているエンドポイントの数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-390">Number of endpoints currently connected to the server.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-391">失敗したログオン</span><span class="sxs-lookup"><span data-stu-id="1fa6a-391">Failed Logons</span></span>  <br/> |<span data-ttu-id="1fa6a-392">エンドポイント サインインの失敗の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-392">Total number of endpoint sign-in failures.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-393">ログオン試行回数</span><span class="sxs-lookup"><span data-stu-id="1fa6a-393">Logon Attempts</span></span>  <br/> |<span data-ttu-id="1fa6a-394">エンドポイント サインインの合計試行回数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-394">Total number of endpoint sign-in attempts.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-395">Endpoints Disconnected</span><span class="sxs-lookup"><span data-stu-id="1fa6a-395">Endpoints Disconnected</span></span>  <br/> |<span data-ttu-id="1fa6a-396">切断されたエンドポイントの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-396">Total number of endpoints that have been disconnected.</span></span>  <br/> |
   
<span data-ttu-id="1fa6a-397">**プレゼンス情報**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-397">**Presence Information**</span></span>

|<span data-ttu-id="1fa6a-398">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-398">**Performance Counter**</span></span>|<span data-ttu-id="1fa6a-399">**説明**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-399">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fa6a-400">SetPresence Calls</span><span class="sxs-lookup"><span data-stu-id="1fa6a-400">SetPresence Calls</span></span>  <br/> |<span data-ttu-id="1fa6a-401">プレゼンス変更の合計試行回数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-401">Total number of presence change attempts.</span></span> <span data-ttu-id="1fa6a-402">さまざまな種類のプレゼンス変更については、「SetPresence (Presence Type) Calls Performance Counter」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-402">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-403">SetPresence の NNN 応答</span><span class="sxs-lookup"><span data-stu-id="1fa6a-403">NNN Responses for SetPresence</span></span>  <br/> |<span data-ttu-id="1fa6a-404">サーバーから受信した nnn 応答コードの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-404">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-405">GetPresence Calls</span><span class="sxs-lookup"><span data-stu-id="1fa6a-405">GetPresence Calls</span></span>  <br/> |<span data-ttu-id="1fa6a-406">プレゼンス要求の取得試行の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-406">Total number of get presence request attempts.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-407">GetPresence の NNN 応答</span><span class="sxs-lookup"><span data-stu-id="1fa6a-407">NNN Responses for GetPresence</span></span>  <br/> |<span data-ttu-id="1fa6a-408">サーバーから受信した nnn 応答コードの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-408">Total number of nnn response codes received from the server.</span></span>  <br/> |
   
<span data-ttu-id="1fa6a-409">**アドレス帳サービス情報**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-409">**Address Book service information**</span></span>

|<span data-ttu-id="1fa6a-410">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-410">**Performance Counter**</span></span>|<span data-ttu-id="1fa6a-411">**説明**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-411">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fa6a-412">ABS Full/Delta File Downloads Attempted</span><span class="sxs-lookup"><span data-stu-id="1fa6a-412">ABS Full/Delta File Downloads Attempted</span></span>  <br/> |<span data-ttu-id="1fa6a-413">試行された完全ファイルまたは差分ファイルのダウンロード要求の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-413">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-414">ABS Full/Delta File Downloads Succeeded</span><span class="sxs-lookup"><span data-stu-id="1fa6a-414">ABS Full/Delta File Downloads Succeeded</span></span>  <br/> |<span data-ttu-id="1fa6a-415">試行された完全ファイルまたは差分ファイルのダウンロード要求の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-415">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-416">アドレス帳 Web クエリ サービス関連のカウンター</span><span class="sxs-lookup"><span data-stu-id="1fa6a-416">Address Book Web Query service related counters</span></span>  <br/> |<span data-ttu-id="1fa6a-417">アドレス帳ファイルのダウンロードに関連するカウンター。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-417">Address book file download related counters.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-418">ABS WS Calls attempted</span><span class="sxs-lookup"><span data-stu-id="1fa6a-418">ABS WS Calls attempted</span></span>  <br/> |<span data-ttu-id="1fa6a-419">試行されたアドレス帳 Web クエリ サービス要求の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-419">Total number of Address Book Web Query service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-420">ABS WS Calls Succeeded</span><span class="sxs-lookup"><span data-stu-id="1fa6a-420">ABS WS Calls Succeeded</span></span>  <br/> |<span data-ttu-id="1fa6a-421">正常な応答コードを返したアドレス帳 Web クエリ サービス要求の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-421">Total number of Address Book Web Query service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-422">ABS WS Calls Failed</span><span class="sxs-lookup"><span data-stu-id="1fa6a-422">ABS WS Calls Failed</span></span>  <br/> |<span data-ttu-id="1fa6a-423">エラー応答コードを返したアドレス帳 Web クエリ サービス要求の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-423">Total number of Address Book Web Query service requests that returned an error response code.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="1fa6a-424">このカテゴリには、アドレス帳サービス (ABS) ファイルのダウンロードとアドレス帳 Web クエリ サービス要求を監視するために使用されるカウンターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-424">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span> 
  
<span data-ttu-id="1fa6a-425">**配布リスト (DL) 情報**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-425">**Distribution List (DL) Information**</span></span>

|<span data-ttu-id="1fa6a-426">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-426">**Performance Counter**</span></span>|<span data-ttu-id="1fa6a-427">**説明**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-427">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fa6a-428">Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="1fa6a-428">Calls Attempted</span></span>  <br/> |<span data-ttu-id="1fa6a-429">試行された配布リスト拡張 (DLX) Web サービス要求の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-429">Total number of distribution list expansion (DLX) web service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-430">Calls Succeeded</span><span class="sxs-lookup"><span data-stu-id="1fa6a-430">Calls Succeeded</span></span>  <br/> |<span data-ttu-id="1fa6a-431">成功した応答コードを返した DLX Web サービス要求の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-431">Total number of DLX web service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-432">Calls Failed</span><span class="sxs-lookup"><span data-stu-id="1fa6a-432">Calls Failed</span></span>  <br/> |<span data-ttu-id="1fa6a-433">エラー応答コードを返した DLX Web サービス要求の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-433">Total number of DLX web service requests that returned an error response code.</span></span>  <br/> |
   

  
> [!NOTE]
> <span data-ttu-id="1fa6a-434">以下に示すパフォーマンス カウンターは、仲介サーバー、音声ビデオ会議サーバー、エッジ サーバー、応答グループ アプリケーション、電話会議 自動応答 に対する通話を含む、すべてのボイス オーバー IP (VoIP) 呼び出し (これらのシナリオが有効な場合) の番号を報告します。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-434">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span> 
  
<span data-ttu-id="1fa6a-435">**VoIP の基本情報**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-435">**VoIP Basic Information**</span></span>

|<span data-ttu-id="1fa6a-436">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-436">**Performance Counter**</span></span>|<span data-ttu-id="1fa6a-437">**説明**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-437">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fa6a-438">Calls Active</span><span class="sxs-lookup"><span data-stu-id="1fa6a-438">Calls Active</span></span>  <br/> |<span data-ttu-id="1fa6a-439">現在進行中の着信/発信音声通話の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-439">Total number of incoming/outgoing voice calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-440">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="1fa6a-440">Calls Terminated</span></span>  <br/> |<span data-ttu-id="1fa6a-441">既に終了している着信/発信音声通話の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-441">Total number of incoming/outgoing voice calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-442">Calls Declined</span><span class="sxs-lookup"><span data-stu-id="1fa6a-442">Calls Declined</span></span>  <br/> |<span data-ttu-id="1fa6a-443">拒否された着信音声呼び出しの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-443">Total number of incoming voice calls declined.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-444">着信/発信呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="1fa6a-444">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="1fa6a-445">試行された着信/発信音声通話の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-445">Total number of incoming/outgoing voice calls attempted.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-446">着信/発信通話の確立</span><span class="sxs-lookup"><span data-stu-id="1fa6a-446">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="1fa6a-447">確立された着信/発信音声通話の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-447">Total number of incoming/outgoing voice calls established.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-448">Calls Received NNN</span><span class="sxs-lookup"><span data-stu-id="1fa6a-448">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="1fa6a-449">サーバーから受信した nnn 応答コードの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-449">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-450">VoIP パス レート (%)</span><span class="sxs-lookup"><span data-stu-id="1fa6a-450">VoIP Pass Rate (%)</span></span>  <br/> |<span data-ttu-id="1fa6a-451">Total calls established/Total calls attempted.</span><span class="sxs-lookup"><span data-stu-id="1fa6a-451">Total calls established/Total calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="1fa6a-452">**応答グループ サービスの通話情報**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-452">**Response Group service Call Information**</span></span>

|<span data-ttu-id="1fa6a-453">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-453">**Performance Counter**</span></span>|<span data-ttu-id="1fa6a-454">**説明**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-454">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fa6a-455">Calls Active</span><span class="sxs-lookup"><span data-stu-id="1fa6a-455">Calls Active</span></span>  <br/> |<span data-ttu-id="1fa6a-456">応答グループ アプリケーションに対するアクティブな通話の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-456">Total number of active calls to the Response Group application.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-457">Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="1fa6a-457">Calls Attempted</span></span>  <br/> |<span data-ttu-id="1fa6a-458">試行された通話の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-458">Total number of calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="1fa6a-459">**インスタント メッセージング (IM) 通話情報**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-459">**Instant Messaging (IM) Call Information**</span></span>

|<span data-ttu-id="1fa6a-460">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-460">**Performance Counter**</span></span>|<span data-ttu-id="1fa6a-461">**説明**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-461">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fa6a-462">Calls Active</span><span class="sxs-lookup"><span data-stu-id="1fa6a-462">Calls Active</span></span>  <br/> |<span data-ttu-id="1fa6a-463">進行中の着信/発信インスタント メッセージング呼び出しの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-463">Total number of ongoing incoming/outgoing instant messaging calls.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-464">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="1fa6a-464">Calls Terminated</span></span>  <br/> |<span data-ttu-id="1fa6a-465">既に終了している着信/発信インスタント メッセージング呼び出しの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-465">Total number of incoming/outgoing instant messaging calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-466">Calls Received NNN</span><span class="sxs-lookup"><span data-stu-id="1fa6a-466">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="1fa6a-467">サーバーから受信した nnn 応答コードの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-467">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-468">IM メッセージの受信/送信</span><span class="sxs-lookup"><span data-stu-id="1fa6a-468">IM Messages Received/Sent</span></span>  <br/> |<span data-ttu-id="1fa6a-469">すべてのセッションで受信または送信されたメッセージの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-469">Total number of messages received or sent for all sessions.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-470">着信/発信呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="1fa6a-470">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="1fa6a-471">試行された着信/発信インスタント メッセージング呼び出しの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-471">Total number of incoming/outgoing instant messaging calls attempted.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-472">着信/発信通話の確立</span><span class="sxs-lookup"><span data-stu-id="1fa6a-472">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="1fa6a-473">確立された着信/発信インスタント メッセージ呼び出しの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-473">Total number of incoming/outgoing instant message calls established.</span></span>  <br/> |
   
<span data-ttu-id="1fa6a-474">**アプリ共有呼び出し情報**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-474">**App Sharing Call Information**</span></span>

|<span data-ttu-id="1fa6a-475">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-475">**Performance Counter**</span></span>|<span data-ttu-id="1fa6a-476">**説明**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-476">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fa6a-477">Calls Active</span><span class="sxs-lookup"><span data-stu-id="1fa6a-477">Calls Active</span></span>  <br/> |<span data-ttu-id="1fa6a-478">進行中の着信/発信アプリケーション共有呼び出しの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-478">Total number of ongoing incoming/outgoing application sharing calls.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-479">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="1fa6a-479">Calls Terminated</span></span>  <br/> |<span data-ttu-id="1fa6a-480">既に終了している着信/発信アプリケーション共有呼び出しの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-480">Total number of incoming/outgoing application sharing calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-481">Calls Received NNN</span><span class="sxs-lookup"><span data-stu-id="1fa6a-481">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="1fa6a-482">サーバーから受信した nnn 応答コードの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-482">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-483">着信/発信呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="1fa6a-483">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="1fa6a-484">試行された着信/発信アプリケーション共有呼び出しの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-484">Total number of incoming/outgoing application sharing calls attempted.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-485">着信/発信通話の確立</span><span class="sxs-lookup"><span data-stu-id="1fa6a-485">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="1fa6a-486">確立された着信/発信アプリケーション共有呼び出しの総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-486">Total number of incoming/outgoing application sharing calls established.</span></span>  <br/> |
   
<span data-ttu-id="1fa6a-487">**CAA 通話情報**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-487">**CAA Call Information**</span></span>

|<span data-ttu-id="1fa6a-488">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-488">**Performance Counter**</span></span>|<span data-ttu-id="1fa6a-489">**説明**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-489">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fa6a-490">Calls Active</span><span class="sxs-lookup"><span data-stu-id="1fa6a-490">Calls Active</span></span>  <br/> |<span data-ttu-id="1fa6a-491">現在進行中の着信/発信公衆交換電話網 (PSTN) 通話の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-491">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-492">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="1fa6a-492">Calls Terminated</span></span>  <br/> |<span data-ttu-id="1fa6a-493">既に終了している着信/発信 PSTN 通話の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-493">Total number of incoming/outgoing PSTN calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-494">着信/発信呼び出しの試行</span><span class="sxs-lookup"><span data-stu-id="1fa6a-494">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="1fa6a-495">試行された着信/発信 PSTN 通話の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-495">Total number of incoming/outgoing PSTN calls attempted.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-496">着信/発信通話の確立</span><span class="sxs-lookup"><span data-stu-id="1fa6a-496">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="1fa6a-497">確立された着信/発信 PSTN 通話の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-497">Total number of incoming/outgoing PSTN calls established.</span></span>  <br/> |
   
<span data-ttu-id="1fa6a-498">**電話会議情報**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-498">**Conference Information**</span></span>

|<span data-ttu-id="1fa6a-499">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-499">**Performance Counter**</span></span>|<span data-ttu-id="1fa6a-500">**説明**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-500">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fa6a-501">アクティブなインスタント メッセージング会議</span><span class="sxs-lookup"><span data-stu-id="1fa6a-501">Active Instant Messaging Conferences</span></span>  <br/> |<span data-ttu-id="1fa6a-502">進行中のインスタント メッセージング会議の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-502">Total number of ongoing instant messaging conferences.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-503">アクティブな音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="1fa6a-503">Active Audio/Video Conferences</span></span>  <br/> |<span data-ttu-id="1fa6a-504">進行中の音声ビデオ (A/V) 会議の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-504">Total number of ongoing audio/video (A/V) conferences.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-505">Active Application Sharing Conferences</span><span class="sxs-lookup"><span data-stu-id="1fa6a-505">Active Application Sharing Conferences</span></span>  <br/> |<span data-ttu-id="1fa6a-506">進行中のアプリケーション共有会議の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-506">Total number of ongoing application sharing conferences.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-507">参加者数</span><span class="sxs-lookup"><span data-stu-id="1fa6a-507">Number of Participants</span></span>  <br/> |<span data-ttu-id="1fa6a-508">現在電話会議に接続している参加者の総数です。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-508">Total number of participants currently connected to conferences.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-509">会議スケジュールの失敗</span><span class="sxs-lookup"><span data-stu-id="1fa6a-509">Conference Schedule Failure</span></span>  <br/> |<span data-ttu-id="1fa6a-510">電話会議をスケジュールしようとして失敗した合計回数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-510">Total number of failures while trying to schedule a conference.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-511">会議参加の失敗</span><span class="sxs-lookup"><span data-stu-id="1fa6a-511">Join Conference Failure</span></span>  <br/> |<span data-ttu-id="1fa6a-512">電話会議への接続中に発生したエラーの総数です。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-512">Total number of failures while trying to connect to a conference.</span></span>  <br/> |
   
<span data-ttu-id="1fa6a-513">**UCWA クライアント カウンター**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-513">**UCWA Client Counters**</span></span>

|<span data-ttu-id="1fa6a-514">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-514">**Performance Counter**</span></span>|<span data-ttu-id="1fa6a-515">**説明**</span><span class="sxs-lookup"><span data-stu-id="1fa6a-515">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fa6a-516">Total Number of IMMCU Joins Succeeded</span><span class="sxs-lookup"><span data-stu-id="1fa6a-516">Total Number of IMMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="1fa6a-517">参加したインスタント メッセージング会議の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-517">Total number of instant messaging conferences joined.</span></span>  <br/> |
|<span data-ttu-id="1fa6a-518">Total Number of DMCU Joins Succeeded</span><span class="sxs-lookup"><span data-stu-id="1fa6a-518">Total Number of DMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="1fa6a-519">参加した A/V 会議の総数。</span><span class="sxs-lookup"><span data-stu-id="1fa6a-519">Total number of A/V conferences joined.</span></span>  <br/> |
   

