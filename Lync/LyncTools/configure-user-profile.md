---
title: ユーザー プロファイルの作成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure User Profile
ms:assetid: 52713245-e502-4539-a238-66ff1aca26b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945594(v=OCS.15)
ms:contentKeyID: 51541419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2441fe97bb57ffdf0f6200f1201e192bfc6bf14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-profile"></a><span data-ttu-id="6e71e-102">ユーザー プロファイルの作成</span><span class="sxs-lookup"><span data-stu-id="6e71e-102">Configure User Profile</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e71e-103">_**最終更新日:** 2018-10-11_</span><span class="sxs-lookup"><span data-stu-id="6e71e-103">_**Topic Last Modified:** 2018-10-11_</span></span>

<span data-ttu-id="6e71e-104">Lync Server 2013 ストレス/パフォーマンスツールパッケージに含まれているツールを使用すると、ロードシミュレーションの実行に使用できるテストユーザーアカウントを作成して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-104">The tools included in the Lync Server 2013 Stress and Performance Tool package enable you to create and configure test user accounts that you can use to run load simulations.</span></span> <span data-ttu-id="6e71e-105">Lync Server 2013 ユーザー作成ツールを使用してユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-105">Use the Lync Server 2013 User Creation Tool to create the users.</span></span> <span data-ttu-id="6e71e-106">(詳細については、「[ユーザーと連絡先を作成する](create-users-and-contacts.md)」を参照してください)。ユーザーが作成されたら、Lync Server 2013 のロード構成ツールを使用して、ユーザープロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-106">(For details, see [Create Users and Contacts](create-users-and-contacts.md).) After users are created, configure the user profiles by using the Lync Server 2013 Load Configuration Tool.</span></span>

<div>

## <a name="running-the-lync-server-2013-load-configuration-tool"></a><span data-ttu-id="6e71e-107">Lync Server 2013 のロード構成ツールの実行</span><span class="sxs-lookup"><span data-stu-id="6e71e-107">Running the Lync Server 2013 Load Configuration Tool</span></span>

<span data-ttu-id="6e71e-108">ユーザープロファイルを構成するには、Lync Server 2013 ロード構成ツール (UserProfileGenerator) を実行し、各タブに入力します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-108">To configure user profiles, run the Lync Server 2013 Load Configuration Tool (UserProfileGenerator.exe) and fill out each of the tabs.</span></span> <span data-ttu-id="6e71e-109">UserProfileGenerator は、シミュレーションの実行に必要なクライアントコンピューターごとにディレクトリを生成します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-109">UserProfileGenerator.exe generates a directory for each of the client computers that you need to run the simulation.</span></span> <span data-ttu-id="6e71e-110">各クライアントディレクトリには、Lync Server 2013 ストレス/パフォーマンスツール (LyncPerfTool) のすべてのインスタンスを開始するためのスクリプトも用意されています。</span><span class="sxs-lookup"><span data-stu-id="6e71e-110">Each client directory also comes with a script to start all the instances of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6e71e-111">UserProfileGenerator で指定されたユーザー固有の値は、そのプールの Lync Server 2013 ユーザー作成ツール (User Tool) で指定された値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e71e-111">The user-specific values specified in UserProfileGenerator must match the values specified in the Lync Server 2013 User Creation Tool (UserProvisioningTool) for the pool.</span></span>



</div>

<span data-ttu-id="6e71e-112">次のセクションで説明するように、Lync Server 2013 のロード構成ツールの各タブにあるフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-112">Fill in the fields on each tab of the Lync Server 2013 Load Configuration Tool, as described in the following sections.</span></span>

<div>

## <a name="common-configuration"></a><span data-ttu-id="6e71e-113">一般的な構成</span><span class="sxs-lookup"><span data-stu-id="6e71e-113">Common Configuration</span></span>

<span data-ttu-id="6e71e-114">次の図に、Lync Server 2013 のロード構成ツールの [**共通の構成**] タブを示します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-114">The **Common Configuration** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span> <span data-ttu-id="6e71e-115">次の手順で説明するように、[**共通の構成**] タブのフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-115">Fill in the fields of the **Common Configuration** tab, as described in the following steps.</span></span>

