---
title: 'Lync Server 2013: エンド ユーザーとしての Lync と Skype の接続の使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5404a42b0d8e2052541ccb9f9178bf33408c2099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a><span data-ttu-id="cb323-102">エンド ユーザーとしての Lync Server 2013 での Lync と Skype の接続の使用</span><span class="sxs-lookup"><span data-stu-id="cb323-102">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb323-103">_**最終更新日:** 2016-12-27_</span><span class="sxs-lookup"><span data-stu-id="cb323-103">_**Topic Last Modified:** 2016-12-27_</span></span>

<span data-ttu-id="cb323-104">Lync-skype 接続を使うと、Skype ユーザと Lync ユーザがお互いをコンタクトとして追加したり、インスタントメッセージを交換したり、音声通話やビデオ通話を発信したりできます。</span><span class="sxs-lookup"><span data-stu-id="cb323-104">Lync-Skype Connectivity enables Skype users and Lync users to add each other as contacts, exchange instant messages and make audio and video calls.</span></span> <span data-ttu-id="cb323-105">Skype ユーザーが Lync ユーザーを追加すると、skype ユーザーは、Lync ユーザーのセッション開始プロトコル (SIP) uniform resource identifier (URI) を含む連絡先を Skype で作成します。</span><span class="sxs-lookup"><span data-stu-id="cb323-105">When a Skype user adds a Lync user, a Skype user will create a contact in Skype containing the session initiation protocol (SIP) uniform resource identifier (URI) of the Lync user.</span></span> <span data-ttu-id="cb323-106">一方、Lync ユーザーが Skype 連絡先を追加すると、lync ユーザーは、skype ユーザー名ではなく、Skype ユーザーの Microsoft アカウント (MSA) を含む Lync の連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="cb323-106">Conversely, when a Lync user adds a Skype contact, the Lync user will create a contact in Lync that will contain the Microsoft Account (MSA) of the Skype user, and not the Skype user name.</span></span>

<span data-ttu-id="cb323-107">**MSA とは何ですか?**</span><span class="sxs-lookup"><span data-stu-id="cb323-107">**What is an MSA?**</span></span> <span data-ttu-id="cb323-108">Lync の連絡先と通信するためには、skype ユーザーが Microsoft アカウント (旧称 Windows Live ID) を使って Skype にサインインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb323-108">Skype users must sign in to Skype with a Microsoft account (previously called Windows Live ID) in order to communicate with Lync contacts.</span></span><span data-ttu-id="cb323-109">Microsoft アカウントは、メールアドレスとパスワードの組み合わせで構成されます。また、Microsoft OneDrive ストレージテクノロジ、Windows Phone、Microsoft Xbox LIVE online ゲームサービス、Microsoft Outlook メッセージングなどのサービスへのサインインにも使用できます。共同作業クライアント (および以前は Microsoft Hotmail web ベースのメールサービスまたは Windows Live Messenger)。</span><span class="sxs-lookup"><span data-stu-id="cb323-109"> A Microsoft account consists of the combination of an email address and a password, which you can also use to sign in to services such as Microsoft OneDrive storage technology, Windows Phone, Microsoft Xbox LIVE online game service, and Microsoft Outlook messaging and collaboration client (and, previously, Microsoft Hotmail web-based e-mail service or Windows Live Messenger).</span></span><span data-ttu-id="cb323-110">メールアドレスとパスワードを使って、これらのサービスまたは他のサービスにサインインする場合は、既に Microsoft アカウントを持っています。</span><span class="sxs-lookup"><span data-stu-id="cb323-110"> If you use an email address and a password to sign in to these or other services, you already have a Microsoft account.</span></span><span data-ttu-id="cb323-111">Microsoft アカウントの作成の詳細については、Microsoft アカウントのサインアップページを[https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb323-111"> For details about creating a Microsoft Account, see the Microsoft account sign-up page at [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061).</span></span> <span data-ttu-id="cb323-112">既存の Skype アカウントを、さまざまなアプリケーションやサービスで、シングルサインオン用の Microsoft アカウントに統合することができます。</span><span class="sxs-lookup"><span data-stu-id="cb323-112">You can merge your existing Skype account with your Microsoft account for single sign-on, across a variety of applications and services.</span></span> <span data-ttu-id="cb323-113">アカウントを統合すると、Skype ユーザーは連絡先要求を Lync ユーザーに送信できます。</span><span class="sxs-lookup"><span data-stu-id="cb323-113">Once the account is merged a Skype user can send a contact request to Lync users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cb323-114">Lync と Skype ユーザーが相互に完全に通信するためには、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb323-114">In order for Lync and Skype users to fully communicate with each other, the following requirements must be met:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="cb323-115">Skype ユーザは、Microsoft アカウント (MSA) を使って Skype クライアントにログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb323-115">Skype users must be logged into their Skype client with a Microsoft Account (MSA).</span></span></P>
> <LI>
> <P><span data-ttu-id="cb323-116">Lync ユーザーは、Lync 管理者によるパブリック IM 接続を有効にしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb323-116">Lync users must be enabled for public IM connectivity by their Lync administrator.</span></span></P>
> <LI>
> <P><span data-ttu-id="cb323-117">Skype ユーザーが Lync の連絡先を追加するときに、連絡先の名前の下に "Lync" と表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cb323-117">When a Skype user adds a Lync contact, verify that the word Lync appears below the contact’s name.</span></span> <span data-ttu-id="cb323-118">これは、Lync URI が検出されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="cb323-118">This indicates that a Lync URI has been found.</span></span></P>
> <LI>
> <P><span data-ttu-id="cb323-119">Skype ユーザーが Lync の連絡先を追加したときに、その Lync ドメインで検索結果がゼロで返されると、PIC プロビジョニングプロセスが完了していないか、Lync ドメインがまだセットアップされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cb323-119">When a Skype user adds a Lync contact and zero search results are returned for that Lync domain, the PIC provisioning process may not have completed, or the Lync domain has not yet been set up.</span></span></P>
> <LI>
> <P><span data-ttu-id="cb323-120">Lync および Skype ユーザーのプライバシー設定によっては、新しい連絡先が各ユーザーによって承認されるまで、IM、ビデオ、プレゼンスが機能しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="cb323-120">Depending on the privacy settings of the Lync and Skype users, IM, video, and presence may not work until the new contacts are accepted by each user.</span></span></P></LI></UL>



