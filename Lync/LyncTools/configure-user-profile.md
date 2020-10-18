---
title: ユーザープロファイルを構成する
description: ユーザープロファイルを構成します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 682297da43797dd2d774094e85e8688ef3c64d98
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573093"
---
# <a name="configure-user-profile"></a><span data-ttu-id="6cc08-103">ユーザープロファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="6cc08-103">Configure User Profile</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cc08-104">_**トピックの最終更新日:** 2018-10-11_</span><span class="sxs-lookup"><span data-stu-id="6cc08-104">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="6cc08-105">Lync Server 2013 ストレスおよびパフォーマンスツールパッケージに含まれているツールを使用すると、ロードシミュレーションの実行に使用できるテストユーザーアカウントを作成および構成できます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-105">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="6cc08-106">Lync Server 2013 ユーザー作成ツールを使用して、ユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-106">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="6cc08-107">(詳細については、「 [Create Users And Contacts](create-users-and-contacts.md)」を参照してください)。ユーザーが作成されたら、Lync Server 2013 負荷構成ツールを使用してユーザープロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-107">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="6cc08-108">Lync Server 2013 Load 構成ツールの実行</span><span class="sxs-lookup"><span data-stu-id="6cc08-108">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="6cc08-109">ユーザープロファイルを構成するには、Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) を実行し、各タブに入力します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-109">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="6cc08-110">UserProfileGenerator.exe は、シミュレーションを実行するために必要な各クライアントコンピューターのディレクトリを生成します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-110">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="6cc08-111">各クライアントディレクトリには、Lync Server 2013 ストレスおよびパフォーマンスツール (LyncPerfTool.exe) のすべてのインスタンスを開始するためのスクリプトも付属しています。</span><span class="sxs-lookup"><span data-stu-id="6cc08-111">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6cc08-112">Userprofilegenerator.exe で指定されたユーザー固有の値は、プールの Lync Server 2013 ユーザー作成ツール (User Tool) で指定された値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-112">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="6cc08-113">次のセクションで説明するように、Lync Server 2013 Load Configuration Tool の各タブのフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-113">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="6cc08-114">一般的な構成</span><span class="sxs-lookup"><span data-stu-id="6cc08-114">Common Configuration</span></span>

