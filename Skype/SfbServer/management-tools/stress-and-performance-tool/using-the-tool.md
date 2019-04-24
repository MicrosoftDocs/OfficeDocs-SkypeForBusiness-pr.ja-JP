---
title: ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールは、Skype を使用します。
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: 実行するには、Skype のビジネス サーバー 2015 のストレスおよびパフォーマンス ツールが必要がありますに両方のユーザー、連絡先、およびユーザー プロファイルを管理できるようが実行しているツールを構成して出力またはツールによって生成される結果を確認し。
ms.openlocfilehash: 7ce25ec13af020734e0784392e457f96399a2398
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198679"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="d4ad5-103">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールは、Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-103">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="d4ad5-104">実行するには、Skype のビジネス サーバー 2015 のストレスおよびパフォーマンス ツールが必要がありますに両方のユーザー、連絡先、およびユーザー プロファイルを管理できるようが実行しているツールを構成して出力またはツールによって生成される結果を確認し。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-104">To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.</span></span>
  
<span data-ttu-id="d4ad5-105">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツール (実行可能ファイルは、LyncPerfTool.exe) は、Skype を実行するのには、4 つの領域があります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-105">There are four areas involved with running the Skype for Business Server 2015 Stress and Performance Tool (the executable is LyncPerfTool.exe):</span></span>
  
- [<span data-ttu-id="d4ad5-106">ユーザーおよび連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-106">Create Users and Contacts</span></span>](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [<span data-ttu-id="d4ad5-107">ユーザー プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-107">Configure User Profile</span></span>](using-the-tool.md#BKMK_UserProfile)
    
- [<span data-ttu-id="d4ad5-108">LyncPerfTool を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-108">Run LyncPerfTool</span></span>](using-the-tool.md#BKMK_RunTool)
    
- [<span data-ttu-id="d4ad5-109">結果の解釈</span><span class="sxs-lookup"><span data-stu-id="d4ad5-109">Interpreting the Results</span></span>](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a><span data-ttu-id="d4ad5-110">ユーザーおよび連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-110">Create Users and Contacts</span></span>
<span data-ttu-id="d4ad5-111"><a name="BKMK_CreateUsersAndContacts"> </a></span><span class="sxs-lookup"><span data-stu-id="d4ad5-111"></span></span>

<span data-ttu-id="d4ad5-112">ビジネス サーバー 2015 (SB 2015) ユーザーのプロビジョニング ツール (UserProvisioningTool.exe) のユーザーおよび連絡先のストレスおよびパフォーマンスのテストを作成するのには、Skype を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-112">You need to use the Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts for your stress and performance testing.</span></span>
  
<span data-ttu-id="d4ad5-113">これは、便利なトピックを読むと役に立つの用語の一覧です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-113">This is a list of helpful terms that might be useful as you read through the topics:</span></span>
  
- <span data-ttu-id="d4ad5-114">**組織単位**の Active Directory ドメイン サービス (AD DS) 組織単位 (OU)。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-114">**Organizational Unit** - The Active Directory Domain Services (AD DS) organizational unit (OU).</span></span>
    
- <span data-ttu-id="d4ad5-115">**連合し、プールの間**のユーザーは、他のインスタント メッセージング (IM) サービスからのユーザーと通信できます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-115">**Federated / Cross Pool** - Users who can communicate with users from other Instant Messaging (IM) services.</span></span>
    
- <span data-ttu-id="d4ad5-116">**配布リスト**または Dl。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-116">**Distribution Lists** - Or DLs.</span></span> <span data-ttu-id="d4ad5-117">これらは、AD DS のユーザーの一覧が含まれている AD DS 内のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-117">These are objects in AD DS that contain a list of AD DS users.</span></span> <span data-ttu-id="d4ad5-118">ユーザーのグループ間での通信を容易にするために使用されています。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-118">They're used to facilitate communications across groups of people.</span></span>
    
- <span data-ttu-id="d4ad5-119">**場所情報サービス**のビジネス サーバー 2015 可能にするサービス、それが有効にされ、電話番号ごとに構成すると強化された 911 (E911) のサービスの物理的な場所を取得するために、Skype。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-119">**Location Info Service** - The Skype for Business Server 2015 service that, when it's enabled and configured per phone, allows for the retrieval of physical location for Enhanced 911 (E911) services.</span></span>
    
- <span data-ttu-id="d4ad5-120">**米国の電話番号**- 電話番号の着信および発信通話のルーティングを逆番号検索 (RNL) のために使用される SIP URI の他のユーザーに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-120">**U.S. Phone Numbers** - Phone numbers assigned to user in addition to the SIP URI that's used for routing inbound and outbound calls in Reverse Number Lookup (RNL).</span></span>
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="d4ad5-121">UserProvisioningTool.exe を使用してユーザーおよび連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-121">Create Users and Contacts by using UserProvisioningTool.exe</span></span>

> [!NOTE]
> <span data-ttu-id="d4ad5-122">開始する前にも、このツールを実行するのには、Domain Admins セキュリティ グループのメンバーとしてログオンしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-122">Before you even begin, be absolutely sure you're logged in as a member of the Domain Admins security group to run this tool.</span></span> <span data-ttu-id="d4ad5-123">Active Directory ユーザーを作成しようとしているため、これを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-123">You need to do this, because you're going to be creating Active Directory users.</span></span> 
  
<span data-ttu-id="d4ad5-124">ユーザーおよび連絡先の負荷のシミュレーションを作成する、Skype のビジネス サーバー ユーザーのプロビジョニング ツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-124">You have to use the Skype for Business Server User Provisioning Tool to create users and contacts for load simulation.</span></span>
  
<span data-ttu-id="d4ad5-125">**ビジネス サーバー ユーザーのプロビジョニング ツールの Skype**は、 **Skype**をビジネス ・ サーバの負荷とパフォーマンス ツールのパッケージと共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-125">The **Skype for Business Server User Provisioning Tool** is installed with the **Skype for Business Server Stress and Performance Tool** package.</span></span> <span data-ttu-id="d4ad5-126">フロント エンド サーバーまたは Standard Edition サーバーをテストするパッケージ インストーラー (CapacityPlanningTool.msi) が実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-126">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server you intend to test.</span></span>
  
<span data-ttu-id="d4ad5-127">フロント エンド サーバーまたは Standard Edition サーバー上で、(InstalledDirectory%LyncStressAndPerfTool\LyncStress である) UserProvisioningTool.exe ファイルを実行してビジネス サーバー ユーザーのプロビジョニング ツールを Skype を起動できます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-127">You can start the Skype for Business Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d4ad5-128">多数のユーザー (たとえば、10,000 以上) を作成するとき、UserProvisioningTool.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-128">When you create a large number of users (for example, 10,000 or more), run the UserProvisioningTool.exe.</span></span> <span data-ttu-id="d4ad5-129">ツールが作成され、*新しい*AD のユーザーを構成するためにこれを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-129">You'll need to do this because the tool will be creating and configuring  *new*  AD users.</span></span>
  
<span data-ttu-id="d4ad5-130">ユーザーのプロビジョニング ツールを開くと、[構成] をクリックし、負荷の構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-130">When the User Provisioning Tool opens, click Configuration and select the Load Configuration.</span></span> 
  
<span data-ttu-id="d4ad5-131">ユーザーおよび連絡先を構成するには、"SampleData.xml"と呼ばれる、パッケージに含まれる既定のファイルをロードします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-131">To begin configuring users and contacts, load the default file included with the package, called "SampleData.xml".</span></span> <span data-ttu-id="d4ad5-132">展開に関連する変更する必要がありますサンプル データを持つフィールドが事前に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-132">This will prepopulate fields with sample data that you'll need to change to make it relevant for your deployment.</span></span>
  
<span data-ttu-id="d4ad5-133">カスタマイズした設定が既に含まれている構成済みの XML ファイルがあれば、代わりにそのファイルを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-133">If you have a preconfigured XML file that already contains your customized settings, you can load that file instead.</span></span> <span data-ttu-id="d4ad5-134">以下のセクションで説明したように、ユーザーのプロビジョニング ツールでは、フィールドを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-134">Fill in the fields in the User Provisioning Tool, as described in the sections below.</span></span>
  
### <a name="to-configure-server-options"></a><span data-ttu-id="d4ad5-135">サーバー オプションを構成するには。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-135">To configure server options:</span></span>

1. <span data-ttu-id="d4ad5-136">**フロント エンド プールの FQDN** ] フィールドには、Standard Edition サーバー、またはユーザーをホストするフロント エンド プールの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-136">In the **Front End Pool FQDN** field, type the fully qualified domain name (FQDN) of the Standard Edition server, or the Front End pool where you want to host the users.</span></span>
    
2. <span data-ttu-id="d4ad5-137">**ユーザー名のプレフィックス**] フィールドに、ままの状態 ("TestUser") などの目的をテストするためのユーザー名に使用するプレフィックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-137">In the **User Name Prefix** field, type a prefix that you want to use to bust your user names for testing purposes (such as "TestUser").</span></span>
    
3. <span data-ttu-id="d4ad5-138">[**パスワード**] フィールドで、すべてのテスト ユーザー アカウントで使用されるパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-138">In the **Password** field, type a password that will be used across all the test user accounts.</span></span>
    
4. <span data-ttu-id="d4ad5-139">[**アカウントのドメイン**] フィールドで、現在の AD ドメインのドメイン名を入力します (テスト ユーザーを作成する 1 つ)。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-139">In the **Account Domain** field, type the domain name of your current AD domain (the one in which you want to create your test users).</span></span>
    
5. <span data-ttu-id="d4ad5-140">[**組織単位**] フィールドで、名前を入力、AD ドメインを作成するは、これらのテスト ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-140">In the **Organizational Unit** field, type the name of the AD domain where you want to create these test users.</span></span> <span data-ttu-id="d4ad5-141">(OU が存在しない場合は、それが作成)。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-141">(If the OU doesn't already exist, it'll be created for you).</span></span>
    
6. <span data-ttu-id="d4ad5-142">[**市外局番**] フィールドで、すべてのテスト ユーザー アカウントで使用するのには 3 桁の市外局番を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-142">In the **Phone Area Code** field, type the three-digit area code to be used across all test user accounts.</span></span> <span data-ttu-id="d4ad5-143">特定する他のユーザーの市外局番と市外局番] を選択したが競合しない AD。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-143">Make certain that the area code you chose doesn't conflict with other users' area codes in AD.</span></span>
    
7. <span data-ttu-id="d4ad5-144">エンタープライズ VoIP のテスト ユーザーを有効にする場合は、**音声を有効に**する] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-144">Click to select the **Voice Enabled** check box, if you want to enable the test users for Enterprise Voice.</span></span>
    
