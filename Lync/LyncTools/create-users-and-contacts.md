---
title: ユーザーと連絡先の作成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1463a7caaad2bcf36996eaac4bd47e2bab25e6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a><span data-ttu-id="d1c72-102">ユーザーと連絡先の作成</span><span class="sxs-lookup"><span data-stu-id="d1c72-102">Create Users and Contacts</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1c72-103">_**最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="d1c72-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="d1c72-104">高パフォーマンスのロードテストの準備として、ユーザーと連絡先を作成するには、Lync Server 2013 ユーザープロビジョニングツール (Userprovisioning Tool) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-104">You must use the Lync Server 2013 User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts in preparation for stress and performance load testing.</span></span>

<span data-ttu-id="d1c72-105">ここでは、このトピックを読むときに役に立つ可能性がある用語と定義の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-105">Here is a list of terms and definitions that you might find useful as you read through this topic.</span></span>

  - <span data-ttu-id="d1c72-106">組織単位– Active Directory ドメインサービスの組織単位 (OU)。</span><span class="sxs-lookup"><span data-stu-id="d1c72-106">Organizational Unit – The Active Directory Domain Services organizational unit (OU).</span></span>

  - <span data-ttu-id="d1c72-107">フェデレーション/クロスプール–インターネットサービスの MSN ネットワーク、AOL®、Yahoo\!®など、他のインスタントメッセージング (IM) サービスからユーザーとの通信を有効にするユーザー。</span><span class="sxs-lookup"><span data-stu-id="d1c72-107">Federated / Cross Pool – Users who will be enabled to communicate with users from other Instant Messaging (IM) services, such as MSN network of Internet services, AOL®, and Yahoo\!®.</span></span>

  - <span data-ttu-id="d1c72-108">配布リスト–ユーザーのグループとの通信を開始するために使用される Active Directory ドメインサービスユーザーの一覧を含む Active Directory ドメインサービス内のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d1c72-108">Distribution Lists – The objects in Active Directory Domain Services that contain a list of Active Directory Domain Services users, used for launching communications with groups of people.</span></span>

  - <span data-ttu-id="d1c72-109">位置情報サービス– Lync Server 2013 サービス。電話ごとに有効にして構成すると、強化された 9-1-1 (E9) サービスの物理的な場所を取得できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-109">Location Info Service – The Lync Server 2013 service that, when enabled and configured per phone, enables retrieval of physical location for Enhanced 9-1-1 (E9-1-1) services.</span></span>

  - <span data-ttu-id="d1c72-110">米国の電話番号–ユーザーに割り当てられている電話番号、着信通話と発信通話、および逆番号参照 (RNL) のルーティングに使用される SIP URI に加えます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-110">U.S. Phone Numbers – The phone numbers that are assigned to users, in addition to the SIP URI that is used for routing inbound and outbound calls and reverse number lookup (RNL).</span></span>

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="d1c72-111">Userプロビジョニングツールを使用してユーザーと連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="d1c72-111">Create Users and Contacts by Using UserProvisioningTool.exe</span></span>

<span data-ttu-id="d1c72-112">ロードシミュレーション用にユーザーと連絡先を作成するには、Lync Server ユーザープロビジョニングツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-112">You must use the Lync Server User Provisioning Tool to create users and contacts for load simulation.</span></span> <span data-ttu-id="d1c72-113">Lync server のユーザープロビジョニングツールは、Lync Server のストレスとパフォーマンスツールパッケージと共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-113">The Lync Server User Provisioning Tool is installed with the Lync Server Stress and Performance Tool package.</span></span> <span data-ttu-id="d1c72-114">パッケージインストーラー (CapacityPlanningTool) が、フロントエンドサーバーまたは Standard Edition サーバーで実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-114">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server.</span></span> <span data-ttu-id="d1c72-115">フロントエンドサーバーまたは Standard Edition サーバーのファイル Userprovisioning Tool を実行して、Lync Server ユーザープロビジョニングツールを\\起動します (% LyncStressAndPerfTool ディレクトリ% LyncStress にあります)。</span><span class="sxs-lookup"><span data-stu-id="d1c72-115">Start the Lync Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d1c72-116">User指定ツールを実行するには、ドメイン管理者セキュリティグループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-116">You must be logged on as a member of the Domain Admins security group in order to run UserProvisioningTool.exe.</span></span> <span data-ttu-id="d1c72-117">User/Tool は新しい Active Directory ドメインサービスユーザーを作成して構成するため、このコンテキストから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-117">It is necessary to run from this context because UserProvisioningTool.exe will be creating and configuring new Active Directory Domain Services users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d1c72-118">多数のユーザー (1万以上) を作成する場合は、ハイエンドコンピューターから User/Tool .exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-118">When you create a significant number of users (10,000 or more), run UserProvisioningTool.exe from a high-end computer.</span></span> <span data-ttu-id="d1c72-119">また、ドメインコントローラーでは、ユーザーが作成されている間も高負荷が発生することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d1c72-119">Note that the domain controller will also experience high load while the users are being created.</span></span>