<span data-ttu-id="6cc08-115">次の図は、Lync Server 2013 Load Configuration Tool の [ **共通の構成** ] タブを示しています。</span><span class="sxs-lookup"><span data-stu-id="6cc08-115">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="6cc08-116">次の手順で説明されているように、[ **共通の構成** ] タブのフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-116">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="6cc08-117">![[共通の構成] タブ](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "[共通の構成] タブ")</span><span class="sxs-lookup"><span data-stu-id="6cc08-117">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="6cc08-118">[ **使用可能なコンピューターの数**] で、LyncPerfTool.exe を実行するために使用するコンピューターの数を入力またはクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cc08-118">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="6cc08-119">シミュレートする必要がある4500ユーザーごとに1台のコンピューターを用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6cc08-119">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="6cc08-120">この数は、負荷レベルを下げる場合、または使用可能な機能のサブセットのみを使用する場合には、異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-120">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="6cc08-121">(負荷レベルは **[一般的なシナリオ** ] タブで設定します)。</span><span class="sxs-lookup"><span data-stu-id="6cc08-121">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="6cc08-122">[ **ユーザー名の接頭辞**] に、ユーザーのユーザー名のプレフィックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-122">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="6cc08-123">ログインするには、Uniform Resource Identifier (URI) は次のようになります: UserPrefix \[ User Start Index...(ユーザー数-1) \]@User ドメイン</span><span class="sxs-lookup"><span data-stu-id="6cc08-123">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="6cc08-124">[ **すべてのユーザーのパスワード**] に、ユーザーの作成に使用したパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-124">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="6cc08-125">このフィールドを空白のままにすると、ユーザー名がパスワードとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-125">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="6cc08-126">[ **ユーザーの開始インデックス**] で、構成する最初のユーザーのインデックスをクリックまたは入力します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-126">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="6cc08-127">さまざまな種類または負荷レベルに対して異なる範囲を構成できますが、構成する範囲ごとに UserProfileGenerator.exe を1回実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-127">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="6cc08-128">[ **ユーザー数**] で、構成するユーザーの合計数をクリックまたは入力します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-128">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="6cc08-129">[ **ユーザーのドメイン**] に、SIP URI に使用するドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-129">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="6cc08-130">これは、Lync Server 2013 フロントエンドサーバーまたは Standard Edition サーバーにログオンする各ユーザーの SIP URI を作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-130">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="6cc08-131">アカウントドメインとは別のものにすることができます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-131">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="6cc08-132">[ **アカウントドメイン**] で、Active Directory ドメインサービスのドメインログオンを入力します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-132">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="6cc08-133">ツールによってすべてのエンドポイント/ユーザーにログインする1秒あたりの同時エンドポイント数の最大値を入力します **(インスタンスごと)** 。</span><span class="sxs-lookup"><span data-stu-id="6cc08-133">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="6cc08-134">推奨されるレートは \< 2 秒/標準 SKU FE です。</span><span class="sxs-lookup"><span data-stu-id="6cc08-134">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="6cc08-135">[ **アクセスプロキシまたはプールの fqdn**] で、クライアントを接続するサーバーの完全修飾ドメイン名 (fqdn) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-135">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="6cc08-136">ユーザーが外部でログオンしている場合は、アクセスプロキシを指定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-136">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="6cc08-137">ユーザーが内部の場合は、プールまたは Standard Edition サーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-137">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="6cc08-138">[ **ポート**] で、SIP に対してユーザーが使用するポートをクリックまたは入力します (既定値は5061です)。</span><span class="sxs-lookup"><span data-stu-id="6cc08-138">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="6cc08-139">[外部ネットワークサーバー設定] で、 **アクセスプロキシまたはプールの FQDN** と **ポート**を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-139">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="6cc08-140">これらの設定は、外部エンドポイントの負荷シミュレーションにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-140">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="6cc08-141">一般的なシナリオ</span><span class="sxs-lookup"><span data-stu-id="6cc08-141">General Scenarios</span></span>