8. <span data-ttu-id="d4ad5-145">**ユーザー数**] フィールドに、テスト ユーザーを作成する場合の合計数を提供します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-145">In the **Number of Users** field, give the total number of test users you want to create.</span></span>
    
9. <span data-ttu-id="d4ad5-146">**インデックスの開始**] フィールドに、ユーザー名のプレフィックス、サフィックスとして使用することを開始番号を与える (などのプレフィックスは"TestUser"、最初の名前は次の例では「0」で終了)</span><span class="sxs-lookup"><span data-stu-id="d4ad5-146">In the **Start Index** field, give the starting number that'll be used as a suffix to the user name prefix (for example, the prefix is "TestUser", and the first name will end in "0" in the example below.)</span></span>
    
     ![[User Creation] タブを表示している User Provisioning Tool](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a><span data-ttu-id="d4ad5-148">ユーザー ボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-148">Create Users button</span></span>

<span data-ttu-id="d4ad5-149">**ユーザーの作成**] ボタンをクリックすると、入力されている入力パラメーターが検証されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-149">When you click on the **Create Users** button, the input parameters you've entered are validated.</span></span> <span data-ttu-id="d4ad5-150">検証エラーがある場合は、それらを修正するように求めします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-150">If there are any validation errors, you'll be prompted to fix them.</span></span> <span data-ttu-id="d4ad5-151">または、ユーザーが表示される起動のすべての値が正しい場合は、(指定した OU がどの) で AD にします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-151">Or, if all the values are correct, users will start appearing in AD (in whichever OU you specified).</span></span> <span data-ttu-id="d4ad5-152">実行時にツールの下部にある進行状況バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-152">You'll see a progress bar at the bottom of the tool as it runs.</span></span> <span data-ttu-id="d4ad5-153">進行状況バーがアクティブなときに、アプリケーションを終了しません。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-153">Don't close the application while the progress bar is active.</span></span>
  
<span data-ttu-id="d4ad5-154">ユーザーの作成に時間がかかり、のでそれに応じて計画をしてください。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-154">User creation takes time, so please plan accordingly.</span></span> <span data-ttu-id="d4ad5-155">このプロセス時間かかることが任意の場所の少数のユーザーでは、数分から、いくつかユーザーの数が多いのです。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-155">This process can take anywhere from several minutes for a few users, to a few hours for a large number of users.</span></span>
  
<span data-ttu-id="d4ad5-156">テスト環境内の AD ドメイン コント ローラーにアクセスする必要はありません、いずれかの範囲を作成するように指定したユーザーのユーザーとしてログインすることによりユーザーの作成を検証もできます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-156">If you don't have access to the AD Domain Controller in your test environment, you can still validate user creation by logging in as one of the users in the range of users you specified to create.</span></span> <span data-ttu-id="d4ad5-157">、プレフィックスと、ユーザー名と @sipDomain のほかに、サフィックスを使用することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-157">Remember to use the prefix, and the suffix, along with the @sipDomain as the username.</span></span> <span data-ttu-id="d4ad5-158">例を次のとおりです: <em>TestUser20@contoso.net</em> 。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-158">Here is an example:  <em>TestUser20@contoso.net</em>  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4ad5-159">ユーザーが既に存在する場合、ユーザーの作成] ボタンをクリックするとに更新されます構成変更によって。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-159">If the users already exist, clicking the Create Users button will update them with any configuration changes.</span></span> 
  
#### <a name="delete-users-button"></a><span data-ttu-id="d4ad5-160">ユーザー ボタンを削除します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-160">Delete Users button</span></span>

<span data-ttu-id="d4ad5-161">**ユーザーの削除**] ボタンをクリックするとタブの入力パラメーターが検証されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-161">When you click on the **Delete Users** button, the tab's input parameters will be validated.</span></span> <span data-ttu-id="d4ad5-162">検証エラーがある場合がするが表示されたら、それらを修正して、入力値が正しい場合は、指定したテスト用ユーザー無効になっているし、する Active Directory から削除します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-162">If there are validation errors, you'll be prompted to fix them, and if the input values are correct, the specified test users will be disabled and deleted from Active Directory.</span></span> <span data-ttu-id="d4ad5-163">もう一度、進行状況バーは、このタブの下部に表示され、進行状況バーがアクティブなときにアプリケーションを閉じる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-163">Again, a progress bar will appear on the bottom of this tab, and you shouldn't close the application while the progress bar is active.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4ad5-164">米国形式の電話番号だけがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-164">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="d4ad5-165">電話番号は常に、ユーザーに割り当てられているし、UserProvisioningTool.exe によって作成されたすべてのユーザーは既定でエンタープライズ VoIP を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-165">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice by default.</span></span> <span data-ttu-id="d4ad5-166">会議自動応答または UC PSTN の呼び出しなどの電話番号を使用するすべてのシナリオでは、呼び出しを正しくルーティングするのにはこの電話番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-166">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="d4ad5-167">このため、*すべてのユーザー*に*一意の電話番号*が必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-167">For this reason,  *every user*  must have a *unique phone number*  .</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4ad5-168">**ユーザーを 2 回作成する必要があるが、別の市外局番を使用する場合を除き、または無効にする CsUser コマンドレットを使用して、以前のユーザーを無効になっている場合、コマンドが失敗します。**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-168">**If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the Disable-CsUser cmdlet.**</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d4ad5-169">連絡先を作成する前に (これは、[ユーザー] タブから) ユーザーの複製を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-169">Before you create contacts, you first need to complete user replication (which is done from the Users tab).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d4ad5-170">ユーザーを作成した場合は、Skype ビジネス サーバーのレプリケーションが完了し、データベース内のユーザー アカウントを作成するまで待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-170">If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="d4ad5-171">**ユーザーの複製が終了していない、エラーが表示されます。**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-171">**If the users haven't finished replicating, you'll see an error.**</span></span> <span data-ttu-id="d4ad5-172">ユーザーは、Skype のビジネス サーバー 2015 のフロント エンド サービスが開始されている場合の複製したら、または指定した合計の番号の最後のユーザーを正常に取得 CsUser コマンドレットを実行してがわかります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-172">You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.</span></span>
  
#### <a name="contacts-creation-tab"></a><span data-ttu-id="d4ad5-173">連絡先の作成] タブ</span><span class="sxs-lookup"><span data-stu-id="d4ad5-173">Contacts Creation tab</span></span>

<span data-ttu-id="d4ad5-174">このタブでは、テストのユーザーの連絡先の詳細情報を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-174">This tab lets you give users' contacts details for your testing.</span></span>
  
![[Contents Creation] タブを表示している User Provisioning Tool](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a><span data-ttu-id="d4ad5-176">ユーザーの連絡先を構成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-176">To configure users' contacts, do the following:</span></span>

1. <span data-ttu-id="d4ad5-177">**ユーザー 1 人あたりの平均連絡先**フィールドに、各ユーザーの連絡先リストに表示する連絡先の数の平均値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-177">In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.</span></span>
    
2. <span data-ttu-id="d4ad5-178">数が等しいすべてのユーザーの連絡先を作成する場合は、[**固定**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-178">Select the **Fixed** check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="d4ad5-179">ユーザー用に作成された連絡先の数を変更する場合は、チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-179">If you want to vary the number of contacts created for users, clear that check box.</span></span>
    
3. <span data-ttu-id="d4ad5-180">**ユーザーごとの平均の連絡先グループ**] フィールドに、ユーザーごとの連絡先グループの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-180">In the **Average Contact Groups per User** field, enter the number of contact groups per user.</span></span> <span data-ttu-id="d4ad5-181">この番号は、**ユーザーごとの連絡先の平均**よりも小さくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-181">This number needs to be smaller than **Average Contacts per User**.</span></span>
    
4. <span data-ttu-id="d4ad5-182">**連合/間のプール連絡先の割合**] フィールドに、0 から 100 までの数字を提供します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-182">In the **Federated / Cross Pool Contacts Percentage** field, give a number between 0 and 100.</span></span> <span data-ttu-id="d4ad5-183">フェデレーション ユーザーとの取引先担当者は、この割合が作成されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-183">This percentage of contacts will be created with the federated users.</span></span>
    
5. <span data-ttu-id="d4ad5-184">**連合/クロス プール ユーザー プレフィックス**] フィールドに、ローカル ユーザーの連絡先リストに追加されるフェデレーション ユーザーのユーザー名を提供します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-184">In the **Federated / Cross Pool User Prefix** field, give the username for federated users that will be added to the contact lists of local users.</span></span>
    
6. <span data-ttu-id="d4ad5-185">**連合/プール ユーザーの SIP ドメインを越える**フィールドに、フェデレーション ユーザーの SIP ドメイン名を提供します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-185">In the **Federated / Cross Pool User SIP Domain** field, give the SIP Domain Name of the federated users.</span></span>
    
7. <span data-ttu-id="d4ad5-186">**ユーザーの作成**] タブで、情報が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-186">In **User Creation** tab make sure the information is correct.</span></span> <span data-ttu-id="d4ad5-187">連絡先は、ユーザーの作成] タブ上の値から作成されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-187">Your contacts will be created from values on the User Creation tab.</span></span>
    
8. <span data-ttu-id="d4ad5-188">連絡先の作成を開始するのには**連絡先の作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-188">Click **Create Contacts** to begin the contact creation.</span></span> <span data-ttu-id="d4ad5-189">このプロセスには数分かかることができます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-189">This process can take several minutes.</span></span> <span data-ttu-id="d4ad5-190">それが完了した後、メッセージがダイアログ ボックスが表示されます「操作が完了正常にします。」</span><span class="sxs-lookup"><span data-stu-id="d4ad5-190">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="d4ad5-191">ユーザーの作成] タブから作成されたユーザーとしてログオンし、作成された連絡先を検証することができます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-191">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d4ad5-192">連絡先が作成されると、このツールは、ターゲット ・ プールのすべてのフロント エンド サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-192">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="d4ad5-193">によって顧客の数は、この操作によって作成された長い時間 (最大 2 時間) を開始するには、フロント エンド サーバーをかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-193">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span> 
  
#### <a name="distribution-list"></a><span data-ttu-id="d4ad5-194">配布リスト</span><span class="sxs-lookup"><span data-stu-id="d4ad5-194">Distribution List</span></span>