<span data-ttu-id="6e71e-116">![[Common Configuration] タブ。](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "[一般的な構成] タブ")</span><span class="sxs-lookup"><span data-stu-id="6e71e-116">![Common Configuration tab.](images/JJ945594.c68dcc8f-10f2-499e-95a2-fccbcc206c2f(OCS.15).jpg "Common Configuration tab.")</span></span>

1.  <span data-ttu-id="6e71e-117">[**使用可能なコンピューター数**] で、LyncPerfTool を実行するために使用するコンピューターの数を入力するか、クリックします。</span><span class="sxs-lookup"><span data-stu-id="6e71e-117">In **Number of Available Machines**, type or click the number of computers that you want to use to run LyncPerfTool.exe.</span></span> <span data-ttu-id="6e71e-118">シミュレートするすべての4500ユーザーに1台のコンピューターを用意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e71e-118">We recommend that you have one computer for every 4,500 users that you will be simulating.</span></span> <span data-ttu-id="6e71e-119">この数値は、読み込みレベルを下げるか、使用可能な機能の一部のみを使う場合に異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e71e-119">That number may vary if you reduce the load level or if you use only a subset of the available features.</span></span> <span data-ttu-id="6e71e-120">(読み込みレベルは **[一般的なシナリオ**] タブで設定します)。</span><span class="sxs-lookup"><span data-stu-id="6e71e-120">(Load levels are set on the **General Scenarios** tab.)</span></span>

2.  <span data-ttu-id="6e71e-121">[**ユーザー名のプレフィックス**] に、ユーザーのユーザー名のプレフィックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-121">In **Prefix for User Names**, type the prefix for the user name of the users.</span></span> <span data-ttu-id="6e71e-122">ログインするには、Uniform Resource Identifier (URI) は次のように\[なります: userprefix ユーザー開始インデックス...(ユーザー数-1)\]@User ドメイン。</span><span class="sxs-lookup"><span data-stu-id="6e71e-122">To log in, the Uniform Resource Identifier (URI) will be: UserPrefix\[User Start Index…(Number Of Users-1)\]@User Domain.</span></span>

3.  <span data-ttu-id="6e71e-123">[**すべてのユーザーのパスワード**] に、ユーザーの作成に使用したパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-123">In **Password for All Users**, enter the password that was used for creating the users.</span></span> <span data-ttu-id="6e71e-124">このフィールドを空白のままにすると、ユーザー名がパスワードとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-124">If you leave this field empty, the username will be used as the password.</span></span>

4.  <span data-ttu-id="6e71e-125">[**ユーザーの開始インデックス**] で、構成する最初のユーザーのインデックスをクリックまたは入力します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-125">In **User Start Index**, click or type the index of the first user to be configured.</span></span> <span data-ttu-id="6e71e-126">さまざまな種類またはロードのレベルごとに異なる範囲を構成できますが、構成する範囲に応じて UserProfileGenerator を1回実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e71e-126">You can configure different ranges for different types or levels of load, but you must run UserProfileGenerator.exe once per the range that you want to configure.</span></span>

5.  <span data-ttu-id="6e71e-127">[**ユーザー**数] で、構成するユーザーの合計数をクリックまたは入力します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-127">In **Number of Users**, click or type the total number of users you are going to configure.</span></span>

6.  <span data-ttu-id="6e71e-128">[**ユーザードメイン**] に、SIP URI として使用するドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-128">In **User Domain**, type the domain used for the SIP URI.</span></span> <span data-ttu-id="6e71e-129">これは、Lync Server 2013 フロントエンドサーバーまたは Standard Edition サーバーにログオンする各ユーザーの SIP URI を作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-129">This is used to construct the SIP URI of each user to log on to the Lync Server 2013 Front End Server or Standard Edition server.</span></span> <span data-ttu-id="6e71e-130">アカウントドメインとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e71e-130">It can be different from the account domain.</span></span>

7.  <span data-ttu-id="6e71e-131">[ **Account domain**] に、Active Directory ドメインサービスのドメインログオンを入力します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-131">In **Account Domain**, type the Active Directory Domain Services domain logon.</span></span>

8.  <span data-ttu-id="6e71e-132">すべてのエンドポイント/ユーザーに対して、ツールでログインする同時エンドポイント **(インスタンスごと)** の最大数を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-132">Enter the maximum number of concurrent endpoints in **Sign In Per Second (per instance)** for which you want the tool to log in all the endpoints/users.</span></span> <span data-ttu-id="6e71e-133">推奨される利率\<は = 2/秒/標準 SKU FE です。</span><span class="sxs-lookup"><span data-stu-id="6e71e-133">The recommended rate is \<=2 per second/standard SKU FE.</span></span>

