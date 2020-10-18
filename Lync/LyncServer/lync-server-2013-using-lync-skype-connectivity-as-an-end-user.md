---
title: 'Lync Server 2013: エンドユーザーとしての Lync-Skype 接続の使用'
description: 'Lync Server 2013: エンドユーザーとして Lync-Skype 接続を使用します。'
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
ms.openlocfilehash: dd669a5cf0b15f7fb2d411e4456553f5469d9f96
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580383"
---
# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a><span data-ttu-id="a8e57-103">エンドユーザーとしての Lync Server 2013 での Lync-Skype 接続の使用</span><span class="sxs-lookup"><span data-stu-id="a8e57-103">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8e57-104">_**トピックの最終更新日:** 2016-12-27_</span><span class="sxs-lookup"><span data-stu-id="a8e57-104">_**Topic Last Modified:** 2016-12-27_</span></span>

<span data-ttu-id="a8e57-105">接続を Lync-Skype すると、Skype ユーザーと Lync ユーザーは、連絡先、exchange インスタントメッセージ、および音声通話とビデオ通話を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="a8e57-105">Lync-Skype Connectivity enables Skype users and Lync users to add each other as contacts, exchange instant messages and make audio and video calls.</span></span> <span data-ttu-id="a8e57-106">Skype ユーザーが Lync ユーザーを追加すると、skype ユーザーは Lync ユーザーのセッション開始プロトコル (SIP) uniform resource identifier (URI) を含む Skype の連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-106">When a Skype user adds a Lync user, a Skype user will create a contact in Skype containing the session initiation protocol (SIP) uniform resource identifier (URI) of the Lync user.</span></span> <span data-ttu-id="a8e57-107">反対に、Lync ユーザーが Skype 連絡先を追加すると、lync ユーザーは skype ユーザー名ではなく、Skype ユーザーの Microsoft アカウント (MSA) を含む Lync で連絡先を作成します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-107">Conversely, when a Lync user adds a Skype contact, the Lync user will create a contact in Lync that will contain the Microsoft Account (MSA) of the Skype user, and not the Skype user name.</span></span>

<span data-ttu-id="a8e57-108">**MSA とは**</span><span class="sxs-lookup"><span data-stu-id="a8e57-108">**What is an MSA?**</span></span> <span data-ttu-id="a8e57-109">Skype ユーザーは、Lync の連絡先と通信するために、Microsoft アカウント (旧称 Windows Live ID) を使用して Skype にサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8e57-109">Skype users must sign in to Skype with a Microsoft account (previously called Windows Live ID) in order to communicate with Lync contacts.</span></span><span data-ttu-id="a8e57-110">Microsoft アカウントは、電子メールアドレスとパスワードの組み合わせで構成されており、Microsoft OneDrive ストレージテクノロジ、Windows Phone、Microsoft Xbox LIVE ゲームサービス、Microsoft Outlook メッセージングおよびコラボレーションクライアント (および以前の Microsoft Hotmail web ベースの電子メールサービスまたは Windows Live Messenger) などのサービスへのサインインにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="a8e57-110"> A Microsoft account consists of the combination of an email address and a password, which you can also use to sign in to services such as Microsoft OneDrive storage technology, Windows Phone, Microsoft Xbox LIVE online game service, and Microsoft Outlook messaging and collaboration client (and, previously, Microsoft Hotmail web-based e-mail service or Windows Live Messenger).</span></span><span data-ttu-id="a8e57-111">電子メールアドレスとパスワードを使用して、これらのサービスまたはその他のサービスにサインインする場合は、既に Microsoft アカウントを持っています。</span><span class="sxs-lookup"><span data-stu-id="a8e57-111"> If you use an email address and a password to sign in to these or other services, you already have a Microsoft account.</span></span><span data-ttu-id="a8e57-112">Microsoft アカウントの作成の詳細については、Microsoft アカウントのサインアップページ () を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061) 。</span><span class="sxs-lookup"><span data-stu-id="a8e57-112"> For details about creating a Microsoft Account, see the Microsoft account sign-up page at [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061).</span></span> <span data-ttu-id="a8e57-113">既存の Skype アカウントを、さまざまなアプリケーションやサービスのシングルサインオン用の Microsoft アカウントに結合することができます。</span><span class="sxs-lookup"><span data-stu-id="a8e57-113">You can merge your existing Skype account with your Microsoft account for single sign-on, across a variety of applications and services.</span></span> <span data-ttu-id="a8e57-114">アカウントが結合されると、Skype ユーザーは Lync ユーザーに対して連絡先要求を送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a8e57-114">Once the account is merged a Skype user can send a contact request to Lync users.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a8e57-115">Lync および Skype ユーザーがお互いに完全に通信できるようにするには、次の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8e57-115">In order for Lync and Skype users to fully communicate with each other, the following requirements must be met:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="a8e57-116">Skype ユーザーは、Microsoft アカウント (MSA) を使用して Skype クライアントにログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8e57-116">Skype users must be logged into their Skype client with a Microsoft Account (MSA).</span></span></P>
> <LI>
> <P><span data-ttu-id="a8e57-117">Lync ユーザーは、Lync 管理者がパブリック IM 接続を有効にしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8e57-117">Lync users must be enabled for public IM connectivity by their Lync administrator.</span></span></P>
> <LI>
> <P><span data-ttu-id="a8e57-118">Skype ユーザーが Lync 連絡先を追加するときに、連絡先の名前の下に「Lync」という語句が表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-118">When a Skype user adds a Lync contact, verify that the word Lync appears below the contact’s name.</span></span> <span data-ttu-id="a8e57-119">これは、Lync URI が見つかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-119">This indicates that a Lync URI has been found.</span></span></P>
> <LI>
> <P><span data-ttu-id="a8e57-120">Skype ユーザーが lync 連絡先を追加し、その Lync ドメインに対して検索結果がゼロで返された場合、PIC プロビジョニングプロセスが完了していないか、または Lync ドメインがまだセットアップされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a8e57-120">When a Skype user adds a Lync contact and zero search results are returned for that Lync domain, the PIC provisioning process may not have completed, or the Lync domain has not yet been set up.</span></span></P>
> <LI>
> <P><span data-ttu-id="a8e57-121">Lync および Skype ユーザーのプライバシー設定によっては、新しい連絡先が各ユーザーによって承認されるまで、IM、ビデオ、プレゼンスが機能しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a8e57-121">Depending on the privacy settings of the Lync and Skype users, IM, video, and presence may not work until the new contacts are accepted by each user.</span></span></P></LI></UL>