<span data-ttu-id="d4ad5-195">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype では、ビジネス 2015年クライアントの Skype での配布リスト (DL) の拡張機能をシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-195">The Skype for Business Server 2015 Stress and Performance Tool can simulate the Distribution List (DL) expansion feature in the Skype for Business 2015 client.</span></span> <span data-ttu-id="d4ad5-196">ユーザー プロビジョニング ツールで、配布リストの展開を有効にしない場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-196">You can skip this step if you don't intend to enable DL expansion in the User Provisioning tool.</span></span>
  
![[Distribution List Creation] タブを表示している User Provisioning Tool](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
<span data-ttu-id="d4ad5-198">配布リスト] タブを使用すると、配布リストの展開機能のストレスおよびパフォーマンス ツールを使用する配布リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-198">The Distribution List tab allows you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="d4ad5-199">配布リストを作成する前にビジネス サーバー 2015 の Skype が必要となる、ForestPrep を実行することを含みます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-199">Before creating DLs, Skype for Business Server 2015 needs to be deployed, including having run ForestPrep.</span></span> <span data-ttu-id="d4ad5-200">、実行されていない場合、配布リストの属性は存在しません、AD スキーマのツールは、配布リストを作成するのにはできませんので。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-200">If this isn't done, the DL attributes will not exist in the AD schema, so the tool won't be able to create DLs.</span></span>
  
### <a name="to-configure-distribution-lists"></a><span data-ttu-id="d4ad5-201">配布リストを構成するには。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-201">To configure Distribution Lists:</span></span>

1. <span data-ttu-id="d4ad5-202">**配布リスト数**] フィールドに、作成する配布リストの合計数を指定します (ここでお勧めするユーザー数の 2 倍の値で開始すること。)。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-202">In the **Number of Distribution Lists** field, give the total number of DLs you want to create (The recommendation here is that you start with a value that is double the number of users you have.).</span></span>
    
2. <span data-ttu-id="d4ad5-203">**配布リストのプレフィックス**] フィールドに、作成するすべての配布リストがある、プレフィックス、 *testDL*などを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-203">In the **Distribution List Prefix** field, enter a prefix that all the DLs you create will have, for example *testDL*  .</span></span> <span data-ttu-id="d4ad5-204">100 の Dl で、つまり、配布リスト名のようになります: testDL0、testDL1、testDL99 まで。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-204">That means, at 100 DLs, your DL names will look like: testDL0, testDL1, up to testDL99.</span></span>
    
3. <span data-ttu-id="d4ad5-205">**版リストの最小のメンバー** ] フィールドに、各配布リストにユーザーの最小数を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-205">In the **Minimum Members in a Dist. List** field, enter the minimum number of users to put in each DL.</span></span>
    
4. <span data-ttu-id="d4ad5-206">**版リストの最大のメンバー** ] フィールドに、各配布リストに追加するユーザーの最大数を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-206">In the **Maximum Members in a Dist. List** field, enter the maximum number of users to add in each DL.</span></span>
    
#### <a name="create-distribution-lists-button"></a><span data-ttu-id="d4ad5-207">配布リスト] ボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-207">Create Distribution Lists button</span></span>

<span data-ttu-id="d4ad5-208">配布リストの作成] ボタンをクリックするとツールは、配布リストをプリフィックスと番号が既に存在と一致するかどうかを確認するのには Active Directory を照会します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-208">When you click the Create Distribution Lists button, the tool queries Active Directory to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="d4ad5-209">ツールは、既に存在しないこれらの Dl を作成します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-209">The tool creates any DLs that don't already exist.</span></span> <span data-ttu-id="d4ad5-210">メンバーを追加する配布リストを新しく作成された、ときに、ユーザーの作成] タブで指定された範囲からユーザーを選択にします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-210">When adding members to these newly created Distribution Lists, it'll choose the users from the range specified on the User Creation tab.</span></span>
  
#### <a name="location-info-service-config-tab"></a><span data-ttu-id="d4ad5-211">場所情報サービスの構成] タブ</span><span class="sxs-lookup"><span data-stu-id="d4ad5-211">Location Info Service Config tab</span></span>

<span data-ttu-id="d4ad5-212">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype では、場所情報サービスのダミーの構成ファイルを生成することも。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-212">The Skype for Business Server 2015 Stress and Performance Tool can also generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="d4ad5-213">場所情報サービス通常はパフォーマンスに大きな影響であるサーバーに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-213">Note that the Location Information Service typically doesn't have significant performance impact on the servers.</span></span> 
  
![[Location Info Service Config] タブを表示している User Provisioning Tool](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
<span data-ttu-id="d4ad5-215">この機能をテストする場合は、フォーム内の値を入力し、LIS 構成ファイルの生成] ボタンをクリックを作成します。CSV ファイルと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-215">If you choose to test this feature, fill in the values in the form and click the Generate LIS Config Files button, which will create .CSV files called:</span></span>
  
- <span data-ttu-id="d4ad5-216">LIS_Subnet.csv</span><span class="sxs-lookup"><span data-stu-id="d4ad5-216">LIS_Subnet.csv</span></span>
    
- <span data-ttu-id="d4ad5-217">LIS_Switches.csv</span><span class="sxs-lookup"><span data-stu-id="d4ad5-217">LIS_Switches.csv</span></span>
    
- <span data-ttu-id="d4ad5-218">LIS_Ports.csv</span><span class="sxs-lookup"><span data-stu-id="d4ad5-218">LIS_Ports.csv</span></span>
    
- <span data-ttu-id="d4ad5-219">LIS_WAP.csv</span><span class="sxs-lookup"><span data-stu-id="d4ad5-219">LIS_WAP.csv</span></span>
    
<span data-ttu-id="d4ad5-220">インポートするのには、LIS データベースにこれらのファイルは、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-220">To import these files into the LIS database use these PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="d4ad5-221">セット CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="d4ad5-221">Set-CsLisSubnet</span></span>
    
- <span data-ttu-id="d4ad5-222">セット CsLisSwitch</span><span class="sxs-lookup"><span data-stu-id="d4ad5-222">Set-CsLisSwitch</span></span>
    
- <span data-ttu-id="d4ad5-223">セット CsLisPort</span><span class="sxs-lookup"><span data-stu-id="d4ad5-223">Set-CsLisPort</span></span>
    
- <span data-ttu-id="d4ad5-224">セット CsWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="d4ad5-224">Set-CsWirelessAccessPoint</span></span>
    
## <a name="configure-user-profile"></a><span data-ttu-id="d4ad5-225">ユーザー プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-225">Configure User Profile</span></span>
<span data-ttu-id="d4ad5-226"><a name="BKMK_UserProfile"> </a></span><span class="sxs-lookup"><span data-stu-id="d4ad5-226"></span></span>

<span data-ttu-id="d4ad5-227">(ユーザー作成ツール) を使用して、ユーザーが作成された後は、ビジネス サーバー 2015 負荷構成ツール (UserProfileGenerator.exe) の Skype でユーザー プロファイルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-227">After your users are created (via the User Creation Tool) you can configure user profiles with the Skype for Business Server 2015 Load Configuration tool (UserProfileGenerator.exe).</span></span>
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a><span data-ttu-id="d4ad5-228">ビジネス サーバー 2015 の読み込みの構成ツールの Skype を実行しています。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-228">Running the Skype for Business Server 2015 Load Configuration tool</span></span>

<span data-ttu-id="d4ad5-229">負荷の構成ツール (UserProfileGenerator.exe) を起動し、タブを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-229">Start the Load Configuration tool (UserProfileGenerator.exe) and fill in the tabs.</span></span> <span data-ttu-id="d4ad5-230">このツールは、シミュレーションを実行する必要があるコンピューター、クライアントごとにディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-230">This tool creates a directory for each of the client computers that you'll need to run your simulations.</span></span> <span data-ttu-id="d4ad5-231">各クライアントのディレクトリには、ビジネス サーバー 2015 のストレスおよびパフォーマンス ツール (LyncPerfTool.exe) は、Skype を起動するためのスクリプトが付属しています。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-231">Each client directory comes with a script to start the Skype for Business Server 2015 Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="d4ad5-232">以下のセクションでは、ビジネス サーバー 2015 の読み込みの構成ツールの Skype の各タブのフィールドに入力する方法の例を提供します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-232">The sections below will give examples of how to fill in the fields on each tab of the Skype for Business Server 2015 Load Configuration tool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d4ad5-233">負荷の構成ツール (UserProfileGenerator.exe) で使用されるユーザー固有の値は、プールのビジネス サーバー 2015 ユーザー作成ツール (UserProvisioningTool.exe) は、Skype で指定した値に一致しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-233">The user-specific values used in the Load Configuration tool (UserProfileGenerator.exe) must match the values specified in the Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) for the pool.</span></span> 
  
#### <a name="common-configuration-tab"></a><span data-ttu-id="d4ad5-234">共通の構成] タブ</span><span class="sxs-lookup"><span data-stu-id="d4ad5-234">Common Configuration tab</span></span>

<span data-ttu-id="d4ad5-235">負荷の構成ツールの**一般的な設定**] タブを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-235">The **Common Configuration** tab of the Load Configuration Tool is shown below.</span></span> <span data-ttu-id="d4ad5-236">次の手順で説明したように、共通の設定] タブのフィールドを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-236">Fill in the fields of the Common Configuration tab, as described in the following steps.</span></span>
  
![[Common Configuration] タブを表示している [User Provisioning] タブ](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. <span data-ttu-id="d4ad5-238">**使用可能なマシンの数**」フィールドには、ストレスおよびパフォーマンス ツール (LyncPerfTool.exe) の実行に使用するコンピューターの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-238">In the **Number of Available Machines** field, type the number of computers you want to use to run the Stress and Performance tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="d4ad5-239">シミュレートすることがあります、4500 のユーザーごとに 1 台のコンピューターがあるが、負荷のレベルを削減またはツールの使用可能な機能が (一般的なシナリオ] タブで設定されている負荷レベル) のサブセットのみを使用する場合、その番号は異なる場合がありますをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-239">We recommend that you have one computer for every 4500 users you'll be simulating, but that number may vary if you reduce the load level, or use only a subset of the tool's available features (Load levels are set on the General Scenarios tab).</span></span>
    
2. <span data-ttu-id="d4ad5-240">**ユーザー名のプレフィックス**] フィールドに、すべてのユーザーのユーザー名フィールドのプレフィックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-240">In the **Prefix for User Names** field, enter a prefix for the user name field of all users.</span></span> <span data-ttu-id="d4ad5-241">統一リソース識別子 (URI) をログに記録されます: *UserPrefix [ユーザーの開始インデックス。(ユーザー 1 の数)]@User ドメイン*は、myUser009@Contoso.com です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-241">To log in the Uniform Resource Identifier (URI) will be: *UserPrefix[User Start Index…(Number Of Users-1)]@User Domain*  , for example, myUser009@Contoso.com.</span></span>
    
