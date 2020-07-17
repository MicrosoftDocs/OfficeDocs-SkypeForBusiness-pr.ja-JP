---
title: ユーザーと連絡先を作成する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f90e6cbb1afb9c4c2dd2b43e1448ca635899531b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a><span data-ttu-id="1a92d-102">ユーザーと連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="1a92d-102">Create Users and Contacts</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a92d-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="1a92d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="1a92d-104">ストレスおよびパフォーマンスの負荷テストの準備として、Lync Server 2013 ユーザープロビジョニングツール (UserProvisioningTool.exe) を使用して、ユーザーと連絡先を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a92d-104">You must use the Lync Server 2013 User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts in preparation for stress and performance load testing.</span></span>

<span data-ttu-id="1a92d-105">ここでは、このトピックを読んでいるときに役立つ可能性がある用語と定義の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-105">Here is a list of terms and definitions that you might find useful as you read through this topic.</span></span>

  - <span data-ttu-id="1a92d-106">組織単位– Active Directory ドメインサービスの組織単位 (OU)。</span><span class="sxs-lookup"><span data-stu-id="1a92d-106">Organizational Unit – The Active Directory Domain Services organizational unit (OU).</span></span>

  - <span data-ttu-id="1a92d-107">フェデレーション/クロスプール– MSN ネットワーク、AOL®、Yahoo®などの他のインスタントメッセージング (IM) サービスのユーザーとの通信を有効にするユーザー \! 。</span><span class="sxs-lookup"><span data-stu-id="1a92d-107">Federated / Cross Pool – Users who will be enabled to communicate with users from other Instant Messaging (IM) services, such as MSN network of Internet services, AOL®, and Yahoo\!®.</span></span>

  - <span data-ttu-id="1a92d-108">配布リスト–ユーザーグループとの通信を開始するために使用される active directory ドメインサービスユーザーの一覧を含む Active Directory ドメインサービス内のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1a92d-108">Distribution Lists – The objects in Active Directory Domain Services that contain a list of Active Directory Domain Services users, used for launching communications with groups of people.</span></span>

  - <span data-ttu-id="1a92d-109">Location Info Service –電話で有効化および構成されている場合に、拡張 9-1-1 (E9-1-1) サービスの物理的な場所の取得を有効にする Lync Server 2013 サービス。</span><span class="sxs-lookup"><span data-stu-id="1a92d-109">Location Info Service – The Lync Server 2013 service that, when enabled and configured per phone, enables retrieval of physical location for Enhanced 9-1-1 (E9-1-1) services.</span></span>

  - <span data-ttu-id="1a92d-110">米国の電話番号–着信と発信の通話および逆引き番号参照 (RNL) のルーティングに使用される SIP URI に加えて、ユーザーに割り当てられている電話番号。</span><span class="sxs-lookup"><span data-stu-id="1a92d-110">U.S. Phone Numbers – The phone numbers that are assigned to users, in addition to the SIP URI that is used for routing inbound and outbound calls and reverse number lookup (RNL).</span></span>

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a><span data-ttu-id="1a92d-111">UserProvisioningTool.exe を使用してユーザーと連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="1a92d-111">Create Users and Contacts by Using UserProvisioningTool.exe</span></span>