9.  <span data-ttu-id="6e71e-134">[**アクセスプロキシ] または [プールの FQDN**] で、クライアントが接続するサーバーの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-134">In **Access Proxy or Pool FQDN**, type the fully qualified domain name (FQDN) of the server that you want the clients to connect to.</span></span> <span data-ttu-id="6e71e-135">ユーザーが外部でログオンしている場合は、アクセスプロキシを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-135">If the users are logging on externally, specify the access proxy.</span></span> <span data-ttu-id="6e71e-136">ユーザーが内部の場合は、プールまたは Standard Edition サーバーの FQDN を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-136">If the users are internal, specify the FQDN of their pool or Standard Edition server.</span></span>

10. <span data-ttu-id="6e71e-137">[ **Port**] で、ユーザーが SIP に使用するポートをクリックまたは入力します (既定では 5061)。</span><span class="sxs-lookup"><span data-stu-id="6e71e-137">In **Port**, click or type the port that you want users to use for SIP (the default is 5061).</span></span>

<span data-ttu-id="6e71e-138">[外部ネットワークサーバー設定] で、**アクセスプロキシまたはプールの FQDN**と**ポート**を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-138">For External Network Server Settings, specify the **Access Proxy or Pool FQDN** and the **Port**.</span></span> <span data-ttu-id="6e71e-139">これらの設定は、外部エンドポイントのロード シミュレーションにのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-139">These settings are used only for External endpoints load simulation.</span></span>

</div>

<div>

## <a name="general-scenarios"></a><span data-ttu-id="6e71e-140">一般的なシナリオ</span><span class="sxs-lookup"><span data-stu-id="6e71e-140">General Scenarios</span></span>

<span data-ttu-id="6e71e-141">次の図は、Lync Server 2013 のロード構成ツールの **[一般的なシナリオ**] タブを示しています。</span><span class="sxs-lookup"><span data-stu-id="6e71e-141">The **General Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="6e71e-142">実行する一般的なシナリオごとにロードレベルとパラメーターを構成するか、無効のままにします。</span><span class="sxs-lookup"><span data-stu-id="6e71e-142">Configure the load levels and parameters for each of the general scenarios that you want to run, or leave disabled.</span></span>

<span data-ttu-id="6e71e-143">![一般的なシナリオタブ。](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "[一般的なシナリオ] タブ")</span><span class="sxs-lookup"><span data-stu-id="6e71e-143">![General Scenarios tab.](images/JJ945594.4f046d39-b532-4baf-99a6-c89d1d6d1fcc(OCS.15).jpg "General Scenarios tab.")</span></span>

1.  <span data-ttu-id="6e71e-144">**インスタントメッセージング**で、ピアツーピアと電話会議が含まれている場合は、読み込みレベルに適切な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-144">In **Instant Messaging**, which includes peer-to-peer and conferencing, specify the appropriate value for the Load Level.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e71e-145">すべてのフィールド (位置情報サービスを除く) の読み込みレベルの値は、[無効]、[<STRONG>低</STRONG>]、[<STRONG>中</STRONG>]、[<STRONG>高</STRONG>]、[<STRONG>カスタム</STRONG>] のいずれかに<STRONG>なり</STRONG>ます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-145">Load level values for all fields (except Location Information Services) are <STRONG>Disabled</STRONG>, <STRONG>Low</STRONG>, <STRONG>Medium</STRONG>, <STRONG>High</STRONG>, and <STRONG>Custom</STRONG>.</span></span> <span data-ttu-id="6e71e-146">Low、Medium、High、または Custom が選択されている場合、構成は各モダリティとクライアントに対して生成されます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-146">When Low, Medium, High, or Custom is selected, configurations will be generated for each modality and client.</span></span> <span data-ttu-id="6e71e-147">High は、サーバーに対してサポートされる最大のロードを生成します。 Medium は負荷の60% に相当し、Low はロードの30% に相当します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-147">High will result in the maximum supported load to be generated for the server, Medium corresponds to 60 percent of the load, and Low corresponds to 30 percent of the load.</span></span>

    
    </div>