<span data-ttu-id="6cc08-142">次の図は、Lync Server 2013 Load Configuration Tool の **[一般的なシナリオ** ] タブを示しています。</span><span class="sxs-lookup"><span data-stu-id="6cc08-142">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="6cc08-143">実行する一般的な各シナリオのロードレベルとパラメーターを構成するか、または無効のままにします。</span><span class="sxs-lookup"><span data-stu-id="6cc08-143">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="6cc08-144">![[一般的なシナリオ] タブ](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "[一般的なシナリオ] タブ")</span><span class="sxs-lookup"><span data-stu-id="6cc08-144">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="6cc08-145">ピアツーピアおよび電話会議が含まれる **インスタントメッセージング**では、負荷レベルに対して適切な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-145">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6cc08-146">すべてのフィールド (場所情報サービスを除く) の読み込みレベルの値は、 <STRONG>無効</STRONG>、 <STRONG>低</STRONG>、 <STRONG>中</STRONG>、 <STRONG>高</STRONG>、および <STRONG>カスタム</STRONG>です。</span><span class="sxs-lookup"><span data-stu-id="6cc08-146">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="6cc08-147">[低]、[中]、[高]、または [カスタム] を選択すると、各モダリティとクライアントの構成が生成されます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-147">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="6cc08-148">High を指定すると、サーバーに対してサポートされる最大負荷が発生します。中では、負荷の60% に相当し、Low は負荷の30% に対応します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-148">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="6cc08-149">電話会議のみである **電話会議**では、[Load Level] に適切な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-149">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="6cc08-150">ピアツーピア通話については、このトピックで後述する「音声シナリオ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cc08-150">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="6cc08-151">マルチビューを有効にするには、そのモダリティの **[詳細設定** ] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-151">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="6cc08-152">[ **アプリケーション共有**] で、Load Level に適切な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-152">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="6cc08-153">データ会議を含む **データの共同作業**では、適切な負荷レベルの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-153">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="6cc08-154">[ **配布リストの展開**] で、[Load Level] に適切な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-154">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="6cc08-155">また、[ **詳細設定** ] ボタンをクリックして、Lync Server ユーザー作成ツール (UserProvisioningTool.exe) の [ **配布リスト** ] タブで構成した値と同じ値をフィールドに入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-155">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="6cc08-156">これらのフィールドの詳細については、「[ユーザーおよび連絡先の作成](create-users-and-contacts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6cc08-156">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="6cc08-157">アドレス帳の [ **Web クエリ**] (アドレス帳のファイルのダウンロードではない) で、[Load Level] に適切な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-157">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="6cc08-158">アドレス帳のダウンロードを有効にするには、対応する [ **詳細** 設定] ボタンをクリックして、 **EnableABSDownload** を true に設定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-158">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="6cc08-159">[ **応答グループサービス**] で、[Load Level] に適切な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-159">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="6cc08-160">対応する **[詳細設定** ] ボタンをクリックし、応答グループサービスエージェントをプロビジョニングするときに既に作成した応答グループの uri を指定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-160">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="6cc08-161">少なくとも1つの応答グループを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-161">You must specify at least one response group.</span></span> <span data-ttu-id="6cc08-162">複数の応答グループを区切るには、セミコロンを使用します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-162">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="6cc08-163">RGSUriSuffixStartIndex および RGSUriSuffixEndIndex を実際の値に更新します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-163">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="6cc08-164">[ **場所情報サービス**] で、[ロードレベル] に適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-164">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="6cc08-165">場所情報サービスの負荷レベルを **有効** または **無効**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-165">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6cc08-166">各シナリオには、その横に <STRONG>[詳細設定</STRONG> ] ボタンがあり、シナリオのバリエーションを有効にする一連のチェックボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-166">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="6cc08-167"><STRONG>Ad-hoc は</STRONG> 、1時間全体に作成される会議のシミュレーションを生成することを意味します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-167"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="6cc08-168"><STRONG>大きな Conf</STRONG> は、大規模な会議のシナリオがシミュレートされることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-168"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="6cc08-169"><STRONG>External</STRONG> は、外部ユーザーもシミュレートすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-169"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="6cc08-170">これらのボタンとチェックボックスを使用すると、Lync Server 2013 のストレスおよびパフォーマンスツール (LyncPerfTool) の動作を変更したり、カスタマイズを可能にしたりする各シナリオに固有の値にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-170">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="6cc08-171"><STRONG>[一般的なシナリオ</STRONG>] タブ (Location Information Services を除く) の各シナリオで、Load Level の値が<STRONG>Custom</STRONG>の場合は、[<STRONG>詳細設定</STRONG>] ダイアログボックスの対応するフィールドを使用して会話速度が計算されます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-171">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="6cc08-172">シナリオによっては、フィールド名は異なりますが、フィールドの説明は「注: この番号は、ドロップダウンメニューからカスタムが選択されている場合にのみ使用されます。」というようになります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-172">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="6cc08-173">通常、[ <STRONG>高</STRONG>]、[ <STRONG>中</STRONG>]、[ <STRONG>低</STRONG> ] の値は、すべてのシナリオのバランスを取るユーザーモデルを使用して、1つのモダリティごとの会話速度を変更します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-173">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="6cc08-174">予想される使用率の違いによってモダリティごとに負荷レベルを変更する必要がある場合は、 <STRONG>カスタム</STRONG> の会話レートを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6cc08-174">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="6cc08-175">音声シナリオ</span><span class="sxs-lookup"><span data-stu-id="6cc08-175">Voice Scenarios</span></span>