3. <span data-ttu-id="d4ad5-242">**すべてのユーザーのパスワード**フィールドに、ユーザーの作成時に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-242">In the **Password for All Users** field, enter the password used during creation of the users.</span></span> <span data-ttu-id="d4ad5-243">このフィールドを空のままにする場合は、パスワードとユーザー名が設定されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-243">If you leave this field empty the username will be set as the password.</span></span>
    
4. <span data-ttu-id="d4ad5-244">**ユーザー開始インデックス**フィールドで構成する最初のユーザーのインデックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-244">In the **User Start Index** field, enter the index of the first user to be configured.</span></span> <span data-ttu-id="d4ad5-245">さまざまな種類のレベルの負荷を複数の範囲を構成することができますが、範囲ごとに構成すると、読み込む構成ツール (UserProfileGenerator.exe) を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-245">You can configure different ranges for different types or levels of load, but you must run the Load Configuration tool (UserProfileGenerator.exe) once per the range you want to configure.</span></span>
    
5. <span data-ttu-id="d4ad5-246">[**ユーザー数**] フィールドで構成しようとしているユーザーの合計数を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-246">In the **Number of Users** field, enter the total number of users you're going to configure.</span></span>
    
6. <span data-ttu-id="d4ad5-247">**ユーザー ドメイン**フィールドに、SIP URI に使用するドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-247">In the **User Domain** field, enter the domain used for the SIP URI.</span></span> <span data-ttu-id="d4ad5-248">これは、ビジネス 2015 フロント エンド サーバーまたは Standard Edition サーバーでは、Skype にログオンする各ユーザーの SIP URI を構築するために使用し、アカウントのドメインと異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-248">This is used to construct the SIP URI of each user to log on to the Skype for Business Server 2015 Front End Server or Standard Edition server, and may be different from the Account Domain.</span></span>
    
7. <span data-ttu-id="d4ad5-249">[**アカウントのドメイン**] フィールドで、AD DS ドメインへのログオンを入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-249">In the **Account Domain** field, enter the AD DS domain logon.</span></span>
    
8. <span data-ttu-id="d4ad5-250">**MPOP 割合**(複数のプレゼンス ポイントの割合)] フィールドに、複数のコンピューターまたはデバイス、たとえば 10% からログオンしているユーザーの割合の値を提供します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-250">In the **MPOP Percentage** (Multiple Point of Presence percentage) field, give a value for the percentage of users that are logged on from multiple machines or devices, for example 10 percent.</span></span>
    
9. <span data-ttu-id="d4ad5-251">**あたり 2 つ目 (インスタンス) ごとに署名**フィールドに、同時実行のエンドポイントの最大数を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-251">Enter the maximum number of concurrent endpoints in the **Sign in Per Second (per Instance)** field.</span></span> <span data-ttu-id="d4ad5-252">これは、最大数は、ユーザーのログインし、1 秒あたり 2 と同じまたはそれより小さい数をお勧め (_lt _ = 2)。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-252">This is the maximum number of log ins for your users, and the recommendation is a rate of less than/equal to 2 per second (<=2).</span></span>
    
10. <span data-ttu-id="d4ad5-253">[**アクセス プロキシまたはプールの FQDN** ] フィールドでは、クライアントに接続するサーバーの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-253">In the **Access Proxy or Pool FQDN** field, enter the fully qualified domain name (FQDN) of the server you want the clients to connect to.</span></span> <span data-ttu-id="d4ad5-254">ユーザーがログオンに外部から、アクセス プロキシを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-254">If the users are logging on externally, you'll need to type the access proxy.</span></span> <span data-ttu-id="d4ad5-255">ユーザーが内部の場合は、エンタープライズ プールまたは Standard Edition サーバーの FQDN を提供します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-255">If the users are internal, give the FQDN of their Enterprise Pool or Standard Edition server.</span></span>
    
11. <span data-ttu-id="d4ad5-256">**[ポート**] フィールドで、ユーザーの SIP を使用するポートを入力します (ここでの既定は 5061 です)。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-256">In the **Port** field, enter the port that you want users to use for SIP (the default here is 5061).</span></span>
    
12. <span data-ttu-id="d4ad5-257">**外部のネットワーク サーバーの設定**のフィールドには、アクセス プロキシまたはプールの FQDN と、もう一度、**ポート**を提供します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-257">For the **External Network Server Settings** field, give the Access Proxy or Pool FQDN and, again, the **Port**.</span></span> <span data-ttu-id="d4ad5-258">これらの設定は、外部エンドポイントの負荷のシミュレーションにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-258">These settings are used only for External endpoints load simulation.</span></span>
    
#### <a name="general-scenarios-tab"></a><span data-ttu-id="d4ad5-259">シナリオの [全般] タブ</span><span class="sxs-lookup"><span data-stu-id="d4ad5-259">General Scenarios tab</span></span>

![[General Scenarios] タブを表示している Load Configuration Tool](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
<span data-ttu-id="d4ad5-261">実行するか、無効のままにする対象を決定することにより提供される一般的なシナリオのそれぞれについて、負荷のレベルとパラメーターを設定できます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-261">You can configure the load levels and parameters for each of the general scenarios offered by determining what you want to run or leave disabled.</span></span> <span data-ttu-id="d4ad5-262">全般的なオプションを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-262">Here are your general options:</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4ad5-263">負荷が、すべてのフィールド、ローカルのインフォメーション サービスのレベルの値は、**無効になっている**、**低**、**中**、**高**、または**カスタム**です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-263">Load level values for all fields but Local Information Services are **Disabled**, **Low**, **Medium**, **High**, or **Custom**.</span></span> <span data-ttu-id="d4ad5-264">無効になっているのですが、任意の設定を選択する場合は、構成をクライアントごとに生成されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-264">If you select any setting but Disabled, then configurations are generated for each client.</span></span> <span data-ttu-id="d4ad5-265">サーバーでサポートされている最大の負荷の高い結果[中] は、60% の負荷が高いです。30% は低いのです。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-265">High results in the max supported load on the server; medium is 60% of high load; low is 30%.</span></span> 
  
- <span data-ttu-id="d4ad5-266">**インスタント メッセージングでは、** ピア ツー ピアおよび会議。負荷のレベルの適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-266">**Instant Messaging -** This includes peer-to-peer and conferencing; choose the appropriate value for Load Level.</span></span>
    
- <span data-ttu-id="d4ad5-267">**オーディオ会議-** オーディオ会議*のみ*の負荷レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-267">**Audio Conferencing -** Choose a load level for audio conferencing *only*  .</span></span> <span data-ttu-id="d4ad5-268">ピア ツー ピアの呼び出しは、**音声のシナリオ**に記載後、もう少し対処が。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-268">Peer-to-peer calls will be tackled a little later in the **Voice Scenarios** section.</span></span> <span data-ttu-id="d4ad5-269">マルチビューを有効にするのには [**詳細設定**] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-269">Open the **Advanced** tab to enable MultiView.</span></span>
    
- <span data-ttu-id="d4ad5-270">**アプリケーションの共有-** アプリケーションを共有するための負荷レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-270">**Application Sharing -** Choose a load level for application sharing.</span></span>
    
- <span data-ttu-id="d4ad5-271">**データの共同作業-** データ会議に含まれるデータの共同作業の負荷レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-271">**Data Collaboration -** Choose a load level for data collaboration, which includes data conferencing.</span></span>
    
- <span data-ttu-id="d4ad5-272">**配布リストの展開-\*\*\*\*[詳細**] ボタンをクリックし、ユーザー作成ツール (UserProvisioningTool.exe) の [配布リスト] タブで構成されている同じ値を持つフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-272">**Distribution List Expansion -** Click the **Advanced** button and fill in the field with the same values configured on the DL tab of the User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="d4ad5-273">負荷のレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-273">Choose a load level.</span></span>
    
- <span data-ttu-id="d4ad5-274">**アドレス帳 Web クエリ**これは、アドレス帳ファイルのダウンロードではなく、アドレス帳の検索サービスです。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-274">**Address Book Web Query -** This is the address book lookup service rather than the address book file download.</span></span> <span data-ttu-id="d4ad5-275">場合は、[**詳細設定**] ボタンをクリックしてアドレス帳ファイルのダウンロードを有効にして、 **EnableABSDownload**を True に設定します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-275">If you want to enable this for address book file downloads, click the **Advanced** button and set **EnableABSDownload** to True.</span></span> <span data-ttu-id="d4ad5-276">負荷レベルの値を提供します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-276">Give a value for load level.</span></span>
    
- <span data-ttu-id="d4ad5-277">**応答グループ サービス-\*\*\*\*[詳細**] ボタンをクリックし、応答グループ サービスのエージェントを提供した場合を既に作成した応答グループの Uri を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-277">**Response Group Service -** Click the **Advanced** button and specify the URIs of the response groups you already created when you provisioned Response Group Service agents.</span></span> <span data-ttu-id="d4ad5-278">少なくとも 1 つの応答グループを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-278">You must choose at least one response group.</span></span> <span data-ttu-id="d4ad5-279">使用するには複数の応答グループ セミコロンで区切ります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-279">To use more, separate the response groups with semicolons.</span></span> <span data-ttu-id="d4ad5-280">**RGSUriSuffixStartIndex**と**RGSUriSuffixEndIndex**を実際の値に更新します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-280">Update **RGSUriSuffixStartIndex** and **RGSUriSuffixEndIndex** to the actual values.</span></span> <span data-ttu-id="d4ad5-281">負荷のレベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-281">Choose a load level.</span></span>
    
- <span data-ttu-id="d4ad5-282">**場所情報サービス-** 有効または無効のいずれかの負荷レベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-282">**Location Information Services -** Select a load level of either Enabled or Disabled.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d4ad5-283">シナリオのそれぞれには、[詳細設定]、および一連の既定の設定のバリエーションを可能にする] チェック ボックスの横にあります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-283">Each of the scenarios has an Advanced button located next to it, and a set of check boxes that enable variations to the default setting.</span></span> 
  
- <span data-ttu-id="d4ad5-284">*メッセージング システム*を選択すると、1 時間全体にわたって作成される会議のシミュレーションを生成するツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-284">Choosing  *Ad-hoc*  will allow the tool to generate simulation of conferences that will be created throughout the hour.</span></span>
    
