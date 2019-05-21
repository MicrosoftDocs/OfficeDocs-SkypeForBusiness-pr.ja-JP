---
title: Skype for Business Server 2015 のストレスとパフォーマンスのツールを使用する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: Skype for Business Server 2015 のストレスとパフォーマンスのツールを実行するには、ユーザー、連絡先、ユーザープロファイルの両方を管理し、実行するツールを構成して、ツールによって生成された出力または結果を確認できるようにする必要があります。
ms.openlocfilehash: e0cf241417272cfa16b3e332e7bafe7a112af38b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277721"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="da578-103">Skype for Business Server 2015 のストレスとパフォーマンスのツールを使用する</span><span class="sxs-lookup"><span data-stu-id="da578-103">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="da578-104">Skype for Business Server 2015 のストレスとパフォーマンスのツールを実行するには、ユーザー、連絡先、ユーザープロファイルの両方を管理し、実行するツールを構成して、ツールによって生成された出力または結果を確認できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="da578-104">To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.</span></span>
  
<span data-ttu-id="da578-105">Skype for Business Server 2015 のストレスとパフォーマンスツールの実行には、次の4つの領域が含まれます (実行可能ファイルは LyncPerfTool)。</span><span class="sxs-lookup"><span data-stu-id="da578-105">There are four areas involved with running the Skype for Business Server 2015 Stress and Performance Tool (the executable is LyncPerfTool.exe):</span></span>
  