</div>

<span data-ttu-id="cb323-121">**Lync 2013 に Skype の連絡先を追加するには**</span><span class="sxs-lookup"><span data-stu-id="cb323-121">**To add a Skype contact to Lync 2013**</span></span>

1.  <span data-ttu-id="cb323-122">Lync で、[**連絡先の追加] をクリックし、[組織外の連絡先を追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb323-122">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="cb323-123">利用可能なコンタクトプロバイダのリストから「 **Skype**」を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb323-123">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="cb323-124">[ **IM アドレス**] フィールドに、Skype ユーザーの Microsoft アカウント (MSA) を入力します。</span><span class="sxs-lookup"><span data-stu-id="cb323-124">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user.</span></span>

4.  <span data-ttu-id="cb323-125">[**連絡先グループに追加**] ドロップダウンボックスで、ユーザーを追加する連絡先グループを選びます。</span><span class="sxs-lookup"><span data-stu-id="cb323-125">In the **Add to contact group** dropdown box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="cb323-126">[**プライバシー関係の設定**] ドロップダウンボックスで、適切な連絡先の設定を選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb323-126">In the **Set privacy relationship** dropdown box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="cb323-127">これで、ユーザーが Lync に連絡先として表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="cb323-127">The user will now appear as a contact in Lync.</span></span> <span data-ttu-id="cb323-128">ユーザーを選び、ユーザー名を右クリックして、[**連絡先カードの表示**] をクリックし、ユーザーのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="cb323-128">Select the user, right-click the user name, and click **See Contact Card** to view the user properties.</span></span> <span data-ttu-id="cb323-129">新しく追加された Skype ユーザとの音声通話またはビデオ通話を確立できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="cb323-129">You can now establish an audio or video call with the newly added Skype user.</span></span>

<span data-ttu-id="cb323-130">連絡先のサポートの詳細については、「 [Lync で連絡先を追加する](https://support.office.com/en-us/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb323-130">For additional information on support for contacts, see [Add a contact in Lync](https://support.office.com/en-us/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span></span>

<span data-ttu-id="cb323-131">Skype ユーザーの Microsoft アカウントでカスタムドメイン名 ( <strong>bob@contoso.com</strong>など) を使用している場合、lync ユーザーは、次の2つの方法で microsoft アカウントを lync に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="cb323-131">When a Skype user’s Microsoft account uses a custom domain name, such as <strong>bob@contoso.com</strong> , a Lync user can add that Microsoft account to Lync in two ways:</span></span>

1.  <span data-ttu-id="cb323-132">[**連絡先の追加**] アイコンを使用するか、</span><span class="sxs-lookup"><span data-stu-id="cb323-132">Use the **Add a Contact** icon, or</span></span>

2.  <span data-ttu-id="cb323-133">[**ユーザーまたは会議室を検索] または [電話番号をダイヤル**する] フィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb323-133">Use the **Find someone or a room, or a dial a number** field.</span></span>

<span data-ttu-id="cb323-134">各インスタンスでは、Lync ユーザーは、Skype ユーザーのメールを次の形式で入力する必要があります。<strong>ユーザー (ドメイン名) @msn .com</strong> 。</span><span class="sxs-lookup"><span data-stu-id="cb323-134">In each instance, the Lync user must enter the Skype user’s email in the following format: <strong>user(domain name)@msn.com</strong> .</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cb323-135">この手順は、次のドメイン名を使用する Microsoft アカウントには必要ありません。 <STRONG>@live .com、@hotmail .com、または @outlook</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="cb323-135">This step is not required for Microsoft accounts that use the following domain names: <STRONG>@live.com, @hotmail.com or @outlook.com</STRONG>.</span></span> <span data-ttu-id="cb323-136">サポートされているカスタムドメイン名の詳細については、「<A href="https://support.microsoft.com/kb/897567">サポートされているパブリック IM ドメイン</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb323-136">For more information on supported custom domain names, see <A href="https://support.microsoft.com/kb/897567">Supported public IM domains</A>.</span></span>



</div>

<span data-ttu-id="cb323-137">**カスタムドメイン名を使用しているときに、Lync に Skype 連絡先を追加するには**</span><span class="sxs-lookup"><span data-stu-id="cb323-137">**To add a Skype contact to Lync when using a custom domain name**</span></span>

1.  <span data-ttu-id="cb323-138">Lync で、[**連絡先の追加] をクリックし、[組織外の連絡先を追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb323-138">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="cb323-139">利用可能なコンタクトプロバイダのリストから「 **Skype**」を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb323-139">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="cb323-140">[ **IM アドレス**] フィールドに、ユーザーの形式 (<strong>ドメイン名) @msn .com</strong>の Skype ユーザーの Microsoft アカウント (MSA) を入力します。</span><span class="sxs-lookup"><span data-stu-id="cb323-140">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user in the format <strong>user(domain name)@msn.com</strong>.</span></span> <span data-ttu-id="cb323-141">ユーザー bob@contoso.com の場合、エントリは<strong>bob (contoso) @msn になり<strong>ます。</span><span class="sxs-lookup"><span data-stu-id="cb323-141">So for user bob@contoso.com, the entry would be <strong>bob(contoso.com)@msn.com<strong> .</span></span>

4.  <span data-ttu-id="cb323-142">[**連絡先グループに追加**] ドロップダウンリストボックスで、ユーザーを追加する連絡先グループを選びます。</span><span class="sxs-lookup"><span data-stu-id="cb323-142">In the **Add to contact group** drop-down list box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="cb323-143">[**プライバシー関係の設定**] ドロップダウンリストボックスで、適切な連絡先の設定を選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb323-143">In the **Set privacy relationship** drop-down list box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="cb323-144">Lync ユーザーは、[ユーザーの**検索] または [会議室**] を使用したり、lync の電話番号をダイヤルしたり、次のようなアドレス<strong>(ドメイン名) @msn</strong>を追加したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cb323-144">A Lync user can also use the **Find someone or a room, or dial a number** field in Lync, and add an address that resembles the following <strong>user(domain name)@msn.com</strong> .</span></span> <span data-ttu-id="cb323-145">Bob@contoso.com Microsoft アカウントの場合、エントリは<strong>bob (contoso) @msn</strong>になります。</span><span class="sxs-lookup"><span data-stu-id="cb323-145">So for the bob@contoso.com Microsoft account, the entry would be <strong>bob(contoso.com)@msn.com</strong> .</span></span>

7.  <span data-ttu-id="cb323-146">連絡先グループに連絡先を追加して、適切なプライバシー関係を選択するには、上記の手順4と5を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb323-146">Follow steps 4 and 5 earlier in this procedure to add the contact to a contact group and to select the appropriate privacy relationship.</span></span>

<span data-ttu-id="cb323-147">**Lync の連絡先を Skype に追加するには**</span><span class="sxs-lookup"><span data-stu-id="cb323-147">**To add a Lync contact to Skype**</span></span>

1.  <span data-ttu-id="cb323-148">Skype にサインインします。</span><span class="sxs-lookup"><span data-stu-id="cb323-148">Sign in to Skype.</span></span> <span data-ttu-id="cb323-149">Skype ユーザは、Microsoft アカウント (MSA) を使って Skype クライアントにログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb323-149">The Skype user must be logged into their Skype client with a Microsoft Account (MSA).</span></span>

2.  <span data-ttu-id="cb323-150">[連絡先の追加] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb323-150">Select the Add Contacts icon.</span></span>

3.  <span data-ttu-id="cb323-151">Lync ユーザーの SIP URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="cb323-151">Enter the SIP URI of the Lync user.</span></span> <span data-ttu-id="cb323-152">たとえば、bob@contoso.com のようになります。</span><span class="sxs-lookup"><span data-stu-id="cb323-152">For example, bob@contoso.com.</span></span>

4.  <span data-ttu-id="cb323-153">検索結果で一致するものが見つかった場合は、Lync ユーザー名の下にある word **Lync**を探します。</span><span class="sxs-lookup"><span data-stu-id="cb323-153">When Skype finds the match in the search results, look for the word **Lync** below the Lync user’s name.</span></span> <span data-ttu-id="cb323-154">これは、Skype が Lync クライアントの SIP URI を正常に見つけたことを示します。</span><span class="sxs-lookup"><span data-stu-id="cb323-154">This indicates Skype successfully located the Lync client’s SIP URI.</span></span> <span data-ttu-id="cb323-155">名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb323-155">Click the name.</span></span>

5.  <span data-ttu-id="cb323-156">ウィンドウの右上隅の [連絡先フォルダーに追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb323-156">In the top right corner of the window, click Add to Contacts.</span></span>

6.  <span data-ttu-id="cb323-157">これで、新しい連絡先が連絡先リストに追加されますが、ユーザーが要求を承認するまでは、[状態] アイコンの代わりに疑問符が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb323-157">The new contact is now added to your contact list, but you’ll see a question mark instead of their status icon until they accept your request.</span></span> <span data-ttu-id="cb323-158">新しい連絡先が要求を受け入れると、相手がオンラインであることを確認したり、IM で会話を開始したり、音声通話やビデオ通話を行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="cb323-158">When your new contact accepts your request, you will be able to see when they are online, initiate IM conversations, and make audio and video calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cb323-159">Lync Server 管理者は、受信要求を許可するように Lync ユーザーのポリシー設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb323-159">The Lync Server administrator must configure the Lync user’s policy settings to allow incoming requests.</span></span> <span data-ttu-id="cb323-160">サポートされていない場合、Lync ユーザーは Skype ユーザーからのコンタクト要求を受信しません。</span><span class="sxs-lookup"><span data-stu-id="cb323-160">If not, the Lync user will not receive contact requests from the Skype user.</span></span> <span data-ttu-id="cb323-161">Lync ユーザーのポリシー設定の構成に応じて、Lync クライアントの [<STRONG>新規</STRONG>] タブに Skype ユーザーの追加要求が表示されます。Skype ユーザーとの通信を開始するには、Lync ユーザーが [お気に入り] の一覧または連絡先リストに Skype ユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb323-161">Depending on the configuration of the Lync user’s policy settings, the request to add the Skype user will appear on the Lync client’s <STRONG>New</STRONG> tab. To begin communicating with the Skype user, the Lync user must add the Skype user to either the Favorites list or a contact list.</span></span> <span data-ttu-id="cb323-162">次の図は、Lync クライアントでの<STRONG>新しい</STRONG>タブの場所を示しています。</span><span class="sxs-lookup"><span data-stu-id="cb323-162">The image below shows the location of the <STRONG>New</STRONG> tab in the Lync client.</span></span>

    
    </div>

<span data-ttu-id="cb323-163">Lync ユーザーは、Skype ユーザーから送信された要求が表示され、Lync ユーザーが見つけられるようにするために、Lync 通知を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb323-163">A Lync user must configure Lync alerts to ensure that requests sent from a Skype user appear and are discoverable by the Lync user.</span></span> <span data-ttu-id="cb323-164">Lync の通知を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb323-164">To configure Lync alerts, complete the procedure that follows.</span></span>

<span data-ttu-id="cb323-165">**Lync 通知を構成するには**</span><span class="sxs-lookup"><span data-stu-id="cb323-165">**To configure Lync Alerts**</span></span>

1.  <span data-ttu-id="cb323-166">Lync クライアントで、[**オプション**] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb323-166">From the Lync client, click the **Options** icon.</span></span>

2.  <span data-ttu-id="cb323-167">[**通知**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cb323-167">Select **Alerts**.</span></span>

3.  <span data-ttu-id="cb323-168">[**一般通知**] で、[**だれかの連絡先リストに追加された場合**に通知する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="cb323-168">Under **General alerts**, check **Tell me when someone adds me to his or her contact list**.</span></span>

4.  <span data-ttu-id="cb323-169">[ **Lync を使っていない連絡先**] で [**招待を許可するが、その他のすべての通信をブロックする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb323-169">Under **Contacts not using Lync**, select **Allow invites but block all other communications**.</span></span>

5.  <span data-ttu-id="cb323-170">[ **OK** ] をクリックして [オプション] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cb323-170">Click **OK** to close the Options window.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