- <span data-ttu-id="d4ad5-285">選択する*大規模な Conf*では、大規模な会議のシナリオをシミュレートすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-285">Choosing  *Large Conf*  means that a Large Conference Scenario will be simulated.</span></span>
    
-  <span data-ttu-id="d4ad5-286">外部のユーザーをシミュレートするツールを*外部*に通知します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-286">*External*  tells the tool to also simulate external users.</span></span>
    
<span data-ttu-id="d4ad5-287">これらのボタンとチェック ボックスは、各シナリオに固有の追加の値はストレスおよびパフォーマンス ツールの動作を変更し、カスタマイズを可能にします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-287">These buttons and check boxes are extra values specific to each scenario and will change the behavior of the Stress and Performance Tool and make customization possible.</span></span>
  
<span data-ttu-id="d4ad5-288">(位置情報サービス) を除く、一般的なシナリオ] タブで各シナリオでは、負荷のレベルの値が**カスタム**の場合、会話率を計算する、[詳細設定] ダイアログ ボックス内の対応するフィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-288">For each scenario on the General Scenarios tab (except for Location Information Services), if the value of Load Level is **Custom**, then the conversation rate will be calculated using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="d4ad5-289">状況によって、フィールド名が異なる場合がありますが、状態は、フィールドの説明:*メモこの番号は、ドロップ ダウン メニューからカスタムを選択した場合のみ使用されます*。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-289">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
<span data-ttu-id="d4ad5-290">会話の単価は、すべてのシナリオのバランスをユーザー モデルには、モーダルかどうかは、**高\*\*\*\*中\*\*\*\*低**値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-290">The values **High**, **Medium**, and **Low**, will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="d4ad5-291">予想される使用率の違いのモダリティごとの負荷レベルを変更する必要がある場合は、カスタム テーマのレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-291">If there's a need to change the load level per modality due to a difference in expected usage, use a Custom conversation rate.</span></span>
  
#### <a name="voice-scenarios-tab"></a><span data-ttu-id="d4ad5-292">音声シナリオ] タブ</span><span class="sxs-lookup"><span data-stu-id="d4ad5-292">Voice Scenarios tab</span></span>

<span data-ttu-id="d4ad5-293">これは、すべてのボイスに関連するシナリオの構成のタブです。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-293">This is the tab for configuration of all your voice-related scenarios.</span></span>
  
![Load Configuration Tool の [Voice Scenarios] タブ](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
<span data-ttu-id="d4ad5-295">オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-295">Your options are:</span></span>
  
- <span data-ttu-id="d4ad5-296">**VoIP-\*\*\*\*[詳細**] ボタンをクリックし、PhoneAreaCode と LocationProfile (ダイヤル プラン) フィールドの値を追加します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-296">**VoIP -** Click the **Advanced** button and add values for the PhoneAreaCode and LocationProfile (dial plan) fields.</span></span> <span data-ttu-id="d4ad5-297">負荷のレベルにも値を提供します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-297">You'll also give a value for Load Level.</span></span> <span data-ttu-id="d4ad5-298">統合コミュニケーション (UC) に VoIP または UC または PSTN ゲートウェイを有効にし、公衆交換電話網 (PSTN) の負荷レベルを選択する場合は、外部の呼び出しをシミュレートするために構成ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-298">If you choose a load level for VoIP or UC/PSTN Gateway enabled, then a public-switched telephone network (PSTN) to unified communications (UC) configuration file will be generated to simulate external calls.</span></span>
    
- <span data-ttu-id="d4ad5-299">**UC または PSTN ゲートウェイ-** 負荷レベルの値を選択する必要があり、無効になっている以外の何かを選択するともあれば、[**詳細設定**] ボタンをクリックすると、PSTN の市外局番の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-299">**UC/PSTN Gateway -** You need to choose a Load Level value, and when you choose anything other than Disabled, you've also got to supply a value for PSTN area code by clicking the **Advanced** button.</span></span> <span data-ttu-id="d4ad5-300">仲介サーバーと PSTN の下の [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-300">Click **Add** under the Mediation Server and PSTN.</span></span> <span data-ttu-id="d4ad5-301">市外局番で構成されているルートがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-301">Make sure you have a route configured for the area code.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="d4ad5-302">ボイス ルートの構成を確認するのには、ビジネス コントロール パネルまたはビジネス管理シェルの Skype のいずれかの Skype を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-302">You can use either the Skype for Business Control Panel or Skype for Business Management Shell to verify your voice route configuration.</span></span> 
  
- <span data-ttu-id="d4ad5-303">**会議アテンダント-** 負荷レベルの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-303">**Conferencing Attendant -** Supply a value for Load Level.</span></span> <span data-ttu-id="d4ad5-304">無効以外の値には、**電話番号**フィールドが有効になります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-304">Any value other than Disabled will enable the **Telephone Number** field.</span></span> <span data-ttu-id="d4ad5-305">使用する自動応答の電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-305">Enter the phone number of the Auto Attendant you want to use.</span></span> <span data-ttu-id="d4ad5-306">[**詳細設定**] をクリックし、 **LocationProfile**フィールドの値を提供します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-306">Click **Advanced** and give a value for the **LocationProfile** field.</span></span>
    
- <span data-ttu-id="d4ad5-307">**駐車サービス-** ここでは、負荷のレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-307">**Call Parking Service -** Here, supply a Load Level.</span></span>
    
- <span data-ttu-id="d4ad5-308">**仲介サーバーおよび PSTN**各仲介サーバーを使用するには、独自の PSTN のシミュレータが必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-308">**Mediation Server and PSTN -** Each Mediation Server that you want to use needs its own PSTN simulator.</span></span> <span data-ttu-id="d4ad5-309">クライアント シミュレータを使用することを決定した後構成をルーティングするように仲介サーバーを呼び出すそのコンピューターに PSTN シミュレータでするように構成します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-309">After you've determined which client you're going to use for the simulator, configuration your Mediation Server to route calls to that computer on the PSTN Simulator you configured.</span></span> <span data-ttu-id="d4ad5-310">仲介サーバーの値を構成するのには [**追加**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-310">Click the **Add** button to configure a value for the Mediation Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d4ad5-311">各シナリオでは、その横にある高度なボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-311">Each scenario has an Advanced button located next to it.</span></span> <span data-ttu-id="d4ad5-312">[詳細設定] ダイアログ ボックスには、ストレスおよびパフォーマンス ツールの動作を変更し、カスタマイズを有効にする各シナリオに固有設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-312">Advanced dialog boxes contain settings specific to each scenario that change the behavior of the Stress and Performance Tool and enable customization.</span></span> <span data-ttu-id="d4ad5-313">_gt ボイス シナリオ] タブで、負荷のレベルの値が**カスタム**の場合は、会話の速度の場合に、各シナリオについては、[詳細設定] ダイアログ ボックスで、対応するフィールドを使用して計算されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-313">> For each scenario on the Voice Scenarios tab, if the value of Load Level is **Custom**, then the conversation rate will be calculated by using the corresponding field in the Advanced dialog box.</span></span> <span data-ttu-id="d4ad5-314">状況によって、フィールド名が異なる場合がありますが、状態は、フィールドの説明:*メモこの番号は、ドロップ ダウン メニューからカスタムを選択した場合のみ使用されます*。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-314">The field name may differ, depending on the scenario, but the field description will state:  *NOTE This number will only be used if Custom is selected from the drop-down menu*  .</span></span>
  
#### <a name="web-app-tab"></a><span data-ttu-id="d4ad5-315">Web アプリケーション] タブ</span><span class="sxs-lookup"><span data-stu-id="d4ad5-315">Web App tab</span></span>

![Load Configuration Tool の [Web app] タブ](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
<span data-ttu-id="d4ad5-317">Web アプリケーションは、サーバーをフロント エンド サーバーにインストールされているユニファイド コミュニケーション Web API (UCWA) サーバーから会議のシナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-317">Web App supports conferencing scenarios through the Unified Communications Web API (UCWA) server that's installed on a Front End server.</span></span> <span data-ttu-id="d4ad5-318">Web アプリケーション] タブを使用すると、すべての web アプリケーションに関連するシナリオを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-318">Use the Web App tab to configure all web app-related scenarios.</span></span> <span data-ttu-id="d4ad5-319">オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-319">Options are:</span></span>
  
- <span data-ttu-id="d4ad5-320">**一般的な Web アプリケーションの設定-\*\*\*\*その他の設定**] をクリックし、VIP のフロント エンド プールのプールのディレクトリ仮想 IP (VIP) に**ReachTargetServerUrl**を設定します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-320">**General Web App Settings -** Click the **Additional Settings** button and set the **ReachTargetServerUrl** to the Directory Pool virtual IP (VIP) of the Front End pool VIP.</span></span>
    
- <span data-ttu-id="d4ad5-321">**アプリケーションの共有-** 負荷レベルの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-321">**Application Sharing -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="d4ad5-322">**データの共同作業-** 負荷レベルの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-322">**Data Collaboration -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="d4ad5-323">**インスタント メッセージングでは、** 負荷レベルの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-323">**Instant Messaging -** Select a value for Load Level.</span></span>
    
- <span data-ttu-id="d4ad5-324">**音声会議-** 負荷レベルの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-324">**Voice Conferencing -** Select a value for Load Level.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d4ad5-325">各シナリオには、**詳細設定**] ボタンの横にあります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-325">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="d4ad5-326">オプションのダイアログ ボックスには、ストレスおよびパフォーマンス ツールの動作を変更し、負荷レベルが**ユーザー設定**を次に、**で指定された値である場合に、Web アプリケーションのシナリオのそれぞれの customization.> を有効にする各シナリオに固有値が含まれています。ConversationsPerHour**フィールドは、既定値の代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-326">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Web App scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="mobility-tab"></a><span data-ttu-id="d4ad5-327">モビリティ] タブ</span><span class="sxs-lookup"><span data-stu-id="d4ad5-327">Mobility tab</span></span>

<span data-ttu-id="d4ad5-328">すべてのモビリティに関連するシナリオを構成するのにには、このタブを使用します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-328">Use this tab to configure all of the mobility-related scenarios.</span></span>
  