<span data-ttu-id="6cc08-176">次の図に、Lync Server 2013 Load Configuration Tool の [ **音声シナリオ** ] タブを示します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-176">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="6cc08-177">音声関連のすべてのシナリオを構成するには、[ **音声シナリオ** ] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-177">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="6cc08-178">![[音声シナリオ] タブ](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "[音声シナリオ] タブ")</span><span class="sxs-lookup"><span data-stu-id="6cc08-178">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="6cc08-179">**VoIP**で、[**詳細設定**] ボタンをクリックし、 **PhoneAreaCode**と**locationprofile** (ダイヤルプラン) フィールドの値を入力します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-179">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="6cc08-180">**Load Level**の値も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-180">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="6cc08-181">**VoIP**および**UC/PSTN ゲートウェイ**の負荷レベルが有効になっている場合は、外部呼び出しをシミュレートする公衆交換電話網 (PSTN) から統合コミュニケーション (UC) 構成ファイルが常に生成されます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-181">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="6cc08-182">[ **UC/PSTN ゲートウェイ**] で、[ロードレベル] の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-182">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="6cc08-183">[**無効**] 以外の負荷レベルを選択する場合は、[仲介サーバーと pstn] の下にある [**追加**] ボタンをクリックして、 **PSTN 市外局番**の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-183">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="6cc08-184">その市外局番に対してルートが構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-184">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6cc08-185">音声ルートの構成を確認するには、Lync Server コントロールパネルまたは Lync Server 管理シェルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-185">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="6cc08-186">[ **会議アテンダント**] で、[ロードレベル] の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-186">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="6cc08-187">読み込みレベル ( **無効**) を選択すると、[ **電話番号** ] フィールドが有効になります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-187">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="6cc08-188">使用する自動応答の電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-188">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="6cc08-189">また、[ **詳細設定** ] ボタンをクリックし、[ **locationprofile** ] フィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-189">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="6cc08-190">[ **コールパークサービス**] で、[ **Load Level**] に適切な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-190">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="6cc08-191">**仲介サーバーと PSTN**で、使用する仲介サーバーごとに、別の PSTN シミュレータを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-191">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="6cc08-192">シミュレータとして使用するクライアントを決定したら、構成した PSTN シミュレータポートでそのコンピューターへの通話をルーティングするように仲介サーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-192">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="6cc08-193">[ **追加** ] をクリックして、仲介サーバーの値を構成します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-193">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6cc08-194">各シナリオには、その横に <STRONG>[詳細設定</STRONG> ] ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-194">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="6cc08-195">これらのボタンを使用すると、Lync Server 2013 のストレスおよびパフォーマンスツール (LyncPerfTool) の動作を変更したり、カスタマイズを有効にしたりする各シナリオに固有の値にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-195">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="6cc08-196">[ <STRONG>音声シナリオ</STRONG> ] タブの各シナリオで、 <STRONG>Load Level</STRONG> の値が <STRONG>Custom</STRONG>の場合は、[ <STRONG>詳細設定</STRONG> ] ダイアログボックスの対応するフィールドを使用して会話速度が計算されます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-196">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="6cc08-197">シナリオによっては、フィールド名は異なりますが、フィールドの説明は「注: この番号は、ドロップダウンメニューからカスタムが選択されている場合にのみ使用されます。」というようになります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-197">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="6cc08-198">到達</span><span class="sxs-lookup"><span data-stu-id="6cc08-198">Reach</span></span>