<span data-ttu-id="1a92d-112">Lync Server ユーザープロビジョニングツールを使用して、ロードシミュレーション用のユーザーと連絡先を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a92d-112">You must use the Lync Server User Provisioning Tool to create users and contacts for load simulation.</span></span> <span data-ttu-id="1a92d-113">Lync server ユーザープロビジョニングツールは、Lync Server のストレスおよびパフォーマンスツールパッケージと共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-113">The Lync Server User Provisioning Tool is installed with the Lync Server Stress and Performance Tool package.</span></span> <span data-ttu-id="1a92d-114">パッケージインストーラー (CapacityPlanningTool.msi) がフロントエンドサーバーまたは Standard Edition サーバー上で実行されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1a92d-114">Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server.</span></span> <span data-ttu-id="1a92d-115">\\フロントエンドサーバーまたは Standard Edition サーバーのファイル UserProvisioningTool.exe (% LyncStress directory% LyncStressAndPerfTool にあります) を実行して、Lync Server ユーザープロビジョニングツールを開始します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-115">Start the Lync Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\\LyncStress) on the Front End Server or on the Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1a92d-116">UserProvisioningTool.exe を実行するためには、Domain Admins セキュリティグループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a92d-116">You must be logged on as a member of the Domain Admins security group in order to run UserProvisioningTool.exe.</span></span> <span data-ttu-id="1a92d-117">UserProvisioningTool.exe が新しい Active Directory ドメインサービスユーザーを作成および構成するため、このコンテキストから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a92d-117">It is necessary to run from this context because UserProvisioningTool.exe will be creating and configuring new Active Directory Domain Services users.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1a92d-118">多数のユーザー (1万以上) を作成する場合は、ハイエンドコンピューターから UserProvisioningTool.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-118">When you create a significant number of users (10,000 or more), run UserProvisioningTool.exe from a high-end computer.</span></span> <span data-ttu-id="1a92d-119">なお、ユーザーが作成されている間は、ドメインコントローラーの負荷も高くなります。</span><span class="sxs-lookup"><span data-stu-id="1a92d-119">Note that the domain controller will also experience high load while the users are being created.</span></span>



</div>