![Load Configuration Tool の [Mobility] タブ](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
<span data-ttu-id="d4ad5-330">オプションをここでは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-330">The options here are:</span></span>
  
- <span data-ttu-id="d4ad5-331">**一般的なモビリティ設定-**[**追加設定**] をクリックし、ディレクター プール仮想 IP (VIP)、またはフロント エンド プールの VIP への UcwaTargetServerUrl フィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-331">**General Mobility Settings -** Click **Additional Settings** and set the field UcwaTargetServerUrl to the Director Pool virtual IP (VIP) or the Front End pool VIP.</span></span>
    
- <span data-ttu-id="d4ad5-332">**プレゼンスと P2P インスタント メッセージング/オーディオ-** 移動のシミュレーションを有効にするのには負荷のレベルの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-332">**Presence and P2P Instant Messaging/Audio -** Select a value for Load Level to enable the Mobility simulation.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d4ad5-333">各シナリオには、**詳細設定**] ボタンの横にあります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-333">Each of the scenarios has an **Advanced** button located next to it.</span></span> <span data-ttu-id="d4ad5-334">オプションのダイアログ ボックスには、ストレスおよびパフォーマンス ツールの動作を変更し、負荷レベルが**ユーザー設定**を次に、**で指定された値である場合に、移動のシナリオのそれぞれの customization.> を有効にする各シナリオに固有値が含まれています。ConversationsPerHour**フィールドは、既定値の代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-334">Advanced dialogs contain values specific to each scenario that will change the behavior of the Stress and Performance Tool and enable customization.> For each of the Mobility scenarios, if the Load Level is **Custom**, then the value specified in the **ConversationsPerHour** field is used instead of the default.</span></span>
  
#### <a name="summary-tab"></a><span data-ttu-id="d4ad5-335">[概要] タブ</span><span class="sxs-lookup"><span data-stu-id="d4ad5-335">Summary tab</span></span>

<span data-ttu-id="d4ad5-336">[概要] タブでは、各シナリオで使用するユーザーを示します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-336">The Summary tab indicates which users to use for each of the scenarios.</span></span>
  
![Load Configuration Tool の [Summary] タブ](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
<span data-ttu-id="d4ad5-338">[概要] タブでは、各シナリオで使用するユーザーを示します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-338">The Summary tab indicates which users to use for each of the scenarios.</span></span> 
  
<span data-ttu-id="d4ad5-339">**カスタム ユーザー範囲生成を有効にする**] チェック ボックスを選択し、シナリオをカスタマイズするユーザーの範囲を持つテーブルをダブルクリックしてユーザーの数値の範囲を手動で構成することができます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-339">It's possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the User Range that you want to customize.</span></span>
  
<span data-ttu-id="d4ad5-340">サインインの速度に対応して生成されたバッチ ファイルでの遅延を含めるために **(RunClient.bat) 追加記号で遅延起動時の設定**を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-340">Check **(RunClient.bat) Add sign-in delay when starting** in order to include delays in the generated batch files to correspond to the sign-in rate.</span></span> <span data-ttu-id="d4ad5-341">多数のユーザーに署名するときは、サーバーの過負荷を防ぐために便利です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-341">This is useful to prevent server overload when signing in a large number of users.</span></span>
  
<span data-ttu-id="d4ad5-342">**ファイルの生成**] をクリックし、構成を生成するフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-342">Click **Generate Files** and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="d4ad5-343">ファイルが正常に作成されたときにダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-343">A dialog box will appear when your files have been successfully created.</span></span>
  
