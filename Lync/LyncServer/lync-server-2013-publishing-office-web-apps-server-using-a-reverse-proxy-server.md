---
title: リバース プロキシ サーバーを使用して Office Web Apps サーバーを公開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f68ae51dba366282d7d3a5668b1358042a29917
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="6c964-102">リバースプロキシサーバーを使用して Lync Server 2013 で Office Web Apps サーバーを発行する</span><span class="sxs-lookup"><span data-stu-id="6c964-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c964-103">_**最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="6c964-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="6c964-104">外部ユーザー (つまり、組織のファイアウォール外からログオンしているユーザー) が Office Web Apps Server PowerPoint プレゼンテーションにアクセスできるようにするには、Office Web Apps サーバーと、Microsoft Forefront などのリバースプロキシサーバーを使用する必要があります。脅威管理ゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="6c964-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="6c964-105">これは、web サイトの公開ルールを作成して構成する必要があることも意味します。このルールは、ユーザーがサーバーに接続できることを確認するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6c964-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="6c964-106">外部ユーザーにアクセス権を付与する必要がない場合は、web サイトの公開ルールを構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6c964-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="6c964-107">Forefront Threat Management Gateway で web サイトの公開ルールを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6c964-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="6c964-108">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Forefront TMG**]、[ **forefront tmg 管理**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="6c964-109">Forefront TMG では、[**ファイアウォールポリシー**] を右クリックし、[**新規作成**] をポイントして、[ **Web サイト発行ルール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="6c964-110">新しい Web 公開ルールウィザードの [**新しい Web 公開ルールウィザードへようこそ**] ページで、[ **web 発行ルール名**] ボックスに新しいルールの名前を入力し (たとえば、[ **Office Web Apps Server ルール**])、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="6c964-111">[**ルールアクションの指定**] ページで、[**許可**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="6c964-112">[**発行の種類**] ページで、[**単一の Web サイトまたはロードバランサーを発行する**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="6c964-113">[**サーバー接続セキュリティ**] ページで、[SSL を使用して**公開された Web サーバーまたはサーバーファームに接続する**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="6c964-114">[**内部発行の詳細**] ページで、[**内部サイト名**] ボックスに Office WEB Apps サーバーの FQDN (たとえば、 **officewebapps01.contoso.com**) を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-114">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**.</span></span> <span data-ttu-id="6c964-115">[**内部サイト名**] ボックスに入力した名前は、Office Web Apps サーバーに割り当てた証明書の [件名] フィールドまたは [サブジェクトの別名] フィールドに表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c964-115">The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="6c964-116">[**内部発行の詳細**] ページで\*\* / \*\* 、[ **Path (オプション)** ] ボックスに入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="6c964-117">/\*構文を使用すると、サイトのすべてのフォルダーとサブフォルダーが公開されるようになります。</span><span class="sxs-lookup"><span data-stu-id="6c964-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="6c964-118">[**パブリック名の詳細**] ページで、[**許可する要求**] ドロップダウンリストから**このドメイン名 (下に入力)** を選び、[パブリック名] ボックスに Office Web Apps サーバーの完全修飾名を入力します。</span><span class="sxs-lookup"><span data-stu-id="6c964-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="6c964-119">この名前は、web サイトへのアクセスに使用する名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c964-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="6c964-120">たとえば、URL http://officewebapps01.contoso.comを使用してサイトにアクセスした場合は、[**パブリック名**] ボックスに「 **officewebapps01.contoso.com** 」と入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c964-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="6c964-121">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-121">Click **Next**.</span></span>

11. <span data-ttu-id="6c964-122">[ **Web リスナーの選択**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="6c964-123">新しい Web リスナーの定義ウィザードで、[ **web リスナー名**] ボックスに新しい web リスナーの名前\*\*\*\* を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="6c964-124">[**クライアント接続セキュリティ**] ページで、[**クライアントとの SSL セキュリティで保護された接続を要求する**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="6c964-125">[ **Web リスナー IP アドレス**] ページで、 **[外部**] を選択し、[**内部**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="6c964-126">[**リスナー SSL 証明書**] ページで、[**この Web リスナーには1つの証明書を使用する**]、[**証明書の選択**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="6c964-127">[**証明書の選択**] ダイアログボックスで、この Web リスナーに使用する証明書を選択し、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="6c964-128">[**リスナー SSL 証明書**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="6c964-129">[**認証の設定**] ページで、[**クライアントが Forefront TMG に資格情報を提供する方法を選択**してください] ドロップダウンリストから [**認証なし**] を選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="6c964-130">[**シングルサインオンの設定**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="6c964-131">[**新しい Web リスナーウィザードの完了**] ページで、選択した構成の概要を確認します。</span><span class="sxs-lookup"><span data-stu-id="6c964-131">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made.</span></span> <span data-ttu-id="6c964-132">準備ができたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-132">When ready, click **Finish**.</span></span>

21. <span data-ttu-id="6c964-133">[ **Web リスナーの選択**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="6c964-134">[**認証委任**] ページで [委任しない] を選択しますが、クライアントは [**公開された Web サーバーの認証に使用するメソッドを選択**する] ドロップダウンリストから**直接認証を受けることがあり**、[**次へ] をクリックします。**.</span><span class="sxs-lookup"><span data-stu-id="6c964-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="6c964-135">[**ユーザー設定**] ページで、適切なユーザーセットが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6c964-135">On the **User Sets** page, confirm that the appropriate user sets are listed.</span></span> <span data-ttu-id="6c964-136">既定では、[**すべてのユーザー** ] ユーザーが設定されています。</span><span class="sxs-lookup"><span data-stu-id="6c964-136">By default, this is the **All Users** user set.</span></span> <span data-ttu-id="6c964-137">[**追加**] をクリックして、定義している他のユーザーセットを追加します。</span><span class="sxs-lookup"><span data-stu-id="6c964-137">Click **Add** to add other user sets you may have defined.</span></span> <span data-ttu-id="6c964-138">完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-138">When complete, click **Next**.</span></span>

24. <span data-ttu-id="6c964-139">[**新しい Web 公開ルールウィザードの完了**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="6c964-140">**[完了**] をクリックしても、プロセスが完了したというわけではありません。つまり、これによって、新しいルールが自動的に適用されることはなくなります。</span><span class="sxs-lookup"><span data-stu-id="6c964-140">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule.</span></span> <span data-ttu-id="6c964-141">代わりに、Forefront TMG のユーザーインターフェイスに表示される [**適用**] ボタンをクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c964-141">Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface.</span></span> <span data-ttu-id="6c964-142">[**構成変更の説明**を**適用**] をクリックすると、[設定の変更] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c964-142">When you click **Apply** the **Configuration Change Description** dialog box will appear.</span></span> <span data-ttu-id="6c964-143">このダイアログボックスで [**適用**] をクリックして、新しい公開ルールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6c964-143">Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="6c964-144">新しいルールが適用された後、ユーザーが新しい PowerPoint プレゼンテーション機能を使用できるように、ルールに若干の変更を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c964-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="6c964-145">この操作を行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6c964-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="6c964-146">Forefront TMG で、新しい公開ルールの名前を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="6c964-147">[**プロパティ**] ダイアログボックスの [To] タブで、**実際の host header ではなく、元のホストヘッダーを転送\*\*\*\*する**オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6c964-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="6c964-148">[**トラフィック**] タブで、[**フィルター** ] をクリックし、[ **HTTP の構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="6c964-149">[**ルールの HTTP ポリシーの構成**] ダイアログボックスで、[**正規化の確認**] チェックボックスをオフにして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="6c964-150">[**プロパティ**] ダイアログボックスで、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="6c964-151">Forefront TMG では、[**適用**] をクリックして変更を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6c964-151">In Forefront TMG, click **Apply** to enable the changes.</span></span> <span data-ttu-id="6c964-152">[**構成の変更**] ダイアログボックスが表示されたら、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6c964-152">When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="6c964-153">インストールが完了したら、「 [Lync server 2013 で Office Web Apps サーバーの構成](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)を確認する」のトピックの手順を使用して、Office Web apps サーバーをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="6c964-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