</div>

<span data-ttu-id="a8e57-122">**Skype 連絡先を Lync 2013 に追加するには**</span><span class="sxs-lookup"><span data-stu-id="a8e57-122">**To add a Skype contact to Lync 2013**</span></span>

1.  <span data-ttu-id="a8e57-123">Lync で、[ **連絡先の追加] をクリックし、自分の組織にない連絡先を追加**します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-123">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="a8e57-124">利用可能な連絡先プロバイダーのリストから、[ **Skype**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-124">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="a8e57-125">[ **IM アドレス** ] フィールドに、Skype ユーザーの Microsoft アカウント (MSA) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-125">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user.</span></span>

4.  <span data-ttu-id="a8e57-126">[ **連絡先グループに追加** ] ドロップダウンボックスで、ユーザーを追加する連絡先グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-126">In the **Add to contact group** dropdown box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="a8e57-127">[ **プライバシー関係の設定** ] ドロップダウンボックスで、適切な連絡先設定を選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8e57-127">In the **Set privacy relationship** dropdown box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="a8e57-128">これで、ユーザーは Lync に連絡先として表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="a8e57-128">The user will now appear as a contact in Lync.</span></span> <span data-ttu-id="a8e57-129">ユーザーを選択し、ユーザー名を右クリックし、[ **連絡先カードを表示** する] をクリックしてユーザーのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-129">Select the user, right-click the user name, and click **See Contact Card** to view the user properties.</span></span> <span data-ttu-id="a8e57-130">新しく追加された Skype ユーザーとの音声またはビデオ通話を確立できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a8e57-130">You can now establish an audio or video call with the newly added Skype user.</span></span>

