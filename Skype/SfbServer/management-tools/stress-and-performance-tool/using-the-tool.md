---
title: Skype for Business Server 2015 Stress and Performance Tool の使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for Business Server 2015 Stress and Performance Tool を実行するには、両側のユーザー、連絡先、およびユーザー プロファイルを管理できること、実行に備えてツールを構成できること、ツールによって生成された出力または結果を確認できることが必要です。
ms.openlocfilehash: 9920eb446452b9df23470a46c16eab754cc91577
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816146"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="2bb0c-103">Skype for Business Server 2015 Stress and Performance Tool の使用</span><span class="sxs-lookup"><span data-stu-id="2bb0c-103">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="2bb0c-104">Skype for Business Server 2015 Stress and Performance Tool を実行するには、両側のユーザー、連絡先、およびユーザー プロファイルを管理できること、実行に備えてツールを構成できること、ツールによって生成された出力または結果を確認できることが必要です。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-104">To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.</span></span>
  
<span data-ttu-id="2bb0c-105">Skype for Business Server 2015 Stress and Performance Tool (実行可能ファイル名: LyncPerfTool.exe) の実行には、次の 4 区分の作業が必要になります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-105">There are four areas involved with running the Skype for Business Server 2015 Stress and Performance Tool (the executable is LyncPerfTool.exe):</span></span>
  