</div>

<span data-ttu-id="d1c72-120">Lync Server ユーザープロビジョニングツールが開いたら、[**構成**] をクリックし、[**構成の読み込み**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-120">When the Lync Server User Provisioning Tool opens, click **Configuration** and select **Load Configuration**.</span></span> <span data-ttu-id="d1c72-121">ユーザーと連絡先の構成を開始するには、パッケージ SampleData に含まれている既定のファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-121">To begin configuring users and contacts, load the default file that is included in the package, SampleData.xml.</span></span> <span data-ttu-id="d1c72-122">これにより、システムで変更する必要があるデータ例のフィールドが事前に作成されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-122">This will prepopulate the fields with example data that you'll need to revise for your system.</span></span> <span data-ttu-id="d1c72-123">既にカスタマイズした設定が含まれている事前構成済みの XML ファイルがある場合は、代わりにそのファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-123">If you have a preconfigured XML file that already contains customized settings, load that file instead.</span></span> <span data-ttu-id="d1c72-124">次のセクションで説明するように、Lync Server ユーザープロビジョニングツールのフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-124">Fill in the fields in the Lync Server User Provisioning Tool, as described in the following sections.</span></span>

<span data-ttu-id="d1c72-125">![[ユーザーの作成] タブ](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "[ユーザーの作成] タブ")</span><span class="sxs-lookup"><span data-stu-id="d1c72-125">![User Creation tab.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "User Creation tab.")</span></span>

<span data-ttu-id="d1c72-126">サーバーオプションを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-126">To configure server options, follow these steps.</span></span>

1.  <span data-ttu-id="d1c72-127">[**フロントエンドプール FQDN**] に、ユーザーをホストする標準エディションサーバーまたはフロントエンドプールの完全修飾ドメイン名 (fqdn) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-127">In **Front End Pool FQDN**, type the fully qualified domain name (FQDN) of the Standard Edition server or Front End pool where you want to host the users.</span></span>

2.  <span data-ttu-id="d1c72-128">[**ユーザー名プレフィックス**] に、テスト目的でユーザー名を作成するために使用するプレフィックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-128">In **User Name Prefix**, type a prefix that you want to use to build user names for testing purposes.</span></span>

3.  <span data-ttu-id="d1c72-129">[**パスワード**] で、すべてのテストユーザーアカウントに適用されるパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-129">In **Password**, specify a password that will be applied for all of the test user accounts.</span></span>

4.  <span data-ttu-id="d1c72-130">[ **Sip ドメイン**] に、テストユーザーの SIP Uri (Uniform resource identifier) に使用するドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-130">In **SIP Domain**, type the domain name to be used for test users’ SIP URIs (Uniform Resource Identifiers).</span></span>

5.  <span data-ttu-id="d1c72-131">[ **Account Domain**] に、テストユーザーを作成する現在の Active Directory ドメインサービスドメインのドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-131">In **Account Domain**, type the domain name of your current Active Directory Domain Services domain, under which you want to create the test users.</span></span>

6.  <span data-ttu-id="d1c72-132">[**組織単位**] に、ユーザーオブジェクトを作成する Active Directory ドメインサービスの OU の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-132">In **Organizational Unit**, type the name of the Active Directory Domain Services OU where you want to create the User objects.</span></span> <span data-ttu-id="d1c72-133">OU が存在しない場合は、作成されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-133">If the OU does not exist, it will be created.</span></span>

7.  <span data-ttu-id="d1c72-134">[**電話の市外局番**] に、テストユーザーアカウントに使用される3桁の市外局番を入力します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-134">In **Phone Area Code**, type the three-digit area code that will be used for test user accounts.</span></span> <span data-ttu-id="d1c72-135">Active Directory ドメインサービスの他のユーザーの市外局番と電話番号が競合していないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d1c72-135">Be sure that phone area code does not conflict with any other users’ area codes in Active Directory Domain Services.</span></span>

8.  <span data-ttu-id="d1c72-136">エンタープライズ Voip のテストユーザーを有効にする場合は、[**音声を有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d1c72-136">Select the **Voice Enabled** check box if you want to enable the test users for Enterprise Voice.</span></span>

9.  <span data-ttu-id="d1c72-137">[**ユーザー**数] で、作成するテストユーザーの合計数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-137">In **Number of Users**, specify the total number of test users that you want to create.</span></span>

10. <span data-ttu-id="d1c72-138">[**開始インデックス**] で、ユーザー名プレフィックスのサフィックスとして使用される開始番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-138">In **Start Index**, specify the starting number that will be used as suffix to the user name prefix.</span></span>

<div>

## <a name="create-users-button"></a><span data-ttu-id="d1c72-139">[ユーザーの作成] ボタン</span><span class="sxs-lookup"><span data-stu-id="d1c72-139">Create Users Button</span></span>

<span data-ttu-id="d1c72-140">[ユーザーの作成] ボタンをクリックすると、すべての入力パラメーターが検証されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-140">When you click on the Create Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="d1c72-141">検証エラーがある場合は、それらの入力値を修正するように求められます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-141">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="d1c72-142">入力値がすべて正しい場合は、Active Directory ドメインサービスでのユーザーの作成が開始されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-142">If all the input values are correct, it will start creating users in Active Directory Domain Services.</span></span> <span data-ttu-id="d1c72-143">進行状況バーは、このフォームの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-143">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="d1c72-144">進行状況バーがアクティブな間は、アプリケーションを閉じないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1c72-144">We recommend that you do not close the application while the progress bar is active.</span></span>

<span data-ttu-id="d1c72-145">ユーザーの作成には時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-145">User Creation is a slow process.</span></span> <span data-ttu-id="d1c72-146">数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-146">It can take several minutes.</span></span> <span data-ttu-id="d1c72-147">ユーザー数が非常に多い場合、プロセスは数時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-147">If the number of users is very large, the process could even take a few hours.</span></span> <span data-ttu-id="d1c72-148">ユーザーが既に存在している場合は、変更を反映して更新されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-148">If the users already exist, they are updated with any changes.</span></span> <span data-ttu-id="d1c72-149">ユーザーが作成されたことを確認するには、範囲内のいずれかのユーザーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="d1c72-149">You can validate that the users were created by logging on as one of the users in the range.</span></span> <span data-ttu-id="d1c72-150">ユーザー名 (LyncUser10@contoso.net など) と、指定したパスワードを使って、ユーザー名としてユーザーのプレフィックス、ユーザー番号、@sipDomain を使います。</span><span class="sxs-lookup"><span data-stu-id="d1c72-150">Use the user prefix, user number, and @sipDomain as the user name (for example, LyncUser10@contoso.net), along with the specified password.</span></span>

</div>

<div>

## <a name="delete-users-button"></a><span data-ttu-id="d1c72-151">[ユーザーの削除] ボタン</span><span class="sxs-lookup"><span data-stu-id="d1c72-151">Delete Users Button</span></span>

<span data-ttu-id="d1c72-152">[ユーザーの削除] ボタンをクリックすると、すべての入力パラメーターが検証されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-152">When you click on Delete Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="d1c72-153">検証エラーがある場合は、それらの入力値を修正するように求められます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-153">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="d1c72-154">入力値がすべて正しい場合は、Active Directory ドメインサービスでユーザーの無効化と削除が開始されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-154">If all the input values are correct, it will start disabling and deleting users in Active Directory Domain Services.</span></span> <span data-ttu-id="d1c72-155">進行状況バーは、このフォームの下部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-155">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="d1c72-156">進行状況バーがアクティブな間は、アプリケーションを閉じないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1c72-156">We recommend that you do not close the application while the progress bar is active.</span></span>

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P><span data-ttu-id="d1c72-157">米国形式の電話番号のみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-157">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="d1c72-158">電話番号は常にユーザーに割り当てられ、Userプロビジョニングツールで作成されたすべてのユーザーはエンタープライズ Voip を有効にします。</span><span class="sxs-lookup"><span data-stu-id="d1c72-158">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice.</span></span> <span data-ttu-id="d1c72-159">電話番号を使用するシナリオ (会議自動アテンダントや UC-PSTN 通話など) では、この電話番号が通話の正しいルーティングのために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-159">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="d1c72-160">このため、すべてのユーザーは固有の電話番号を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-160">For this reason, every user must have a unique phone number.</span></span> <span data-ttu-id="d1c72-161">ユーザーを2回作成する必要がある場合は、別の市外局番を使用しない限り、または以前のユーザー<STRONG>が無効に</STRONG>なっている場合は、このコマンドが失敗します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-161">If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the <STRONG>Disable-CsUser</STRONG> cmdlet.</span></span></P>
> <LI>
> <P><span data-ttu-id="d1c72-162">連絡先を作成する前に、[ユーザー] タブから実行されたユーザーの複製を完了しておく必要があります。ユーザーを作成したばかりの場合は、Lync Server のレプリケーションが完了するのを待って、データベースのユーザーアカウントを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-162">Before you create contacts, you must first complete user replication, performed from the Users tab. If you have just created your users, you must wait until Lync Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="d1c72-163">ユーザーが複製を完了していない場合は、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-163">If the users have not finished replicating, you will see an error.</span></span> <span data-ttu-id="d1c72-164">Lync Server 2013 のフロントエンドサービスが開始された場合、またはユーザーが最後のユーザーに対して、ユーザーの<STRONG>取得-csuser</STRONG>コマンドレットを正常に実行した場合に、ユーザーが複製を完了した日時がわかります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-164">You will know when users have finished replicating if Lync Server 2013 Front End service has started, or by successfully running the <STRONG>Get-CsUser</STRONG> cmdlet on the last user.</span></span></P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a><span data-ttu-id="d1c72-165">[連絡先の作成] タブ</span><span class="sxs-lookup"><span data-stu-id="d1c72-165">Contacts Creation Tab</span></span>

<span data-ttu-id="d1c72-166">[連絡先の作成] タブでは、ユーザーの連絡先の詳細を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-166">The Contacts Creation tab enables you to specify details for users’ contacts.</span></span>

<span data-ttu-id="d1c72-167">![[連絡先の作成] タブ。](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "[連絡先の作成] タブ")</span><span class="sxs-lookup"><span data-stu-id="d1c72-167">![Contacts Creation tab.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Contacts Creation tab.")</span></span>

<span data-ttu-id="d1c72-168">ユーザーの連絡先を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-168">To configure users’ contacts, follow these steps.</span></span>

1.  <span data-ttu-id="d1c72-169">[ユーザーごとの平均連絡先] で、各ユーザーの連絡先リストに入力する連絡先の平均数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-169">In Average Contacts per User, specify the average number of contacts to populate in contact lists for each of the users.</span></span>

2.  <span data-ttu-id="d1c72-170">[Fixed] チェックボックスは、すべてのユーザーに同数の連絡先を作成する場合にオンにします。</span><span class="sxs-lookup"><span data-stu-id="d1c72-170">Select the Fixed check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="d1c72-171">ユーザー用に作成された連絡先の数を変更する場合は、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="d1c72-171">If you want to vary the number of contacts created for users, clear the check box.</span></span>

3.  <span data-ttu-id="d1c72-172">[ユーザーごとの平均連絡先グループ] で、ユーザーごとの連絡先グループの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-172">In Average Contact Groups per User, specify the number of contact groups per user.</span></span> <span data-ttu-id="d1c72-173">この数値は、ユーザー1人あたり平均連絡先より小さい必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-173">This number must be smaller than Average Contacts per User.</span></span>

4.  <span data-ttu-id="d1c72-174">[フェデレーションまたはクロスプールの連絡先割合] で、0 ~ 100 の範囲の数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-174">In Federated / Cross Pool Contacts Percentage, specify a number between 0 and 100.</span></span> <span data-ttu-id="d1c72-175">この割合の連絡先が、フェデレーション ユーザーで作成されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-175">This percentage of contacts will be created with the federated users.</span></span>

5.  <span data-ttu-id="d1c72-176">[フェデレーションまたはクロスプールのユーザープレフィックス] で、ローカルユーザーの連絡先リストに追加されるフェデレーションユーザーのユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-176">In Federated / Cross Pool User Prefix, specify the username for federated users that will be added to the contact lists of local users.</span></span>

6.  <span data-ttu-id="d1c72-177">[フェデレーション/クロスプールユーザー SIP ドメイン] で、フェデレーションされたユーザーの SIP ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-177">In Federated / Cross Pool User SIP Domain, specify the SIP Domain Name of the federated users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1c72-178">連絡先を作成するときに、どのユーザーもサインインする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d1c72-178">None of the users should be signed in when creating contacts.</span></span>

    
    </div>

7.  <span data-ttu-id="d1c72-179">[ユーザー作成] タブで、パラメーターが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-179">In User Creation tab, verify that the parameters are correct.</span></span> <span data-ttu-id="d1c72-180">連絡先を作成するユーザーの範囲は、[ユーザー作成] タブから取得されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-180">The range of users for which contacts will be created is obtained from the User Creation tab.</span></span>

8.  <span data-ttu-id="d1c72-181">[Create Contacts] をクリックして、連絡先の作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-181">Click Create Contacts to begin the contact creation.</span></span> <span data-ttu-id="d1c72-182">この処理は、数分間かかります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-182">This process can take several minutes.</span></span> <span data-ttu-id="d1c72-183">処理の完了後、"Operation Completed Successfully" というメッセージのダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-183">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="d1c72-184">作成した連絡先は、[User Creation] タブで作成したユーザーとしてログインすることで検証できます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-184">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1c72-185">連絡先の作成後、このツールによりターゲット プール内のすべてのフロント エンド サーバーが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-185">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="d1c72-186">フロント エンド サーバーの起動には長い時間がかかることがあります (最大 2 時間)。この時間は、この操作で作成した連絡先の数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-186">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span>

    
    </div>

</div>

<div>

## <a name="distribution-list"></a><span data-ttu-id="d1c72-187">配布リスト</span><span class="sxs-lookup"><span data-stu-id="d1c72-187">Distribution List</span></span>

<span data-ttu-id="d1c72-188">Lync Server 2013 のストレスとパフォーマンスツールの機能の1つは、Lync 2013 の配布リスト (DL) 展開機能をシミュレートすることです。</span><span class="sxs-lookup"><span data-stu-id="d1c72-188">One of the features of the Lync Server 2013 Stress and Performance Tool is to simulate the distribution list (DL) expansion feature in Lync 2013.</span></span> <span data-ttu-id="d1c72-189">Userプロビジョニングツールで DL の展開を有効にしない場合は、この手順をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-189">If you are not going to enable DL expansion in UserProvisioningTool, you can skip this step.</span></span>

<span data-ttu-id="d1c72-190">![[配布リストの作成] タブ](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "[配布リストの作成] タブ")</span><span class="sxs-lookup"><span data-stu-id="d1c72-190">![Distribution List Creation tab.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Distribution List Creation tab.")</span></span>

<span data-ttu-id="d1c72-191">[配布リスト] タブでは、ストレスとパフォーマンスツールが配布リストの展開機能に使用する Dl を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-191">The Distribution List tab enables you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="d1c72-192">DLs を作成する前に、Lync Server 2013 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-192">Prior to creating DLs, Lync Server 2013 must already be installed.</span></span> <span data-ttu-id="d1c72-193">Lync Server 2013 ForestPrep を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1c72-193">You must have run Lync Server 2013 ForestPrep.</span></span> <span data-ttu-id="d1c72-194">そうしないと、DL 属性は Active Directory ドメインサービススキーマに存在せず、ツールが Dl を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="d1c72-194">Otherwise, the DL attributes do not exist in the Active Directory Domain Services schema and the tool will not be able to create DLs.</span></span>

<span data-ttu-id="d1c72-195">配布リストを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-195">To configure distribution lists, follow these steps.</span></span>

1.  <span data-ttu-id="d1c72-196">[配布リストの数] で、作成する Dl の合計数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-196">In Number of Distribution Lists, specify the total number of DLs that you want to create.</span></span> <span data-ttu-id="d1c72-197">(ユーザー数の2倍で始めることをお勧めします)。</span><span class="sxs-lookup"><span data-stu-id="d1c72-197">(We recommend that you start with twice the number of users).</span></span> <span data-ttu-id="d1c72-198">0から n-1 の番号が付けられます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-198">They are numbered from 0 to n-1.</span></span>

2.  <span data-ttu-id="d1c72-199">[配布リストのプレフィックス] で、Dl が持つプレフィックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-199">In Distribution List Prefix, specify the prefix that the DLs will have.</span></span> <span data-ttu-id="d1c72-200">たとえば、100 Dl と testDL のプレフィックスを指定すると、Dl には testDL0、testDL1 などの名前が testDL99 からという名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-200">For example if you specify 100 DLs and a prefix of testDL, the DLs will be named testDL0, testDL1, and so on, through testDL99.</span></span>

3.  <span data-ttu-id="d1c72-201">Dist の最小メンバー数で、各配布リストに追加するユーザーの最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-201">In Minimum Members in a Dist. List, specify the minimum number of users to add in each Distribution List.</span></span>

4.  <span data-ttu-id="d1c72-202">[Dist] リストのメンバーの最大数で、各配布リストに追加するユーザーの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-202">In Maximum Members in a Dist. List, specify the maximum number of users to add in each Distribution List.</span></span>

<div>

## <a name="create-distribution-lists-button"></a><span data-ttu-id="d1c72-203">[配布リストの作成] ボタン</span><span class="sxs-lookup"><span data-stu-id="d1c72-203">Create Distribution Lists Button</span></span>

<span data-ttu-id="d1c72-204">[配布リストの作成] をクリックすると、ツールによって Active Directory ドメインサービスが照会され、プレフィックスと番号が一致する配布リストが既に存在するかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-204">When you click the Create Distribution Lists button, the tool queries Active Directory Domain Services to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="d1c72-205">このツールは、まだ存在していないもののみを作成します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-205">The tool will create only the ones that do not already exist.</span></span> <span data-ttu-id="d1c72-206">新しく作成された配布リストにメンバーを追加すると、[ユーザー作成] タブで指定された範囲からユーザーが選択されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-206">When adding members to these newly created Distribution Lists, it will pick the users from the range specified on the User Creation tab.</span></span>

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a><span data-ttu-id="d1c72-207">[所在地情報] サービス構成タブ</span><span class="sxs-lookup"><span data-stu-id="d1c72-207">Location Info Service Config Tab</span></span>

<span data-ttu-id="d1c72-208">Lync Server 2013 応力とパフォーマンスツールの機能の1つは、位置情報サービスのためのダミー構成ファイルを生成することです。</span><span class="sxs-lookup"><span data-stu-id="d1c72-208">One of the features of the Lync Server 2013 Stress and Performance Tool is to generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="d1c72-209">通常、位置情報サービスは、サーバーに対して大幅なパフォーマンスに影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="d1c72-209">The Location Information Service typically does not have any significant performance impact on the servers.</span></span>

<span data-ttu-id="d1c72-210">![[位置情報] サービス構成タブ。](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "[Location Info Service Config] タブ")</span><span class="sxs-lookup"><span data-stu-id="d1c72-210">![Location Info Service Config tab.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config tab.")</span></span>

<span data-ttu-id="d1c72-211">この機能をテストする場合は、フォームに記載されている値を入力して、[LIS 構成ファイルの生成] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1c72-211">If you choose to test this feature, you can fill in the values mentioned in the form and then click the Generate LIS Config Files button.</span></span> <span data-ttu-id="d1c72-212">\_これにより、lis\_の .csv ファイル (.csv、\_lis、.csv、および LIS\_WAP .csv) という csv ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="d1c72-212">It will generate CSV files called LIS\_Subnet.csv, LIS\_Switches.csv, LIS\_Ports.csv, and LIS\_WAP.csv.</span></span> <span data-ttu-id="d1c72-213">これらの CSV ファイルを LIS データベースにインポートするには、 **CsLisSubnet**コマンドレット、 **CsLisSwitch**コマンドレット、 **CsLisPort**コマンドレット、 **set-CsWirelessAccessPoint**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1c72-213">You can then import these CSV files into LIS database by using the **Set-CsLisSubnet** cmdlet, the **Set-CsLisSwitch** cmdlet, the **Set-CsLisPort** cmdlet, and the **Set-CsWirelessAccessPoint** cmdlet, respectively.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