2.  <span data-ttu-id="6e71e-148">電話**会議 (電話**会議のみ) で、[読み込みレベル] に適切な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-148">In **Audio Conferencing**, which is audio conferencing only, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="6e71e-149">ピアツーピア通話については、このトピックで後述する「ボイスシナリオ」セクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-149">Peer-to-peer calls are covered in the Voice Scenarios section later in this topic.</span></span> <span data-ttu-id="6e71e-150">MultiView を有効にするには、そのモダリティの **[詳細設定**] タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-150">To enable MultiView, open the **Advanced** tab for that modality.</span></span>

3.  <span data-ttu-id="6e71e-151">[**アプリケーション共有**] で、[Load Level] に適切な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-151">In **Application Sharing**, specify the appropriate value for Load Level.</span></span>

4.  <span data-ttu-id="6e71e-152">データ会議を含む**データコラボレーション**では、読み込みレベルに適した値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-152">In **Data Collaboration**, which includes data conferencing, specify the appropriate value for Load Level.</span></span>

5.  <span data-ttu-id="6e71e-153">**配布リストの展開**で、[読み込みレベル] に適切な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-153">In **Distribution List Expansion**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="6e71e-154">また、[**詳細設定**] ボタンをクリックして、Lync Server ユーザー作成ツール (userプロビジョニングツール .exe) の [**配布リスト**] タブで設定したものと同じ値をフィールドに入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e71e-154">You must also click the **Advanced** button, and then fill in the fields with the same values that you configured on the **Distribution List** tab of the Lync Server User Creation Tool (UserProvisioningTool.exe).</span></span> <span data-ttu-id="6e71e-155">これらのフィールドの詳細については、「[ユーザーと連絡先を作成する](create-users-and-contacts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e71e-155">For details about these fields, see [Create Users and Contacts](create-users-and-contacts.md)</span></span>

6.  <span data-ttu-id="6e71e-156">アドレス帳の**Web クエリ**(アドレス帳ファイルのダウンロードではなく) である場合は、読み込みレベルに適した値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-156">In **Address Book Web Query**, which is the address book lookup service (not the address book file download), specify the appropriate value for Load Level.</span></span> <span data-ttu-id="6e71e-157">アドレス帳のダウンロードを有効にするには、対応する **[詳細**設定] ボタンをクリックして、 **EnableABSDownload**を true に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-157">To enable address book downloads, click the corresponding **Advanced** button, and then set **EnableABSDownload** to true.</span></span>

7.  <span data-ttu-id="6e71e-158">[**応答グループサービス**] で、読み込みレベルに適切な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-158">In **Response Group Service**, specify the appropriate value for Load Level.</span></span> <span data-ttu-id="6e71e-159">また、対応する **[詳細設定**] ボタンをクリックし、応答グループサービスエージェントのプロビジョニング時に既に作成した応答グループの uri を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e71e-159">You must also click the corresponding **Advanced** button, and then specify the URIs of the response groups you have already created when provisioning Response Group Service agents.</span></span> <span data-ttu-id="6e71e-160">少なくとも1つの応答グループを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e71e-160">You must specify at least one response group.</span></span> <span data-ttu-id="6e71e-161">複数の返信グループを区切るには、セミコロンを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-161">Use semicolons to separate multiple response groups.</span></span> <span data-ttu-id="6e71e-162">実際の値になるように、[RGSUriSuffixStartIndex] と [RGSUriSuffixEndIndex] を更新します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-162">Update RGSUriSuffixStartIndex and RGSUriSuffixEndIndex to the actual values.</span></span>

8.  <span data-ttu-id="6e71e-163">[**位置情報サービス**] で、[読み込みレベル] に適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-163">In **Location Information Services**, select the appropriate value for Load Level.</span></span> <span data-ttu-id="6e71e-164">位置情報サービスの読み込みレベルは、**有効**または**無効**にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e71e-164">The load level for Location Information Services must be **Enabled** or **Disabled**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e71e-165">各シナリオには、その横に<STRONG>[詳細設定</STRONG>] ボタンと、シナリオのバリエーションを可能にする一連のチェックボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="6e71e-165">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it, and a set of check boxes that enable variations of the scenarios.</span></span> <span data-ttu-id="6e71e-166"><STRONG>臨時の場合は</STRONG>、1時間を通じて作成される電話会議のシミュレーションを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-166"><STRONG>Ad-hoc</STRONG> means to generate simulation of conferences that will be created throughout the hour.</span></span> <span data-ttu-id="6e71e-167"><STRONG>大</STRONG>人数は、大規模な会議のシナリオがシミュレートされることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-167"><STRONG>Large Conf</STRONG> means that Large Conference Scenario will be simulated.</span></span> <span data-ttu-id="6e71e-168"><STRONG>外部</STRONG>ユーザーもシミュレートすることができます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-168"><STRONG>External</STRONG> means to also simulate external users.</span></span><BR><span data-ttu-id="6e71e-169">これらのボタンとチェックボックスを使用すると、Lync Server 2013 のストレスとパフォーマンスツール (LyncPerfTool) の動作を変更したり、カスタマイズしたりできるように、各シナリオに固有の値にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-169">These buttons and check boxes allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and make customization possible.</span></span> <span data-ttu-id="6e71e-170">[<STRONG>一般的なシナリオ</STRONG>] タブ (Location Information Services を除く) の各シナリオで、[読み込みレベル] の値が<STRONG>Custom</STRONG>の場合は、[<STRONG>詳細設定</STRONG>] ダイアログボックスの対応するフィールドを使って、会話の料金が計算されます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-170">For each scenario on the <STRONG>General Scenarios</STRONG> tab (except for Location Information Services), if the value of Load Level is <STRONG>Custom</STRONG>, then the conversation rate will be calculated using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="6e71e-171">フィールド名はシナリオによって異なりますが、フィールドの説明は "注: この番号は、ドロップダウンメニューから [カスタム] を選択した場合にのみ使用されます。"</span><span class="sxs-lookup"><span data-stu-id="6e71e-171">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span> <span data-ttu-id="6e71e-172">通常、[<STRONG>高</STRONG>]、[<STRONG>中</STRONG>]、[<STRONG>低</STRONG>] の値は、すべてのシナリオのバランスを考慮したユーザーモデルでの、モダリティあたりの会話料金を変更します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-172">In general, the values <STRONG>High</STRONG>, <STRONG>Medium</STRONG>, and <STRONG>Low</STRONG> will alter the conversation rates per modality in line with the User Model that is a balance of all the scenarios.</span></span> <span data-ttu-id="6e71e-173">期待される使用状況の違いにより、モダリティあたりのロードレベルを変更する必要がある場合は、<STRONG>カスタム</STRONG>会話レートを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e71e-173">If there is a need to change the load level per modality due to a difference in expected usage, we recommend using a <STRONG>Custom</STRONG> conversation rate.</span></span><BR>



</div>

</div>

<div>

## <a name="voice-scenarios"></a><span data-ttu-id="6e71e-174">音声シナリオ</span><span class="sxs-lookup"><span data-stu-id="6e71e-174">Voice Scenarios</span></span>

<span data-ttu-id="6e71e-175">次の図は、Lync Server 2013 のロード構成ツールの [**音声シナリオ**] タブを示しています。</span><span class="sxs-lookup"><span data-stu-id="6e71e-175">The **Voice Scenarios** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="6e71e-176">ボイス関連のすべてのシナリオを構成するには、[**ボイスシナリオ**] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-176">Use the **Voice Scenarios** tab to configure all of the voice-related scenarios.</span></span>

<span data-ttu-id="6e71e-177">![[音声シナリオ] タブ。](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "[音声シナリオ] タブ")</span><span class="sxs-lookup"><span data-stu-id="6e71e-177">![Voice Scenarios tab.](images/JJ945594.28edf664-da59-40b0-9a0e-196f01e9ca86(OCS.15).jpg "Voice Scenarios tab.")</span></span>

1.  <span data-ttu-id="6e71e-178">**VoIP**では、[**詳細設定**] ボタンをクリックし、[ **PhoneAreaCode** ] と [ **locationprofile** (dial plan)] の各フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-178">In **VoIP**, click the **Advanced** button, and then provide values for the **PhoneAreaCode** and **LocationProfile** (dial plan) fields.</span></span> <span data-ttu-id="6e71e-179">また、 **Load Level**の値も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e71e-179">You must also specify a value for **Load Level**.</span></span> <span data-ttu-id="6e71e-180">**VoIP**および**UC/PSTN ゲートウェイ**の読み込みレベルが有効になっている場合、公衆交換電話網 (PSTN) から統合通信 (UC) 構成ファイルが常に生成され、外部通話がシミュレートされます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-180">If Load Level for **VoIP** and **UC/PSTN Gateway** is Enabled, then a public switched telephone network (PSTN) to unified communications (UC) configuration file will always be generated that will simulate external calls.</span></span>

2.  <span data-ttu-id="6e71e-181">**UC/PSTN ゲートウェイ**で、Load Level の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-181">In **UC/PSTN Gateway**, specify a value for Load Level.</span></span> <span data-ttu-id="6e71e-182">[**無効**] 以外の読み込みレベルを選択した場合、[仲介サーバーと pstn] の下にある [**追加**] ボタンをクリックして、 **PSTN 市外**局番の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e71e-182">If you select a load level other than **Disabled**, you must supply a value for **PSTN Area Code** by clicking the **Add** button under Mediation Server and PSTN.</span></span> <span data-ttu-id="6e71e-183">その市外局番用に構成されているルートがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-183">Verify that you have a route configured for that area code.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6e71e-184">[Lync Server] コントロールパネルまたは Lync Server 管理シェルを使って、ボイスルートの構成を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-184">You can use either the Lync Server Control Panel or the Lync Server Management Shell to verify voice route configuration.</span></span>

    
    </div>

3.  <span data-ttu-id="6e71e-185">**会議アテンダント**で、[読み込みレベル] の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-185">In **Conferencing Attendant**, specify a value for Load Level.</span></span> <span data-ttu-id="6e71e-186">読み込みレベル (**無効**) を選択すると、[**電話番号**] フィールドが有効になります。</span><span class="sxs-lookup"><span data-stu-id="6e71e-186">Selecting a load level (other than **Disabled**) will enable the **Telephone Number** field.</span></span> <span data-ttu-id="6e71e-187">使用する自動応答の電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-187">Enter the telephone number of the Auto Attendant that you want to use.</span></span> <span data-ttu-id="6e71e-188">また、[**詳細設定**] ボタンをクリックし、[ **locationprofile** ] フィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-188">Also, click the **Advanced** button, and then specify a value for the **LocationProfile** field.</span></span>

4.  <span data-ttu-id="6e71e-189">[ **Call パーク] サービス**で、[ **Load Level**] に適切な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-189">In **Call Park Service**, specify the appropriate value for **Load Level**.</span></span>

5.  <span data-ttu-id="6e71e-190">**仲介サーバーと PSTN**で、使用する各仲介サーバーについて、別個の PSTN シミュレータを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e71e-190">In **Mediation Server and PSTN**, for each Mediation Server that you want to use, you must have a separate PSTN simulator.</span></span> <span data-ttu-id="6e71e-191">シミュレータとして使用するクライアントを決定したら、構成した PSTN シミュレータポートでそのコンピューターへの通話をルーティングするために、仲介サーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e71e-191">After you have determined which client you are going to use as the simulator, you need to configure your Mediation Server to route calls to that computer on the PSTN Simulator port that you configured.</span></span> <span data-ttu-id="6e71e-192">[**追加**] をクリックして、仲介サーバーの値を構成します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-192">Click **Add** to configure the value for the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e71e-193">それぞれのシナリオの横には <STRONG>[Advanced]</STRONG> ボタンが配置されています。</span><span class="sxs-lookup"><span data-stu-id="6e71e-193">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="6e71e-194">これらのボタンを使うと、Lync Server 2013 のストレスとパフォーマンスツール (LyncPerfTool) の動作を変更し、カスタマイズを有効にする各シナリオに固有の値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-194">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="6e71e-195">[<STRONG>音声シナリオ</STRONG>] タブの各シナリオで、[<STRONG>読み込みレベル</STRONG>] の値が<STRONG>Custom</STRONG>の場合は、[<STRONG>詳細設定</STRONG>] ダイアログボックスの対応するフィールドを使って、会話の料金を計算します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-195">For each scenario on the <STRONG>Voice Scenarios</STRONG> tab, if the value of <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the conversation rate will be calculated by using the corresponding field in the <STRONG>Advanced</STRONG> dialog box.</span></span> <span data-ttu-id="6e71e-196">フィールド名はシナリオによって異なりますが、フィールドの説明は "注: この番号は、ドロップダウンメニューから [カスタム] を選択した場合にのみ使用されます。"</span><span class="sxs-lookup"><span data-stu-id="6e71e-196">The field name differs, depending on the scenario, but the field description will state, "NOTE: This number will only be used if Custom is selected from the drop-down menu."</span></span>



</div>

</div>

<div>

## <a name="reach"></a><span data-ttu-id="6e71e-197">実現</span><span class="sxs-lookup"><span data-stu-id="6e71e-197">Reach</span></span>

<span data-ttu-id="6e71e-198">リーチは、Lync Server 2013 の新しいエクスペリエンスであり、フロントエンドサーバーにインストールされているユニファイドコミュニケーション Web API (UCWA) サーバーを介して会議シナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="6e71e-198">Reach is a new experience in Lync Server 2013 that supports conferencing scenarios through the Unified Communications Web API (UCWA) server that is installed on the Front-End server.</span></span> <span data-ttu-id="6e71e-199">Lync Server 2013 のロード構成ツールの [**リーチ**] タブは、次の図のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-199">The **Reach** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="6e71e-200">[**リーチ**] タブを使用して、すべてのリーチ関連シナリオを構成します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-200">Use the **Reach** tab to configure all the reach-related scenarios.</span></span>

<span data-ttu-id="6e71e-201">![[到達] タブ](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "[到達] タブ")</span><span class="sxs-lookup"><span data-stu-id="6e71e-201">![Reach tab.](images/JJ945594.65ccf6de-0e8d-47ba-93f3-9dcb39d3fd62(OCS.15).jpg "Reach tab.")</span></span>

1.  <span data-ttu-id="6e71e-202">[**全般] 設定**の横にある [**詳細**設定] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e71e-202">Click the **Advanced** button next to **General Reach Settings**.</span></span> <span data-ttu-id="6e71e-203">フィールド**UcwaTargetServerUrl**をディレクタープールの仮想 IP (vip) またはフロントエンドプール VIP に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-203">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="6e71e-204">[**アプリケーション共有**]、[**データ共同作業**]、[ **IM**] で、[ **Load Level**] に適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-204">In **Application Sharing**, **Data Collaboration**, and **IM**, select the appropriate value for **Load Level**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e71e-205">それぞれのシナリオの横には <STRONG>[Advanced]</STRONG> ボタンが配置されています。</span><span class="sxs-lookup"><span data-stu-id="6e71e-205">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="6e71e-206">これらのボタンを使うと、Lync Server 2013 のストレスとパフォーマンスツール (LyncPerfTool) の動作を変更し、カスタマイズを有効にする各シナリオに固有の値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-206">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="6e71e-207">各リーチシナリオで、 <STRONG>Load Level</STRONG>が<STRONG>Custom</STRONG>の場合は、既定値の代わりに、 <STRONG>ConversationsPerHour</STRONG>フィールドに指定された値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-207">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default</span></span>



</div>

<span data-ttu-id="6e71e-208">[**モバイル**] タブを使用して、すべてのモビリティ関連のシナリオを構成します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-208">Use the **Mobility** tab to configure all of the mobility-related scenarios.</span></span>

<span data-ttu-id="6e71e-209">![[モバイル] タブ。](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "[モビリティ] タブ")</span><span class="sxs-lookup"><span data-stu-id="6e71e-209">![Mobility tab.](images/JJ945594.4dd8f3e0-921c-48a5-8b23-2a0330d3c334(OCS.15).jpg "Mobility tab.")</span></span>

1.  <span data-ttu-id="6e71e-210">「**モビリティー (UCWA)**」の横にある **「詳細**」ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e71e-210">Click the **Advanced** button next to **Mobility (UCWA)**.</span></span> <span data-ttu-id="6e71e-211">フィールド**UcwaTargetServerUrl**をディレクタープールの仮想 IP (vip) またはフロントエンドプール VIP に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-211">Set the field **UcwaTargetServerUrl** to the Director pool virtual IP (VIP) or the Front End pool VIP.</span></span>

2.  <span data-ttu-id="6e71e-212">**プレゼンスと P2P インスタントメッセージング\\オーディオ**で、「**読み込みレベル**」に適切な値を選択して、モビリティーシナリオシミュレーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6e71e-212">In **Presence and P2P Instant Messaging\\Audio**, select the appropriate value for **Load Level** to enable Mobility Scenario simulation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6e71e-213">それぞれのシナリオの横には <STRONG>[Advanced]</STRONG> ボタンが配置されています。</span><span class="sxs-lookup"><span data-stu-id="6e71e-213">Each of the scenarios has an <STRONG>Advanced</STRONG> button located next to it.</span></span> <span data-ttu-id="6e71e-214">これらのボタンを使うと、Lync Server 2013 のストレスとパフォーマンスツール (LyncPerfTool) の動作を変更し、カスタマイズを有効にする各シナリオに固有の値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-214">These buttons allow access to values specific to each scenario that will change the behavior of the Lync Server 2013 Stress and Performance Tool (LyncPerfTool) and enable customization.</span></span> <span data-ttu-id="6e71e-215">各リーチシナリオで、 <STRONG>Load Level</STRONG>が<STRONG>Custom</STRONG>の場合は、既定ではなく、 <STRONG>ConversationsPerHour</STRONG>フィールドに指定された値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-215">For each of the Reach scenarios, if the <STRONG>Load Level</STRONG> is <STRONG>Custom</STRONG>, then the value specified in the <STRONG>ConversationsPerHour</STRONG> field is used instead of the default.</span></span>



</div>

</div>

<div>

## <a name="summary"></a><span data-ttu-id="6e71e-216">概要</span><span class="sxs-lookup"><span data-stu-id="6e71e-216">Summary</span></span>

<span data-ttu-id="6e71e-217">次の図は、Lync Server 2013 のロード構成ツールの [**概要**] タブを示しています。</span><span class="sxs-lookup"><span data-stu-id="6e71e-217">The **Summary** tab of the Lync Server 2013 Load Configuration Tool is shown in the following figure.</span></span>

<span data-ttu-id="6e71e-218">![[概要] タブ。](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "[概要] タブ")</span><span class="sxs-lookup"><span data-stu-id="6e71e-218">![Summary tab.](images/JJ945594.c675e869-8ded-4195-8c2a-68d844fc96ad(OCS.15).jpg "Summary tab.")</span></span>

<span data-ttu-id="6e71e-219">[**概要**] タブには、各シナリオで使用するユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-219">The **Summary** tab indicates which users to use for each of the scenarios.</span></span> <span data-ttu-id="6e71e-220">[**カスタムユーザー範囲の生成を有効に**する] チェックボックスをオンにして、ユーザー**設定の範囲**を含むテーブルのシナリオをダブルクリックして、ユーザー番号の範囲を手動で構成することができます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-220">It is possible to manually configure user number ranges by selecting the **Enable Custom User Range Generation** check box, and then double-clicking the scenario in the table that has the **User Range** that you want to customize.</span></span> <span data-ttu-id="6e71e-221">チェック (RunClient) を開始するときにサインインの遅延を追加し、生成されたバッチファイルで、サインイン速度に対応する遅延を含めるようにします。</span><span class="sxs-lookup"><span data-stu-id="6e71e-221">Check (RunClient.bat) Add sign-in delay when starting, in order to include delays in the generated batch files to correspond with the sign-in rate.</span></span> <span data-ttu-id="6e71e-222">これは、多数のユーザーがサインにするときにサーバーの過負荷を防止する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-222">This is useful to prevent server overload when signing in a large number of users.</span></span> <span data-ttu-id="6e71e-223">[**ファイルの生成**] をクリックし、構成を生成するフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6e71e-223">Click **Generate Files**, and select the folder where you want to generate the configuration.</span></span> <span data-ttu-id="6e71e-224">ファイルが正常に作成されると、次の図のようなダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e71e-224">A dialog box similar to the following figure will appear when your files have been successfully created.</span></span>

<span data-ttu-id="6e71e-225">![ファイルが作成されたという確認](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "ファイルが作成されたという確認")</span><span class="sxs-lookup"><span data-stu-id="6e71e-225">![Acknowledgement that files have been created.](images/JJ945594.00dc1e92-bfba-48e7-9568-b97ad864491e(OCS.15).jpg "Acknowledgement that files have been created.")</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6e71e-226">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e71e-226">See Also</span></span>


[<span data-ttu-id="6e71e-227">ユーザーと連絡先の作成</span><span class="sxs-lookup"><span data-stu-id="6e71e-227">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
</div>
</div>
<span></span>
</div>
</div>
</div>