- [<span data-ttu-id="2bb0c-106">ユーザーと連絡先の作成</span><span class="sxs-lookup"><span data-stu-id="2bb0c-106">Create Users and Contacts</span></span>](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [<span data-ttu-id="2bb0c-107">ユーザー プロファイルの構成</span><span class="sxs-lookup"><span data-stu-id="2bb0c-107">Configure User Profile</span></span>](using-the-tool.md#BKMK_UserProfile)
    
- [<span data-ttu-id="2bb0c-108">LyncPerfTool の実行</span><span class="sxs-lookup"><span data-stu-id="2bb0c-108">Run LyncPerfTool</span></span>](using-the-tool.md#BKMK_RunTool)
    
- [<span data-ttu-id="2bb0c-109">結果の解釈</span><span class="sxs-lookup"><span data-stu-id="2bb0c-109">Interpreting the Results</span></span>](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a><span data-ttu-id="2bb0c-110">ユーザーと連絡先の作成</span><span class="sxs-lookup"><span data-stu-id="2bb0c-110">Create Users and Contacts</span></span>
<span data-ttu-id="2bb0c-111"><a name="BKMK_CreateUsersAndContacts"> </a></span><span class="sxs-lookup"><span data-stu-id="2bb0c-111"><a name="BKMK_CreateUsersAndContacts"> </a></span></span>

<span data-ttu-id="2bb0c-112">Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) を使用して、ストレスおよびパフォーマンス テストのためのユーザーと連絡先を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-112">You need to use the Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts for your stress and performance testing.</span></span>
  
<span data-ttu-id="2bb0c-113">次に示すリストは、このトピックを読み進めるときに役立つことがある便利な用語です。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-113">This is a list of helpful terms that might be useful as you read through the topics:</span></span>
  
- <span data-ttu-id="2bb0c-114">**Organizational Unit (組織単位)**: Active Directory Domain Services (AD DS) の組織単位 (OU)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-114">**Organizational Unit** - The Active Directory Domain Services (AD DS) organizational unit (OU).</span></span>
    
- <span data-ttu-id="2bb0c-115">**Federated/Cross Pool (フェデレーション/クロス プール)**: 別のインスタント メッセージング (IM) サービスのユーザーと通信できるユーザー。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-115">**Federated / Cross Pool** - Users who can communicate with users from other Instant Messaging (IM) services.</span></span>
    
- <span data-ttu-id="2bb0c-116">**配布リスト (Distribution List)**: DL。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-116">**Distribution Lists** - Or DLs.</span></span> <span data-ttu-id="2bb0c-117">AD DS ユーザーのリストを格納している AD DS のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-117">These are objects in AD DS that contain a list of AD DS users.</span></span> <span data-ttu-id="2bb0c-118">ユーザー グループ間の通信を円滑に進めるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-118">They're used to facilitate communications across groups of people.</span></span>
    
- <span data-ttu-id="2bb0c-119">**Location Info Service (場所情報サービス)**: Skype for Business Server 2015 のサービスであり、電話ごとに有効化および構成しておくと、Enhanced 911 (E911) サービスに対応する物理的な位置の取得が可能になります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-119">**Location Info Service** - The Skype for Business Server 2015 service that, when it's enabled and configured per phone, allows for the retrieval of physical location for Enhanced 911 (E911) services.</span></span>
    
- <span data-ttu-id="2bb0c-120">**U.S. Phone Numbers (米国の電話番号)**: SIP URI と共にユーザーに割り当てられる電話番号であり、番号の逆引き検索 (RNL) で着信通話と発信通話をルーティングするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-120">**U.S. Phone Numbers** - Phone numbers assigned to user in addition to the SIP URI that's used for routing inbound and outbound calls in Reverse Number Lookup (RNL).</span></span>
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="2bb0c-121">UserProvisioningTool.exe を使用してユーザーと連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="2bb0c-121">Create Users and Contacts by using UserProvisioningTool.exe</span></span>

> [!NOTE]
> <span data-ttu-id="2bb0c-122">このツールを実行するために、Domain Admins セキュリティ グループのメンバーとしてログインしていることを作業の開始前に必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-122">Before you even begin, be absolutely sure you're logged in as a member of the Domain Admins security group to run this tool.</span></span> <span data-ttu-id="2bb0c-123">これは、この作業で Active Directory ユーザーを作成することになるために必要な行動です。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-123">You need to do this, because you're going to be creating Active Directory users.</span></span> 
  
<span data-ttu-id="2bb0c-124">ロード シミュレーションのためのユーザーと連絡先を作成する場合は、Skype for Business Server User Provisioning Tool を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-124">You have to use the Skype for Business Server User Provisioning Tool to create users and contacts for load simulation.</span></span>
  
<span data-ttu-id="2bb0c-125">**Skype for Business Server User Provisioning Tool** は、**Skype for Business Server Stress and Performance Tool** パッケージと共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-125">The **Skype for Business Server User Provisioning Tool** is installed with the **Skype for Business Server Stress and Performance Tool** package.</span></span> <span data-ttu-id="2bb0c-126">このパッケージ インストーラー (CapacityPlanningTool.msi) は、テスト目的のフロント エンド サーバーまたは Standard Edition サーバーで実行しておきます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-126">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server you intend to test.</span></span>
  
<span data-ttu-id="2bb0c-127">Skype for Business Server User Provisioning Tool は、フロント エンド サーバーまたは Standard Edition サーバーで UserProvisioningTool.exe (%InstalledDirectory%LyncStressAndPerfTool\LyncStress にあります) を実行することで開始できます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-127">You can start the Skype for Business Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2bb0c-128">多数のユーザー (10,000 ユーザー以上) を作成するときには、UserProvisioningTool.exe を実行してください。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-128">When you create a large number of users (for example, 10,000 or more), run the UserProvisioningTool.exe.</span></span> <span data-ttu-id="2bb0c-129">これは、このツールによって*新しい* AD ユーザーの作成と構成が実行されるために必要です。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-129">You'll need to do this because the tool will be creating and configuring  *new*  AD users.</span></span>
  
<span data-ttu-id="2bb0c-130">User Provisioning Tool を起動したら、[Configuration] をクリックして [Load Configuration] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-130">When the User Provisioning Tool opens, click Configuration and select the Load Configuration.</span></span> 
  
<span data-ttu-id="2bb0c-131">ユーザーと連絡先を構成するには、パッケージに含まれている "SampleData.xml" という既定のファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-131">To begin configuring users and contacts, load the default file included with the package, called "SampleData.xml".</span></span> <span data-ttu-id="2bb0c-132">これにより、各フィールドがサンプル データで再設定されます。ただし、それぞれの展開に応じて、このデータを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-132">This will prepopulate fields with sample data that you'll need to change to make it relevant for your deployment.</span></span>
  
<span data-ttu-id="2bb0c-133">カスタマイズした設定が含まれている構成済みの XML ファイルがある場合は、そのファイルを読み込むことも可能です。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-133">If you have a preconfigured XML file that already contains your customized settings, you can load that file instead.</span></span> <span data-ttu-id="2bb0c-134">次の各セクションで説明するように、User Provisioning Tool のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-134">Fill in the fields in the User Provisioning Tool, as described in the sections below.</span></span>
  
### <a name="to-configure-server-options"></a><span data-ttu-id="2bb0c-135">サーバー オプションを構成するには:</span><span class="sxs-lookup"><span data-stu-id="2bb0c-135">To configure server options:</span></span>

1. <span data-ttu-id="2bb0c-136">**[Front End Pool FQDN]** フィールドに、Standard Edition サーバー、またはユーザーをホストするフロント エンド プールの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-136">In the **Front End Pool FQDN** field, type the fully qualified domain name (FQDN) of the Standard Edition server, or the Front End pool where you want to host the users.</span></span>
    
2. <span data-ttu-id="2bb0c-137">**[User Name Prefix]** フィールドに、テスト目的のユーザー名を無効にする際に使用するプレフィックスを入力します ("TestUser" など)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-137">In the **User Name Prefix** field, type a prefix that you want to use to bust your user names for testing purposes (such as "TestUser").</span></span>
    
3. <span data-ttu-id="2bb0c-138">**[Password]** フィールドに、すべてのテスト ユーザー アカウントに使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-138">In the **Password** field, type a password that will be used across all the test user accounts.</span></span>
    
4. <span data-ttu-id="2bb0c-139">**[Account Domain]** フィールドに、現在の AD ドメインのドメイン名を入力します (テスト ユーザーの作成先にするドメイン)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-139">In the **Account Domain** field, type the domain name of your current AD domain (the one in which you want to create your test users).</span></span>
    
5. <span data-ttu-id="2bb0c-140">**[Organizational Unit]** フィールドに、該当するテスト ユーザーの作成先にする AD ドメインの名前を入力します </span><span class="sxs-lookup"><span data-stu-id="2bb0c-140">In the **Organizational Unit** field, type the name of the AD domain where you want to create these test users.</span></span> <span data-ttu-id="2bb0c-141">(この OU が存在していない場合は、自動的に作成されます)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-141">(If the OU doesn't already exist, it'll be created for you).</span></span>
    
6. <span data-ttu-id="2bb0c-142">**[Phone Area Code]** フィールドに、すべてのテスト ユーザー アカウントに使用する 3 桁の市外局番を入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-142">In the **Phone Area Code** field, type the three-digit area code to be used across all test user accounts.</span></span> <span data-ttu-id="2bb0c-143">ここで選択する市外局番は、AD 内の他のユーザーの市外局番と競合しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-143">Make certain that the area code you chose doesn't conflict with other users' area codes in AD.</span></span>
    
7. <span data-ttu-id="2bb0c-144">**[Voice Enabled]** チェックボックスをクリックしてオンにします (テスト ユーザーがエンタープライズ VoIP を使用できるようにする場合)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-144">Click to select the **Voice Enabled** check box, if you want to enable the test users for Enterprise Voice.</span></span>
    
8. <span data-ttu-id="2bb0c-145">**[Number of Users]** フィールドでは、作成するテスト ユーザーの合計数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-145">In the **Number of Users** field, give the total number of test users you want to create.</span></span>
    
9. <span data-ttu-id="2bb0c-146">**[Start Index]** フィールドでは、ユーザー名プレフィックスのサフィックスとして使用する最初の番号を指定します (次の例の場合、プレフィックスは "TestUser" になり、最初の名前の末尾は "0" になります)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-146">In the **Start Index** field, give the starting number that'll be used as a suffix to the user name prefix (for example, the prefix is "TestUser", and the first name will end in "0" in the example below.)</span></span>
    
     ![[User Creation] タブを表示している User Provisioning Tool。](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a><span data-ttu-id="2bb0c-148">[Create Users] ボタン</span><span class="sxs-lookup"><span data-stu-id="2bb0c-148">Create Users button</span></span>

<span data-ttu-id="2bb0c-149">**[Create Users]** ボタンをクリックすると、入力した入力パラメーターが検証されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-149">When you click on the **Create Users** button, the input parameters you've entered are validated.</span></span> <span data-ttu-id="2bb0c-150">検証エラーが見つかると、そのエラーの修正を求められます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-150">If there are any validation errors, you'll be prompted to fix them.</span></span> <span data-ttu-id="2bb0c-151">すべての値が適切な場合は、AD (指定した OU 内) にユーザーが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-151">Or, if all the values are correct, users will start appearing in AD (in whichever OU you specified).</span></span> <span data-ttu-id="2bb0c-152">ツールの実行時には、下側に進行状況バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-152">You'll see a progress bar at the bottom of the tool as it runs.</span></span> <span data-ttu-id="2bb0c-153">進行状況バーがアクティブになっている間は、アプリケーションを終了しないでください。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-153">Don't close the application while the progress bar is active.</span></span>
  
<span data-ttu-id="2bb0c-154">ユーザーの作成には時間がかかるため、それに応じて計画を立ててください。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-154">User creation takes time, so please plan accordingly.</span></span> <span data-ttu-id="2bb0c-155">この処理には、数分間 (ユーザーが少数の場合) から数時間 (ユーザーが多数の場合) かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-155">This process can take anywhere from several minutes for a few users, to a few hours for a large number of users.</span></span>
  
<span data-ttu-id="2bb0c-156">テスト環境の AD ドメイン コントローラーにアクセスできない場合でも、作成対象に指定したユーザーの範囲内のいずれかのユーザーとしてログインすることで、ユーザーの作成を検証できます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-156">If you don't have access to the AD Domain Controller in your test environment, you can still validate user creation by logging in as one of the users in the range of users you specified to create.</span></span> <span data-ttu-id="2bb0c-157">ユーザー名として、@sipDomain と共にプレフィックスとサフィックスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-157">Remember to use the prefix, and the suffix, along with the @sipDomain as the username.</span></span> <span data-ttu-id="2bb0c-158">たとえば、<em>TestUser20@contoso.net</em> のようにします。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-158">Here is an example:  <em>TestUser20@contoso.net</em>  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="2bb0c-159">既にユーザーが存在している場合に [Create Users] ボタンをクリックすると、そのユーザーは構成の変更内容によって更新されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-159">If the users already exist, clicking the Create Users button will update them with any configuration changes.</span></span> 
  
#### <a name="delete-users-button"></a><span data-ttu-id="2bb0c-160">[Delete Users] ボタン</span><span class="sxs-lookup"><span data-stu-id="2bb0c-160">Delete Users button</span></span>

<span data-ttu-id="2bb0c-161">**[Delete Users]** ボタンをクリックすると、そのタブの入力パラメーターが検証されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-161">When you click on the **Delete Users** button, the tab's input parameters will be validated.</span></span> <span data-ttu-id="2bb0c-162">検証エラーが見つかると、そのエラーの修正を求められます。入力値が適切な場合は、指定したテスト ユーザーが無効化され、Active Directory から削除されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-162">If there are validation errors, you'll be prompted to fix them, and if the input values are correct, the specified test users will be disabled and deleted from Active Directory.</span></span> <span data-ttu-id="2bb0c-163">前述したように、このタブの下側に進行状況バーが表示されます。この進行状況バーがアクティブになっている間はアプリケーションを終了しないでください。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-163">Again, a progress bar will appear on the bottom of this tab, and you shouldn't close the application while the progress bar is active.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2bb0c-164">米国形式の電話番号のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-164">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="2bb0c-165">ユーザーには電話番号が常に割り当てられます。また、UserProvisioningTool.exe で作成されたすべてのユーザーは、既定でエンタープライズ VoIP が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-165">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice by default.</span></span> <span data-ttu-id="2bb0c-166">電話番号を使用するシナリオ (会議自動アテンダントや UC-PSTN 通話など) では、この電話番号が通話の正しいルーティングのために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-166">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="2bb0c-167">そのため、*すべてのユーザー*に*一意の電話番号*を用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-167">For this reason,  *every user*  must have a *unique phone number*  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="2bb0c-168">**ユーザーを 2 回作成する必要がある場合は、別の市外局番を使用するか、Disable-CsUser コマンドレットを使用して以前のユーザーを削除してください。それ以外の場合は、ユーザー作成のコマンドが失敗します。**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-168">**If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the Disable-CsUser cmdlet.**</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2bb0c-169">連絡先の作成前に、まず、ユーザーのレプリケーションを完了しておく必要があります (この操作は、[Users] タブで実行します)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-169">Before you create contacts, you first need to complete user replication (which is done from the Users tab).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="2bb0c-170">ユーザー作成の直後の場合は、Skype for Business Server レプリケーションが完了して、データベースにユーザー アカウントが設定されるまで、しばらくの間待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-170">If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="2bb0c-171">**ユーザーのレプリケーションが完了していないと、エラーが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-171">**If the users haven't finished replicating, you'll see an error.**</span></span> <span data-ttu-id="2bb0c-172">ユーザーのレプリケーションの完了は、Skype for Business Server 2015 フロント エンド サービスが開始されていること、または指定した合計数の最後のユーザーに対する Get-CsUser コマンドレットが正常に実行されたことによって確認できます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-172">You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.</span></span>
  
#### <a name="contacts-creation-tab"></a><span data-ttu-id="2bb0c-173">[Contacts Creation] タブ</span><span class="sxs-lookup"><span data-stu-id="2bb0c-173">Contacts Creation tab</span></span>

<span data-ttu-id="2bb0c-174">このタブを使用すると、テストのためのユーザーの連絡先詳細を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-174">This tab lets you give users' contacts details for your testing.</span></span>
  
![[Contents Creation] タブを表示している User Provisioning Tool。](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a><span data-ttu-id="2bb0c-176">ユーザーの連絡先を構成するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-176">To configure users' contacts, do the following:</span></span>

1. <span data-ttu-id="2bb0c-177">**[Average Contacts per User]** フィールドに、ユーザーごとの連絡先リストに設定する連絡先の平均数を入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-177">In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.</span></span>
    
2. <span data-ttu-id="2bb0c-178">**[Fixed]** チェックボックスは、すべてのユーザーに同数の連絡先を作成する場合にオンにします。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-178">Select the **Fixed** check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="2bb0c-179">各ユーザーに異なる数の連絡先を作成する場合は、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-179">If you want to vary the number of contacts created for users, clear that check box.</span></span>
    
3. <span data-ttu-id="2bb0c-180">**[Average Contact Groups per User]** フィールドに、ユーザーごとの連絡先グループの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-180">In the **Average Contact Groups per User** field, enter the number of contact groups per user.</span></span> <span data-ttu-id="2bb0c-181">この数は、**[Average Contacts per User]** よりも小さい数にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-181">This number needs to be smaller than **Average Contacts per User**.</span></span>
    
4. <span data-ttu-id="2bb0c-182">**[Federated / Cross Pool Contacts Percentage]** フィールドで、0 から 100 までの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-182">In the **Federated / Cross Pool Contacts Percentage** field, give a number between 0 and 100.</span></span> <span data-ttu-id="2bb0c-183">この割合の連絡先が、フェデレーション ユーザーで作成されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-183">This percentage of contacts will be created with the federated users.</span></span>
    
5. <span data-ttu-id="2bb0c-184">**[Federated / Cross Pool User Prefix]** フィールドで、ローカル ユーザーの連絡先リストに追加するフェデレーション ユーザーのユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-184">In the **Federated / Cross Pool User Prefix** field, give the username for federated users that will be added to the contact lists of local users.</span></span>
    
6. <span data-ttu-id="2bb0c-185">**[Federated / Cross Pool User SIP Domain]** で、フェデレーション ユーザーの SIP ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-185">In the **Federated / Cross Pool User SIP Domain** field, give the SIP Domain Name of the federated users.</span></span>
    
7. <span data-ttu-id="2bb0c-186">**[User Creation]** タブで、情報に間違いがないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-186">In **User Creation** tab make sure the information is correct.</span></span> <span data-ttu-id="2bb0c-187">連絡先は、[User Creation] タブの各値に基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-187">Your contacts will be created from values on the User Creation tab.</span></span>
    
8. <span data-ttu-id="2bb0c-188">**[Create Contacts]** をクリックして、連絡先の作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-188">Click **Create Contacts** to begin the contact creation.</span></span> <span data-ttu-id="2bb0c-189">この処理は、数分間かかります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-189">This process can take several minutes.</span></span> <span data-ttu-id="2bb0c-190">処理の完了後、"Operation Completed Successfully" というメッセージのダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-190">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="2bb0c-191">作成した連絡先は、[User Creation] タブで作成したユーザーとしてログインすることで検証できます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-191">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2bb0c-192">連絡先の作成後、このツールによりターゲット プール内のすべてのフロント エンド サーバーが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-192">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="2bb0c-193">フロント エンド サーバーの起動には長い時間がかかることがあります (最大 2 時間)。この時間は、この操作で作成した連絡先の数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-193">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span> 
  
#### <a name="distribution-list"></a><span data-ttu-id="2bb0c-194">配布リスト</span><span class="sxs-lookup"><span data-stu-id="2bb0c-194">Distribution List</span></span>

<span data-ttu-id="2bb0c-195">Skype for Business Server 2015 Stress and Performance Tool では、Skype for Business 2015 クライアントの配布リスト (DL) 展開機能をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-195">The Skype for Business Server 2015 Stress and Performance Tool can simulate the Distribution List (DL) expansion feature in the Skype for Business 2015 client.</span></span> <span data-ttu-id="2bb0c-196">User Provisioning Tool で DL 展開を有効にしない場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-196">You can skip this step if you don't intend to enable DL expansion in the User Provisioning tool.</span></span>
  
![[Distribution List Creation] タブを表示している User Provisioning Tool。](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
<span data-ttu-id="2bb0c-198">[Distribution List] タブでは、Stress and Performance Tool で配布リスト展開機能に使用される DL を作成できます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-198">The Distribution List tab allows you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="2bb0c-199">DL の作成前に、Skype for Business Server 2015 を展開しておく必要があります。これには、ForestPrep の実行も含まれます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-199">Before creating DLs, Skype for Business Server 2015 needs to be deployed, including having run ForestPrep.</span></span> <span data-ttu-id="2bb0c-200">この操作を実行していないと、DL の属性が AD スキーマに存在しないことになるため、このツールで DL を作成できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-200">If this isn't done, the DL attributes will not exist in the AD schema, so the tool won't be able to create DLs.</span></span>
  
### <a name="to-configure-distribution-lists"></a><span data-ttu-id="2bb0c-201">配布リストを構成するには:</span><span class="sxs-lookup"><span data-stu-id="2bb0c-201">To configure Distribution Lists:</span></span>

1. <span data-ttu-id="2bb0c-202">**[Number of Distribution Lists]** フィールドに、作成する DL の合計数を指定します (最初はユーザー数の倍の値にすることをお勧めします)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-202">In the **Number of Distribution Lists** field, give the total number of DLs you want to create (The recommendation here is that you start with a value that is double the number of users you have.).</span></span>
    
2. <span data-ttu-id="2bb0c-203">**[Distribution List Prefix]** フィールドに、作成する DL のすべてに付加するプレフィックスを入力します (例: *testDL*)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-203">In the **Distribution List Prefix** field, enter a prefix that all the DLs you create will have, for example *testDL*  .</span></span> <span data-ttu-id="2bb0c-204">つまり、DL 数が 100 の場合、DL の名前は testDL0、testDL1 のようになり、最後は testDL99 になります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-204">That means, at 100 DLs, your DL names will look like: testDL0, testDL1, up to testDL99.</span></span>
    
3. <span data-ttu-id="2bb0c-205">**[Minimum Members in a Dist. List]** フィールドに、それぞれの DL に収めるユーザーの最小数を入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-205">In the **Minimum Members in a Dist. List** field, enter the minimum number of users to put in each DL.</span></span>
    
4. <span data-ttu-id="2bb0c-206">**[Maximum Members in a Dist. List]** フィールドに、それぞれの DL に追加するユーザーの最大数を入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-206">In the **Maximum Members in a Dist. List** field, enter the maximum number of users to add in each DL.</span></span>
    
#### <a name="create-distribution-lists-button"></a><span data-ttu-id="2bb0c-207">[Create Distribution Lists] ボタン</span><span class="sxs-lookup"><span data-stu-id="2bb0c-207">Create Distribution Lists button</span></span>

<span data-ttu-id="2bb0c-208">[Create Distribution Lists] ボタンをクリックすると、このツールは Active Directory を照会して、配布リストが既存のプレフィックスと数に一致するかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-208">When you click the Create Distribution Lists button, the tool queries Active Directory to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="2bb0c-209">まだ存在していない DL については、ツールによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-209">The tool creates any DLs that don't already exist.</span></span> <span data-ttu-id="2bb0c-210">この新しく作成した配布リストにメンバーを追加するときには、[User Creation] タブで指定した範囲のユーザーが選択されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-210">When adding members to these newly created Distribution Lists, it'll choose the users from the range specified on the User Creation tab.</span></span>
  
#### <a name="location-info-service-config-tab"></a><span data-ttu-id="2bb0c-211">[Location Info Service Config] タブ</span><span class="sxs-lookup"><span data-stu-id="2bb0c-211">Location Info Service Config tab</span></span>

<span data-ttu-id="2bb0c-212">Skype for Business Server 2015 Stress and Performance Tool では、場所情報サービスに対応するダミーの構成ファイルを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-212">The Skype for Business Server 2015 Stress and Performance Tool can also generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="2bb0c-213">通常、場所情報サービスがサーバーのパフォーマンスに重大な影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-213">Note that the Location Information Service typically doesn't have significant performance impact on the servers.</span></span> 
  
![[Location Info Service Config] タブを表示している User Provisioning Tool。](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
<span data-ttu-id="2bb0c-215">この機能をテストする場合は、フォームに値を入力してから [Generate LIS Config Files] ボタンをクリックします。これにより、次の .CSV ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-215">If you choose to test this feature, fill in the values in the form and click the Generate LIS Config Files button, which will create .CSV files called:</span></span>
  
- <span data-ttu-id="2bb0c-216">LIS_Subnet.csv</span><span class="sxs-lookup"><span data-stu-id="2bb0c-216">LIS_Subnet.csv</span></span>
    
- <span data-ttu-id="2bb0c-217">LIS_Switches.csv</span><span class="sxs-lookup"><span data-stu-id="2bb0c-217">LIS_Switches.csv</span></span>
    
- <span data-ttu-id="2bb0c-218">LIS_Ports.csv</span><span class="sxs-lookup"><span data-stu-id="2bb0c-218">LIS_Ports.csv</span></span>
    
- <span data-ttu-id="2bb0c-219">LIS_WAP.csv</span><span class="sxs-lookup"><span data-stu-id="2bb0c-219">LIS_WAP.csv</span></span>
    
<span data-ttu-id="2bb0c-220">これらのファイルを LIS データベースにインポートする場合は、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-220">To import these files into the LIS database use these PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="2bb0c-221">Set-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="2bb0c-221">Set-CsLisSubnet</span></span>
    
- <span data-ttu-id="2bb0c-222">Set-CsLisSwitch</span><span class="sxs-lookup"><span data-stu-id="2bb0c-222">Set-CsLisSwitch</span></span>
    
- <span data-ttu-id="2bb0c-223">Set-CsLisPort</span><span class="sxs-lookup"><span data-stu-id="2bb0c-223">Set-CsLisPort</span></span>
    
- <span data-ttu-id="2bb0c-224">Set-CsWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="2bb0c-224">Set-CsWirelessAccessPoint</span></span>
    
## <a name="configure-user-profile"></a><span data-ttu-id="2bb0c-225">ユーザー プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="2bb0c-225">Configure User Profile</span></span>
<span data-ttu-id="2bb0c-226"><a name="BKMK_UserProfile"> </a></span><span class="sxs-lookup"><span data-stu-id="2bb0c-226"><a name="BKMK_UserProfile"> </a></span></span>

<span data-ttu-id="2bb0c-227">ユーザーの作成後 (User Creation Tool を使用)、Skype for Business Server 2015 Load Configuration ツールを使用してユーザー プロファイルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-227">After your users are created (via the User Creation Tool) you can configure user profiles with the Skype for Business Server 2015 Load Configuration tool (UserProfileGenerator.exe).</span></span>
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a><span data-ttu-id="2bb0c-228">Skype for Business Server 2015 Load Configuration ツールの実行</span><span class="sxs-lookup"><span data-stu-id="2bb0c-228">Running the Skype for Business Server 2015 Load Configuration tool</span></span>

<span data-ttu-id="2bb0c-229">Load Configuration ツール (UserProfileGenerator.exe) を起動して、各タブに入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-229">Start the Load Configuration tool (UserProfileGenerator.exe) and fill in the tabs.</span></span> <span data-ttu-id="2bb0c-230">このツールでは、シミュレーションに必要なクライアント コンピューターごとにディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-230">This tool creates a directory for each of the client computers that you'll need to run your simulations.</span></span> <span data-ttu-id="2bb0c-231">それぞれのクライアント ディレクトリには、Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe) を実行するためのスクリプトが付属します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-231">Each client directory comes with a script to start the Skype for Business Server 2015 Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="2bb0c-232">次からの各セクションでは、Skype for Business Server 2015 Load Configuration ツールの各タブにあるフィールドの入力例を示します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-232">The sections below will give examples of how to fill in the fields on each tab of the Skype for Business Server 2015 Load Configuration tool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2bb0c-233">Load Configuration ツール (UserProfileGenerator.exe) で使用されるユーザー固有の値は、Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) でプールに指定した値と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-233">The user-specific values used in the Load Configuration tool (UserProfileGenerator.exe) must match the values specified in the Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) for the pool.</span></span> 
  
#### <a name="common-configuration-tab"></a><span data-ttu-id="2bb0c-234">[Common Configuration] タブ</span><span class="sxs-lookup"><span data-stu-id="2bb0c-234">Common Configuration tab</span></span>

<span data-ttu-id="2bb0c-235">Load Configuration Tool の **[Common Configuration]** タブを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-235">The **Common Configuration** tab of the Load Configuration Tool is shown below.</span></span> <span data-ttu-id="2bb0c-236">次の各手順で説明するように、[Common Configuration] タブのフィールドを入力してください。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-236">Fill in the fields of the Common Configuration tab, as described in the following steps.</span></span>
  
![[Common Configuration] タブを表示している [User Provisioning] タブ。](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. <span data-ttu-id="2bb0c-238">**[Number of Available Machines]** フィールドに、Stress and Performance Tool (LyncPerfTool.exe) の実行に使用するコンピューターの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-238">In the **Number of Available Machines** field, type the number of computers you want to use to run the Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="2bb0c-239">4500 ユーザーごとに 1 台のコンピューターを用意することをお勧めします。ただし、負荷レベルを下げる場合や、ツールで使用できる機能の一部のみを使用する場合、その数を変更してもかまいません (負荷レベルは、[General Scenarios] タブで設定します)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-239">We recommend that you have one computer for every 4500 users you'll be simulating, but that number may vary if you reduce the load level, or use only a subset of the tool's available features (Load levels are set on the General Scenarios tab).</span></span>
    
2. <span data-ttu-id="2bb0c-240">**[Prefix for User Names]** フィールドに、すべてのユーザーのユーザー名フィールドに対するプレフィックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-240">In the **Prefix for User Names** field, enter a prefix for the user name field of all users.</span></span> <span data-ttu-id="2bb0c-241">ログインするための Uniform Resource Identifier (URI) は、*ユーザーのプレフィックス[ユーザーの最初のインデックス …(ユーザー数-1)]@ユーザーのドメイン* になります (例: myUser009@Contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-241">To log in the Uniform Resource Identifier (URI) will be: *UserPrefix[User Start Index…(Number Of Users-1)]@User Domain*  , for example, myUser009@Contoso.com.</span></span>
    
3. <span data-ttu-id="2bb0c-242">**[Password for All Users]** に、ユーザーの作成時に使用したパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-242">In the **Password for All Users** field, enter the password used during creation of the users.</span></span> <span data-ttu-id="2bb0c-243">このフィールドを空白のままにすると、ユーザー名がパスワードとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-243">If you leave this field empty the username will be set as the password.</span></span>
    
4. <span data-ttu-id="2bb0c-244">**[User Start Index]** フィールドに、構成する最初のユーザーのインデックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-244">In the **User Start Index** field, enter the index of the first user to be configured.</span></span> <span data-ttu-id="2bb0c-245">それぞれの種類または負荷のレベルごとに異なる範囲を構成できますが、構成対象の範囲ごとに Load Configuration ツール (UserProfileGenerator.exe) を 1 回実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-245">You can configure different ranges for different types or levels of load, but you must run the Load Configuration tool (UserProfileGenerator.exe) once per the range you want to configure.</span></span>
    
5. <span data-ttu-id="2bb0c-246">**[Number of Users]** フィールドに、構成するユーザーの合計数を入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-246">In the **Number of Users** field, enter the total number of users you're going to configure.</span></span>
    
6. <span data-ttu-id="2bb0c-247">**[User Domain]** フィールドに、SIP URI に使用するドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-247">In the **User Domain** field, enter the domain used for the SIP URI.</span></span> <span data-ttu-id="2bb0c-248">これは、各ユーザーが Skype for Business Server 2015 フロント エンド サーバーまたは Standard Edition サーバーにログオンするための SIP URI を構築する際に使用され、[Account Domain] とは異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-248">This is used to construct the SIP URI of each user to log on to the Skype for Business Server 2015 Front End Server or Standard Edition server, and may be different from the Account Domain.</span></span>
    
7. <span data-ttu-id="2bb0c-249">**[Account Domain]** フィールドに、AD DS ドメイン ログオンを入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-249">In the **Account Domain** field, enter the AD DS domain logon.</span></span>
    
8. <span data-ttu-id="2bb0c-250">**[MPOP Percentage]** (Multiple Point of Presence のパーセンテージ) フィールドには、複数のコンピューターまたはデバイスからログオンするユーザーの割合を指定します (たとえば、10 パーセントなど)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-250">In the **MPOP Percentage** (Multiple Point of Presence percentage) field, give a value for the percentage of users that are logged on from multiple machines or devices, for example 10 percent.</span></span>
    
9. <span data-ttu-id="2bb0c-251">同時エンドポイントの最大数は、**[Sign in Per Second (per Instance)]** フィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-251">Enter the maximum number of concurrent endpoints in the **Sign in Per Second (per Instance)** field.</span></span> <span data-ttu-id="2bb0c-252">これは、ユーザーの最大ログイン数であり、毎秒 2 ログイン以下の割合 (<=2) にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-252">This is the maximum number of log ins for your users, and the recommendation is a rate of less than/equal to 2 per second (<=2).</span></span>
    
10. <span data-ttu-id="2bb0c-253">**[Access Proxy or Pool FQDN]** フィールドに、クライアントの接続先にするサーバーの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-253">In the **Access Proxy or Pool FQDN** field, enter the fully qualified domain name (FQDN) of the server you want the clients to connect to.</span></span> <span data-ttu-id="2bb0c-254">ユーザーが外部的にログオンする場合は、アクセス プロキシを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-254">If the users are logging on externally, you'll need to type the access proxy.</span></span> <span data-ttu-id="2bb0c-255">ユーザーが内部の場合は、エンタープライズ プール サーバーまたは Standard Edition サーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-255">If the users are internal, give the FQDN of their Enterprise Pool or Standard Edition server.</span></span>
    
11. <span data-ttu-id="2bb0c-256">**[Port]** フィールドに、ユーザーが SIP に使用するポートを入力します (既定値は 5061)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-256">In the **Port** field, enter the port that you want users to use for SIP (the default here is 5061).</span></span>
    
12. <span data-ttu-id="2bb0c-257">**[External Network Server Settings]** フィールドには、[Access Proxy or Pool FQDN] と **[Port]** を再度指定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-257">For the **External Network Server Settings** field, give the Access Proxy or Pool FQDN and, again, the **Port**.</span></span> <span data-ttu-id="2bb0c-258">これらの設定は、外部エンドポイントのロード シミュレーションにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-258">These settings are used only for External endpoints load simulation.</span></span>
    
#### <a name="general-scenarios-tab"></a><span data-ttu-id="2bb0c-259">[General Scenarios] タブ</span><span class="sxs-lookup"><span data-stu-id="2bb0c-259">General Scenarios tab</span></span>

![[General Scenarios] タブを表示している Load Configuration Tool。](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
<span data-ttu-id="2bb0c-261">負荷レベルとパラメーターは、実行内容を決定することで示される一般的なシナリオごとに構成することも無効のままにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-261">You can configure the load levels and parameters for each of the general scenarios offered by determining what you want to run or leave disabled.</span></span> <span data-ttu-id="2bb0c-262">次に、一般的なオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-262">Here are your general options:</span></span>
  
> [!NOTE]
> <span data-ttu-id="2bb0c-263">[Local Information Services] 以外のすべてのフィールドの負荷レベルの値は、**[Disabled]**、**[Low]**、**[Medium]**、**[High]**、または **[Custom]** です。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-263">Load level values for all fields but Local Information Services are **Disabled**, **Low**, **Medium**, **High**, or **Custom**.</span></span> <span data-ttu-id="2bb0c-264">[Disabled] 以外の設定を選択すると、クライアントごとの構成が生成されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-264">If you select any setting but Disabled, then configurations are generated for each client.</span></span> <span data-ttu-id="2bb0c-265">[High] はサーバーでサポートされる最大負荷になります。[Medium] は最大負荷の 60%、[Low] は 30% になります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-265">High results in the max supported load on the server; medium is 60% of high load; low is 30%.</span></span> 
  
- <span data-ttu-id="2bb0c-266">**Instant Messaging**: ピアツーピアおよび会議通話が含まれます。適切な負荷レベルの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-266">**Instant Messaging -** This includes peer-to-peer and conferencing; choose the appropriate value for Load Level.</span></span>
    
- <span data-ttu-id="2bb0c-267">**Audio Conferencing**: 会議通話*のみ*の負荷レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-267">**Audio Conferencing -** Choose a load level for audio conferencing *only*  .</span></span> <span data-ttu-id="2bb0c-268">ピアツーピア通話については、この後の「**Voice Scenarios**」セクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-268">Peer-to-peer calls will be tackled a little later in the **Voice Scenarios** section.</span></span> <span data-ttu-id="2bb0c-269">**[Advanced]** タブを開いて、マルチビューを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-269">Open the **Advanced** tab to enable MultiView.</span></span>
    
- <span data-ttu-id="2bb0c-270">**Application Sharing**: アプリケーション共有の負荷レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-270">**Application Sharing -** Choose a load level for application sharing.</span></span>
    
- <span data-ttu-id="2bb0c-271">**Data Collaboration**: データ コラボレーション (データ会議を含む) の負荷レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-271">**Data Collaboration -** Choose a load level for data collaboration, which includes data conferencing.</span></span>
    
- <span data-ttu-id="2bb0c-272">**Distribution List Expansion**: **[Advanced]** ボタンをクリックして、User Creation Tool (UserProvisioningTool.exe) の [DL] タブで構成したものと同じ値をフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-272">**Distribution List Expansion -** Click the **Advanced** button and fill in the field with the same values configured on the DL tab of the User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="2bb0c-273">負荷レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-273">Choose a load level.</span></span>
    
- <span data-ttu-id="2bb0c-274">**Address Book Web Query**: アドレス帳の検索サービスです。アドレス帳ファイルのダウンロードではありません。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-274">**Address Book Web Query -** This is the address book lookup service rather than the address book file download.</span></span> <span data-ttu-id="2bb0c-275">アドレス帳ファイルのダウンロードに対して有効にするには、**[Advanced]** ボタンをクリックして **[EnableABSDownload]** を True に設定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-275">If you want to enable this for address book file downloads, click the **Advanced** button and set **EnableABSDownload** to True.</span></span> <span data-ttu-id="2bb0c-276">負荷レベルの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-276">Give a value for load level.</span></span>
    
- <span data-ttu-id="2bb0c-277">**Response Group Service**: **[Advanced]** ボタンをクリックして、応答グループ サービスのエージェントのプロビジョニング時に作成した応答グループの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-277">**Response Group Service -** Click the **Advanced** button and specify the URIs of the response groups you already created when you provisioned Response Group Service agents.</span></span> <span data-ttu-id="2bb0c-278">少なくとも 1 つの応答グループを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-278">You must choose at least one response group.</span></span> <span data-ttu-id="2bb0c-279">それよりも多くの応答グループを使用する場合は、それらをセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-279">To use more, separate the response groups with semicolons.</span></span> <span data-ttu-id="2bb0c-280">実際の値になるように、**[RGSUriSuffixStartIndex]** と **[RGSUriSuffixEndIndex]** を更新します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-280">Update **RGSUriSuffixStartIndex** and **RGSUriSuffixEndIndex** to the actual values.</span></span> <span data-ttu-id="2bb0c-281">負荷レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-281">Choose a load level.</span></span>
    
- <span data-ttu-id="2bb0c-282">**Location Information Services**: [Enabled] または [Disabled] のどちらかの負荷レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-282">**Location Information Services -** Select a load level of either Enabled or Disabled.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2bb0c-283">それぞれのシナリオの横には [Advanced] ボタンがあります。また、既定の設定のバリエーションを有効にするチェックボックスのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-283">Each of the scenarios has an Advanced button located next to it, and a set of check boxes that enable variations to the default setting.</span></span> 
  
- <span data-ttu-id="2bb0c-284">*[Ad-hoc]* を選択すると、ツールによって 1 時間の間に作成される会議通話のシミュレーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-284">Choosing  *Ad-hoc*  will allow the tool to generate simulation of conferences that will be created throughout the hour.</span></span>
    
- <span data-ttu-id="2bb0c-285">*[Large Conf]* を選択すると、大規模な会議通話のシナリオがシミュレートされます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-285">Choosing  *Large Conf*  means that a Large Conference Scenario will be simulated.</span></span>
    
-  <span data-ttu-id="2bb0c-286">*[External]* では、外部ユーザーについてもシミュレートするようにツールに指示します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-286">*External*  tells the tool to also simulate external users.</span></span>
    
<span data-ttu-id="2bb0c-287">これらのボタンとチェックボックスは、それぞれのシナリオに固有な追加の値であり、Stress and Performance Tool の動作を変更して、カスタマイズを可能にします。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-287">These buttons and check boxes are extra values specific to each scenario and will change the behavior of the Stress and Performance Tool and make customization possible.</span></span>
  
<span data-ttu-id="2bb0c-288">[General Scenarios] タブの各シナリオ ([Location Information Services] を除く) では、負荷レベルの値が **[Custom]** の場合、会話レートが [Advanced] ダイアログ ボックスの対応するフィールドを使用して計算されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-288">For each scenario on the General Scenarios tab (except for Location Information Services), if the value of Load Level is **Custom**, then the conversation rate will be calculated using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="2bb0c-289">フィールド名はシナリオによって異なることがありますが、フィールドの説明には、*[NOTE This number will only be used if Custom is selected from the drop-down menu]* (注: この数値は、ドロップダウン メニューから [Custom] を選択した場合にのみ使用されます) と示されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-289">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
<span data-ttu-id="2bb0c-290">**[High]**、**[Medium]**、および **[Low]** の値は、すべてのシナリオのバランスを取ったユーザー モデルに合せてモダリティごとの会話レートを変更します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-290">The values **High**, **Medium**, and **Low**, will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="2bb0c-291">想定される使用状況とは異なるために、モダリティごとの負荷レベルを変更する必要がある場合は、[Custom] の会話レートを使用します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-291">If there's a need to change the load level per modality due to a difference in expected usage, use a Custom conversation rate.</span></span>
  
#### <a name="voice-scenarios-tab"></a><span data-ttu-id="2bb0c-292">[Voice Scenarios] タブ</span><span class="sxs-lookup"><span data-stu-id="2bb0c-292">Voice Scenarios tab</span></span>

<span data-ttu-id="2bb0c-293">このタブでは、すべての音声関連のシナリオを構成します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-293">This is the tab for configuration of all your voice-related scenarios.</span></span>
  
![Load Configuration Tool の [Voice Scenarios] タブ。](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
<span data-ttu-id="2bb0c-295">オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-295">Your options are:</span></span>
  
- <span data-ttu-id="2bb0c-296">**[VoIP]**: **[Advanced]** ボタンをクリックして、[PhoneAreaCode] と [LocationProfile (dial plan)] フィールドの値を追加します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-296">**VoIP -** Click the **Advanced** button and add values for the PhoneAreaCode and LocationProfile (dial plan) fields.</span></span> <span data-ttu-id="2bb0c-297">また、負荷レベルの値も指定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-297">You'll also give a value for Load Level.</span></span> <span data-ttu-id="2bb0c-298">[VoIP] または [UC/PSTN Gateway] の負荷レベルを有効にすると、外部通話をシミュレートするために、公衆交換電話網 (PSTN) から統合コミュニケーション (UC) への構成ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-298">If you choose a load level for VoIP or UC/PSTN Gateway enabled, then a public-switched telephone network (PSTN) to unified communications (UC) configuration file will be generated to simulate external calls.</span></span>
    
- <span data-ttu-id="2bb0c-299">**UC/PSTN Gateway**: 負荷レベルの値を選択する必要があり、[Disabled] 以外の値を選択した場合は、**[Advanced]** ボタンをクリックして PSTN 市外局番の値も指定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-299">**UC/PSTN Gateway -** You need to choose a Load Level value, and when you choose anything other than Disabled, you've also got to supply a value for PSTN area code by clicking the **Advanced** button.</span></span> <span data-ttu-id="2bb0c-300">[Mediation Server and PSTN] の下側にある **[Add]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-300">Click **Add** under the Mediation Server and PSTN.</span></span> <span data-ttu-id="2bb0c-301">その市外局番のルートが構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-301">Make sure you have a route configured for the area code.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="2bb0c-302">Skype for Business コントロール パネルまたは Skype for Business 管理シェルを使用すると、音声ルートの構成を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-302">You can use either the Skype for Business Control Panel or Skype for Business Management Shell to verify your voice route configuration.</span></span> 
  
- <span data-ttu-id="2bb0c-303">**Conferencing Attendant**: 負荷レベルの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-303">**Conferencing Attendant -** Supply a value for Load Level.</span></span> <span data-ttu-id="2bb0c-304">[Disabled] 以外の値にすると、**[Telephone Number]** フィールドが有効になります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-304">Any value other than Disabled will enable the **Telephone Number** field.</span></span> <span data-ttu-id="2bb0c-305">使用する自動応答の電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-305">Enter the phone number of the Auto Attendant you want to use.</span></span> <span data-ttu-id="2bb0c-306">**[Advanced]** をクリックして、**[LocationProfile]** フィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-306">Click **Advanced** and give a value for the **LocationProfile** field.</span></span>
    
- <span data-ttu-id="2bb0c-307">**Call Parking Service**: 負荷レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-307">**Call Parking Service -** Here, supply a Load Level.</span></span>
    
- <span data-ttu-id="2bb0c-308">**Mediation Server and PSTN**: 使用する仲介サーバーごとに独自の PSTN シミュレーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-308">**Mediation Server and PSTN -** Each Mediation Server that you want to use needs its own PSTN simulator.</span></span> <span data-ttu-id="2bb0c-309">シミュレーターに使用するクライアントを決定したら、構成した PSTN シミュレーターで、そのコンピューターに通話をルーティングするように仲介サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-309">After you've determined which client you're going to use for the simulator, configuration your Mediation Server to route calls to that computer on the PSTN Simulator you configured.</span></span> <span data-ttu-id="2bb0c-310">**[Add]** ボタンをクリックして、仲介サーバーの値を構成します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-310">Click the **Add** button to configure a value for the Mediation Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2bb0c-311">それぞれのシナリオの横には [Advanced] ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-311">Each scenario has an Advanced button located next to it.</span></span> <span data-ttu-id="2bb0c-312">[Advanced] ダイアログ ボックスには、Stress and Performance Tool の動作を変更してカスタマイズを可能にする、各シナリオに固有の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-312">Advanced dialog boxes contain settings specific to each scenario that change the behavior of the Stress and Performance Tool and enable customization.</span></span> <span data-ttu-id="2bb0c-313">> [Voice Scenarios] タブの各シナリオでは、負荷レベルの値が **[Custom]** の場合、会話レートが [Advanced] ダイアログ ボックスの対応するフィールドを使用して計算されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-313">> For each scenario on the Voice Scenarios tab, if the value of Load Level is **Custom**, then the conversation rate will be calculated by using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="2bb0c-314">フィールド名はシナリオによって異なることがありますが、フィールドの説明には、*[NOTE This number will only be used if Custom is selected from the drop-down menu]* (注: この数値は、ドロップダウン メニューから [Custom] を選択した場合にのみ使用されます) と示されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-314">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
#### <a name="web-app-tab"></a><span data-ttu-id="2bb0c-315">[Web App] タブ</span><span class="sxs-lookup"><span data-stu-id="2bb0c-315">Web App tab</span></span>

![Load Configuration Tool の [Web app] タブ。](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
<span data-ttu-id="2bb0c-317">[Web App] では、フロント エンド サーバーにインストールされた Unified Communications Web API (UCWA) サーバーによる会議シナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-317">Web App supports conferencing scenarios through the Unified Communications Web API (UCWA) server that's installed on a Front End server.</span></span> <span data-ttu-id="2bb0c-318">[Web App] タブを使用して、Web アプリ関連のすべてのシナリオを構成します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-318">Use the Web App tab to configure all web app-related scenarios.</span></span> <span data-ttu-id="2bb0c-319">オプションは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-319">Options are:</span></span>
  
- <span data-ttu-id="2bb0c-320">**General Web App Settings**: **[Additional Settings]** ボタンをクリックして、**[ReachTargetServerUrl]** をフロント エンド プール VIP のディレクトリ プール仮想 IP (VIP) に設定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-320">**General Web App Settings -** Click the **Additional Settings** button and set the **ReachTargetServerUrl** to the Directory Pool virtual IP (VIP) of the Front End pool VIP.</span></span>
    
- <span data-ttu-id="2bb0c-321">**Application Sharing**: 負荷レベルの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-321">**Application Sharing -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="2bb0c-322">**Data Collaboration**: 負荷レベルの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-322">**Data Collaboration -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="2bb0c-323">**Instant Messaging**: 負荷レベルの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-323">**Instant Messaging -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="2bb0c-324">**Voice Conferencing**: 負荷レベルの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-324">**Voice Conferencing -** Select a value for Load Level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2bb0c-325">それぞれのシナリオの横には **[Advanced]** ボタンが配置されています。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-325">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="2bb0c-326">[Advanced] ダイアログには、Stress and Performance Tool の動作を変更してカスタマイズを可能にする、各シナリオに固有の値が含まれています。> それぞれの [Web App] のシナリオについて、負荷レベルが **[Custom]** の場合は、既定値の代わりに **[ConversationsPerHour]** フィールドに指定した値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-326">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Web App scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="mobility-tab"></a><span data-ttu-id="2bb0c-327">[Mobility] タブ</span><span class="sxs-lookup"><span data-stu-id="2bb0c-327">Mobility tab</span></span>

<span data-ttu-id="2bb0c-328">このタブを使用して、モビリティ関連のシナリオのすべてを構成します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-328">Use this tab to configure all of the mobility-related scenarios.</span></span>
  
![Load Configuration Tool の [Mobility] タブ。](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
<span data-ttu-id="2bb0c-330">次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-330">The options here are:</span></span>
  
- <span data-ttu-id="2bb0c-331">**General Mobility Settings**: **[Additional Settings]** をクリックして、[UcwaTargetServerUrl] フィールドをフロント エンド プール VIP のディレクトリ プール仮想 IP (VIP) に設定します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-331">**General Mobility Settings -** Click **Additional Settings** and set the field UcwaTargetServerUrl to the Director Pool virtual IP (VIP) or the Front End pool VIP.</span></span>
    
- <span data-ttu-id="2bb0c-332">**Presence and P2P Instant Messaging/Audio**: 負荷レベルの値を選択して、モビリティのシミュレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-332">**Presence and P2P Instant Messaging/Audio -** Select a value for Load Level to enable the Mobility simulation.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2bb0c-333">それぞれのシナリオの横には **[Advanced]** ボタンが配置されています。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-333">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="2bb0c-334">[Advanced] ダイアログには、Stress and Performance Tool の動作を変更してカスタマイズを可能にする、各シナリオに固有の値が含まれています。> それぞれの [Mobility] のシナリオについて、負荷レベルが **[Custom]** の場合は、既定値の代わりに **[ConversationsPerHour]** フィールドに指定した値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-334">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Mobility scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="summary-tab"></a><span data-ttu-id="2bb0c-335">[Summary] タブ</span><span class="sxs-lookup"><span data-stu-id="2bb0c-335">Summary tab</span></span>

<span data-ttu-id="2bb0c-336">[Summary] タブには、シナリオごとに使用するユーザーが示されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-336">The Summary tab indicates which users to use for each of the scenarios.</span></span>
  
![Load Configuration Tool の [Summary] タブ。](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
<span data-ttu-id="2bb0c-338">[Summary] タブには、シナリオごとに使用するユーザーが示されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-338">The Summary tab indicates which users to use for each of the scenarios.</span></span> 
  
<span data-ttu-id="2bb0c-339">ユーザー番号の範囲は、**[Enable Custom User Range Generation]** チェック ボックスをオンにして、表内でカスタマイズするユーザー範囲があるシナリオをダブルクリックすると手動で構成できます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-339">It's possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the User Range that you want to customize.</span></span>
  
<span data-ttu-id="2bb0c-340">サインイン レートに合せて生成されたバッチ ファイルに遅延を含める場合は、**[(RunClient.bat) Add sign-in delay when starting]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-340">Check **(RunClient.bat) Add sign-in delay when starting** in order to include delays in the generated batch files to correspond to the sign-in rate.</span></span> <span data-ttu-id="2bb0c-341">これは、多数のユーザーがサインにするときにサーバーの過負荷を防止する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-341">This is useful to prevent server overload when signing in a large number of users.</span></span>
  
<span data-ttu-id="2bb0c-342">**[Generate Files]** をクリックして、構成の生成先にするフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-342">Click **Generate Files** and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="2bb0c-343">ファイルが正常に作成されると、ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-343">A dialog box will appear when your files have been successfully created.</span></span>
  
!["Load configuration files generated successfully" というメッセージ ボックス。](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a><span data-ttu-id="2bb0c-346">LyncPerfTool の実行</span><span class="sxs-lookup"><span data-stu-id="2bb0c-346">Run LyncPerfTool</span></span>
<span data-ttu-id="2bb0c-347"><a name="BKMK_RunTool"> </a></span><span class="sxs-lookup"><span data-stu-id="2bb0c-347"><a name="BKMK_RunTool"> </a></span></span>

<span data-ttu-id="2bb0c-348">Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe) の実行前に、ユーザー、連絡先、およびシナリオを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-348">You'll need to create users, contacts, and scenarios before running the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="2bb0c-349">これらの操作を実行するツールの使用方法の詳細については、この記事で前述した「[ユーザーと連絡先の作成](using-the-tool.md#BKMK_CreateUsersAndContacts)」および「[ユーザー プロファイルの構成](using-the-tool.md#BKMK_UserProfile)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-349">For details about using the tools to perform these actions, see [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) and [Configure User Profile](using-the-tool.md#BKMK_UserProfile) previously in this article.</span></span> <span data-ttu-id="2bb0c-350">これらのツールを実行することで、必須のパラメーターが含まれたバッチ ファイルの一部として、Stress and Performance Tool で実行するファイルも生成されます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-350">Running these tools will also generate a file that will run with the Stress and Performance tool as part of a batch file with the required parameters included.</span></span>
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="2bb0c-351">Skype for Business Server 2015 Stress and Performance Tool の実行</span><span class="sxs-lookup"><span data-stu-id="2bb0c-351">Running the Skype for Business Server 2015 Stress and Performance tool</span></span>

<span data-ttu-id="2bb0c-352">Load Configuration ツール (UserProfileGenerator.exe) では、パフォーマンス カウンターを登録して XML 構成ファイルを読み込むことで、Stress and Performance Tool (LyncPerfTool.exe) の実行が可能になるバッチ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-352">The Load Configuration tool (UserProfileGenerator.exe) creates a batch file that enables you to run the Stress and Performance tool (LyncPerfTool.exe) by registering performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="2bb0c-353">このバッチ ファイルでは、構成ファイルごとに LyncPerfTool.exe の 1 つのインスタンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-353">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="2bb0c-354">バッチ ファイルを実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-354">To run the batch file follow these steps:</span></span>
  
### <a name="run-the-stress-and-performance-test"></a><span data-ttu-id="2bb0c-355">Stress and Performance テストの実行</span><span class="sxs-lookup"><span data-stu-id="2bb0c-355">Run the Stress and Performance test</span></span>

1. <span data-ttu-id="2bb0c-356">各クライアント コンピューターの LyncPerfTool.exe があるディレクトリに、構成フォルダーとファイルが含まれているフォルダーをコピーします </span><span class="sxs-lookup"><span data-stu-id="2bb0c-356">Copy the folder with the configuration folders and files inside to the directory that has LyncPerfTool.exe on each client computer.</span></span> <span data-ttu-id="2bb0c-357">(たとえば、1.28_13.16.16 という名前のフォルダー内に構成ファイルを生成した場合は、そのフォルダーを LyncPerfTool.exe が含まれているフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-357">(For example, if you generated the configuration files in the folder named 1.28_13.16.16, copy that folder to the folder with LyncPerfTool.exe in it.</span></span> <span data-ttu-id="2bb0c-358">この操作をクライアントごとに実行します)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-358">Do this on each client.)</span></span>
    
2. <span data-ttu-id="2bb0c-359">クライアントのフォルダーに移動して、**RunClient** バッチ スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-359">Navigate to the client folder and run the **RunClient** batch script.</span></span> <span data-ttu-id="2bb0c-360">Windows のエクスプローラーでバッチ ファイルをダブルクリックすると、そのクライアント用のすべての構成ファイルを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-360">You can double-click the batch file in Windows Explorer and it will run all of the configuration files for that client.</span></span> <span data-ttu-id="2bb0c-361">また、次の構文を使用して、クライアントのフォルダーからスクリプトを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-361">You can also run the script from a client folder by using the following syntax:</span></span>
    
   ```PowerShell
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

<span data-ttu-id="2bb0c-362">Stress and Performance Tool を直接実行するには、コマンド プロンプトを開いて、コマンド ラインで次のコマンドを入力します (この操作を初めて実行する場合は、このトピックの注記で後述するように、パフォーマンス カウンターの登録 `regsvr32 /i /n /s LyncPerfToolPerf.dll` を実行してください)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-362">To run the Stress and Performance tool directly, open a command prompt and type the following command at the command line (and when doing this for the first time, be sure to register the performance counters  `regsvr32 /i /n /s LyncPerfToolPerf.dll`, as shown in the note later in this topic):</span></span>
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

<span data-ttu-id="2bb0c-363">ツールで構成ファイル内の値が表示されるようにするには、次に示すように、前述のコマンドに `/displayfile` パラメーターを含めます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-363">To have the tool display the values in the configuration file, include the  `/displayfile` parameter on the preceding command, so that it looks like this:</span></span>
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

<span data-ttu-id="2bb0c-364">処理を*終了*するには、Ctrl キーを押しながら C キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-364">To  *end*  the process, press Ctrl+C.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2bb0c-365">Stress and Performance Tool を直接実行する前に、コマンド `regsvr32 /i /n /s LyncPerfToolPerf.dll` でパフォーマンス カウンターを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-365">Before running the Stress and Performance tool directly, you must register the performance counters via the following command:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`</span></span>
  
> [!NOTE]
> <span data-ttu-id="2bb0c-366">起動した Stress and Performance Tool のすべてのインスタンスは、通常、1 秒間に 1 ユーザーの割合でユーザーのサインインをすぐに開始します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-366">Every instance of the Stress and Performance tool that you start will immediately begin signing in users, usually at a rate of one user per second.</span></span> 
  
<span data-ttu-id="2bb0c-367">プールに対するユーザー サインインの最大レートは、毎秒約 12 ユーザーになります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-367">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="2bb0c-368">そのため、ユーザーがサインインしている間は、同時に 12 個よりも多くの LyncPerfTool.exe のインスタンスを実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-368">This means that you shouldn't start more than 12 LyncPerfTool.exe instances at the same time while users are still signing in.</span></span> <span data-ttu-id="2bb0c-369">1 秒間に 1 ユーザーの割合で 1000 ユーザーが完全にサインインするには、約 20 分かかります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-369">One thousand users will take about 20 minutes to fully sign in at one per second.</span></span>
  
## <a name="interpreting-the-results"></a><span data-ttu-id="2bb0c-370">結果の解釈</span><span class="sxs-lookup"><span data-stu-id="2bb0c-370">Interpreting the Results</span></span>
<span data-ttu-id="2bb0c-371"><a name="BKMK_Interpret"> </a></span><span class="sxs-lookup"><span data-stu-id="2bb0c-371"><a name="BKMK_Interpret"> </a></span></span>

<span data-ttu-id="2bb0c-372">Skype for Business Server 2015 Stress and Performance Tool には、クライアントの実行内容と問題が発生しているかどうかを判断する際に役立つ多くのカウンターがあります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-372">The Skype for Business Server 2015 Stress and Performance Tool has many counters that can help you understand what the client is doing, and whether it's encountering issues.</span></span>
  
### <a name="client-counters"></a><span data-ttu-id="2bb0c-373">クライアントのカウンター</span><span class="sxs-lookup"><span data-stu-id="2bb0c-373">Client Counters</span></span>

<span data-ttu-id="2bb0c-374">実行中の LyncPerfTool.exe の各インスタンスには、カウンターの個別のインスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-374">Each instance of LyncPerfTool.exe running has a separate instance of the counters.</span></span> <span data-ttu-id="2bb0c-375">それぞれのインスタンスには、そのプロセス ID による名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-375">Each instance is named by its process ID.</span></span> <span data-ttu-id="2bb0c-376">クライアントが過負荷になると、別の問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-376">If clients are overloaded other issues can occur.</span></span> <span data-ttu-id="2bb0c-377">こうした問題を防止するには:</span><span class="sxs-lookup"><span data-stu-id="2bb0c-377">To prevent these issues:</span></span>
  
- <span data-ttu-id="2bb0c-378">クライアント コンピューターの CPU およびメモリの使用状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-378">Monitor CPU and Memory usage on the client computers.</span></span> <span data-ttu-id="2bb0c-379">CPU が継続的に 90% 以上になっている場合は、ユーザーの数を減らします。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-379">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>
    
- <span data-ttu-id="2bb0c-380">メモリ占有領域が大きいときに、ページ ファイルが不足すると問題が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-380">When the Memory footprint is high, you may run into issues if the Page File begins to run out of space.</span></span> <span data-ttu-id="2bb0c-381">コミット チャージがコンピューターの制限に達していないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-381">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="2bb0c-382">メモリ制限に達した場合は、ページ ファイルのサイズを大きくするか、ユーザーの数を減らします。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-382">If you are running into Memory limits consider increasing the Page File size or reducing the number of users.</span></span>
    
<span data-ttu-id="2bb0c-383">次に、主なパフォーマンス カウンターのリストを示します。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-383">Here's a list of key performance counters:</span></span>
  
<span data-ttu-id="2bb0c-384">**一般情報**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-384">**General Information**</span></span>

|<span data-ttu-id="2bb0c-385">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-385">**Performance Counter**</span></span>|<span data-ttu-id="2bb0c-386">**説明**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-386">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2bb0c-387">Time Spent in Minutes</span><span class="sxs-lookup"><span data-stu-id="2bb0c-387">Time Spent in Minutes</span></span>  <br/> |<span data-ttu-id="2bb0c-388">プロセスの開始からの経過時間。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-388">Time spent since the process was started.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-389">Active Endpoints</span><span class="sxs-lookup"><span data-stu-id="2bb0c-389">Active Endpoints</span></span>  <br/> |<span data-ttu-id="2bb0c-390">現在サーバーに接続しているエンドポイントの数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-390">Number of endpoints currently connected to the server.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-391">Failed Logons</span><span class="sxs-lookup"><span data-stu-id="2bb0c-391">Failed Logons</span></span>  <br/> |<span data-ttu-id="2bb0c-392">エンドポイント サインインの合計失敗数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-392">Total number of endpoint sign-in failures.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-393">Logon Attempts</span><span class="sxs-lookup"><span data-stu-id="2bb0c-393">Logon Attempts</span></span>  <br/> |<span data-ttu-id="2bb0c-394">エンドポイント サインインの合計試行数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-394">Total number of endpoint sign-in attempts.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-395">Endpoints Disconnected</span><span class="sxs-lookup"><span data-stu-id="2bb0c-395">Endpoints Disconnected</span></span>  <br/> |<span data-ttu-id="2bb0c-396">切断されたエンドポイントの合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-396">Total number of endpoints that have been disconnected.</span></span>  <br/> |
   
<span data-ttu-id="2bb0c-397">**プレゼンス情報**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-397">**Presence Information**</span></span>

|<span data-ttu-id="2bb0c-398">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-398">**Performance Counter**</span></span>|<span data-ttu-id="2bb0c-399">**説明**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-399">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2bb0c-400">SetPresence Calls</span><span class="sxs-lookup"><span data-stu-id="2bb0c-400">SetPresence Calls</span></span>  <br/> |<span data-ttu-id="2bb0c-401">プレゼンス変更の合計試行数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-401">Total number of presence change attempts.</span></span> <span data-ttu-id="2bb0c-402">プレゼンス変更のさまざまな種類については、SetPresence (プレゼンスの種類) Calls パフォーマンス カウンターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-402">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-403">NNN Responses for SetPresence</span><span class="sxs-lookup"><span data-stu-id="2bb0c-403">NNN Responses for SetPresence</span></span>  <br/> |<span data-ttu-id="2bb0c-404">サーバーから受信した nnn 応答コードの合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-404">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-405">GetPresence Calls</span><span class="sxs-lookup"><span data-stu-id="2bb0c-405">GetPresence Calls</span></span>  <br/> |<span data-ttu-id="2bb0c-406">プレゼンス取得要求の合計試行数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-406">Total number of get presence request attempts.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-407">NNN Responses for GetPresence</span><span class="sxs-lookup"><span data-stu-id="2bb0c-407">NNN Responses for GetPresence</span></span>  <br/> |<span data-ttu-id="2bb0c-408">サーバーから受信した nnn 応答コードの合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-408">Total number of nnn response codes received from the server.</span></span>  <br/> |
   
<span data-ttu-id="2bb0c-409">**アドレス帳サービスの情報**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-409">**Address Book service information**</span></span>

|<span data-ttu-id="2bb0c-410">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-410">**Performance Counter**</span></span>|<span data-ttu-id="2bb0c-411">**説明**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-411">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2bb0c-412">ABS Full/Delta File Downloads Attempted</span><span class="sxs-lookup"><span data-stu-id="2bb0c-412">ABS Full/Delta File Downloads Attempted</span></span>  <br/> |<span data-ttu-id="2bb0c-413">試行された完全または差分ファイル ダウンロード要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-413">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-414">ABS Full/Delta File Downloads Succeeded</span><span class="sxs-lookup"><span data-stu-id="2bb0c-414">ABS Full/Delta File Downloads Succeeded</span></span>  <br/> |<span data-ttu-id="2bb0c-415">試行された完全または差分ファイル ダウンロード要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-415">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-416">アドレス帳 Web クエリ サービスに関連するカウンター</span><span class="sxs-lookup"><span data-stu-id="2bb0c-416">Address Book Web Query service related counters</span></span>  <br/> |<span data-ttu-id="2bb0c-417">アドレス帳ファイルのダウンロードに関連するカウンター。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-417">Address book file download related counters.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-418">ABS WS Calls attempted</span><span class="sxs-lookup"><span data-stu-id="2bb0c-418">ABS WS Calls attempted</span></span>  <br/> |<span data-ttu-id="2bb0c-419">試行したアドレス帳 Web クエリ サービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-419">Total number of Address Book Web Query service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-420">ABS WS Calls Succeeded</span><span class="sxs-lookup"><span data-stu-id="2bb0c-420">ABS WS Calls Succeeded</span></span>  <br/> |<span data-ttu-id="2bb0c-421">成功応答コードを返したアドレス帳 Web クエリ サービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-421">Total number of Address Book Web Query service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-422">ABS WS Calls Failed</span><span class="sxs-lookup"><span data-stu-id="2bb0c-422">ABS WS Calls Failed</span></span>  <br/> |<span data-ttu-id="2bb0c-423">エラー応答コードを返したアドレス帳 Web クエリ サービスの合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-423">Total number of Address Book Web Query service requests that returned an error response code.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="2bb0c-424">このカテゴリには、アドレス帳サービス (ABS) のファイル ダウンロードとアドレス帳 Web クエリ サービスの要求を監視するために使用するカウンターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-424">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span> 
  
<span data-ttu-id="2bb0c-425">**配布リスト (DL) の情報**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-425">**Distribution List (DL) Information**</span></span>

|<span data-ttu-id="2bb0c-426">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-426">**Performance Counter**</span></span>|<span data-ttu-id="2bb0c-427">**説明**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-427">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2bb0c-428">Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="2bb0c-428">Calls Attempted</span></span>  <br/> |<span data-ttu-id="2bb0c-429">試行した配布リスト展開 (DLX) Web サービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-429">Total number of distribution list expansion (DLX) web service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-430">Calls Succeeded</span><span class="sxs-lookup"><span data-stu-id="2bb0c-430">Calls Succeeded</span></span>  <br/> |<span data-ttu-id="2bb0c-431">成功応答コードを返した DLX Web サービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-431">Total number of DLX web service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-432">Calls Failed</span><span class="sxs-lookup"><span data-stu-id="2bb0c-432">Calls Failed</span></span>  <br/> |<span data-ttu-id="2bb0c-433">エラー応答コードを返した DLX Web サービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-433">Total number of DLX web service requests that returned an error response code.</span></span>  <br/> |
   

  
> [!NOTE]
> <span data-ttu-id="2bb0c-434">次に示す各パフォーマンス カウンターは、すべての Voice over IP (VoIP) の通話数を報告します。これには、仲介サーバー、音声ビデオ会議サーバー、エッジ サーバー、応答グループ アプリケーション、および電話会議自動応答に対する通話が含まれます (これらのシナリオが有効な場合)。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-434">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span> 
  
<span data-ttu-id="2bb0c-435">**VoIP の基本情報**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-435">**VoIP Basic Information**</span></span>

|<span data-ttu-id="2bb0c-436">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-436">**Performance Counter**</span></span>|<span data-ttu-id="2bb0c-437">**説明**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-437">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2bb0c-438">Calls Active</span><span class="sxs-lookup"><span data-stu-id="2bb0c-438">Calls Active</span></span>  <br/> |<span data-ttu-id="2bb0c-439">現在進行中の着信/発信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-439">Total number of incoming/outgoing voice calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-440">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="2bb0c-440">Calls Terminated</span></span>  <br/> |<span data-ttu-id="2bb0c-441">既に終了している着信/発信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-441">Total number of incoming/outgoing voice calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-442">Calls Declined</span><span class="sxs-lookup"><span data-stu-id="2bb0c-442">Calls Declined</span></span>  <br/> |<span data-ttu-id="2bb0c-443">拒否した着信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-443">Total number of incoming voice calls declined.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-444">Incoming/Outgoing Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="2bb0c-444">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="2bb0c-445">試行した着信/発信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-445">Total number of incoming/outgoing voice calls attempted.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-446">Incoming/Outgoing Calls Established</span><span class="sxs-lookup"><span data-stu-id="2bb0c-446">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="2bb0c-447">成立した着信/発信音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-447">Total number of incoming/outgoing voice calls established.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-448">Calls Received NNN</span><span class="sxs-lookup"><span data-stu-id="2bb0c-448">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="2bb0c-449">サーバーから受信した nnn 応答コードの合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-449">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-450">VoIP Pass Rate (%)</span><span class="sxs-lookup"><span data-stu-id="2bb0c-450">VoIP Pass Rate (%)</span></span>  <br/> |<span data-ttu-id="2bb0c-451">成立した通話の合計/試行した通話の合計。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-451">Total calls established/Total calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="2bb0c-452">**応答グループ サービス通話の情報**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-452">**Response Group service Call Information**</span></span>

|<span data-ttu-id="2bb0c-453">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-453">**Performance Counter**</span></span>|<span data-ttu-id="2bb0c-454">**説明**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-454">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2bb0c-455">Calls Active</span><span class="sxs-lookup"><span data-stu-id="2bb0c-455">Calls Active</span></span>  <br/> |<span data-ttu-id="2bb0c-456">応答グループ アプリケーションへのアクティブな通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-456">Total number of active calls to the Response Group application.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-457">Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="2bb0c-457">Calls Attempted</span></span>  <br/> |<span data-ttu-id="2bb0c-458">試行した通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-458">Total number of calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="2bb0c-459">**インスタント メッセージング (IM) 通話の情報**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-459">**Instant Messaging (IM) Call Information**</span></span>

|<span data-ttu-id="2bb0c-460">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-460">**Performance Counter**</span></span>|<span data-ttu-id="2bb0c-461">**説明**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-461">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2bb0c-462">Calls Active</span><span class="sxs-lookup"><span data-stu-id="2bb0c-462">Calls Active</span></span>  <br/> |<span data-ttu-id="2bb0c-463">進行中の着信/発信インスタント メッセージング通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-463">Total number of ongoing incoming/outgoing instant messaging calls.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-464">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="2bb0c-464">Calls Terminated</span></span>  <br/> |<span data-ttu-id="2bb0c-465">既に終了している着信/発信インスタント メッセージング通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-465">Total number of incoming/outgoing instant messaging calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-466">Calls Received NNN</span><span class="sxs-lookup"><span data-stu-id="2bb0c-466">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="2bb0c-467">サーバーから受信した nnn 応答コードの合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-467">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-468">IM Messages Received/Sent</span><span class="sxs-lookup"><span data-stu-id="2bb0c-468">IM Messages Received/Sent</span></span>  <br/> |<span data-ttu-id="2bb0c-469">すべてのセッションで受信または送信したメッセージの合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-469">Total number of messages received or sent for all sessions.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-470">Incoming/Outgoing Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="2bb0c-470">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="2bb0c-471">試行した着信/発信インスタント メッセージング通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-471">Total number of incoming/outgoing instant messaging calls attempted.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-472">Incoming/Outgoing Calls Established</span><span class="sxs-lookup"><span data-stu-id="2bb0c-472">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="2bb0c-473">成立した着信/発信インスタント メッセージ通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-473">Total number of incoming/outgoing instant message calls established.</span></span>  <br/> |
   
<span data-ttu-id="2bb0c-474">**アプリケーション共有通話の情報**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-474">**App Sharing Call Information**</span></span>

|<span data-ttu-id="2bb0c-475">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-475">**Performance Counter**</span></span>|<span data-ttu-id="2bb0c-476">**説明**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-476">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2bb0c-477">Calls Active</span><span class="sxs-lookup"><span data-stu-id="2bb0c-477">Calls Active</span></span>  <br/> |<span data-ttu-id="2bb0c-478">進行中の着信/発信アプリケーション共有通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-478">Total number of ongoing incoming/outgoing application sharing calls.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-479">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="2bb0c-479">Calls Terminated</span></span>  <br/> |<span data-ttu-id="2bb0c-480">既に終了している着信/発信アプリケーション共有通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-480">Total number of incoming/outgoing application sharing calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-481">Calls Received NNN</span><span class="sxs-lookup"><span data-stu-id="2bb0c-481">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="2bb0c-482">サーバーから受信した nnn 応答コードの合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-482">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-483">Incoming/Outgoing Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="2bb0c-483">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="2bb0c-484">試行した着信/発信アプリケーション共有通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-484">Total number of incoming/outgoing application sharing calls attempted.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-485">Incoming/Outgoing Calls Established</span><span class="sxs-lookup"><span data-stu-id="2bb0c-485">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="2bb0c-486">成立した着信/発信アプリケーション共有通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-486">Total number of incoming/outgoing application sharing calls established.</span></span>  <br/> |
   
<span data-ttu-id="2bb0c-487">**CAA 通話の情報**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-487">**CAA Call Information**</span></span>

|<span data-ttu-id="2bb0c-488">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-488">**Performance Counter**</span></span>|<span data-ttu-id="2bb0c-489">**説明**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-489">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2bb0c-490">Calls Active</span><span class="sxs-lookup"><span data-stu-id="2bb0c-490">Calls Active</span></span>  <br/> |<span data-ttu-id="2bb0c-491">現在進行中の着信/発信公衆交換電話網 (PSTN) 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-491">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-492">Calls Terminated</span><span class="sxs-lookup"><span data-stu-id="2bb0c-492">Calls Terminated</span></span>  <br/> |<span data-ttu-id="2bb0c-493">既に終了している着信/発信 PSTN 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-493">Total number of incoming/outgoing PSTN calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-494">Incoming/Outgoing Calls Attempted</span><span class="sxs-lookup"><span data-stu-id="2bb0c-494">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="2bb0c-495">試行した着信/発信 PSTN 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-495">Total number of incoming/outgoing PSTN calls attempted.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-496">Incoming/Outgoing Calls Established</span><span class="sxs-lookup"><span data-stu-id="2bb0c-496">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="2bb0c-497">成立した着信/発信 PSTN 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-497">Total number of incoming/outgoing PSTN calls established.</span></span>  <br/> |
   
<span data-ttu-id="2bb0c-498">**会議通話の情報**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-498">**Conference Information**</span></span>

|<span data-ttu-id="2bb0c-499">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-499">**Performance Counter**</span></span>|<span data-ttu-id="2bb0c-500">**説明**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-500">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2bb0c-501">Active Instant Messaging Conferences</span><span class="sxs-lookup"><span data-stu-id="2bb0c-501">Active Instant Messaging Conferences</span></span>  <br/> |<span data-ttu-id="2bb0c-502">進行中のインスタント メッセージング会議通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-502">Total number of ongoing instant messaging conferences.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-503">Active Audio/Video Conferences</span><span class="sxs-lookup"><span data-stu-id="2bb0c-503">Active Audio/Video Conferences</span></span>  <br/> |<span data-ttu-id="2bb0c-504">進行中の音声ビデオ (A/V) 会議通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-504">Total number of ongoing audio/video (A/V) conferences.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-505">Active Application Sharing Conferences</span><span class="sxs-lookup"><span data-stu-id="2bb0c-505">Active Application Sharing Conferences</span></span>  <br/> |<span data-ttu-id="2bb0c-506">進行中のアプリケーション共有会議通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-506">Total number of ongoing application sharing conferences.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-507">Number of Participants</span><span class="sxs-lookup"><span data-stu-id="2bb0c-507">Number of Participants</span></span>  <br/> |<span data-ttu-id="2bb0c-508">会議通話に現在接続している参加者の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-508">Total number of participants currently connected to conferences.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-509">Conference Schedule Failure</span><span class="sxs-lookup"><span data-stu-id="2bb0c-509">Conference Schedule Failure</span></span>  <br/> |<span data-ttu-id="2bb0c-510">会議通話のスケジュールに失敗した合計回数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-510">Total number of failures while trying to schedule a conference.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-511">Join Conference Failure</span><span class="sxs-lookup"><span data-stu-id="2bb0c-511">Join Conference Failure</span></span>  <br/> |<span data-ttu-id="2bb0c-512">会議通話への接続に失敗した合計回数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-512">Total number of failures while trying to connect to a conference.</span></span>  <br/> |
   
<span data-ttu-id="2bb0c-513">**UCWA クライアントのカウンター**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-513">**UCWA Client Counters**</span></span>

|<span data-ttu-id="2bb0c-514">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-514">**Performance Counter**</span></span>|<span data-ttu-id="2bb0c-515">**説明**</span><span class="sxs-lookup"><span data-stu-id="2bb0c-515">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2bb0c-516">Total Number of IMMCU Joins Succeeded</span><span class="sxs-lookup"><span data-stu-id="2bb0c-516">Total Number of IMMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="2bb0c-517">参加したインスタント メッセージング会議通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-517">Total number of instant messaging conferences joined.</span></span>  <br/> |
|<span data-ttu-id="2bb0c-518">Total Number of DMCU Joins Succeeded</span><span class="sxs-lookup"><span data-stu-id="2bb0c-518">Total Number of DMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="2bb0c-519">参加した音声ビデオ会議通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="2bb0c-519">Total number of A/V conferences joined.</span></span>  <br/> |
   