!["Load configuration files generated successfully" というメッセージ ボックス。](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a><span data-ttu-id="d4ad5-346">LyncPerfTool を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-346">Run LyncPerfTool</span></span>
<span data-ttu-id="d4ad5-347"><a name="BKMK_RunTool"> </a></span><span class="sxs-lookup"><span data-stu-id="d4ad5-347"></span></span>

<span data-ttu-id="d4ad5-348">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツール (LyncPerfTool.exe) は、Skype を実行する前にユーザー、連絡先、およびシナリオを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-348">You'll need to create users, contacts, and scenarios before running the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe).</span></span> <span data-ttu-id="d4ad5-349">これらのアクションを実行するツールの使用の詳細についてを参照してください[ユーザーの作成および取引先担当者](using-the-tool.md#BKMK_CreateUsersAndContacts)および[ユーザー プロファイルを構成する](using-the-tool.md#BKMK_UserProfile)以前この資料にします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-349">For details about using the tools to perform these actions, see [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts) and [Configure User Profile](using-the-tool.md#BKMK_UserProfile) previously in this article.</span></span> <span data-ttu-id="d4ad5-350">これらのツールを実行すると、含まれている必要なパラメーターを使用してストレスおよびパフォーマンス ツールを使用してバッチ ファイルの一部として実行するファイルも生成されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-350">Running these tools will also generate a file that will run with the Stress and Performance tool as part of a batch file with the required parameters included.</span></span>
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="d4ad5-351">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype を実行しています。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-351">Running the Skype for Business Server 2015 Stress and Performance tool</span></span>

<span data-ttu-id="d4ad5-352">負荷の構成ツール (UserProfileGenerator.exe) は、ストレスおよびパフォーマンス ツール (LyncPerfTool.exe) を実行するには、パフォーマンス カウンターを登録して、XML 構成ファイルをロードすることを可能にするバッチ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-352">The Load Configuration tool (UserProfileGenerator.exe) creates a batch file that enables you to run the Stress and Performance tool (LyncPerfTool.exe) by registering performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="d4ad5-353">バッチ ファイルは、構成ファイルごとの LyncPerfTool.exe の 1 つのインスタンスを実行します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-353">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="d4ad5-354">バッチ ファイルを実行には、これらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-354">To run the batch file follow these steps:</span></span>
  
### <a name="run-the-stress-and-performance-test"></a><span data-ttu-id="d4ad5-355">ストレスおよびパフォーマンスのテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-355">Run the Stress and Performance test</span></span>

1. <span data-ttu-id="d4ad5-356">構成フォルダー内のファイルとフォルダーを各クライアント コンピューターで LyncPerfTool.exe のあるディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-356">Copy the folder with the configuration folders and files inside to the directory that has LyncPerfTool.exe on each client computer.</span></span> <span data-ttu-id="d4ad5-357">(などの 1.28_13.16.16 をという名前のフォルダー内の構成ファイルを生成する場合そのフォルダー フォルダーにコピー LyncPerfTool.exe とにします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-357">(For example, if you generated the configuration files in the folder named 1.28_13.16.16, copy that folder to the folder with LyncPerfTool.exe in it.</span></span> <span data-ttu-id="d4ad5-358">これは各クライアントにします。)</span><span class="sxs-lookup"><span data-stu-id="d4ad5-358">Do this on each client.)</span></span>
    
2. <span data-ttu-id="d4ad5-359">クライアントのフォルダーに移動し、 **RunClient**のバッチ スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-359">Navigate to the client folder and run the **RunClient** batch script.</span></span> <span data-ttu-id="d4ad5-360">Windows エクスプ ローラーでバッチ ファイルをダブルクリックすることができ、すべての構成ファイルにクライアントに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-360">You can double-click the batch file in Windows Explorer and it will run all of the configuration files for that client.</span></span> <span data-ttu-id="d4ad5-361">次の構文を使用してクライアントのフォルダーからスクリプトを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-361">You can also run the script from a client folder by using the following syntax:</span></span>
    
   ```
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

<span data-ttu-id="d4ad5-362">ストレスおよびパフォーマンス ツールを直接実行、コマンド プロンプトを開き、コマンドラインで次のコマンドを入力する (最初にこれを行うときは、パフォーマンス カウンターを登録することを確認して`regsvr32 /i /n /s LyncPerfToolPerf.dll`、このトピックの後半で示すように、)。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-362">To run the Stress and Performance tool directly, open a command prompt and type the following command at the command line (and when doing this for the first time, be sure to register the performance counters  `regsvr32 /i /n /s LyncPerfToolPerf.dll`, as shown in the note later in this topic):</span></span>
  
```
LyncPerfTool.exe /file:IM_client0.xml
```

<span data-ttu-id="d4ad5-363">構成ファイルの値を表示するツールを表示するには、`/displayfile`を次のようなので、上記のコマンドのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-363">To have the tool display the values in the configuration file, include the  `/displayfile` parameter on the preceding command, so that it looks like this:</span></span>
  
```
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

<span data-ttu-id="d4ad5-364">*終了*処理をするには、Ctrl キーを押しながら C キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-364">To  *end*  the process, press Ctrl+C.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4ad5-365">ストレスおよびパフォーマンス ツールを直接実行する前に、次のコマンドを使用してパフォーマンス カウンターを登録する必要があります。`regsvr32 /i /n /s LyncPerfToolPerf.dll`</span><span class="sxs-lookup"><span data-stu-id="d4ad5-365">Before running the Stress and Performance tool directly, you must register the performance counters via the following command:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4ad5-366">ストレスおよびパフォーマンス ツールを起動するすべてのインスタンスはすぐに 1 人のユーザーが 1 秒あたりの速度で通常のユーザーに署名します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-366">Every instance of the Stress and Performance tool that you start will immediately begin signing in users, usually at a rate of one user per second.</span></span> 
  
<span data-ttu-id="d4ad5-367">レート プールのサインイン用ユーザーのピーク時は、1 秒あたり 12 についてです。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-367">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="d4ad5-368">これは、必要はありませんを起動する 12 の複数の LyncPerfTool.exe インスタンスを同時にユーザーがサインインしても、ことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-368">This means that you shouldn't start more than 12 LyncPerfTool.exe instances at the same time while users are still signing in.</span></span> <span data-ttu-id="d4ad5-369">1000 人のユーザーは完全に 1 秒ごとに 1 つのサインインに約 20 分かかります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-369">One thousand users will take about 20 minutes to fully sign in at one per second.</span></span>
  
## <a name="interpreting-the-results"></a><span data-ttu-id="d4ad5-370">結果の解釈</span><span class="sxs-lookup"><span data-stu-id="d4ad5-370">Interpreting the Results</span></span>
<span data-ttu-id="d4ad5-371"><a name="BKMK_Interpret"> </a></span><span class="sxs-lookup"><span data-stu-id="d4ad5-371"></span></span>

<span data-ttu-id="d4ad5-372">ビジネス サーバー 2015 のストレスおよびパフォーマンス ツールの Skype では、クライアントが何をして、には問題が発生したかどうかを理解するのに役立つ多数のカウンターがあります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-372">The Skype for Business Server 2015 Stress and Performance Tool has many counters that can help you understand what the client is doing, and whether it's encountering issues.</span></span>
  
### <a name="client-counters"></a><span data-ttu-id="d4ad5-373">クライアント カウンター</span><span class="sxs-lookup"><span data-stu-id="d4ad5-373">Client Counters</span></span>

<span data-ttu-id="d4ad5-374">実行している LyncPerfTool.exe の各インスタンスには、別のカウンターのインスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-374">Each instance of LyncPerfTool.exe running has a separate instance of the counters.</span></span> <span data-ttu-id="d4ad5-375">各インスタンスは、プロセス ID によってという名前</span><span class="sxs-lookup"><span data-stu-id="d4ad5-375">Each instance is named by its process ID.</span></span> <span data-ttu-id="d4ad5-376">クライアントがオーバー ロードされた場合その他の問題が発生することができます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-376">If clients are overloaded other issues can occur.</span></span> <span data-ttu-id="d4ad5-377">これらの問題を防ぐ。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-377">To prevent these issues:</span></span>
  
- <span data-ttu-id="d4ad5-378">クライアント コンピューター上の CPU とメモリの使用率を監視します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-378">Monitor CPU and Memory usage on the client computers.</span></span> <span data-ttu-id="d4ad5-379">CPU が継続的に、90% を超える場合は、ユーザーの数を減らします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-379">If the CPU is consistently above 90 percent, reduce the number of users.</span></span>
    
- <span data-ttu-id="d4ad5-380">メモリ使用量が高いときは、ページ ・ ファイル領域が不足する場合の問題に実行できます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-380">When the Memory footprint is high, you may run into issues if the Page File begins to run out of space.</span></span> <span data-ttu-id="d4ad5-381">コミット チャージがコンピューター上の制限をヒットしないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-381">Verify that the Commit Charge is not hitting the limit on the computer.</span></span> <span data-ttu-id="d4ad5-382">メモリの制限に実行している場合は、ページ ファイル サイズを増やすか、ユーザーの数を減らすことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-382">If you are running into Memory limits consider increasing the Page File size or reducing the number of users.</span></span>
    
<span data-ttu-id="d4ad5-383">主要なパフォーマンス カウンターの一覧を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-383">Here's a list of key performance counters:</span></span>
  
<span data-ttu-id="d4ad5-384">**一般的な情報**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-384">**General Information**</span></span>

|<span data-ttu-id="d4ad5-385">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-385">**Performance Counter**</span></span>|<span data-ttu-id="d4ad5-386">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-386">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4ad5-387">時間を分単位で</span><span class="sxs-lookup"><span data-stu-id="d4ad5-387">Time Spent in Minutes</span></span>  <br/> |<span data-ttu-id="d4ad5-388">プロセスが開始されたために費やされた時間。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-388">Time spent since the process was started.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-389">アクティブなエンドポイント</span><span class="sxs-lookup"><span data-stu-id="d4ad5-389">Active Endpoints</span></span>  <br/> |<span data-ttu-id="d4ad5-390">サーバーに現在接続されているエンドポイントの数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-390">Number of endpoints currently connected to the server.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-391">失敗したログオン</span><span class="sxs-lookup"><span data-stu-id="d4ad5-391">Failed Logons</span></span>  <br/> |<span data-ttu-id="d4ad5-392">サインインに失敗したエンドポイントの合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-392">Total number of endpoint sign-in failures.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-393">ログオンの試行</span><span class="sxs-lookup"><span data-stu-id="d4ad5-393">Logon Attempts</span></span>  <br/> |<span data-ttu-id="d4ad5-394">エンドポイント サインイン試行の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-394">Total number of endpoint sign-in attempts.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-395">エンドポイントが切断されています。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-395">Endpoints Disconnected</span></span>  <br/> |<span data-ttu-id="d4ad5-396">接続が切れたエンドポイントの合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-396">Total number of endpoints that have been disconnected.</span></span>  <br/> |
   
<span data-ttu-id="d4ad5-397">**プレゼンス情報**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-397">**Presence Information**</span></span>

|<span data-ttu-id="d4ad5-398">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-398">**Performance Counter**</span></span>|<span data-ttu-id="d4ad5-399">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-399">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4ad5-400">SetPresence の呼び出し</span><span class="sxs-lookup"><span data-stu-id="d4ad5-400">SetPresence Calls</span></span>  <br/> |<span data-ttu-id="d4ad5-401">プレゼンスの合計数は、試行回数を変更します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-401">Total number of presence change attempts.</span></span> <span data-ttu-id="d4ad5-402">プレゼンス変更の種類は、SetPresence (プレゼンス型) の呼び出しのパフォーマンス カウンターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-402">For different types of presence changes, see the SetPresence (Presence Type) Calls Performance Counter.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-403">SetPresence の NNN の応答</span><span class="sxs-lookup"><span data-stu-id="d4ad5-403">NNN Responses for SetPresence</span></span>  <br/> |<span data-ttu-id="d4ad5-404">Nnn 応答コードがサーバーからの受信の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-404">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-405">GetPresence の呼び出し</span><span class="sxs-lookup"><span data-stu-id="d4ad5-405">GetPresence Calls</span></span>  <br/> |<span data-ttu-id="d4ad5-406">数の合計は、プレゼンス要求の回数を取得します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-406">Total number of get presence request attempts.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-407">GetPresence の NNN の応答</span><span class="sxs-lookup"><span data-stu-id="d4ad5-407">NNN Responses for GetPresence</span></span>  <br/> |<span data-ttu-id="d4ad5-408">Nnn 応答コードがサーバーからの受信の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-408">Total number of nnn response codes received from the server.</span></span>  <br/> |
   
<span data-ttu-id="d4ad5-409">**アドレス帳サービスの情報**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-409">**Address Book service information**</span></span>

|<span data-ttu-id="d4ad5-410">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-410">**Performance Counter**</span></span>|<span data-ttu-id="d4ad5-411">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-411">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4ad5-412">ABS フル/差分ファイルをダウンロードしようとしました</span><span class="sxs-lookup"><span data-stu-id="d4ad5-412">ABS Full/Delta File Downloads Attempted</span></span>  <br/> |<span data-ttu-id="d4ad5-413">フルまたは差分ファイルのダウンロード要求が試行の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-413">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-414">ABS フル/差分ファイルのダウンロードに成功しました</span><span class="sxs-lookup"><span data-stu-id="d4ad5-414">ABS Full/Delta File Downloads Succeeded</span></span>  <br/> |<span data-ttu-id="d4ad5-415">フルまたは差分ファイルのダウンロード要求が試行の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-415">Total number of full or delta file download requests attempted.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-416">アドレス帳 Web クエリ サービスに関連するカウンター</span><span class="sxs-lookup"><span data-stu-id="d4ad5-416">Address Book Web Query service related counters</span></span>  <br/> |<span data-ttu-id="d4ad5-417">アドレス帳ファイルは、関連するカウンターをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-417">Address book file download related counters.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-418">ABS WS 呼び出しを実行しようと</span><span class="sxs-lookup"><span data-stu-id="d4ad5-418">ABS WS Calls attempted</span></span>  <br/> |<span data-ttu-id="d4ad5-419">実行しようとアドレス帳 Web クエリ サービスの要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-419">Total number of Address Book Web Query service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-420">ABS WS の呼び出しに成功しました</span><span class="sxs-lookup"><span data-stu-id="d4ad5-420">ABS WS Calls Succeeded</span></span>  <br/> |<span data-ttu-id="d4ad5-421">正常な応答コードが返されるアドレス帳 Web クエリ サービスの要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-421">Total number of Address Book Web Query service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-422">ABS WS の呼び出しに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-422">ABS WS Calls Failed</span></span>  <br/> |<span data-ttu-id="d4ad5-423">エラー応答コードが返されるアドレス帳 Web クエリ サービスの要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-423">Total number of Address Book Web Query service requests that returned an error response code.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="d4ad5-424">このカテゴリには、アドレス帳サービス (ABS) ファイルをダウンロードし、アドレス帳 Web クエリ サービス要求を監視するために使用するカウンターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-424">This category includes counters used to monitor Address Book service (ABS) file downloads and Address Book Web Query service requests.</span></span> 
  
<span data-ttu-id="d4ad5-425">**配布リスト (DL) の情報**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-425">**Distribution List (DL) Information**</span></span>

|<span data-ttu-id="d4ad5-426">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-426">**Performance Counter**</span></span>|<span data-ttu-id="d4ad5-427">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-427">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4ad5-428">呼び出しを実行しようと</span><span class="sxs-lookup"><span data-stu-id="d4ad5-428">Calls Attempted</span></span>  <br/> |<span data-ttu-id="d4ad5-429">配布リストの拡張されて web サービス要求が試行の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-429">Total number of distribution list expansion (DLX) web service requests attempted.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-430">呼び出しに成功しました</span><span class="sxs-lookup"><span data-stu-id="d4ad5-430">Calls Succeeded</span></span>  <br/> |<span data-ttu-id="d4ad5-431">正常な応答コードが返されましたが、DLX の web サービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-431">Total number of DLX web service requests that returned a successful response code.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-432">呼び出しが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-432">Calls Failed</span></span>  <br/> |<span data-ttu-id="d4ad5-433">エラー応答コードが返された DLX の web サービス要求の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-433">Total number of DLX web service requests that returned an error response code.</span></span>  <br/> |
   

  
> [!NOTE]
> <span data-ttu-id="d4ad5-434">パフォーマンス カウンターを以下に示しますレポート番号のボイスはすべての IP (VoIP) 呼び出しは、仲介サーバー、A への呼び出しなどの上/V 会議サーバー、エッジ サーバー、応答グループ アプリケーション、および会議の自動応答、これらのシナリオを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-434">The performance counters listed below report numbers for all Voice over IP (VoIP) calls, including calls to Mediation Server, A/V Conferencing Server, Edge Server, Response Group application, and Conference Auto Attendant, when these scenarios are enabled.</span></span> 
  
<span data-ttu-id="d4ad5-435">**VoIP の基本情報**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-435">**VoIP Basic Information**</span></span>

|<span data-ttu-id="d4ad5-436">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-436">**Performance Counter**</span></span>|<span data-ttu-id="d4ad5-437">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-437">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4ad5-438">アクティブな呼び出し</span><span class="sxs-lookup"><span data-stu-id="d4ad5-438">Calls Active</span></span>  <br/> |<span data-ttu-id="d4ad5-439">音声の着信/発信の合計数は現在進行中呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-439">Total number of incoming/outgoing voice calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-440">呼び出しが終了しました</span><span class="sxs-lookup"><span data-stu-id="d4ad5-440">Calls Terminated</span></span>  <br/> |<span data-ttu-id="d4ad5-441">音声通話の着信/発信の合計数は既に終了しました。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-441">Total number of incoming/outgoing voice calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-442">呼び出しが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-442">Calls Declined</span></span>  <br/> |<span data-ttu-id="d4ad5-443">着信音声通話の合計数を辞退しました。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-443">Total number of incoming voice calls declined.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-444">着信/発信呼び出しを実行しようと</span><span class="sxs-lookup"><span data-stu-id="d4ad5-444">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="d4ad5-445">着信/発信音声呼び出しを試行の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-445">Total number of incoming/outgoing voice calls attempted.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-446">着信/発信呼び出しの確立</span><span class="sxs-lookup"><span data-stu-id="d4ad5-446">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="d4ad5-447">確立された着信/発信音声通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-447">Total number of incoming/outgoing voice calls established.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-448">呼び出しの受信した NNN</span><span class="sxs-lookup"><span data-stu-id="d4ad5-448">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="d4ad5-449">Nnn 応答コードがサーバーからの受信の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-449">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-450">VoIP の成功率 (%)</span><span class="sxs-lookup"><span data-stu-id="d4ad5-450">VoIP Pass Rate (%)</span></span>  <br/> |<span data-ttu-id="d4ad5-451">合計通話が確立されると合計実行しようとします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-451">Total calls established/Total calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="d4ad5-452">**応答グループ サービスの呼び出しについて**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-452">**Response Group service Call Information**</span></span>

|<span data-ttu-id="d4ad5-453">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-453">**Performance Counter**</span></span>|<span data-ttu-id="d4ad5-454">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-454">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4ad5-455">アクティブな呼び出し</span><span class="sxs-lookup"><span data-stu-id="d4ad5-455">Calls Active</span></span>  <br/> |<span data-ttu-id="d4ad5-456">応答グループ アプリケーションのアクティブな呼び出しの合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-456">Total number of active calls to the Response Group application.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-457">呼び出しを実行しようと</span><span class="sxs-lookup"><span data-stu-id="d4ad5-457">Calls Attempted</span></span>  <br/> |<span data-ttu-id="d4ad5-458">実行しようとする呼び出しの合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-458">Total number of calls attempted.</span></span>  <br/> |
   
<span data-ttu-id="d4ad5-459">**インスタント メッセージング (IM) の呼び出しについて**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-459">**Instant Messaging (IM) Call Information**</span></span>

|<span data-ttu-id="d4ad5-460">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-460">**Performance Counter**</span></span>|<span data-ttu-id="d4ad5-461">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-461">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4ad5-462">アクティブな呼び出し</span><span class="sxs-lookup"><span data-stu-id="d4ad5-462">Calls Active</span></span>  <br/> |<span data-ttu-id="d4ad5-463">継続的な着信/発信のインスタント メッセージング呼び出しの合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-463">Total number of ongoing incoming/outgoing instant messaging calls.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-464">呼び出しが終了しました</span><span class="sxs-lookup"><span data-stu-id="d4ad5-464">Calls Terminated</span></span>  <br/> |<span data-ttu-id="d4ad5-465">インスタント メッセージング呼び出しの着信/発信の合計数は既に終了しました。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-465">Total number of incoming/outgoing instant messaging calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-466">呼び出しの受信した NNN</span><span class="sxs-lookup"><span data-stu-id="d4ad5-466">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="d4ad5-467">Nnn 応答コードがサーバーからの受信の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-467">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-468">受信/送信された IM メッセージ</span><span class="sxs-lookup"><span data-stu-id="d4ad5-468">IM Messages Received/Sent</span></span>  <br/> |<span data-ttu-id="d4ad5-469">メッセージの合計数の受信または送信のすべてのセッションです。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-469">Total number of messages received or sent for all sessions.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-470">着信/発信呼び出しを実行しようと</span><span class="sxs-lookup"><span data-stu-id="d4ad5-470">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="d4ad5-471">着信/発信インスタント メッセージングの呼び出しの試行の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-471">Total number of incoming/outgoing instant messaging calls attempted.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-472">着信/発信呼び出しの確立</span><span class="sxs-lookup"><span data-stu-id="d4ad5-472">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="d4ad5-473">確立された着信/発信のインスタント メッセージ呼び出しの合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-473">Total number of incoming/outgoing instant message calls established.</span></span>  <br/> |
   
<span data-ttu-id="d4ad5-474">**アプリケーション呼び出し情報の共有**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-474">**App Sharing Call Information**</span></span>

|<span data-ttu-id="d4ad5-475">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-475">**Performance Counter**</span></span>|<span data-ttu-id="d4ad5-476">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-476">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4ad5-477">アクティブな呼び出し</span><span class="sxs-lookup"><span data-stu-id="d4ad5-477">Calls Active</span></span>  <br/> |<span data-ttu-id="d4ad5-478">進行中の着信/発信アプリケーションの共有の呼び出しの合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-478">Total number of ongoing incoming/outgoing application sharing calls.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-479">呼び出しが終了しました</span><span class="sxs-lookup"><span data-stu-id="d4ad5-479">Calls Terminated</span></span>  <br/> |<span data-ttu-id="d4ad5-480">着信/発信のアプリケーションの呼び出しを既に共有の合計数が終了しました。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-480">Total number of incoming/outgoing application sharing calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-481">呼び出しの受信した NNN</span><span class="sxs-lookup"><span data-stu-id="d4ad5-481">Calls Received NNN</span></span>  <br/> |<span data-ttu-id="d4ad5-482">Nnn 応答コードがサーバーからの受信の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-482">Total number of nnn response codes received from the server.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-483">着信/発信呼び出しを実行しようと</span><span class="sxs-lookup"><span data-stu-id="d4ad5-483">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="d4ad5-484">着信/発信アプリケーションの共有しようとする呼び出しの合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-484">Total number of incoming/outgoing application sharing calls attempted.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-485">着信/発信呼び出しの確立</span><span class="sxs-lookup"><span data-stu-id="d4ad5-485">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="d4ad5-486">着信/発信アプリケーションの共有を確立する呼び出しの合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-486">Total number of incoming/outgoing application sharing calls established.</span></span>  <br/> |
   
<span data-ttu-id="d4ad5-487">**CAA の呼び出しについて**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-487">**CAA Call Information**</span></span>

|<span data-ttu-id="d4ad5-488">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-488">**Performance Counter**</span></span>|<span data-ttu-id="d4ad5-489">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-489">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4ad5-490">アクティブな呼び出し</span><span class="sxs-lookup"><span data-stu-id="d4ad5-490">Calls Active</span></span>  <br/> |<span data-ttu-id="d4ad5-491">公衆交換電話網 (PSTN) の着信/発信の合計数は現在進行中呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-491">Total number of incoming/outgoing public switched telephone network (PSTN) calls ongoing currently.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-492">呼び出しが終了しました</span><span class="sxs-lookup"><span data-stu-id="d4ad5-492">Calls Terminated</span></span>  <br/> |<span data-ttu-id="d4ad5-493">PSTN 通話の着信/発信の合計数は既に終了しました。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-493">Total number of incoming/outgoing PSTN calls already terminated.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-494">着信/発信呼び出しを実行しようと</span><span class="sxs-lookup"><span data-stu-id="d4ad5-494">Incoming/Outgoing Calls Attempted</span></span>  <br/> |<span data-ttu-id="d4ad5-495">PSTN 通話を受信/送信試行の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-495">Total number of incoming/outgoing PSTN calls attempted.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-496">着信/発信呼び出しの確立</span><span class="sxs-lookup"><span data-stu-id="d4ad5-496">Incoming/Outgoing Calls Established</span></span>  <br/> |<span data-ttu-id="d4ad5-497">確立された着信/発信の PSTN 通話の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-497">Total number of incoming/outgoing PSTN calls established.</span></span>  <br/> |
   
<span data-ttu-id="d4ad5-498">**会議情報**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-498">**Conference Information**</span></span>

|<span data-ttu-id="d4ad5-499">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-499">**Performance Counter**</span></span>|<span data-ttu-id="d4ad5-500">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-500">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4ad5-501">アクティブなインスタント メッセージング会議</span><span class="sxs-lookup"><span data-stu-id="d4ad5-501">Active Instant Messaging Conferences</span></span>  <br/> |<span data-ttu-id="d4ad5-502">インスタント メッセージング会議を進行中の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-502">Total number of ongoing instant messaging conferences.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-503">アクティブなオーディオ/ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="d4ad5-503">Active Audio/Video Conferences</span></span>  <br/> |<span data-ttu-id="d4ad5-504">数の継続的なオーディオ/ビデオ (A/V) 会議。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-504">Total number of ongoing audio/video (A/V) conferences.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-505">アクティブなアプリケーションの共有の会議</span><span class="sxs-lookup"><span data-stu-id="d4ad5-505">Active Application Sharing Conferences</span></span>  <br/> |<span data-ttu-id="d4ad5-506">会議を共有して継続的なアプリケーションの合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-506">Total number of ongoing application sharing conferences.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-507">参加者の数</span><span class="sxs-lookup"><span data-stu-id="d4ad5-507">Number of Participants</span></span>  <br/> |<span data-ttu-id="d4ad5-508">会議に現在接続している参加者の合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-508">Total number of participants currently connected to conferences.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-509">会議スケジュールの障害</span><span class="sxs-lookup"><span data-stu-id="d4ad5-509">Conference Schedule Failure</span></span>  <br/> |<span data-ttu-id="d4ad5-510">会議をスケジュールしようとしているときにエラーの合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-510">Total number of failures while trying to schedule a conference.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-511">障害の会議に参加します。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-511">Join Conference Failure</span></span>  <br/> |<span data-ttu-id="d4ad5-512">会議への接続中のエラーの合計数です。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-512">Total number of failures while trying to connect to a conference.</span></span>  <br/> |
   
<span data-ttu-id="d4ad5-513">**UCWA クライアント カウンター**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-513">**UCWA Client Counters**</span></span>

|<span data-ttu-id="d4ad5-514">**パフォーマンス カウンター**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-514">**Performance Counter**</span></span>|<span data-ttu-id="d4ad5-515">**説明**</span><span class="sxs-lookup"><span data-stu-id="d4ad5-515">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d4ad5-516">IMMCU の合計数を結合に成功しました</span><span class="sxs-lookup"><span data-stu-id="d4ad5-516">Total Number of IMMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="d4ad5-517">インスタント メッセージング会議の合計数が参加しています。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-517">Total number of instant messaging conferences joined.</span></span>  <br/> |
|<span data-ttu-id="d4ad5-518">DMCU の合計数を結合に成功しました</span><span class="sxs-lookup"><span data-stu-id="d4ad5-518">Total Number of DMCU Joins Succeeded</span></span>  <br/> |<span data-ttu-id="d4ad5-519">A の合計数 V 会議に参加するいるとします。</span><span class="sxs-lookup"><span data-stu-id="d4ad5-519">Total number of A/V conferences joined.</span></span>  <br/> |
   