<span data-ttu-id="6cc08-199">リーチは、Front-End サーバーにインストールされている統合コミュニケーション Web API (UCWA) サーバーを介して会議シナリオをサポートする、Lync Server 2013 の新しい機能です。</span><span class="sxs-lookup"><span data-stu-id="6cc08-199">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="6cc08-200">次の図は、Lync Server 2013 Load Configuration Tool の [ **リーチ** ] タブを示しています。</span><span class="sxs-lookup"><span data-stu-id="6cc08-200">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="6cc08-201">[ **リーチ** ] タブを使用して、すべてのリーチ関連シナリオを構成します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-201">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="6cc08-202">![[リーチ] タブ](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "[リーチ] タブ")</span><span class="sxs-lookup"><span data-stu-id="6cc08-202">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="6cc08-203">[**全般] 設定**の横にある [**詳細**設定] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cc08-203">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="6cc08-204">フィールド **UcwaTargetServerUrl** をディレクタープール仮想 IP (vip) またはフロントエンドプール VIP に設定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-204">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="6cc08-205">[ **アプリケーション共有**]、[ **共同作業**]、[ **IM**] で、[ **ロードレベル**] に適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-205">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6cc08-206">各シナリオには、その横に <STRONG>[詳細設定</STRONG> ] ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-206">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="6cc08-207">これらのボタンを使用すると、Lync Server 2013 のストレスおよびパフォーマンスツール (LyncPerfTool) の動作を変更したり、カスタマイズを有効にしたりする各シナリオに固有の値にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-207">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="6cc08-208">各リーチシナリオで、 <STRONG>Load Level</STRONG> が <STRONG>Custom</STRONG>の場合は、 <STRONG>ConversationsPerHour</STRONG> フィールドに指定された値が既定値の代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-208">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="6cc08-209">Mobility 関連のすべてのシナリオを構成するには、[ **モビリティ** ] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-209">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="6cc08-210">![[モビリティ] タブ](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "[モビリティ] タブ")</span><span class="sxs-lookup"><span data-stu-id="6cc08-210">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="6cc08-211">**Mobility (UCWA)** の横にある [**詳細設定**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6cc08-211">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="6cc08-212">フィールド **UcwaTargetServerUrl** をディレクタープール仮想 IP (vip) またはフロントエンドプール VIP に設定します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-212">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="6cc08-213">[ **プレゼンス] および [P2P インスタントメッセージング \\ オーディオ**] で、[ **ロードレベル** ] に適切な値を選択してモビリティシナリオシミュレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6cc08-213">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6cc08-214">各シナリオには、その横に <STRONG>[詳細設定</STRONG> ] ボタンがあります。</span><span class="sxs-lookup"><span data-stu-id="6cc08-214">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="6cc08-215">これらのボタンを使用すると、Lync Server 2013 のストレスおよびパフォーマンスツール (LyncPerfTool) の動作を変更したり、カスタマイズを有効にしたりする各シナリオに固有の値にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-215">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="6cc08-216">各リーチシナリオで、 <STRONG>Load Level</STRONG> が <STRONG>Custom</STRONG>の場合は、 <STRONG>ConversationsPerHour</STRONG> フィールドに指定された値が既定値の代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-216">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="6cc08-217">要約</span><span class="sxs-lookup"><span data-stu-id="6cc08-217">Summary</span></span>

<span data-ttu-id="6cc08-218">次の図は、Lync Server 2013 Load Configuration Tool の [ **概要** ] タブを示しています。</span><span class="sxs-lookup"><span data-stu-id="6cc08-218">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="6cc08-219">![[概要] タブ](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "[概要] タブ")</span><span class="sxs-lookup"><span data-stu-id="6cc08-219">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="6cc08-220">[ **概要** ] タブには、各シナリオでどのユーザーを使用するかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-220">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="6cc08-221">[ **カスタムユーザー範囲の生成を有効に** する] チェックボックスをオンにして、カスタマイズする **ユーザー範囲** を含むテーブルのシナリオをダブルクリックして、ユーザー番号範囲を手動で構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-221">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="6cc08-222">[開始時にサインイン遅延を追加する] チェックボックスを RunClient.bat オンにすると、生成されたバッチファイルに遅延を含めることができます。このとき、サインイン率に対応しています。</span><span class="sxs-lookup"><span data-stu-id="6cc08-222">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="6cc08-223">これは、多数のユーザーでの署名時にサーバーの過負荷を回避するのに便利です。</span><span class="sxs-lookup"><span data-stu-id="6cc08-223">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="6cc08-224">[ **ファイルの生成**] をクリックし、構成を生成するフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6cc08-224">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="6cc08-225">ファイルが正常に作成されると、次の図のようなダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6cc08-225">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="6cc08-226">![ファイルが作成されたことを確認する。](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "ファイルが作成されたことを確認する。")</span><span class="sxs-lookup"><span data-stu-id="6cc08-226">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6cc08-227">関連項目</span><span class="sxs-lookup"><span data-stu-id="6cc08-227">See Also</span></span>


[<span data-ttu-id="6cc08-228">ユーザーと連絡先を作成する</span><span class="sxs-lookup"><span data-stu-id="6cc08-228">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