<span data-ttu-id="1a92d-120">Lync Server ユーザープロビジョニングツールが開いたら、[**構成**] をクリックして、[**構成の読み込み**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-120">When the Lync Server User Provisioning Tool opens, click **Configuration** and select **Load Configuration**.</span></span> <span data-ttu-id="1a92d-121">ユーザーおよび連絡先の構成を開始するには、SampleData.xml パッケージに含まれる既定のファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-121">To begin configuring users and contacts, load the default file that is included in the package, SampleData.xml.</span></span> <span data-ttu-id="1a92d-122">これにより、システムで変更する必要があるサンプルデータのフィールドが事前に作成されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-122">This will prepopulate the fields with example data that you'll need to revise for your system.</span></span> <span data-ttu-id="1a92d-123">既にカスタマイズされた設定を含む XML ファイルが事前に構成されている場合は、そのファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-123">If you have a preconfigured XML file that already contains customized settings, load that file instead.</span></span> <span data-ttu-id="1a92d-124">次のセクションで説明されているように、Lync Server ユーザープロビジョニングツールのフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-124">Fill in the fields in the Lync Server User Provisioning Tool, as described in the following sections.</span></span>

<span data-ttu-id="1a92d-125">![[ユーザー作成] タブ](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "[ユーザー作成] タブ")</span><span class="sxs-lookup"><span data-stu-id="1a92d-125">![User Creation tab.](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "User Creation tab.")</span></span>

<span data-ttu-id="1a92d-126">サーバーオプションを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-126">To configure server options, follow these steps.</span></span>

1.  <span data-ttu-id="1a92d-127">[**フロントエンドプールの fqdn**] に、ユーザーをホストする Standard Edition サーバーまたはフロントエンドプールの完全修飾ドメイン名 (fqdn) を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-127">In **Front End Pool FQDN**, type the fully qualified domain name (FQDN) of the Standard Edition server or Front End pool where you want to host the users.</span></span>

2.  <span data-ttu-id="1a92d-128">[**ユーザー名のプレフィックス**] に、テストのためにユーザー名を作成するために使用するプレフィックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-128">In **User Name Prefix**, type a prefix that you want to use to build user names for testing purposes.</span></span>

3.  <span data-ttu-id="1a92d-129">[**パスワード**] で、すべてのテストユーザーアカウントに適用されるパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-129">In **Password**, specify a password that will be applied for all of the test user accounts.</span></span>

4.  <span data-ttu-id="1a92d-130">[ **Sip ドメイン**] に、テストユーザーの SIP Uri (Uniform resource identifier) に使用するドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-130">In **SIP Domain**, type the domain name to be used for test users’ SIP URIs (Uniform Resource Identifiers).</span></span>

5.  <span data-ttu-id="1a92d-131">[**アカウントドメイン**] で、テストユーザーを作成する、現在の Active Directory ドメインサービスドメインのドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-131">In **Account Domain**, type the domain name of your current Active Directory Domain Services domain, under which you want to create the test users.</span></span>

6.  <span data-ttu-id="1a92d-132">[**組織単位**] に、ユーザーオブジェクトを作成する Active Directory ドメインサービス OU の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-132">In **Organizational Unit**, type the name of the Active Directory Domain Services OU where you want to create the User objects.</span></span> <span data-ttu-id="1a92d-133">OU が存在しない場合は、作成されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-133">If the OU does not exist, it will be created.</span></span>

7.  <span data-ttu-id="1a92d-134">[**電話番号のコード**] で、テストユーザーアカウントに使用される3桁の市外局番を入力します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-134">In **Phone Area Code**, type the three-digit area code that will be used for test user accounts.</span></span> <span data-ttu-id="1a92d-135">Active Directory ドメインサービスの他のユーザーの市外局番と、電話の市外局番が競合しないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="1a92d-135">Be sure that phone area code does not conflict with any other users’ area codes in Active Directory Domain Services.</span></span>

8.  <span data-ttu-id="1a92d-136">エンタープライズ Voip のテストユーザーを有効にする場合は、[**音声を有効**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1a92d-136">Select the **Voice Enabled** check box if you want to enable the test users for Enterprise Voice.</span></span>

9.  <span data-ttu-id="1a92d-137">[**ユーザー**数] で、作成するテストユーザーの合計数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-137">In **Number of Users**, specify the total number of test users that you want to create.</span></span>

10. <span data-ttu-id="1a92d-138">[**開始インデックス**] で、ユーザー名プレフィックスのサフィックスとして使用する開始番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-138">In **Start Index**, specify the starting number that will be used as suffix to the user name prefix.</span></span>

<div>

## <a name="create-users-button"></a><span data-ttu-id="1a92d-139">[ユーザーの作成] ボタン</span><span class="sxs-lookup"><span data-stu-id="1a92d-139">Create Users Button</span></span>

<span data-ttu-id="1a92d-140">[ユーザーの作成] ボタンをクリックすると、すべての入力パラメーターが検証されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-140">When you click on the Create Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="1a92d-141">検証エラーがある場合は、入力値を修正するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-141">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="1a92d-142">入力値がすべて正しい場合は、Active Directory ドメインサービスでユーザーの作成が開始されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-142">If all the input values are correct, it will start creating users in Active Directory Domain Services.</span></span> <span data-ttu-id="1a92d-143">このフォームの下部に進行状況バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-143">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="1a92d-144">進行状況バーがアクティブな間はアプリケーションを閉じないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1a92d-144">We recommend that you do not close the application while the progress bar is active.</span></span>

<span data-ttu-id="1a92d-145">ユーザーの作成は低速なプロセスです。</span><span class="sxs-lookup"><span data-stu-id="1a92d-145">User Creation is a slow process.</span></span> <span data-ttu-id="1a92d-146">数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a92d-146">It can take several minutes.</span></span> <span data-ttu-id="1a92d-147">ユーザー数が非常に多い場合は、処理に数時間かかることもあります。</span><span class="sxs-lookup"><span data-stu-id="1a92d-147">If the number of users is very large, the process could even take a few hours.</span></span> <span data-ttu-id="1a92d-148">ユーザーが既に存在する場合は、変更によって更新されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-148">If the users already exist, they are updated with any changes.</span></span> <span data-ttu-id="1a92d-149">ユーザーが作成されたことを検証するには、範囲内のユーザーの1人としてログオンします。</span><span class="sxs-lookup"><span data-stu-id="1a92d-149">You can validate that the users were created by logging on as one of the users in the range.</span></span> <span data-ttu-id="1a92d-150">ユーザー名 (LyncUser10@contoso.net など) として、および指定されたパスワードを使用して、ユーザーのプレフィックス、ユーザー番号、@sipDomain を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-150">Use the user prefix, user number, and @sipDomain as the user name (for example, LyncUser10@contoso.net), along with the specified password.</span></span>

</div>

<div>

## <a name="delete-users-button"></a><span data-ttu-id="1a92d-151">[ユーザーの削除] ボタン</span><span class="sxs-lookup"><span data-stu-id="1a92d-151">Delete Users Button</span></span>

<span data-ttu-id="1a92d-152">[ユーザーの削除] ボタンをクリックすると、すべての入力パラメーターが検証されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-152">When you click on Delete Users button, it will validate all the input parameters.</span></span>

  - <span data-ttu-id="1a92d-153">検証エラーがある場合は、入力値を修正するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-153">If there are any validation errors, it will prompt you to correct those input values.</span></span>

  - <span data-ttu-id="1a92d-154">入力値がすべて正しい場合は、Active Directory ドメインサービスでユーザーの無効化と削除が開始されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-154">If all the input values are correct, it will start disabling and deleting users in Active Directory Domain Services.</span></span> <span data-ttu-id="1a92d-155">このフォームの下部に進行状況バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-155">A progress bar will appear at the bottom of this form.</span></span> <span data-ttu-id="1a92d-156">進行状況バーがアクティブな間はアプリケーションを閉じないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1a92d-156">We recommend that you do not close the application while the progress bar is active.</span></span>

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P><span data-ttu-id="1a92d-157">米国形式の電話番号のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="1a92d-157">Only U.S.-formatted phone numbers are supported.</span></span> <span data-ttu-id="1a92d-158">電話番号は常にユーザーに割り当てられ、UserProvisioningTool.exe によって作成されたすべてのユーザーがエンタープライズ Voip に対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="1a92d-158">Phone numbers are always assigned to users, and all users created by UserProvisioningTool.exe are enabled for Enterprise Voice.</span></span> <span data-ttu-id="1a92d-159">電話会議の自動応答や UC 通話など、電話番号を使用するシナリオでは、この電話番号を使用して通話を適切にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="1a92d-159">Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls.</span></span> <span data-ttu-id="1a92d-160">このため、すべてのユーザーが一意の電話番号を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a92d-160">For this reason, every user must have a unique phone number.</span></span> <span data-ttu-id="1a92d-161">ユーザーを2回作成する必要がある場合は、別の市外局番を使用しないと、このコマンドは失敗します。または、以前のユーザーが無効にされている場合は、 <STRONG>Disable-CsUser</STRONG>コマンドレットを使用しています。</span><span class="sxs-lookup"><span data-stu-id="1a92d-161">If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the <STRONG>Disable-CsUser</STRONG> cmdlet.</span></span></P>
> <LI>
> <P><span data-ttu-id="1a92d-162">連絡先を作成する前に、[ユーザー] タブから実行する最初に、ユーザーのレプリケーションを完了する必要があります。ユーザーを作成したばかりの場合は、Lync Server のレプリケーションが完了するのを待って、データベースのユーザーアカウントを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a92d-162">Before you create contacts, you must first complete user replication, performed from the Users tab. If you have just created your users, you must wait until Lync Server replication completes and populates the user accounts in the database.</span></span> <span data-ttu-id="1a92d-163">ユーザーが複製を完了していない場合は、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-163">If the users have not finished replicating, you will see an error.</span></span> <span data-ttu-id="1a92d-164">Lync Server 2013 のフロントエンドサービスが開始された場合、または最後のユーザーに対して<STRONG>Get-help ユーザー</STRONG>コマンドレットが正常に実行された場合に、ユーザーがレプリケーションを終了したことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-164">You will know when users have finished replicating if Lync Server 2013 Front End service has started, or by successfully running the <STRONG>Get-CsUser</STRONG> cmdlet on the last user.</span></span></P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a><span data-ttu-id="1a92d-165">[連絡先の作成] タブ</span><span class="sxs-lookup"><span data-stu-id="1a92d-165">Contacts Creation Tab</span></span>

<span data-ttu-id="1a92d-166">[連絡先の作成] タブでは、ユーザーの連絡先の詳細を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-166">The Contacts Creation tab enables you to specify details for users’ contacts.</span></span>

<span data-ttu-id="1a92d-167">![[連絡先の作成] タブ](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "[連絡先の作成] タブ")</span><span class="sxs-lookup"><span data-stu-id="1a92d-167">![Contacts Creation tab.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Contacts Creation tab.")</span></span>

<span data-ttu-id="1a92d-168">ユーザーの連絡先を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-168">To configure users’ contacts, follow these steps.</span></span>

1.  <span data-ttu-id="1a92d-169">[ユーザーごとの平均連絡先] で、各ユーザーの連絡先リストに設定する連絡先の平均数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-169">In Average Contacts per User, specify the average number of contacts to populate in contact lists for each of the users.</span></span>

2.  <span data-ttu-id="1a92d-170">すべてのユーザーに対して同じ数の連絡先を作成する場合は、[固定] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="1a92d-170">Select the Fixed check box if you want to create an equal number of contacts for every user.</span></span> <span data-ttu-id="1a92d-171">ユーザーに対して作成する連絡先の数を変更する場合は、このチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="1a92d-171">If you want to vary the number of contacts created for users, clear the check box.</span></span>

3.  <span data-ttu-id="1a92d-172">[ユーザーごとの平均連絡先グループ] で、ユーザーごとの連絡先グループの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-172">In Average Contact Groups per User, specify the number of contact groups per user.</span></span> <span data-ttu-id="1a92d-173">この数値は、ユーザーごとの平均連絡先よりも小さくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a92d-173">This number must be smaller than Average Contacts per User.</span></span>

4.  <span data-ttu-id="1a92d-174">[フェデレーション/プール間の連絡先の割合] で、0 ~ 100 の範囲の数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-174">In Federated / Cross Pool Contacts Percentage, specify a number between 0 and 100.</span></span> <span data-ttu-id="1a92d-175">この割合の連絡先は、フェデレーションユーザーによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-175">This percentage of contacts will be created with the federated users.</span></span>

5.  <span data-ttu-id="1a92d-176">[フェデレーション/クロスプールのユーザープレフィックス] で、ローカルユーザーの連絡先リストに追加するフェデレーションユーザーのユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-176">In Federated / Cross Pool User Prefix, specify the username for federated users that will be added to the contact lists of local users.</span></span>

6.  <span data-ttu-id="1a92d-177">[フェデレーション/クロスプールユーザー SIP ドメイン] で、フェデレーションユーザーの SIP ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-177">In Federated / Cross Pool User SIP Domain, specify the SIP Domain Name of the federated users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1a92d-178">連絡先を作成するときに、ユーザーにサインインする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1a92d-178">None of the users should be signed in when creating contacts.</span></span>

    
    </div>

7.  <span data-ttu-id="1a92d-179">[ユーザーの作成] タブで、パラメーターが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-179">In User Creation tab, verify that the parameters are correct.</span></span> <span data-ttu-id="1a92d-180">連絡先を作成するユーザーの範囲は、[ユーザーの作成] タブから取得されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-180">The range of users for which contacts will be created is obtained from the User Creation tab.</span></span>

8.  <span data-ttu-id="1a92d-181">[連絡先の作成] をクリックして、連絡先の作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-181">Click Create Contacts to begin the contact creation.</span></span> <span data-ttu-id="1a92d-182">この処理には数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a92d-182">This process can take several minutes.</span></span> <span data-ttu-id="1a92d-183">完了すると、"操作は正常に完了しました" というメッセージと共にダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-183">After it completes, a dialog box will appear with the message, "Operation Completed Successfully."</span></span> <span data-ttu-id="1a92d-184">[ユーザーの作成] タブから作成されたユーザーとしてログオンすることによって作成された連絡先を検証できます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-184">You can validate the contacts that were created by logging on as a user that was created from the User Creation tab.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1a92d-185">連絡先を作成した後、このツールは、移動先のプール内のすべてのフロントエンドサーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-185">After the contacts are created, this tool will restart all the Front End Servers in the target pool.</span></span> <span data-ttu-id="1a92d-186">この操作によって作成された連絡先の数によっては、フロントエンドサーバーが起動するまでに長い時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a92d-186">It may take longer (up to 2 hours) for the Front End Servers to start, depending on how many contacts were created by this operation.</span></span>

    
    </div>

</div>

<div>

## <a name="distribution-list"></a><span data-ttu-id="1a92d-187">配布リスト</span><span class="sxs-lookup"><span data-stu-id="1a92d-187">Distribution List</span></span>

<span data-ttu-id="1a92d-188">Lync Server 2013 のストレスおよびパフォーマンスツールの機能の1つは、Lync 2013 で配布リスト (DL) の展開機能をシミュレートすることです。</span><span class="sxs-lookup"><span data-stu-id="1a92d-188">One of the features of the Lync Server 2013 Stress and Performance Tool is to simulate the distribution list (DL) expansion feature in Lync 2013.</span></span> <span data-ttu-id="1a92d-189">Userare Tool で DL 拡張を有効にしない場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-189">If you are not going to enable DL expansion in UserProvisioningTool, you can skip this step.</span></span>

<span data-ttu-id="1a92d-190">![[配布リストの作成] タブ](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "[配布リストの作成] タブ")</span><span class="sxs-lookup"><span data-stu-id="1a92d-190">![Distribution List Creation tab.](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Distribution List Creation tab.")</span></span>

<span data-ttu-id="1a92d-191">[配布リスト] タブを使用すると、ストレスおよびパフォーマンスツールが配布リストの展開機能で使用する Dl を作成できます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-191">The Distribution List tab enables you to create DLs that the Stress and Performance Tool will use for Distribution List Expansion feature.</span></span> <span data-ttu-id="1a92d-192">DLs を作成する前に、Lync Server 2013 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a92d-192">Prior to creating DLs, Lync Server 2013 must already be installed.</span></span> <span data-ttu-id="1a92d-193">Lync Server 2013 ForestPrep を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a92d-193">You must have run Lync Server 2013 ForestPrep.</span></span> <span data-ttu-id="1a92d-194">それ以外の場合、DL 属性は Active Directory ドメインサービススキーマに存在しないため、ツールは DLs を作成できません。</span><span class="sxs-lookup"><span data-stu-id="1a92d-194">Otherwise, the DL attributes do not exist in the Active Directory Domain Services schema and the tool will not be able to create DLs.</span></span>

<span data-ttu-id="1a92d-195">配布リストを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-195">To configure distribution lists, follow these steps.</span></span>

1.  <span data-ttu-id="1a92d-196">[配布リストの数] で、作成する Dl の合計数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-196">In Number of Distribution Lists, specify the total number of DLs that you want to create.</span></span> <span data-ttu-id="1a92d-197">(ユーザー数の2倍にすることをお勧めします)。</span><span class="sxs-lookup"><span data-stu-id="1a92d-197">(We recommend that you start with twice the number of users).</span></span> <span data-ttu-id="1a92d-198">0 ~ n-1 の番号が付けられます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-198">They are numbered from 0 to n-1.</span></span>

2.  <span data-ttu-id="1a92d-199">[配布リストのプレフィックス] で、DLs が持つプレフィックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-199">In Distribution List Prefix, specify the prefix that the DLs will have.</span></span> <span data-ttu-id="1a92d-200">たとえば、100 Dl という名前の testDL を指定すると、DLs には testDL0、testDL1 という名前が付けられ、testDL99 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-200">For example if you specify 100 DLs and a prefix of testDL, the DLs will be named testDL0, testDL1, and so on, through testDL99.</span></span>

3.  <span data-ttu-id="1a92d-201">[Dist.] の [最低限のメンバー] で、各配布リストに追加するユーザーの最小数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-201">In Minimum Members in a Dist. List, specify the minimum number of users to add in each Distribution List.</span></span>

4.  <span data-ttu-id="1a92d-202">[Dist. の最大メンバー数] ボックスの一覧で、各配布リストに追加するユーザーの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-202">In Maximum Members in a Dist. List, specify the maximum number of users to add in each Distribution List.</span></span>

<div>

## <a name="create-distribution-lists-button"></a><span data-ttu-id="1a92d-203">[配布リストの作成] ボタン</span><span class="sxs-lookup"><span data-stu-id="1a92d-203">Create Distribution Lists Button</span></span>

<span data-ttu-id="1a92d-204">[配布リストの作成] ボタンをクリックすると、Active Directory ドメインサービスに照会して、プレフィックスと番号に一致する配布リストが既に存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-204">When you click the Create Distribution Lists button, the tool queries Active Directory Domain Services to see if distribution lists matching the prefix and numbers already exist.</span></span> <span data-ttu-id="1a92d-205">このツールでは、まだ存在していないもののみが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-205">The tool will create only the ones that do not already exist.</span></span> <span data-ttu-id="1a92d-206">新しく作成した配布リストにメンバーを追加すると、[ユーザーの作成] タブで指定された範囲からユーザーが選択されます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-206">When adding members to these newly created Distribution Lists, it will pick the users from the range specified on the User Creation tab.</span></span>

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a><span data-ttu-id="1a92d-207">[Location Info Service Config] タブ</span><span class="sxs-lookup"><span data-stu-id="1a92d-207">Location Info Service Config Tab</span></span>

<span data-ttu-id="1a92d-208">Lync Server 2013 ストレスおよびパフォーマンスツールの機能の1つは、場所情報サービスのダミー構成ファイルを生成することです。</span><span class="sxs-lookup"><span data-stu-id="1a92d-208">One of the features of the Lync Server 2013 Stress and Performance Tool is to generate dummy configuration files for the Location Information Service.</span></span> <span data-ttu-id="1a92d-209">通常、場所情報サービスは、サーバーのパフォーマンスに重大な影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="1a92d-209">The Location Information Service typically does not have any significant performance impact on the servers.</span></span>

<span data-ttu-id="1a92d-210">![[Location Info Service Config] タブ](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "[Location Info Service Config] タブ")</span><span class="sxs-lookup"><span data-stu-id="1a92d-210">![Location Info Service Config tab.](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Location Info Service Config tab.")</span></span>

<span data-ttu-id="1a92d-211">この機能をテストすることを選択した場合は、フォームに記載されている値を入力し、[LIS Config ファイルの生成] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a92d-211">If you choose to test this feature, you can fill in the values mentioned in the form and then click the Generate LIS Config Files button.</span></span> <span data-ttu-id="1a92d-212">これにより、LIS \_Subnet.csv、lis \_Switches.csv、lis \_Ports.csv、および lisWAP.csv という CSV ファイルが生成され \_ ます。</span><span class="sxs-lookup"><span data-stu-id="1a92d-212">It will generate CSV files called LIS\_Subnet.csv, LIS\_Switches.csv, LIS\_Ports.csv, and LIS\_WAP.csv.</span></span> <span data-ttu-id="1a92d-213">その後、これらの CSV ファイルを LIS データベースにインポートするには、 **CsLisSubnet**コマンドレット、 **CsLisSwitch**コマンドレット、 **CsLisPort**コマンドレット、および**CsWirelessAccessPoint**コマンドレットをそれぞれ使用します。</span><span class="sxs-lookup"><span data-stu-id="1a92d-213">You can then import these CSV files into LIS database by using the **Set-CsLisSubnet** cmdlet, the **Set-CsLisSwitch** cmdlet, the **Set-CsLisPort** cmdlet, and the **Set-CsWirelessAccessPoint** cmdlet, respectively.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