- [<span data-ttu-id="da578-106">ユーザーと連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="da578-106">Create Users and Contacts</span></span>](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [<span data-ttu-id="da578-107">ユーザープロファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="da578-107">Configure User Profile</span></span>](using-the-tool.md#BKMK_UserProfile)
    
- [<span data-ttu-id="da578-108">LyncPerfTool を実行する</span><span class="sxs-lookup"><span data-stu-id="da578-108">Run LyncPerfTool</span></span>](using-the-tool.md#BKMK_RunTool)
    
- [<span data-ttu-id="da578-109">結果を解釈する</span><span class="sxs-lookup"><span data-stu-id="da578-109">Interpreting the Results</span></span>](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a><span data-ttu-id="da578-110">ユーザーと連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="da578-110">Create Users and Contacts</span></span>
<span data-ttu-id="da578-111"><a name="BKMK_CreateUsersAndContacts"> </a></span><span class="sxs-lookup"><span data-stu-id="da578-111"></span></span>

<span data-ttu-id="da578-112">ストレスとパフォーマンスのテストのためにユーザーと連絡先を作成するには、Skype for Business Server 2015 (SB 2015) ユーザープロビジョニングツール (Userprovisioning Tool) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da578-112">You need to use the Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts for your stress and performance testing.</span></span>
  
<span data-ttu-id="da578-113">これは、トピックを読むときに役立つ可能性がある有用な用語の一覧です。</span><span class="sxs-lookup"><span data-stu-id="da578-113">This is a list of helpful terms that might be useful as you read through the topics:</span></span>
  
- <span data-ttu-id="da578-114">**組織単位**-Active Directory ドメインサービス (AD DS) 組織単位 (OU)。</span><span class="sxs-lookup"><span data-stu-id="da578-114">**Organizational Unit** - The Active Directory Domain Services (AD DS) organizational unit (OU).</span></span>
    
- <span data-ttu-id="da578-115">**フェデレーション/クロスプール**-他のインスタントメッセージング (IM) サービスからユーザーと通信できるユーザー。</span><span class="sxs-lookup"><span data-stu-id="da578-115">**Federated / Cross Pool** - Users who can communicate with users from other Instant Messaging (IM) services.</span></span>
    
- <span data-ttu-id="da578-116">**配布リスト**または dl。</span><span class="sxs-lookup"><span data-stu-id="da578-116">**Distribution Lists** - Or DLs.</span></span> <span data-ttu-id="da578-117">Ad ds ユーザーの一覧を含む AD DS のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="da578-117">These are objects in AD DS that contain a list of AD DS users.</span></span> <span data-ttu-id="da578-118">複数のユーザーによるコミュニケーションを容易にするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="da578-118">They're used to facilitate communications across groups of people.</span></span>
    
- <span data-ttu-id="da578-119">**位置情報サービス**-Skype For business Server 2015 サービスが有効になっていて、スマートフォンで構成されている場合は、拡張 911 (E911) サービスの物理的な場所を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="da578-119">**Location Info Service** - The Skype for Business Server 2015 service that, when it's enabled and configured per phone, allows for the retrieval of physical location for Enhanced 911 (E911) services.</span></span>
    
- <span data-ttu-id="da578-120">**米国の電話番号**-ユーザーに割り当てられている電話番号と、逆引き番号参照 (RNL) での着信および発信通話のルーティングに使用される SIP URI。</span><span class="sxs-lookup"><span data-stu-id="da578-120">**U.S. Phone Numbers** - Phone numbers assigned to user in addition to the SIP URI that's used for routing inbound and outbound calls in Reverse Number Lookup (RNL).</span></span>
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="da578-121">Userプロビジョニングツールを使用してユーザーと連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="da578-121">Create Users and Contacts by using UserProvisioningTool.exe</span></span>

> [!NOTE]
> <span data-ttu-id="da578-122">開始する前に、このツールを実行するには、ドメイン管理者セキュリティグループのメンバーとしてログインしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="da578-122">Before you even begin, be absolutely sure you're logged in as a member of the Domain Admins security group to run this tool.</span></span> <span data-ttu-id="da578-123">Active Directory ユーザーを作成しようとしているため、この操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="da578-123">You need to do this, because you're going to be creating Active Directory users.</span></span> 
  
<span data-ttu-id="da578-124">ロードシミュレーション用にユーザーと連絡先を作成するには、Skype for Business Server ユーザープロビジョニングツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da578-124">You have to use the Skype for Business Server User Provisioning Tool to create users and contacts for load simulation.</span></span>
  
<span data-ttu-id="da578-125">Skype for business **server のユーザープロビジョニングツール**は、 **Skype for Business server のストレスとパフォーマンスツール**パッケージと共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="da578-125">The **Skype for Business Server User Provisioning Tool** is installed with the **Skype for Business Server Stress and Performance Tool** package.</span></span> <span data-ttu-id="da578-126">パッケージインストーラー (CapacityPlanningTool) が、フロントエンドサーバーまたはテストする Standard Edition サーバーで実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da578-126">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server you intend to test.</span></span>
  
<span data-ttu-id="da578-127">Skype for Business Server ユーザープロビジョニングツールを起動するには、フロントエンドサーバーまたは Standard Edition サーバーのファイル Userprovisioning Tool (% LyncStressAndPerfTool ディレクトリ% \ LyncStress) を実行します。</span><span class="sxs-lookup"><span data-stu-id="da578-127">You can start the Skype for Business Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="da578-128">多数のユーザー (たとえば、1万など) を作成する場合は、User指定ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="da578-128">When you create a large number of users (for example, 10,000 or more), run the UserProvisioningTool.exe.</span></span> <span data-ttu-id="da578-129">この操作は、ツールが*新しい*広告ユーザーを作成して構成するために必要です。</span><span class="sxs-lookup"><span data-stu-id="da578-129">You'll need to do this because the tool will be creating and configuring  *new*  AD users.</span></span>
  
<span data-ttu-id="da578-130">ユーザープロビジョニングツールが開いたら、[構成] をクリックし、読み込み構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="da578-130">When the User Provisioning Tool opens, click Configuration and select the Load Configuration.</span></span> 
  
<span data-ttu-id="da578-131">ユーザーと連絡先の構成を開始するには、パッケージに含まれている既定のファイル ("SampleData" と呼ばれます) を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="da578-131">To begin configuring users and contacts, load the default file included with the package, called "SampleData.xml".</span></span> <span data-ttu-id="da578-132">これにより、展開に関連するように変更する必要があるサンプルデータを含むフィールドが事前に設定されます。</span><span class="sxs-lookup"><span data-stu-id="da578-132">This will prepopulate fields with sample data that you'll need to change to make it relevant for your deployment.</span></span>
  
<span data-ttu-id="da578-133">既にカスタマイズした設定が含まれている構成済みの XML ファイルがある場合は、そのファイルを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="da578-133">If you have a preconfigured XML file that already contains your customized settings, you can load that file instead.</span></span> <span data-ttu-id="da578-134">以下のセクションで説明するように、ユーザープロビジョニングツールのフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-134">Fill in the fields in the User Provisioning Tool, as described in the sections below.</span></span>
  
### <a name="to-configure-server-options"></a><span data-ttu-id="da578-135">サーバーオプションを構成するには:</span><span class="sxs-lookup"><span data-stu-id="da578-135">To configure server options:</span></span>

1. <span data-ttu-id="da578-136">[**フロントエンドプールの fqdn** ] フィールドに、Standard Edition サーバーの完全修飾ドメイン名 (fqdn)、またはユーザーをホストするフロントエンドプールを入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-136">In the **Front End Pool FQDN** field, type the fully qualified domain name (FQDN) of the Standard Edition server, or the Front End pool where you want to host the users.</span></span>
    
2. <span data-ttu-id="da578-137">[**ユーザー名プレフィックス**] フィールドに、テスト目的 ("TestUser" など) のユーザー名の bust に使用するプレフィックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-137">In the **User Name Prefix** field, type a prefix that you want to use to bust your user names for testing purposes (such as "TestUser").</span></span>
    
3. <span data-ttu-id="da578-138">[**パスワード**] フィールドに、すべてのテストユーザーアカウントで使用されるパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-138">In the **Password** field, type a password that will be used across all the test user accounts.</span></span>
    
4. <span data-ttu-id="da578-139">[ **Account domain** ] フィールドに、現在の AD ドメインのドメイン名 (テストユーザーを作成するドメイン名) を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-139">In the **Account Domain** field, type the domain name of your current AD domain (the one in which you want to create your test users).</span></span>
    
5. <span data-ttu-id="da578-140">[**組織単位**] フィールドに、これらのテストユーザーを作成する広告ドメインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-140">In the **Organizational Unit** field, type the name of the AD domain where you want to create these test users.</span></span> <span data-ttu-id="da578-141">(OU がまだ存在しない場合は、自動的に作成されます)。</span><span class="sxs-lookup"><span data-stu-id="da578-141">(If the OU doesn't already exist, it'll be created for you).</span></span>
    
6. <span data-ttu-id="da578-142">[**電話の市外局番**] フィールドに、すべてのテストユーザーアカウントで使用する3桁の市外局番を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-142">In the **Phone Area Code** field, type the three-digit area code to be used across all test user accounts.</span></span> <span data-ttu-id="da578-143">選択した市外局番が広告の他のユーザーの市外局番と競合していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="da578-143">Make certain that the area code you chose doesn't conflict with other users' area codes in AD.</span></span>
    
7. <span data-ttu-id="da578-144">エンタープライズ Voip のテストユーザーを有効にする場合は、[**音声を有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="da578-144">Click to select the **Voice Enabled** check box, if you want to enable the test users for Enterprise Voice.</span></span>
    
8. <span data-ttu-id="da578-145">[**ユーザー**数] フィールドで、作成するテストユーザーの合計数を指定します。</span><span class="sxs-lookup"><span data-stu-id="da578-145">In the **Number of Users** field, give the total number of test users you want to create.</span></span>
    
9. <span data-ttu-id="da578-146">[**開始インデックス**] フィールドで、ユーザー名のプレフィックスのサフィックスとして使用される開始番号を指定します (たとえば、プレフィックスは "TestUser"、次の例では、最初の名前は "0" になります)。</span><span class="sxs-lookup"><span data-stu-id="da578-146">In the **Start Index** field, give the starting number that'll be used as a suffix to the user name prefix (for example, the prefix is "TestUser", and the first name will end in "0" in the example below.)</span></span>
    
     ![[User Creation] タブを表示している User Provisioning Tool](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a><span data-ttu-id="da578-148">[ユーザーの作成] ボタン</span><span class="sxs-lookup"><span data-stu-id="da578-148">Create Users button</span></span>

<span data-ttu-id="da578-149">[**ユーザーの作成**] ボタンをクリックすると、入力した入力パラメーターが検証されます。</span><span class="sxs-lookup"><span data-stu-id="da578-149">When you click on the **Create Users** button, the input parameters you've entered are validated.</span></span> <span data-ttu-id="da578-150">検証エラーがある場合は、それらを修正するように求められます。</span><span class="sxs-lookup"><span data-stu-id="da578-150">If there are any validation errors, you'll be prompted to fix them.</span></span> <span data-ttu-id="da578-151">または、すべての値が正しい場合は、ユーザーは AD に (指定した OU で) 表示されます。</span><span class="sxs-lookup"><span data-stu-id="da578-151">Or, if all the values are correct, users will start appearing in AD (in whichever OU you specified).</span></span> <span data-ttu-id="da578-152">ツールの実行中、ツールの下部に進行状況バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da578-152">You'll see a progress bar at the bottom of the tool as it runs.</span></span> <span data-ttu-id="da578-153">進行状況バーがアクティブになっている間はアプリケーションを閉じません。</span><span class="sxs-lookup"><span data-stu-id="da578-153">Don't close the application while the progress bar is active.</span></span>
  
<span data-ttu-id="da578-154">ユーザーの作成には時間がかかるため、適切な計画を立ててください。</span><span class="sxs-lookup"><span data-stu-id="da578-154">User creation takes time, so please plan accordingly.</span></span> <span data-ttu-id="da578-155">このプロセスでは、数人のユーザー、および多数のユーザーに対して数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="da578-155">This process can take anywhere from several minutes for a few users, to a few hours for a large number of users.</span></span>
  
<span data-ttu-id="da578-156">テスト環境の AD ドメインコントローラーにアクセスできない場合でも、指定したユーザーの範囲のいずれかのユーザーとしてログインすることで、ユーザーの作成を検証することができます。</span><span class="sxs-lookup"><span data-stu-id="da578-156">If you don't have access to the AD Domain Controller in your test environment, you can still validate user creation by logging in as one of the users in the range of users you specified to create.</span></span> <span data-ttu-id="da578-157">@SipDomain と共に、プレフィックスとサフィックスを使用して、ユーザー名と同じようにしてください。</span><span class="sxs-lookup"><span data-stu-id="da578-157">Remember to use the prefix, and the suffix, along with the @sipDomain as the username.</span></span> <span data-ttu-id="da578-158"><em>TestUser20@contoso.net</em>の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da578-158">Here is an example:  <em>TestUser20@contoso.net</em>  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="da578-159">ユーザーが既に存在している場合は、[ユーザーの作成] をクリックすると、構成の変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="da578-159">If the users already exist, clicking the Create Users button will update them with any configuration changes.</span></span> 
  
#### <a name="delete-users-button"></a><span data-ttu-id="da578-160">[ユーザーの削除] ボタン</span><span class="sxs-lookup"><span data-stu-id="da578-160">Delete Users button</span></span>

<span data-ttu-id="da578-161">[**ユーザーの削除**] ボタンをクリックすると、タブの入力パラメーターが検証されます。</span><span class="sxs-lookup"><span data-stu-id="da578-161">When you click on the **Delete Users** button, the tab's input parameters will be validated.</span></span> <span data-ttu-id="da578-162">検証エラーがある場合は、それらを修正するように求められ、入力値が正しく設定されている場合は、指定したテストユーザーが無効になり、Active Directory から削除されます。</span><span class="sxs-lookup"><span data-stu-id="da578-162">If there are validation errors, you'll be prompted to fix them, and if the input values are correct, the specified test users will be disabled and deleted from Active Directory.</span></span> <span data-ttu-id="da578-163">この場合も、このタブの下部に進行状況バーが表示され、進行状況バーがアクティブな間はアプリケーションを閉じないでください。</span><span class="sxs-lookup"><span data-stu-id="da578-163">Again, a progress bar will appear on the bottom of this tab, and you shouldn't close the application while the progress bar is active.</span></span>
  
> [!NOTE]
> <span data-ttu-id="da578-164">米国で書式設定された電話番号のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="da578-164">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="da578-165">電話番号は常にユーザーに割り当てられます。また、User/Tool によって作成されたすべてのユーザーは、既定でエンタープライズ Voip が有効になります。</span><span class="sxs-lookup"><span data-stu-id="da578-165">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice by default.</span></span> <span data-ttu-id="da578-166">電話会議の自動応答や UC-PSTN 通話など、電話番号を使用するシナリオでは、この電話番号を使用して、通話を適切にルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="da578-166">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="da578-167">このため、*すべてのユーザー*は固有の*電話番号*を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="da578-167">For this reason,  *every user*  must have a *unique phone number*  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="da578-168">**ユーザーを2回作成する必要がある場合は、別の市外局番を使用しない限り、または以前のユーザーが無効になっている場合は、このコマンドが失敗します。**</span><span class="sxs-lookup"><span data-stu-id="da578-168">**If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the Disable-CsUser cmdlet.**</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="da578-169">連絡先を作成する前に、まずユーザーの複製を完了する必要があります (これは [ユーザー] タブから行われます)。</span><span class="sxs-lookup"><span data-stu-id="da578-169">Before you create contacts, you first need to complete user replication (which is done from the Users tab).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="da578-170">ユーザーを作成したばかりの場合は、Skype for Business Server のレプリケーションが完了するのを待ってから、データベースのユーザーアカウントを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da578-170">If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="da578-171">**ユーザーが複製を完了していない場合は、エラーが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="da578-171">**If the users haven't finished replicating, you'll see an error.**</span></span> <span data-ttu-id="da578-172">Skype for Business Server 2015 のフロントエンドサービスが開始された場合、または指定した合計数の最後のユーザーに対して、ユーザーの取得が完了した場合に、ユーザーが複製を完了した日時がわかります。</span><span class="sxs-lookup"><span data-stu-id="da578-172">You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.</span></span>
  
#### <a name="contacts-creation-tab"></a><span data-ttu-id="da578-173">[連絡先の作成] タブ</span><span class="sxs-lookup"><span data-stu-id="da578-173">Contacts Creation tab</span></span>

<span data-ttu-id="da578-174">このタブでは、ユーザーのテスト用の連絡先情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="da578-174">This tab lets you give users' contacts details for your testing.</span></span>
  
![[Contents Creation] タブを表示している User Provisioning Tool](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a><span data-ttu-id="da578-176">ユーザーの連絡先を構成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="da578-176">To configure users' contacts, do the following:</span></span>

1. <span data-ttu-id="da578-177">[**ユーザーごとの連絡先の平均**] フィールドに、各ユーザーの連絡先リストに入力する連絡先の平均数を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-177">In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.</span></span>
    
2. <span data-ttu-id="da578-178">すべてのユーザーに対して同数の連絡先を作成する場合は、[**固定**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="da578-178">Select the **Fixed** check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="da578-179">ユーザー用に作成された連絡先の数を変更する場合は、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="da578-179">If you want to vary the number of contacts created for users, clear that check box.</span></span>
    
3. <span data-ttu-id="da578-180">[**ユーザーごとの平均連絡先グループ**] フィールドに、ユーザーごとの連絡先グループの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-180">In the **Average Contact Groups per User** field, enter the number of contact groups per user.</span></span> <span data-ttu-id="da578-181">この数値は、**ユーザーごとの平均連絡先**よりも小さい必要があります。</span><span class="sxs-lookup"><span data-stu-id="da578-181">This number needs to be smaller than **Average Contacts per User**.</span></span>
    
4. <span data-ttu-id="da578-182">[**フェデレーション/クロスプールの連絡先割合**] フィールドに、0から100までの数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-182">In the **Federated / Cross Pool Contacts Percentage** field, give a number between 0 and 100.</span></span> <span data-ttu-id="da578-183">この割合の連絡先は、フェデレーションされたユーザーと共に作成されます。</span><span class="sxs-lookup"><span data-stu-id="da578-183">This percentage of contacts will be created with the federated users.</span></span>
    
5. <span data-ttu-id="da578-184">[**フェデレーション/クロスプールユーザープレフィックス**] フィールドに、ローカルユーザーの連絡先リストに追加されるフェデレーションユーザーのユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="da578-184">In the **Federated / Cross Pool User Prefix** field, give the username for federated users that will be added to the contact lists of local users.</span></span>
    
6. <span data-ttu-id="da578-185">[**フェデレーション/クロスプールユーザー Sip ドメイン**] フィールドで、フェデレーションされたユーザーの SIP ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="da578-185">In the **Federated / Cross Pool User SIP Domain** field, give the SIP Domain Name of the federated users.</span></span>
    
7. <span data-ttu-id="da578-186">[**ユーザー作成**] タブで、情報が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="da578-186">In **User Creation** tab make sure the information is correct.</span></span> <span data-ttu-id="da578-187">連絡先は、[ユーザー作成] タブの値から作成されます。</span><span class="sxs-lookup"><span data-stu-id="da578-187">Your contacts will be created from values on the User Creation tab.</span></span>
    
8. <span data-ttu-id="da578-188">[**連絡先の作成**] をクリックして、連絡先の作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="da578-188">Click **Create Contacts** to begin the contact creation.</span></span> <span data-ttu-id="da578-189">このプロセスは数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="da578-189">This process can take several minutes.</span></span> <span data-ttu-id="da578-190">完了すると、"操作が正常に完了しました" というメッセージが表示されたダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da578-190">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="da578-191">[ユーザー作成] タブから作成されたユーザーとしてログオンして作成された連絡先を確認できます。</span><span class="sxs-lookup"><span data-stu-id="da578-191">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
> [!NOTE]
> <span data-ttu-id="da578-192">このツールは、連絡先を作成した後、ターゲットプール内のすべてのフロントエンドサーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="da578-192">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="da578-193">この操作によって作成された連絡先の数によっては、フロントエンドサーバーが起動するまでに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="da578-193">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span> 
  
#### <a name="distribution-list"></a><span data-ttu-id="da578-194">配布リスト</span><span class="sxs-lookup"><span data-stu-id="da578-194">Distribution List</span></span>

<span data-ttu-id="da578-195">Skype for Business Server 2015 ストレスおよびパフォーマンスツールは、Skype for Business 2015 クライアントで配布リスト (DL) の展開機能をシミュレートすることができます。</span><span class="sxs-lookup"><span data-stu-id="da578-195">The Skype for Business Server 2015 Stress and Performance Tool can simulate the Distribution List (DL) expansion feature in the Skype for Business 2015 client.</span></span> <span data-ttu-id="da578-196">ユーザープロビジョニングツールで DL の展開を有効にしない場合は、この手順をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="da578-196">You can skip this step if you don't intend to enable DL expansion in the User Provisioning tool.</span></span>
  
![[Distribution List Creation] タブを表示している User Provisioning Tool](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
<span data-ttu-id="da578-198">[配布リスト] タブでは、ストレスとパフォーマンスツールが配布リストの展開機能に使用する Dl を作成できます。</span><span class="sxs-lookup"><span data-stu-id="da578-198">The Distribution List tab allows you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="da578-199">DLs を作成する前に、ForestPrep 実行を含む、Skype for Business Server 2015 を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da578-199">Before creating DLs, Skype for Business Server 2015 needs to be deployed, including having run ForestPrep.</span></span> <span data-ttu-id="da578-200">これを行わない場合、DL 属性は AD スキーマには存在しないため、このツールでは Dl を作成できません。</span><span class="sxs-lookup"><span data-stu-id="da578-200">If this isn't done, the DL attributes will not exist in the AD schema, so the tool won't be able to create DLs.</span></span>
  
### <a name="to-configure-distribution-lists"></a><span data-ttu-id="da578-201">配布リストを構成するには:</span><span class="sxs-lookup"><span data-stu-id="da578-201">To configure Distribution Lists:</span></span>

1. <span data-ttu-id="da578-202">[**配布リストの数**] フィールドに、作成する dl の合計数を指定します (ここでは、ユーザーの数が2倍の値から開始することをお勧めします)。</span><span class="sxs-lookup"><span data-stu-id="da578-202">In the **Number of Distribution Lists** field, give the total number of DLs you want to create (The recommendation here is that you start with a value that is double the number of users you have.).</span></span>
    
2. <span data-ttu-id="da578-203">[**配布リストのプレフィックス**] フィールドに、作成するすべての dl に含まれるプレフィックス ( *testdl*など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-203">In the **Distribution List Prefix** field, enter a prefix that all the DLs you create will have, for example *testDL*  .</span></span> <span data-ttu-id="da578-204">つまり、100 Dl では、DL 名は次のようになります。 testDL0、testDL1、testDL99 になります。</span><span class="sxs-lookup"><span data-stu-id="da578-204">That means, at 100 DLs, your DL names will look like: testDL0, testDL1, up to testDL99.</span></span>
    
3. <span data-ttu-id="da578-205">[ **Dist. リストの最小メンバー**数] フィールドに、各 DL に含めるユーザーの最小数を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-205">In the **Minimum Members in a Dist. List** field, enter the minimum number of users to put in each DL.</span></span>
    
4. <span data-ttu-id="da578-206">[ **Dist. リストの最大メンバー**数] フィールドに、各 DL に追加するユーザーの最大数を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-206">In the **Maximum Members in a Dist. List** field, enter the maximum number of users to add in each DL.</span></span>
    
#### <a name="create-distribution-lists-button"></a><span data-ttu-id="da578-207">[配布リストの作成] ボタン</span><span class="sxs-lookup"><span data-stu-id="da578-207">Create Distribution Lists button</span></span>

<span data-ttu-id="da578-208">[配布リストの作成] をクリックすると、ツールによって Active Directory が照会され、プレフィックスと番号が一致する配布リストが既に存在するかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="da578-208">When you click the Create Distribution Lists button, the tool queries Active Directory to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="da578-209">このツールでは、まだ存在していない Dl が作成されます。</span><span class="sxs-lookup"><span data-stu-id="da578-209">The tool creates any DLs that don't already exist.</span></span> <span data-ttu-id="da578-210">新しく作成された配布リストにメンバーを追加するときは、[ユーザー作成] タブで指定された範囲からユーザーを選びます。</span><span class="sxs-lookup"><span data-stu-id="da578-210">When adding members to these newly created Distribution Lists, it'll choose the users from the range specified on the User Creation tab.</span></span>
  
#### <a name="location-info-service-config-tab"></a><span data-ttu-id="da578-211">[所在地情報] サービス構成タブ</span><span class="sxs-lookup"><span data-stu-id="da578-211">Location Info Service Config tab</span></span>

<span data-ttu-id="da578-212">Skype for Business Server 2015 ストレスおよびパフォーマンスツールは、位置情報サービスのためのダミー構成ファイルを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="da578-212">The Skype for Business Server 2015 Stress and Performance Tool can also generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="da578-213">通常、位置情報サービスは、サーバーのパフォーマンスに大きな影響を与えないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="da578-213">Note that the Location Information Service typically doesn't have significant performance impact on the servers.</span></span> 
  
![[Location Info Service Config] タブを表示している User Provisioning Tool](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
<span data-ttu-id="da578-215">この機能をテストする場合は、フォームの値を入力して、[LIS 構成ファイルの生成] ボタンをクリックします。これは作成されます。CSV ファイル:</span><span class="sxs-lookup"><span data-stu-id="da578-215">If you choose to test this feature, fill in the values in the form and click the Generate LIS Config Files button, which will create .CSV files called:</span></span>
  
- <span data-ttu-id="da578-216">LIS_Subnet</span><span class="sxs-lookup"><span data-stu-id="da578-216">LIS_Subnet.csv</span></span>
    
- <span data-ttu-id="da578-217">LIS_Switches</span><span class="sxs-lookup"><span data-stu-id="da578-217">LIS_Switches.csv</span></span>
    
- <span data-ttu-id="da578-218">LIS_Ports</span><span class="sxs-lookup"><span data-stu-id="da578-218">LIS_Ports.csv</span></span>
    
- <span data-ttu-id="da578-219">LIS_WAP</span><span class="sxs-lookup"><span data-stu-id="da578-219">LIS_WAP.csv</span></span>
    
<span data-ttu-id="da578-220">これらのファイルを LIS データベースにインポートするには、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="da578-220">To import these files into the LIS database use these PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="da578-221">Set-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="da578-221">Set-CsLisSubnet</span></span>
    
- <span data-ttu-id="da578-222">Set-CsLisSwitch</span><span class="sxs-lookup"><span data-stu-id="da578-222">Set-CsLisSwitch</span></span>
    
- <span data-ttu-id="da578-223">Set-CsLisPort</span><span class="sxs-lookup"><span data-stu-id="da578-223">Set-CsLisPort</span></span>
    
- <span data-ttu-id="da578-224">Set-CsWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="da578-224">Set-CsWirelessAccessPoint</span></span>
    
## <a name="configure-user-profile"></a><span data-ttu-id="da578-225">ユーザープロファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="da578-225">Configure User Profile</span></span>
<span data-ttu-id="da578-226"><a name="BKMK_UserProfile"> </a></span><span class="sxs-lookup"><span data-stu-id="da578-226"></span></span>

<span data-ttu-id="da578-227">ユーザー作成ツールを使用してユーザーを作成した後、Skype for Business Server 2015 ロード構成ツール (UserProfileGenerator) を使用して、ユーザープロファイルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="da578-227">After your users are created (via the User Creation Tool) you can configure user profiles with the Skype for Business Server 2015 Load Configuration tool (UserProfileGenerator.exe).</span></span>
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a><span data-ttu-id="da578-228">Skype for Business Server 2015 のロード構成ツールの実行</span><span class="sxs-lookup"><span data-stu-id="da578-228">Running the Skype for Business Server 2015 Load Configuration tool</span></span>

<span data-ttu-id="da578-229">ロード構成ツール (UserProfileGenerator) を起動し、タブを入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-229">Start the Load Configuration tool (UserProfileGenerator.exe) and fill in the tabs.</span></span> <span data-ttu-id="da578-230">このツールは、シミュレーションの実行に必要なクライアントコンピューターごとにディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="da578-230">This tool creates a directory for each of the client computers that you'll need to run your simulations.</span></span> <span data-ttu-id="da578-231">各クライアントディレクトリには、Skype for Business Server 2015 応力とパフォーマンスツール (LyncPerfTool) を起動するためのスクリプトが用意されています。</span><span class="sxs-lookup"><span data-stu-id="da578-231">Each client directory comes with a script to start the Skype for Business Server 2015 Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="da578-232">以下のセクションでは、Skype for Business Server 2015 のロード構成ツールの各タブのフィールドに入力する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="da578-232">The sections below will give examples of how to fill in the fields on each tab of the Skype for Business Server 2015 Load Configuration tool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="da578-233">ロード構成ツール (UserProfileGenerator) で使用されるユーザー固有の値は、プールの Skype for Business Server 2015 ユーザー作成ツール (Userプロビジョニングツール) で指定した値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da578-233">The user-specific values used in the Load Configuration tool (UserProfileGenerator.exe) must match the values specified in the Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) for the pool.</span></span> 
  
#### <a name="common-configuration-tab"></a><span data-ttu-id="da578-234">[共通の構成] タブ</span><span class="sxs-lookup"><span data-stu-id="da578-234">Common Configuration tab</span></span>

<span data-ttu-id="da578-235">ロード構成ツールの [**共通の構成**] タブを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="da578-235">The **Common Configuration** tab of the Load Configuration Tool is shown below.</span></span> <span data-ttu-id="da578-236">次の手順で説明するように、[共通の構成] タブのフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-236">Fill in the fields of the Common Configuration tab, as described in the following steps.</span></span>
  
![[Common Configuration] タブを表示している [User Provisioning] タブ](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. <span data-ttu-id="da578-238">[**使用可能なマシン数**] フィールドに、ストレスとパフォーマンスツール (LyncPerfTool) を実行するために使用するコンピューターの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-238">In the **Number of Available Machines** field, type the number of computers you want to use to run the Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="da578-239">シミュレートするすべての4500ユーザーに1台のコンピューターを用意することをお勧めしますが、この数値は、読み込みレベルを下げるか、ツールの使用可能な機能の一部のみを使用することをお勧めします (読み込みレベルは、[一般的なシナリオ] タブで設定されています)。</span><span class="sxs-lookup"><span data-stu-id="da578-239">We recommend that you have one computer for every 4500 users you'll be simulating, but that number may vary if you reduce the load level, or use only a subset of the tool's available features (Load levels are set on the General Scenarios tab).</span></span>
    
2. <span data-ttu-id="da578-240">[**ユーザー名のプレフィックス**] フィールドに、すべてのユーザーの [ユーザー名] フィールドのプレフィックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-240">In the **Prefix for User Names** field, enter a prefix for the user name field of all users.</span></span> <span data-ttu-id="da578-241">Uniform Resource Identifier (URI) をログインするには、次のようにします。 *Userprefix [ユーザーの開始インデックス...](ユーザー数-1)]@User ドメイン*(たとえば、myUser009@Contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="da578-241">To log in the Uniform Resource Identifier (URI) will be: *UserPrefix[User Start Index…(Number Of Users-1)]@User Domain*  , for example, myUser009@Contoso.com.</span></span>
    
3. <span data-ttu-id="da578-242">[**すべてのユーザーのパスワード**] フィールドに、ユーザーの作成時に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-242">In the **Password for All Users** field, enter the password used during creation of the users.</span></span> <span data-ttu-id="da578-243">このフィールドを空白のままにすると、ユーザー名がパスワードとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="da578-243">If you leave this field empty the username will be set as the password.</span></span>
    
4. <span data-ttu-id="da578-244">[**ユーザーの開始インデックス**] フィールドに、構成する最初のユーザーのインデックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-244">In the **User Start Index** field, enter the index of the first user to be configured.</span></span> <span data-ttu-id="da578-245">さまざまな種類またはロードのレベルに対して異なる範囲を構成できますが、構成する範囲に応じて、読み込み構成ツール (UserProfileGenerator) を1回実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da578-245">You can configure different ranges for different types or levels of load, but you must run the Load Configuration tool (UserProfileGenerator.exe) once per the range you want to configure.</span></span>
    
5. <span data-ttu-id="da578-246">[**ユーザー**数] フィールドに、構成するユーザーの合計数を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-246">In the **Number of Users** field, enter the total number of users you're going to configure.</span></span>
    
6. <span data-ttu-id="da578-247">[**ユーザードメイン**] フィールドに、SIP URI として使用されているドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-247">In the **User Domain** field, enter the domain used for the SIP URI.</span></span> <span data-ttu-id="da578-248">これは、Skype for Business Server 2015 フロントエンドサーバーまたは Standard Edition サーバーにログオンする各ユーザーの SIP URI を作成するために使用され、アカウントドメインとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="da578-248">This is used to construct the SIP URI of each user to log on to the Skype for Business Server 2015 Front End Server or Standard Edition server, and may be different from the Account Domain.</span></span>
    
7. <span data-ttu-id="da578-249">[ **Account domain** ] フィールドに、AD DS ドメインのログオンを入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-249">In the **Account Domain** field, enter the AD DS domain logon.</span></span>
    
8. <span data-ttu-id="da578-250">[ **MPOP** percent (複数のプレゼンス値)] フィールドに、複数のコンピューターまたはデバイスからログオンしているユーザーのうち、10パーセントなどの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-250">In the **MPOP Percentage** (Multiple Point of Presence percentage) field, give a value for the percentage of users that are logged on from multiple machines or devices, for example 10 percent.</span></span>
    
9. <span data-ttu-id="da578-251">[ **1 秒あたりのサインイン**数] フィールドに、同時エンドポイントの最大数を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-251">Enter the maximum number of concurrent endpoints in the **Sign in Per Second (per Instance)** field.</span></span> <span data-ttu-id="da578-252">これは、ユーザーのログインの最大数であり、推奨値は1秒あたりの秒数 (< = 2) です。</span><span class="sxs-lookup"><span data-stu-id="da578-252">This is the maximum number of log ins for your users, and the recommendation is a rate of less than/equal to 2 per second (<=2).</span></span>
    
10. <span data-ttu-id="da578-253">[**アクセスプロキシ] または [プールの FQDN** ] フィールドに、クライアントが接続するサーバーの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-253">In the **Access Proxy or Pool FQDN** field, enter the fully qualified domain name (FQDN) of the server you want the clients to connect to.</span></span> <span data-ttu-id="da578-254">ユーザーが外部でログオンしている場合は、アクセスプロキシを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da578-254">If the users are logging on externally, you'll need to type the access proxy.</span></span> <span data-ttu-id="da578-255">ユーザーが内部の場合は、エンタープライズプールまたは Standard Edition サーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="da578-255">If the users are internal, give the FQDN of their Enterprise Pool or Standard Edition server.</span></span>
    
11. <span data-ttu-id="da578-256">[**ポート**] フィールドに、ユーザーが SIP に使用するポートを入力します (既定では 5061)。</span><span class="sxs-lookup"><span data-stu-id="da578-256">In the **Port** field, enter the port that you want users to use for SIP (the default here is 5061).</span></span>
    
12. <span data-ttu-id="da578-257">[**外部ネットワークサーバー設定**] フィールドにアクセスプロキシまたはプールの FQDN を入力し、もう一度**ポート**を指定します。</span><span class="sxs-lookup"><span data-stu-id="da578-257">For the **External Network Server Settings** field, give the Access Proxy or Pool FQDN and, again, the **Port**.</span></span> <span data-ttu-id="da578-258">これらの設定は、外部エンドポイントのロードシミュレーションでのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="da578-258">These settings are used only for External endpoints load simulation.</span></span>
    
#### <a name="general-scenarios-tab"></a><span data-ttu-id="da578-259">一般的なシナリオタブ</span><span class="sxs-lookup"><span data-stu-id="da578-259">General Scenarios tab</span></span>

![[General Scenarios] タブを表示している Load Configuration Tool](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
<span data-ttu-id="da578-261">実行する操作を特定したり、無効のままにしたりすることで、各一般的なシナリオのロードレベルとパラメーターを構成できます。</span><span class="sxs-lookup"><span data-stu-id="da578-261">You can configure the load levels and parameters for each of the general scenarios offered by determining what you want to run or leave disabled.</span></span> <span data-ttu-id="da578-262">一般的なオプションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="da578-262">Here are your general options:</span></span>
  
> [!NOTE]
> <span data-ttu-id="da578-263">すべてのフィールドの読み込みレベル値。ただし、ローカルインフォメーションサービスは、[無効]、[**低**]、[**中**]、[**高**]、または [**カスタム**] に**なり**ます。</span><span class="sxs-lookup"><span data-stu-id="da578-263">Load level values for all fields but Local Information Services are **Disabled**, **Low**, **Medium**, **High**, or **Custom**.</span></span> <span data-ttu-id="da578-264">設定を選択した状態で無効にした場合は、各クライアントに対して構成が生成されます。</span><span class="sxs-lookup"><span data-stu-id="da578-264">If you select any setting but Disabled, then configurations are generated for each client.</span></span> <span data-ttu-id="da578-265">サーバーでサポートされている最大の負荷が高になります。medium は高負荷の 60%低は 30% です。</span><span class="sxs-lookup"><span data-stu-id="da578-265">High results in the max supported load on the server; medium is 60% of high load; low is 30%.</span></span> 
  
- <span data-ttu-id="da578-266">**インスタントメッセージ-** これには、ピアツーピアと会議が含まれます。[読み込みレベル] に適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="da578-266">**Instant Messaging -** This includes peer-to-peer and conferencing; choose the appropriate value for Load Level.</span></span>
    
- <span data-ttu-id="da578-267">**電話会議-** 電話会議*のみ*のロードレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="da578-267">**Audio Conferencing -** Choose a load level for audio conferencing *only*  .</span></span> <span data-ttu-id="da578-268">ピアツーピア通話は、「**ボイスシナリオ**」セクションで後述します。</span><span class="sxs-lookup"><span data-stu-id="da578-268">Peer-to-peer calls will be tackled a little later in the **Voice Scenarios** section.</span></span> <span data-ttu-id="da578-269">**[詳細設定**] タブを開いて、MultiView を有効にします。</span><span class="sxs-lookup"><span data-stu-id="da578-269">Open the **Advanced** tab to enable MultiView.</span></span>
    
- <span data-ttu-id="da578-270">**アプリケーション共有-** アプリケーション共有の読み込みレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="da578-270">**Application Sharing -** Choose a load level for application sharing.</span></span>
    
- <span data-ttu-id="da578-271">**データの共同作業-** データの共同作業に使用する読み込みレベルを選択します。これには、データ会議が含まれます。</span><span class="sxs-lookup"><span data-stu-id="da578-271">**Data Collaboration -** Choose a load level for data collaboration, which includes data conferencing.</span></span>
    
- <span data-ttu-id="da578-272">**配布リストの展開-**[**詳細設定**] ボタンをクリックして、ユーザー作成ツールの [DL] タブで構成された同じ値のフィールドに入力します (userプロビジョニングツール .exe)。</span><span class="sxs-lookup"><span data-stu-id="da578-272">**Distribution List Expansion -** Click the **Advanced** button and fill in the field with the same values configured on the DL tab of the User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="da578-273">読み込みレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="da578-273">Choose a load level.</span></span>
    
- <span data-ttu-id="da578-274">**アドレス帳 Web クエリ-** これは、アドレス帳ファイルのダウンロードではなく、アドレス帳の参照サービスです。</span><span class="sxs-lookup"><span data-stu-id="da578-274">**Address Book Web Query -** This is the address book lookup service rather than the address book file download.</span></span> <span data-ttu-id="da578-275">アドレス帳ファイルのダウンロードに対してこれを有効にする場合は、[**詳細**設定] ボタンをクリックして、 **EnableABSDownload**を True に設定します。</span><span class="sxs-lookup"><span data-stu-id="da578-275">If you want to enable this for address book file downloads, click the **Advanced** button and set **EnableABSDownload** to True.</span></span> <span data-ttu-id="da578-276">Load level の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="da578-276">Give a value for load level.</span></span>
    
- <span data-ttu-id="da578-277">**応答グループサービス-**[**詳細設定**] ボタンをクリックし、応答グループサービスエージェントをプロビジョニングしたときに既に作成した応答グループの uri を指定します。</span><span class="sxs-lookup"><span data-stu-id="da578-277">**Response Group Service -** Click the **Advanced** button and specify the URIs of the response groups you already created when you provisioned Response Group Service agents.</span></span> <span data-ttu-id="da578-278">少なくとも1つの応答グループを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da578-278">You must choose at least one response group.</span></span> <span data-ttu-id="da578-279">さらに使用するには、返答グループをセミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="da578-279">To use more, separate the response groups with semicolons.</span></span> <span data-ttu-id="da578-280">**RGSUriSuffixStartIndex**と**RGSUriSuffixEndIndex**を実際の値に更新します。</span><span class="sxs-lookup"><span data-stu-id="da578-280">Update **RGSUriSuffixStartIndex** and **RGSUriSuffixEndIndex** to the actual values.</span></span> <span data-ttu-id="da578-281">読み込みレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="da578-281">Choose a load level.</span></span>
    
- <span data-ttu-id="da578-282">**位置情報サービス-**[有効] または [無効] のいずれかの読み込みレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="da578-282">**Location Information Services -** Select a load level of either Enabled or Disabled.</span></span>
    
> [!NOTE]
> <span data-ttu-id="da578-283">各シナリオには、その横に詳細ボタンがあります。また、既定の設定のバリエーションを有効にするチェックボックスのセットがあります。</span><span class="sxs-lookup"><span data-stu-id="da578-283">Each of the scenarios has an Advanced button located next to it, and a set of check boxes that enable variations to the default setting.</span></span> 
  
- <span data-ttu-id="da578-284">[*アドホック*] を選択すると、時間を通じて作成される電話会議のシミュレーションがツールによって生成されます。</span><span class="sxs-lookup"><span data-stu-id="da578-284">Choosing  *Ad-hoc*  will allow the tool to generate simulation of conferences that will be created throughout the hour.</span></span>
    
- <span data-ttu-id="da578-285">[*大きな Conf*を選択すると、大規模な会議シナリオがシミュレートされます。</span><span class="sxs-lookup"><span data-stu-id="da578-285">Choosing  *Large Conf*  means that a Large Conference Scenario will be simulated.</span></span>
    
-  <span data-ttu-id="da578-286">*外部*ユーザーに対しても、外部ユーザーのシミュレーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="da578-286">*External*  tells the tool to also simulate external users.</span></span>
    
<span data-ttu-id="da578-287">これらのボタンとチェックボックスは、それぞれのシナリオに固有の追加値であり、ストレスとパフォーマンスツールの動作を変更して、カスタマイズできるようにします。</span><span class="sxs-lookup"><span data-stu-id="da578-287">These buttons and check boxes are extra values specific to each scenario and will change the behavior of the Stress and Performance Tool and make customization possible.</span></span>
  
<span data-ttu-id="da578-288">[一般的なシナリオ] タブ (Location Information Services を除く) の各シナリオで、[読み込みレベル] の値が**Custom**の場合は、[詳細設定] ダイアログボックスの対応するフィールドを使って、会話の料金が計算されます。</span><span class="sxs-lookup"><span data-stu-id="da578-288">For each scenario on the General Scenarios tab (except for Location Information Services), if the value of Load Level is **Custom**, then the conversation rate will be calculated using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="da578-289">シナリオによってはフィールド名が異なる場合がありますが、フィールドの説明は次のようになります。*注この番号は、ドロップダウンメニューから [カスタム] が選択されている場合にのみ使用*されます。</span><span class="sxs-lookup"><span data-stu-id="da578-289">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
<span data-ttu-id="da578-290">**高**、**中**、**低**の値は、すべてのシナリオのバランスを考慮したユーザーモデルでの、モダリティあたりの会話料金を変更します。</span><span class="sxs-lookup"><span data-stu-id="da578-290">The values **High**, **Medium**, and **Low**, will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="da578-291">予想される使用状況の違いにより、モダリティあたりのロードレベルを変更する必要がある場合は、カスタム会話レートを使用します。</span><span class="sxs-lookup"><span data-stu-id="da578-291">If there's a need to change the load level per modality due to a difference in expected usage, use a Custom conversation rate.</span></span>
  
#### <a name="voice-scenarios-tab"></a><span data-ttu-id="da578-292">[音声シナリオ] タブ</span><span class="sxs-lookup"><span data-stu-id="da578-292">Voice Scenarios tab</span></span>

<span data-ttu-id="da578-293">これは、すべての音声関連のシナリオを構成するためのタブです。</span><span class="sxs-lookup"><span data-stu-id="da578-293">This is the tab for configuration of all your voice-related scenarios.</span></span>
  
![Load Configuration Tool の [Voice Scenarios] タブ](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
<span data-ttu-id="da578-295">以下のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="da578-295">Your options are:</span></span>
  
- <span data-ttu-id="da578-296">**VoIP-**[**詳細設定**] ボタンをクリックして、PhoneAreaCode と locationprofile (dial plan) フィールドの値を追加します。</span><span class="sxs-lookup"><span data-stu-id="da578-296">**VoIP -** Click the **Advanced** button and add values for the PhoneAreaCode and LocationProfile (dial plan) fields.</span></span> <span data-ttu-id="da578-297">また、Load Level の値も指定します。</span><span class="sxs-lookup"><span data-stu-id="da578-297">You'll also give a value for Load Level.</span></span> <span data-ttu-id="da578-298">VoIP または UC/PSTN ゲートウェイが有効になっている場合、読み込みレベルを選択すると、公衆交換電話網 (PSTN) を統合通信 (UC) 構成ファイルに生成して、外部通話をシミュレートすることができます。</span><span class="sxs-lookup"><span data-stu-id="da578-298">If you choose a load level for VoIP or UC/PSTN Gateway enabled, then a public-switched telephone network (PSTN) to unified communications (UC) configuration file will be generated to simulate external calls.</span></span>
    
- <span data-ttu-id="da578-299">**UC/PSTN ゲートウェイ-**[読み込みレベル] の値を選択する必要があります。 [無効] 以外のものを選択する場合は、 **[詳細設定**] ボタンをクリックしても、PSTN 市外局番の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da578-299">**UC/PSTN Gateway -** You need to choose a Load Level value, and when you choose anything other than Disabled, you've also got to supply a value for PSTN area code by clicking the **Advanced** button.</span></span> <span data-ttu-id="da578-300">仲介サーバーと PSTN の下にある [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da578-300">Click **Add** under the Mediation Server and PSTN.</span></span> <span data-ttu-id="da578-301">市外局番用のルートが構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da578-301">Make sure you have a route configured for the area code.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="da578-302">Skype for Business コントロールパネルまたは Skype for Business の管理シェルを使用して、ボイスルートの構成を確認できます。</span><span class="sxs-lookup"><span data-stu-id="da578-302">You can use either the Skype for Business Control Panel or Skype for Business Management Shell to verify your voice route configuration.</span></span> 
  
- <span data-ttu-id="da578-303">**会議アテンダント-** Load Level の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="da578-303">**Conferencing Attendant -** Supply a value for Load Level.</span></span> <span data-ttu-id="da578-304">無効以外の値を指定すると、**電話番号**フィールドが有効になります。</span><span class="sxs-lookup"><span data-stu-id="da578-304">Any value other than Disabled will enable the **Telephone Number** field.</span></span> <span data-ttu-id="da578-305">使用する自動応答の電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-305">Enter the phone number of the Auto Attendant you want to use.</span></span> <span data-ttu-id="da578-306">[**詳細設定**] をクリックし、[ **locationprofile** ] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="da578-306">Click **Advanced** and give a value for the **LocationProfile** field.</span></span>
    
- <span data-ttu-id="da578-307">**電話パーキングサービス-** ここでは、読み込みレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="da578-307">**Call Parking Service -** Here, supply a Load Level.</span></span>
    
- <span data-ttu-id="da578-308">**仲介サーバーと PSTN-** 使用する各仲介サーバーには、独自の PSTN シミュレータが必要です。</span><span class="sxs-lookup"><span data-stu-id="da578-308">**Mediation Server and PSTN -** Each Mediation Server that you want to use needs its own PSTN simulator.</span></span> <span data-ttu-id="da578-309">シミュレータに使用するクライアントを決めたら、構成済みの PSTN シミュレータでそのコンピューターへの通話をルーティングするために、仲介サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="da578-309">After you've determined which client you're going to use for the simulator, configuration your Mediation Server to route calls to that computer on the PSTN Simulator you configured.</span></span> <span data-ttu-id="da578-310">[**追加**] ボタンをクリックして、仲介サーバーの値を構成します。</span><span class="sxs-lookup"><span data-stu-id="da578-310">Click the **Add** button to configure a value for the Mediation Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="da578-311">各シナリオには、その横に [詳細設定] ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="da578-311">Each scenario has an Advanced button located next to it.</span></span> <span data-ttu-id="da578-312">[詳細設定] ダイアログボックスには、ストレスとパフォーマンスツールの動作を変更してカスタマイズを有効にする各シナリオに固有の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="da578-312">Advanced dialog boxes contain settings specific to each scenario that change the behavior of the Stress and Performance Tool and enable customization.</span></span> <span data-ttu-id="da578-313">> [ボイスシナリオ] タブの各シナリオで、[読み込みレベル] の値が**Custom**の場合は、[詳細設定] ダイアログボックスの対応するフィールドを使って、会話の料金を計算します。</span><span class="sxs-lookup"><span data-stu-id="da578-313">> For each scenario on the Voice Scenarios tab, if the value of Load Level is **Custom**, then the conversation rate will be calculated by using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="da578-314">シナリオによってはフィールド名が異なる場合がありますが、フィールドの説明は次のようになります。*注この番号は、ドロップダウンメニューから [カスタム] が選択されている場合にのみ使用*されます。</span><span class="sxs-lookup"><span data-stu-id="da578-314">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
#### <a name="web-app-tab"></a><span data-ttu-id="da578-315">[Web アプリ] タブ</span><span class="sxs-lookup"><span data-stu-id="da578-315">Web App tab</span></span>

![Load Configuration Tool の [Web app] タブ](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
<span data-ttu-id="da578-317">Web アプリは、フロントエンドサーバーにインストールされているユニファイドコミュニケーション Web API (UCWA) サーバーを通じて、会議シナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="da578-317">Web App supports conferencing scenarios through the Unified Communications Web API (UCWA) server that's installed on a Front End server.</span></span> <span data-ttu-id="da578-318">Web アプリのタブを使用して、web アプリに関連するすべてのシナリオを構成します。</span><span class="sxs-lookup"><span data-stu-id="da578-318">Use the Web App tab to configure all web app-related scenarios.</span></span> <span data-ttu-id="da578-319">オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="da578-319">Options are:</span></span>
  
- <span data-ttu-id="da578-320">**一般的な Web アプリの設定-**[**追加の設定**] ボタンをクリックして、フロントエンドプール VIP のディレクトリプール仮想 IP (vip) に**ReachTargetServerUrl**を設定します。</span><span class="sxs-lookup"><span data-stu-id="da578-320">**General Web App Settings -** Click the **Additional Settings** button and set the **ReachTargetServerUrl** to the Directory Pool virtual IP (VIP) of the Front End pool VIP.</span></span>
    
- <span data-ttu-id="da578-321">**アプリケーション共有-**[レベルの読み込み] の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="da578-321">**Application Sharing -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="da578-322">**データの共同作業-**[レベルの読み込み] の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="da578-322">**Data Collaboration -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="da578-323">**インスタントメッセージ-**[レベルの読み込み] の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="da578-323">**Instant Messaging -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="da578-324">**音声会議-**[レベルの読み込み] の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="da578-324">**Voice Conferencing -** Select a value for Load Level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="da578-325">各シナリオには、その横に **[詳細設定**] ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="da578-325">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="da578-326">[詳細設定] \*\*\*\*\*\*ダイアログには、ストレスとパフォーマンスツールの動作を変更して > を有効にする各シナリオに固有の値が含まれています。また、読み込みレベルが Custom の場合は、\*\* 既定の代わりに ConversationsPerHour フィールドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="da578-326">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Web App scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="mobility-tab"></a><span data-ttu-id="da578-327">[モバイル] タブ</span><span class="sxs-lookup"><span data-stu-id="da578-327">Mobility tab</span></span>

<span data-ttu-id="da578-328">このタブを使用して、すべてのモビリティ関連シナリオを構成します。</span><span class="sxs-lookup"><span data-stu-id="da578-328">Use this tab to configure all of the mobility-related scenarios.</span></span>
  
![Load Configuration Tool の [Mobility] タブ](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
<span data-ttu-id="da578-330">以下のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="da578-330">The options here are:</span></span>
  
- <span data-ttu-id="da578-331">**一般的なモバイル設定**[**追加の設定**] をクリックし、フィールド UcwaTargetServerUrl をディレクタープール仮想 IP (vip) またはフロントエンドプール VIP に設定します。</span><span class="sxs-lookup"><span data-stu-id="da578-331">**General Mobility Settings -** Click **Additional Settings** and set the field UcwaTargetServerUrl to the Director Pool virtual IP (VIP) or the Front End pool VIP.</span></span>
    
- <span data-ttu-id="da578-332">**プレゼンスと P2P インスタントメッセージング/オーディオ-**[読み込みレベル] の値を選択して、モビリティーシミュレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="da578-332">**Presence and P2P Instant Messaging/Audio -** Select a value for Load Level to enable the Mobility simulation.</span></span>
    
> [!NOTE]
> <span data-ttu-id="da578-333">各シナリオには、その横に **[詳細設定**] ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="da578-333">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="da578-334">[詳細設定] \*\*\*\*\*\*ダイアログには、ストレスとパフォーマンスツールの動作を変更して > を有効にする各シナリオに固有の値が含まれています。また、読み込みレベルが Custom の場合は、\*\* 既定の代わりに ConversationsPerHour フィールドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="da578-334">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Mobility scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="summary-tab"></a><span data-ttu-id="da578-335">[概要] タブ</span><span class="sxs-lookup"><span data-stu-id="da578-335">Summary tab</span></span>

<span data-ttu-id="da578-336">[概要] タブには、各シナリオで使用するユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da578-336">The Summary tab indicates which users to use for each of the scenarios.</span></span>
  
![Load Configuration Tool の [Summary] タブ](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
<span data-ttu-id="da578-338">[概要] タブには、各シナリオで使用するユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da578-338">The Summary tab indicates which users to use for each of the scenarios.</span></span> 
  
<span data-ttu-id="da578-339">[**カスタムユーザー範囲の生成を有効に**する] チェックボックスをオンにして、ユーザー設定の範囲を含むテーブルのシナリオをダブルクリックして、ユーザー番号の範囲を手動で構成することができます。</span><span class="sxs-lookup"><span data-stu-id="da578-339">It's possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the User Range that you want to customize.</span></span>
  
<span data-ttu-id="da578-340">[チェック (Runclient)] は、生成されたバッチファイルで、サインイン速度に対応する遅延を含めるために、**開始時にサインインの遅延を追加**します。</span><span class="sxs-lookup"><span data-stu-id="da578-340">Check **(RunClient.bat) Add sign-in delay when starting** in order to include delays in the generated batch files to correspond to the sign-in rate.</span></span> <span data-ttu-id="da578-341">これは、多数のユーザーにサインインするときにサーバーの過負荷を防ぐために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="da578-341">This is useful to prevent server overload when signing in a large number of users.</span></span>
  
<span data-ttu-id="da578-342">[**ファイルの生成**] をクリックし、構成を生成するフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="da578-342">Click **Generate Files** and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="da578-343">ファイルが正常に作成されると、ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da578-343">A dialog box will appear when your files have been successfully created.</span></span>
  
!["Load configuration files generated successfully" というメッセージ ボックス。](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a><span data-ttu-id="da578-346">LyncPerfTool を実行する</span><span class="sxs-lookup"><span data-stu-id="da578-346">Run LyncPerfTool</span></span>
<span data-ttu-id="da578-347"><a name="BKMK_RunTool"> </a></span><span class="sxs-lookup"><span data-stu-id="da578-347"></span></span>

<span data-ttu-id="da578-348">Skype for Business Server 2015 応力とパフォーマンスツール (LyncPerfTool) を実行する前に、ユーザー、連絡先、シナリオを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da578-348">You'll need to create users, contacts, and scenarios before running the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="da578-349">これらの操作を実行するためのツールの使用について詳しくは、この記事の「[ユーザーと連絡先を作成](using-the-tool.md#BKMK_CreateUsersAndContacts)し、[ユーザープロファイルを構成](using-the-tool.md#BKMK_UserProfile)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="da578-349">For details about using the tools to perform these actions, see [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) and [Configure User Profile](using-the-tool.md#BKMK_UserProfile) previously in this article.</span></span> <span data-ttu-id="da578-350">これらのツールを実行すると、必要なパラメーターが含まれるバッチファイルの一部として実行されるストレスとパフォーマンスのツールで実行されるファイルも生成されます。</span><span class="sxs-lookup"><span data-stu-id="da578-350">Running these tools will also generate a file that will run with the Stress and Performance tool as part of a batch file with the required parameters included.</span></span>
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="da578-351">Skype for Business Server 2015 のストレスとパフォーマンスのツールを実行する</span><span class="sxs-lookup"><span data-stu-id="da578-351">Running the Skype for Business Server 2015 Stress and Performance tool</span></span>

<span data-ttu-id="da578-352">ロード構成ツール (UserProfileGenerator) は、パフォーマンスカウンターを登録して XML 構成ファイルを読み込むことで、ストレスとパフォーマンスツール (LyncPerfTool) を実行できるバッチファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="da578-352">The Load Configuration tool (UserProfileGenerator.exe) creates a batch file that enables you to run the Stress and Performance tool (LyncPerfTool.exe) by registering performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="da578-353">バッチファイルは、構成ファイルごとに LyncPerfTool の1つのインスタンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="da578-353">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="da578-354">バッチファイルを実行するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="da578-354">To run the batch file follow these steps:</span></span>
  
### <a name="run-the-stress-and-performance-test"></a><span data-ttu-id="da578-355">ストレスとパフォーマンスのテストを実行する</span><span class="sxs-lookup"><span data-stu-id="da578-355">Run the Stress and Performance test</span></span>

1. <span data-ttu-id="da578-356">各クライアントコンピューターに LyncPerfTool が含まれているディレクトリに、構成フォルダーとファイルが含まれるフォルダーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="da578-356">Copy the folder with the configuration folders and files inside to the directory that has LyncPerfTool.exe on each client computer.</span></span> <span data-ttu-id="da578-357">(たとえば、1.28 _ 13.16.16 という名前のフォルダーに構成ファイルを生成した場合は、そのフォルダーを、LyncPerfTool が含まれているフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="da578-357">(For example, if you generated the configuration files in the folder named 1.28_13.16.16, copy that folder to the folder with LyncPerfTool.exe in it.</span></span> <span data-ttu-id="da578-358">各クライアントでこの操作を実行します。)</span><span class="sxs-lookup"><span data-stu-id="da578-358">Do this on each client.)</span></span>
    
2. <span data-ttu-id="da578-359">クライアントフォルダーに移動し、 **Runclient**バッチスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="da578-359">Navigate to the client folder and run the **RunClient** batch script.</span></span> <span data-ttu-id="da578-360">Windows エクスプローラーでバッチファイルをダブルクリックすると、そのクライアントのすべての構成ファイルが実行されます。</span><span class="sxs-lookup"><span data-stu-id="da578-360">You can double-click the batch file in Windows Explorer and it will run all of the configuration files for that client.</span></span> <span data-ttu-id="da578-361">次の構文を使用して、クライアントフォルダーからスクリプトを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="da578-361">You can also run the script from a client folder by using the following syntax:</span></span>
    
   ```
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

<span data-ttu-id="da578-362">ストレスとパフォーマンスのツールを直接実行するには、コマンドプロンプトを開いて、コマンドラインで次のコマンドを入力します (初めて実行する場合は、このトピックの`regsvr32 /i /n /s LyncPerfToolPerf.dll`後半のメモに示すように、パフォーマンスカウンターを登録してください)。</span><span class="sxs-lookup"><span data-stu-id="da578-362">To run the Stress and Performance tool directly, open a command prompt and type the following command at the command line (and when doing this for the first time, be sure to register the performance counters  `regsvr32 /i /n /s LyncPerfToolPerf.dll`, as shown in the note later in this topic):</span></span>
  
```
LyncPerfTool.exe /file:IM_client0.xml
```

<span data-ttu-id="da578-363">ツールに構成ファイルの値を表示させるには、次`/displayfile`のようにパラメーターを前のコマンドに追加します。</span><span class="sxs-lookup"><span data-stu-id="da578-363">To have the tool display the values in the configuration file, include the  `/displayfile` parameter on the preceding command, so that it looks like this:</span></span>
  
```
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

<span data-ttu-id="da578-364">プロセスを*終了*するには、Ctrl キーを押しながら C キーを押します。</span><span class="sxs-lookup"><span data-stu-id="da578-364">To  *end*  the process, press Ctrl+C.</span></span>
  
> [!NOTE]
> <span data-ttu-id="da578-365">ストレスとパフォーマンスのツールを直接実行する前に、次のコマンドを使用してパフォーマンスカウンターを登録する必要があります。`regsvr32 /i /n /s LyncPerfToolPerf.dll`</span><span class="sxs-lookup"><span data-stu-id="da578-365">Before running the Stress and Performance tool directly, you must register the performance counters via the following command:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`</span></span>
  
> [!NOTE]
> <span data-ttu-id="da578-366">開始するストレスとパフォーマンスのツールのすべてのインスタンスは、通常、1秒あたり1人のユーザーの代わりにユーザーのサインインを開始します。</span><span class="sxs-lookup"><span data-stu-id="da578-366">Every instance of the Stress and Performance tool that you start will immediately begin signing in users, usually at a rate of one user per second.</span></span> 
  
<span data-ttu-id="da578-367">プールのピークユーザーのサインイン速度は約 12/秒です。</span><span class="sxs-lookup"><span data-stu-id="da578-367">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="da578-368">これは、ユーザーがサインインしている間に、12個を超える LyncPerfTool インスタンスを同時に開始しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="da578-368">This means that you shouldn't start more than 12 LyncPerfTool.exe instances at the same time while users are still signing in.</span></span> <span data-ttu-id="da578-369">1000ユーザーの場合は、1秒あたりのサインインが完了するまで20分ほどかかります。</span><span class="sxs-lookup"><span data-stu-id="da578-369">One thousand users will take about 20 minutes to fully sign in at one per second.</span></span>
  
## <a name="interpreting-the-results"></a><span data-ttu-id="da578-370">結果を解釈する</span><span class="sxs-lookup"><span data-stu-id="da578-370">Interpreting the Results</span></span>
<span data-ttu-id="da578-371"><a name="BKMK_Interpret"> </a></span><span class="sxs-lookup"><span data-stu-id="da578-371"></span></span>

<span data-ttu-id="da578-372">Skype for Business Server 2015 のストレスとパフォーマンスのツールには、クライアントの動作を理解するのに役立つ多くのカウンターと、問題が発生しているかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da578-372">The Skype for Business Server 2015 Stress and Performance Tool has many counters that can help you understand what the client is doing, and whether it's encountering issues.</span></span>
  
### <a name="client-counters"></a><span data-ttu-id="da578-373">クライアントカウンター</span><span class="sxs-lookup"><span data-stu-id="da578-373">Client Counters</span></span>

<span data-ttu-id="da578-374">LyncPerfTool の各インスタンスには、カウンターの個別のインスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="da578-374">Each instance of LyncPerfTool.exe running has a separate instance of the counters.</span></span> <span data-ttu-id="da578-375">各インスタンスには、プロセス ID で名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="da578-375">Each instance is named by its process ID.</span></span> <span data-ttu-id="da578-376">クライアントの過負荷が発生する場合は、他の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da578-376">If clients are overloaded other issues can occur.</span></span> <span data-ttu-id="da578-377">この問題を回避するには:</span><span class="sxs-lookup"><span data-stu-id="da578-377">To prevent these issues:</span></span>
  
- <span data-ttu-id="da578-378">クライアントコンピューターの CPU およびメモリ使用量を監視します。</span><span class="sxs-lookup"><span data-stu-id="da578-378">Monitor CPU and Memory usage on the client computers.</span></span> <span data-ttu-id="da578-379">CPU が常に 90% を超えている場合は、ユーザーの数を減らします。</span><span class="sxs-lookup"><span data-stu-id="da578-379">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>
    
- <span data-ttu-id="da578-380">メモリフットプリントが多い場合、ページファイルの領域が不足し始めると、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="da578-380">When the Memory footprint is high, you may run into issues if the Page File begins to run out of space.</span></span> <span data-ttu-id="da578-381">コミットチャージがコンピューターの制限に達していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="da578-381">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="da578-382">メモリの制限を使用している場合は、ページファイルのサイズを大きくするか、ユーザーの数を減らすことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="da578-382">If you are running into Memory limits consider increasing the Page File size or reducing the number of users.</span></span>
    
<span data-ttu-id="da578-383">主要なパフォーマンスカウンターの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="da578-383">Here's a list of key performance counters:</span></span>
  
<span data-ttu-id="da578-384">**一般的な情報**</span><span class="sxs-lookup"><span data-stu-id="da578-384">**General Information**</span></span>

|<span data-ttu-id="da578-385">**パフォーマンスカウンター**</span><span class="sxs-lookup"><span data-stu-id="da578-385">**Performance Counter**</span></span>|<span data-ttu-id="da578-386">**説明**</span><span class="sxs-lookup"><span data-stu-id="da578-386">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da578-387">分数で費やした時間</span><span class="sxs-lookup"><span data-stu-id="da578-387">Time Spent in Minutes</span></span>  <br/> |<span data-ttu-id="da578-388">プロセスが開始されてから経過した時間。</span><span class="sxs-lookup"><span data-stu-id="da578-388">Time spent since the process was started.</span></span>  <br/> |
|<span data-ttu-id="da578-389">アクティブなエンドポイント</span><span class="sxs-lookup"><span data-stu-id="da578-389">Active Endpoints</span></span>  <br/> |<span data-ttu-id="da578-390">現在サーバーに接続されているエンドポイントの数です。</span><span class="sxs-lookup"><span data-stu-id="da578-390">Number of endpoints currently connected to the server.</span></span>  <br/> |
|<span data-ttu-id="da578-391">失敗したログオン</span><span class="sxs-lookup"><span data-stu-id="da578-391">Failed Logons</span></span>  <br/> |<span data-ttu-id="da578-392">エンドポイントのサインインエラーの合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-392">Total number of endpoint sign-in failures.</span></span>  <br/> |
|<span data-ttu-id="da578-393">ログオン試行</span><span class="sxs-lookup"><span data-stu-id="da578-393">Logon Attempts</span></span>  <br/> |<span data-ttu-id="da578-394">エンドポイントのサインイン試行の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-394">Total number of endpoint sign-in attempts.</span></span>  <br/> |
|<span data-ttu-id="da578-395">エンドポイントが切断されました</span><span class="sxs-lookup"><span data-stu-id="da578-395">Endpoints Disconnected</span></span>  <br/> |<span data-ttu-id="da578-396">切断されたエンドポイントの合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-396">Total number of endpoints that have been disconnected.</span></span>  <br/> |
   
<span data-ttu-id="da578-397">**プレゼンス情報**</span><span class="sxs-lookup"><span data-stu-id="da578-397">**Presence Information**</span></span>

|<span data-ttu-id="da578-398">**パフォーマンスカウンター**</span><span class="sxs-lookup"><span data-stu-id="da578-398">**Performance Counter**</span></span>|<span data-ttu-id="da578-399">**説明**</span><span class="sxs-lookup"><span data-stu-id="da578-399">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da578-400">SetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="da578-400">SetPresence Calls</span></span>  <br/> |<span data-ttu-id="da578-401">プレゼンス変更の試行回数の合計です。</span><span class="sxs-lookup"><span data-stu-id="da578-401">Total number of presence change attempts.</span></span> <span data-ttu-id="da578-402">さまざまな種類のプレゼンス変更については、「SetPresence (プレゼンスの種類) 呼び出しのパフォーマンスカウンター」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da578-402">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span>  <br/> |
|<span data-ttu-id="da578-403">SetPresence の NNN 応答</span><span class="sxs-lookup"><span data-stu-id="da578-403">NNN Responses for SetPresence</span></span>  <br/> |<span data-ttu-id="da578-404">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-404">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="da578-405">GetPresence 通話</span><span class="sxs-lookup"><span data-stu-id="da578-405">GetPresence Calls</span></span>  <br/> |<span data-ttu-id="da578-406">プレゼンス要求の取得試行の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-406">Total number of get presence request attempts.</span></span>  <br/> |
|<span data-ttu-id="da578-407">GetPresence に対する NNN の応答</span><span class="sxs-lookup"><span data-stu-id="da578-407">NNN Responses for GetPresence</span></span>  <br/> |<span data-ttu-id="da578-408">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-408">Total number of nnn response codes received from the server.</span></span>  <br/> |
   
<span data-ttu-id="da578-409">**アドレス帳サービス情報**</span><span class="sxs-lookup"><span data-stu-id="da578-409">**Address Book service information**</span></span>

|<span data-ttu-id="da578-410">**パフォーマンスカウンター**</span><span class="sxs-lookup"><span data-stu-id="da578-410">**Performance Counter**</span></span>|<span data-ttu-id="da578-411">**説明**</span><span class="sxs-lookup"><span data-stu-id="da578-411">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da578-412">完全なフル/差分ファイルのダウンロードが試行される</span><span class="sxs-lookup"><span data-stu-id="da578-412">ABS Full/Delta File Downloads Attempted</span></span>  <br/> |<span data-ttu-id="da578-413">試行されたフルまたは差分ファイルのダウンロード要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-413">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="da578-414">ABS フル/差分ファイルのダウンロードに成功しました</span><span class="sxs-lookup"><span data-stu-id="da578-414">ABS Full/Delta File Downloads Succeeded</span></span>  <br/> |<span data-ttu-id="da578-415">試行されたフルまたは差分ファイルのダウンロード要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-415">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="da578-416">アドレス帳 Web クエリサービスに関連するカウンター</span><span class="sxs-lookup"><span data-stu-id="da578-416">Address Book Web Query service related counters</span></span>  <br/> |<span data-ttu-id="da578-417">アドレス帳ファイルのダウンロードに関連するカウンター。</span><span class="sxs-lookup"><span data-stu-id="da578-417">Address book file download related counters.</span></span>  <br/> |
|<span data-ttu-id="da578-418">ABS 呼び出しを実行しました</span><span class="sxs-lookup"><span data-stu-id="da578-418">ABS WS Calls attempted</span></span>  <br/> |<span data-ttu-id="da578-419">試行されたアドレス帳 Web クエリサービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-419">Total number of Address Book Web Query service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="da578-420">ABS 呼び出しに成功しました</span><span class="sxs-lookup"><span data-stu-id="da578-420">ABS WS Calls Succeeded</span></span>  <br/> |<span data-ttu-id="da578-421">成功応答コードを返した、アドレス帳 Web クエリサービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-421">Total number of Address Book Web Query service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="da578-422">ABS 呼び出しに失敗しました</span><span class="sxs-lookup"><span data-stu-id="da578-422">ABS WS Calls Failed</span></span>  <br/> |<span data-ttu-id="da578-423">エラー応答コードを返した、アドレス帳 Web クエリサービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-423">Total number of Address Book Web Query service requests that returned an error response code.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="da578-424">このカテゴリには、アドレス帳サービス (ABS) ファイルのダウンロードとアドレス帳の Web クエリサービス要求を監視するために使用されるカウンターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="da578-424">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span> 
  
<span data-ttu-id="da578-425">**配布リスト (DL) 情報**</span><span class="sxs-lookup"><span data-stu-id="da578-425">**Distribution List (DL) Information**</span></span>

|<span data-ttu-id="da578-426">**パフォーマンスカウンター**</span><span class="sxs-lookup"><span data-stu-id="da578-426">**Performance Counter**</span></span>|<span data-ttu-id="da578-427">**説明**</span><span class="sxs-lookup"><span data-stu-id="da578-427">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da578-428">通話を発信しました</span><span class="sxs-lookup"><span data-stu-id="da578-428">Calls Attempted</span></span>  <br/> |<span data-ttu-id="da578-429">試みた配布リスト展開 (DLX) web サービス要求の合計数。</span><span class="sxs-lookup"><span data-stu-id="da578-429">Total number of distribution list expansion (DLX) web service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="da578-430">通話成功</span><span class="sxs-lookup"><span data-stu-id="da578-430">Calls Succeeded</span></span>  <br/> |<span data-ttu-id="da578-431">成功した応答コードを返した DLX web サービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-431">Total number of DLX web service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="da578-432">通話失敗</span><span class="sxs-lookup"><span data-stu-id="da578-432">Calls Failed</span></span>  <br/> |<span data-ttu-id="da578-433">エラー応答コードを返した DLX web サービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-433">Total number of DLX web service requests that returned an error response code.</span></span>  <br/> |
   

  
> [!NOTE]
> <span data-ttu-id="da578-434">以下のパフォーマンスカウンターには、これらのシナリオが有効な場合に、仲介サーバー、A/V 会議サーバー、エッジサーバー、応答グループアプリケーション、会議の自動応答など、すべてのボイスオーバー IP (VoIP) 通話の番号が報告されます。</span><span class="sxs-lookup"><span data-stu-id="da578-434">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span> 
  
<span data-ttu-id="da578-435">**VoIP の基本情報**</span><span class="sxs-lookup"><span data-stu-id="da578-435">**VoIP Basic Information**</span></span>

|<span data-ttu-id="da578-436">**パフォーマンスカウンター**</span><span class="sxs-lookup"><span data-stu-id="da578-436">**Performance Counter**</span></span>|<span data-ttu-id="da578-437">**説明**</span><span class="sxs-lookup"><span data-stu-id="da578-437">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da578-438">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="da578-438">Calls Active</span></span>  <br/> |<span data-ttu-id="da578-439">現在進行中の着信/発信音声通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-439">Total number of incoming/outgoing voice calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="da578-440">通話終了</span><span class="sxs-lookup"><span data-stu-id="da578-440">Calls Terminated</span></span>  <br/> |<span data-ttu-id="da578-441">着信/発信の音声通話の合計数は既に終了しています。</span><span class="sxs-lookup"><span data-stu-id="da578-441">Total number of incoming/outgoing voice calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="da578-442">通話拒否</span><span class="sxs-lookup"><span data-stu-id="da578-442">Calls Declined</span></span>  <br/> |<span data-ttu-id="da578-443">拒否された音声通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-443">Total number of incoming voice calls declined.</span></span>  <br/> |
|<span data-ttu-id="da578-444">着信/発信通話を発信しました</span><span class="sxs-lookup"><span data-stu-id="da578-444">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="da578-445">発信した音声通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="da578-445">Total number of incoming/outgoing voice calls attempted.</span></span>  <br/> |
|<span data-ttu-id="da578-446">確立された着信/発信通話</span><span class="sxs-lookup"><span data-stu-id="da578-446">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="da578-447">送受信された音声通話の合計数が設定されました。</span><span class="sxs-lookup"><span data-stu-id="da578-447">Total number of incoming/outgoing voice calls established.</span></span>  <br/> |
|<span data-ttu-id="da578-448">通話受信 NNN</span><span class="sxs-lookup"><span data-stu-id="da578-448">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="da578-449">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-449">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="da578-450">VoIP パスレート (%)</span><span class="sxs-lookup"><span data-stu-id="da578-450">VoIP Pass Rate (%)</span></span>  <br/> |<span data-ttu-id="da578-451">発信された通話合計発信/合計通話が完了しました。</span><span class="sxs-lookup"><span data-stu-id="da578-451">Total calls established/Total calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="da578-452">**応答グループサービスの通話情報**</span><span class="sxs-lookup"><span data-stu-id="da578-452">**Response Group service Call Information**</span></span>

|<span data-ttu-id="da578-453">**パフォーマンスカウンター**</span><span class="sxs-lookup"><span data-stu-id="da578-453">**Performance Counter**</span></span>|<span data-ttu-id="da578-454">**説明**</span><span class="sxs-lookup"><span data-stu-id="da578-454">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da578-455">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="da578-455">Calls Active</span></span>  <br/> |<span data-ttu-id="da578-456">応答グループアプリケーションへのアクティブな通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-456">Total number of active calls to the Response Group application.</span></span>  <br/> |
|<span data-ttu-id="da578-457">通話を発信しました</span><span class="sxs-lookup"><span data-stu-id="da578-457">Calls Attempted</span></span>  <br/> |<span data-ttu-id="da578-458">試行された通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-458">Total number of calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="da578-459">**インスタントメッセージング (IM) 通話情報**</span><span class="sxs-lookup"><span data-stu-id="da578-459">**Instant Messaging (IM) Call Information**</span></span>

|<span data-ttu-id="da578-460">**パフォーマンスカウンター**</span><span class="sxs-lookup"><span data-stu-id="da578-460">**Performance Counter**</span></span>|<span data-ttu-id="da578-461">**説明**</span><span class="sxs-lookup"><span data-stu-id="da578-461">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da578-462">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="da578-462">Calls Active</span></span>  <br/> |<span data-ttu-id="da578-463">進行中の着信/発信インスタントメッセージ通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-463">Total number of ongoing incoming/outgoing instant messaging calls.</span></span>  <br/> |
|<span data-ttu-id="da578-464">通話終了</span><span class="sxs-lookup"><span data-stu-id="da578-464">Calls Terminated</span></span>  <br/> |<span data-ttu-id="da578-465">受信/送信されたインスタントメッセージの通話の合計数が既に終了しています。</span><span class="sxs-lookup"><span data-stu-id="da578-465">Total number of incoming/outgoing instant messaging calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="da578-466">通話受信 NNN</span><span class="sxs-lookup"><span data-stu-id="da578-466">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="da578-467">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-467">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="da578-468">受信/送信された IM メッセージ</span><span class="sxs-lookup"><span data-stu-id="da578-468">IM Messages Received/Sent</span></span>  <br/> |<span data-ttu-id="da578-469">すべてのセッションで受信または送信されたメッセージの合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-469">Total number of messages received or sent for all sessions.</span></span>  <br/> |
|<span data-ttu-id="da578-470">着信/発信通話を発信しました</span><span class="sxs-lookup"><span data-stu-id="da578-470">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="da578-471">発信したインスタントメッセージ通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="da578-471">Total number of incoming/outgoing instant messaging calls attempted.</span></span>  <br/> |
|<span data-ttu-id="da578-472">確立された着信/発信通話</span><span class="sxs-lookup"><span data-stu-id="da578-472">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="da578-473">確立された受信/送信インスタントメッセージの合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-473">Total number of incoming/outgoing instant message calls established.</span></span>  <br/> |
   
<span data-ttu-id="da578-474">**アプリ共有の通話情報**</span><span class="sxs-lookup"><span data-stu-id="da578-474">**App Sharing Call Information**</span></span>

|<span data-ttu-id="da578-475">**パフォーマンスカウンター**</span><span class="sxs-lookup"><span data-stu-id="da578-475">**Performance Counter**</span></span>|<span data-ttu-id="da578-476">**説明**</span><span class="sxs-lookup"><span data-stu-id="da578-476">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da578-477">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="da578-477">Calls Active</span></span>  <br/> |<span data-ttu-id="da578-478">進行中の着信/送信アプリケーション共有通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-478">Total number of ongoing incoming/outgoing application sharing calls.</span></span>  <br/> |
|<span data-ttu-id="da578-479">通話終了</span><span class="sxs-lookup"><span data-stu-id="da578-479">Calls Terminated</span></span>  <br/> |<span data-ttu-id="da578-480">受信/送信アプリケーション共有通話の合計数が既に終了しています。</span><span class="sxs-lookup"><span data-stu-id="da578-480">Total number of incoming/outgoing application sharing calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="da578-481">通話受信 NNN</span><span class="sxs-lookup"><span data-stu-id="da578-481">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="da578-482">サーバーから受信した nnn 応答コードの合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-482">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="da578-483">着信/発信通話を発信しました</span><span class="sxs-lookup"><span data-stu-id="da578-483">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="da578-484">試行された受信/送信アプリケーション共有通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="da578-484">Total number of incoming/outgoing application sharing calls attempted.</span></span>  <br/> |
|<span data-ttu-id="da578-485">確立された着信/発信通話</span><span class="sxs-lookup"><span data-stu-id="da578-485">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="da578-486">確立された受信/送信アプリケーション共有通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-486">Total number of incoming/outgoing application sharing calls established.</span></span>  <br/> |
   
<span data-ttu-id="da578-487">**CAA を通話情報**</span><span class="sxs-lookup"><span data-stu-id="da578-487">**CAA Call Information**</span></span>

|<span data-ttu-id="da578-488">**パフォーマンスカウンター**</span><span class="sxs-lookup"><span data-stu-id="da578-488">**Performance Counter**</span></span>|<span data-ttu-id="da578-489">**説明**</span><span class="sxs-lookup"><span data-stu-id="da578-489">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da578-490">アクティブな通話</span><span class="sxs-lookup"><span data-stu-id="da578-490">Calls Active</span></span>  <br/> |<span data-ttu-id="da578-491">現在進行中の着信/発信公衆交換電話網 (PSTN) 通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-491">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="da578-492">通話終了</span><span class="sxs-lookup"><span data-stu-id="da578-492">Calls Terminated</span></span>  <br/> |<span data-ttu-id="da578-493">着信/発信された PSTN 通話の合計数は既に終了しています。</span><span class="sxs-lookup"><span data-stu-id="da578-493">Total number of incoming/outgoing PSTN calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="da578-494">着信/発信通話を発信しました</span><span class="sxs-lookup"><span data-stu-id="da578-494">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="da578-495">試行された着信/発信の PSTN 通話の合計数。</span><span class="sxs-lookup"><span data-stu-id="da578-495">Total number of incoming/outgoing PSTN calls attempted.</span></span>  <br/> |
|<span data-ttu-id="da578-496">確立された着信/発信通話</span><span class="sxs-lookup"><span data-stu-id="da578-496">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="da578-497">確立された着信/発信 PSTN 通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-497">Total number of incoming/outgoing PSTN calls established.</span></span>  <br/> |
   
<span data-ttu-id="da578-498">**会議情報**</span><span class="sxs-lookup"><span data-stu-id="da578-498">**Conference Information**</span></span>

|<span data-ttu-id="da578-499">**パフォーマンスカウンター**</span><span class="sxs-lookup"><span data-stu-id="da578-499">**Performance Counter**</span></span>|<span data-ttu-id="da578-500">**説明**</span><span class="sxs-lookup"><span data-stu-id="da578-500">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da578-501">アクティブなインスタントメッセージ会議</span><span class="sxs-lookup"><span data-stu-id="da578-501">Active Instant Messaging Conferences</span></span>  <br/> |<span data-ttu-id="da578-502">進行中のインスタントメッセージ会議の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-502">Total number of ongoing instant messaging conferences.</span></span>  <br/> |
|<span data-ttu-id="da578-503">アクティブな音声/ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="da578-503">Active Audio/Video Conferences</span></span>  <br/> |<span data-ttu-id="da578-504">進行中の音声/ビデオ (A/V) 会議の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-504">Total number of ongoing audio/video (A/V) conferences.</span></span>  <br/> |
|<span data-ttu-id="da578-505">アクティブなアプリケーション共有会議</span><span class="sxs-lookup"><span data-stu-id="da578-505">Active Application Sharing Conferences</span></span>  <br/> |<span data-ttu-id="da578-506">進行中のアプリケーション共有会議の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-506">Total number of ongoing application sharing conferences.</span></span>  <br/> |
|<span data-ttu-id="da578-507">参加者の数</span><span class="sxs-lookup"><span data-stu-id="da578-507">Number of Participants</span></span>  <br/> |<span data-ttu-id="da578-508">現在会議に接続されている参加者の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-508">Total number of participants currently connected to conferences.</span></span>  <br/> |
|<span data-ttu-id="da578-509">会議のスケジュールエラー</span><span class="sxs-lookup"><span data-stu-id="da578-509">Conference Schedule Failure</span></span>  <br/> |<span data-ttu-id="da578-510">会議をスケジュールしようとしたときに発生したエラーの合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-510">Total number of failures while trying to schedule a conference.</span></span>  <br/> |
|<span data-ttu-id="da578-511">電話会議に参加できない</span><span class="sxs-lookup"><span data-stu-id="da578-511">Join Conference Failure</span></span>  <br/> |<span data-ttu-id="da578-512">会議に接続しようとしているときに発生したエラーの合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-512">Total number of failures while trying to connect to a conference.</span></span>  <br/> |
   
<span data-ttu-id="da578-513">**UCWA クライアントカウンター**</span><span class="sxs-lookup"><span data-stu-id="da578-513">**UCWA Client Counters**</span></span>

|<span data-ttu-id="da578-514">**パフォーマンスカウンター**</span><span class="sxs-lookup"><span data-stu-id="da578-514">**Performance Counter**</span></span>|<span data-ttu-id="da578-515">**説明**</span><span class="sxs-lookup"><span data-stu-id="da578-515">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da578-516">成功した IMMCU の結合の合計数</span><span class="sxs-lookup"><span data-stu-id="da578-516">Total Number of IMMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="da578-517">参加したインスタントメッセージ会議の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-517">Total number of instant messaging conferences joined.</span></span>  <br/> |
|<span data-ttu-id="da578-518">成功した DMCU 結合の合計数</span><span class="sxs-lookup"><span data-stu-id="da578-518">Total Number of DMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="da578-519">参加した A/V 会議の合計数です。</span><span class="sxs-lookup"><span data-stu-id="da578-519">Total number of A/V conferences joined.</span></span>  <br/> |
   