<span data-ttu-id="a8e57-131">連絡先のサポートの詳細については、「 [Lync の連絡先を追加する](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8e57-131">For additional information on support for contacts, see [Add a contact in Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).</span></span>

<span data-ttu-id="a8e57-132">Skype ユーザーの Microsoft アカウントで <strong>bob@contoso.com</strong> などのカスタムドメイン名を使用すると、lync ユーザーは次の2つの方法で microsoft アカウントを lync に追加できます。</span><span class="sxs-lookup"><span data-stu-id="a8e57-132">When a Skype user’s Microsoft account uses a custom domain name, such as <strong>bob@contoso.com</strong> , a Lync user can add that Microsoft account to Lync in two ways:</span></span>

1.  <span data-ttu-id="a8e57-133">[ **連絡先の追加** ] アイコンを使用するか、</span><span class="sxs-lookup"><span data-stu-id="a8e57-133">Use the **Add a Contact** icon, or</span></span>

2.  <span data-ttu-id="a8e57-134">[ **人物または会議室を探す] または [電話番号をダイヤル** する] フィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-134">Use the **Find someone or a room, or a dial a number** field.</span></span>

<span data-ttu-id="a8e57-135">各インスタンスで、Lync ユーザーは Skype ユーザーの電子メールを次の形式で入力する必要があります。 <strong>ユーザー (ドメイン名) @msn .com</strong> 。</span><span class="sxs-lookup"><span data-stu-id="a8e57-135">In each instance, the Lync user must enter the Skype user’s email in the following format: <strong>user(domain name)@msn.com</strong> .</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a8e57-136">この手順は、次のドメイン名を使用する Microsoft アカウントには必要ありません。 <STRONG>@live .com、@hotmail、または @outlook</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="a8e57-136">This step is not required for Microsoft accounts that use the following domain names: <STRONG>@live.com, @hotmail.com or @outlook.com</STRONG>.</span></span> <span data-ttu-id="a8e57-137">サポートされているカスタムドメイン名の詳細については、「 <A href="https://support.microsoft.com/kb/897567">サポートされているパブリック IM ドメイン</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8e57-137">For more information on supported custom domain names, see <A href="https://support.microsoft.com/kb/897567">Supported public IM domains</A>.</span></span>



</div>

<span data-ttu-id="a8e57-138">**カスタムドメイン名を使用して Skype 連絡先を Lync に追加するには**</span><span class="sxs-lookup"><span data-stu-id="a8e57-138">**To add a Skype contact to Lync when using a custom domain name**</span></span>

1.  <span data-ttu-id="a8e57-139">Lync で、[ **連絡先の追加] をクリックし、自分の組織にない連絡先を追加**します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-139">From Lync, click **Add a Contact, Add a Contact Not in My Organization**.</span></span>

2.  <span data-ttu-id="a8e57-140">利用可能な連絡先プロバイダーのリストから、[ **Skype**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-140">From the list of available contact providers, select **Skype**.</span></span>

3.  <span data-ttu-id="a8e57-141">[ **IM アドレス** ] フィールドに、ユーザーの形式 <strong>(ドメイン名) @msn</strong>で、Skype ユーザーの Microsoft アカウント (MSA) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-141">In the **IM Address** field, enter the Microsoft Account (MSA) of the Skype user in the format <strong>user(domain name)@msn.com</strong>.</span></span> <span data-ttu-id="a8e57-142">このため、ユーザー bob@contoso.com の場合、このエントリは <strong> bob (@msn) <strong> となります。</span><span class="sxs-lookup"><span data-stu-id="a8e57-142">So for user bob@contoso.com, the entry would be <strong>bob(contoso.com)@msn.com<strong> .</span></span>

4.  <span data-ttu-id="a8e57-143">[ **連絡先グループに追加** ] ドロップダウンリストボックスで、ユーザーを追加する連絡先グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-143">In the **Add to contact group** drop-down list box, select a contact group to add the user to.</span></span>

5.  <span data-ttu-id="a8e57-144">[ **プライバシー関係の設定** ] ドロップダウンリストボックスで、適切な連絡先設定を選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8e57-144">In the **Set privacy relationship** drop-down list box, select the appropriate contact setting and then click **OK**.</span></span>

6.  <span data-ttu-id="a8e57-145">Lync ユーザーは、[人の検索] または [会議室] を使用したり、Lync で **電話番号の** フィールドにダイヤルしたり、次のようなアドレスを追加したりすることもできます <strong>(ドメイン名) @msn .com</strong> 。</span><span class="sxs-lookup"><span data-stu-id="a8e57-145">A Lync user can also use the **Find someone or a room, or dial a number** field in Lync, and add an address that resembles the following <strong>user(domain name)@msn.com</strong> .</span></span> <span data-ttu-id="a8e57-146">そのため、bob@contoso.com Microsoft アカウントの場合、このエントリは <strong>bob (@msn)</strong> となります。</span><span class="sxs-lookup"><span data-stu-id="a8e57-146">So for the bob@contoso.com Microsoft account, the entry would be <strong>bob(contoso.com)@msn.com</strong> .</span></span>

7.  <span data-ttu-id="a8e57-147">連絡先を連絡先グループに追加し、適切なプライバシー関係を選択するには、上記の手順4と5に従います。</span><span class="sxs-lookup"><span data-stu-id="a8e57-147">Follow steps 4 and 5 earlier in this procedure to add the contact to a contact group and to select the appropriate privacy relationship.</span></span>

<span data-ttu-id="a8e57-148">**Lync 連絡先を Skype に追加するには**</span><span class="sxs-lookup"><span data-stu-id="a8e57-148">**To add a Lync contact to Skype**</span></span>

1.  <span data-ttu-id="a8e57-149">Skype にサインインします。</span><span class="sxs-lookup"><span data-stu-id="a8e57-149">Sign in to Skype.</span></span> <span data-ttu-id="a8e57-150">Skype ユーザーは、Microsoft アカウント (MSA) を使用して Skype クライアントにログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8e57-150">The Skype user must be logged into their Skype client with a Microsoft Account (MSA).</span></span>

2.  <span data-ttu-id="a8e57-151">[連絡先の追加] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-151">Select the Add Contacts icon.</span></span>

3.  <span data-ttu-id="a8e57-152">Lync ユーザーの SIP URI を入力します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-152">Enter the SIP URI of the Lync user.</span></span> <span data-ttu-id="a8e57-153">たとえば、bob@contoso.com です。</span><span class="sxs-lookup"><span data-stu-id="a8e57-153">For example, bob@contoso.com.</span></span>

4.  <span data-ttu-id="a8e57-154">検索結果で一致するものが見つかった場合は、Lync ユーザー名の下にある word **lync** を検索します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-154">When Skype finds the match in the search results, look for the word **Lync** below the Lync user’s name.</span></span> <span data-ttu-id="a8e57-155">これは、Skype が Lync クライアントの SIP URI に正常に配置されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-155">This indicates Skype successfully located the Lync client’s SIP URI.</span></span> <span data-ttu-id="a8e57-156">名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8e57-156">Click the name.</span></span>

5.  <span data-ttu-id="a8e57-157">ウィンドウの右上にある [連絡先に追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8e57-157">In the top right corner of the window, click Add to Contacts.</span></span>

6.  <span data-ttu-id="a8e57-158">連絡先リストに新しい連絡先が追加されましたが、要求を承諾するまでは、[状態] アイコンではなく、疑問符が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8e57-158">The new contact is now added to your contact list, but you’ll see a question mark instead of their status icon until they accept your request.</span></span> <span data-ttu-id="a8e57-159">新しい連絡先が要求を受信すると、オンライン状態を確認したり、IM 会話を開始したり、音声およびビデオ通話を行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a8e57-159">When your new contact accepts your request, you will be able to see when they are online, initiate IM conversations, and make audio and video calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a8e57-160">Lync Server 管理者は、受信要求を許可するように Lync ユーザーのポリシー設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8e57-160">The Lync Server administrator must configure the Lync user’s policy settings to allow incoming requests.</span></span> <span data-ttu-id="a8e57-161">それ以外の場合、Lync ユーザーは Skype ユーザーからの連絡先要求を受信しません。</span><span class="sxs-lookup"><span data-stu-id="a8e57-161">If not, the Lync user will not receive contact requests from the Skype user.</span></span> <span data-ttu-id="a8e57-162">Lync ユーザーのポリシー設定の構成によっては、Skype ユーザーを追加する要求が Lync クライアントの [ <STRONG>新規作成</STRONG> ] タブに表示されます。Skype ユーザーとの通信を開始するには、Lync ユーザーが [お気に入り] 一覧または連絡先リストに Skype ユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8e57-162">Depending on the configuration of the Lync user’s policy settings, the request to add the Skype user will appear on the Lync client’s <STRONG>New</STRONG> tab. To begin communicating with the Skype user, the Lync user must add the Skype user to either the Favorites list or a contact list.</span></span> <span data-ttu-id="a8e57-163">下の図は、Lync クライアントの <STRONG>新しい</STRONG> タブの場所を示しています。</span><span class="sxs-lookup"><span data-stu-id="a8e57-163">The image below shows the location of the <STRONG>New</STRONG> tab in the Lync client.</span></span>

    
    </div>

<span data-ttu-id="a8e57-164">Lync ユーザーは、Skype ユーザーから送信された要求が Lync ユーザーに表示され、検出可能であることを確認するために、Lync alerts を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8e57-164">A Lync user must configure Lync alerts to ensure that requests sent from a Skype user appear and are discoverable by the Lync user.</span></span> <span data-ttu-id="a8e57-165">Lync alerts を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-165">To configure Lync alerts, complete the procedure that follows.</span></span>

<span data-ttu-id="a8e57-166">**Lync Alerts を構成するには**</span><span class="sxs-lookup"><span data-stu-id="a8e57-166">**To configure Lync Alerts**</span></span>

1.  <span data-ttu-id="a8e57-167">Lync クライアントから、[ **オプション** ] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8e57-167">From the Lync client, click the **Options** icon.</span></span>

2.  <span data-ttu-id="a8e57-168">[ **通知**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-168">Select **Alerts**.</span></span>

3.  <span data-ttu-id="a8e57-169">[ **一般的な通知**] で、自分の **連絡先リストにユーザーが追加されたときに**[通知] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="a8e57-169">Under **General alerts**, check **Tell me when someone adds me to his or her contact list**.</span></span>

4.  <span data-ttu-id="a8e57-170">[ **Lync を使用しない連絡先**] で、[ **招待を許可するが、他のすべての通信をブロックする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8e57-170">Under **Contacts not using Lync**, select **Allow invites but block all other communications**.</span></span>

5.  <span data-ttu-id="a8e57-171">[ **OK]** をクリックして、[オプション] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a8e57-171">Click **OK** to close the Options window.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

