---
title: リバースプロキシサーバーを使用して Office Web Apps サーバーを公開する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1d1dae773c96cfa6d16994e5b3c6aec2504b16c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="37176-102">Lync Server 2013 でのリバースプロキシサーバーを使用した Office Web Apps サーバーの発行</span><span class="sxs-lookup"><span data-stu-id="37176-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37176-103">_**トピックの最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="37176-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="37176-104">外部ユーザー (つまり、組織のファイアウォールの外側からログオンしているユーザー) が Office Web Apps サーバーの PowerPoint プレゼンテーションにアクセスできるようにするには、Office Web Apps サーバーと、Microsoft Forefront などのリバースプロキシサーバーを使用する必要があります。脅威管理ゲートウェイ。</span><span class="sxs-lookup"><span data-stu-id="37176-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="37176-105">また、web サイト公開ルールを作成して構成する必要があることも意味します。このルールは、ユーザーがサーバーに接続できることを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="37176-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="37176-106">外部ユーザーへのアクセスを提供する必要がない場合は、web サイト公開ルールを構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="37176-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="37176-107">Forefront Threat Management Gateway に Web サイト公開ルールを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="37176-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="37176-108">[**スタート**] ボタンをクリックし、[**すべてのプログラム**]、[**Microsoft Forefront TMG**]、[**Forefront TMG Management**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="37176-109">Forefront TMG で、[**ファイアウォール ポリシー**] を右クリックし、[**新規作成**] をポイントして、[**Web サイト公開ルール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="37176-110">新しい Web 公開ルール ウィザードの [**新しい Web 公開ルール ウィザードへようこそ**] ページで、[**Web 公開ルールの名前**] ボックスに新しいルールの名前 (たとえば、**Office Web Apps サーバー ルール**) を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="37176-111">[**ルールの動作の選択**] ページで、[**許可**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="37176-112">[**公開の種類**] ページで、[**1 つの Web サイトまたは負荷分散装置を公開する**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="37176-113">[**サーバー接続セキュリティ**] ページで、[**公開された Web サーバーまたはサーバー ファームへの接続に SSL を使用する**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="37176-p102">[**内部公開の詳細**] ページで、[**内部サイト名**] ボックスに Office Web Apps サーバーの FQDN (たとえば、**officewebapps01.contoso.com**) を入力し、[**次へ**] をクリックします。[**内部サイト名**] ボックスに入力する名前は、Office Web Apps サーバーに割り当てられた証明書の "サブジェクト" または "サブジェクト代替名" フィールドに表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="37176-p102">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**. The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="37176-116">[**内部公開の詳細**] ページで\*\* / \*\* 、[**パス (省略可)** ] ボックスに入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="37176-117">/\*構文を使用すると、サイトのすべてのフォルダーとサブフォルダーが発行されるようにできます。</span><span class="sxs-lookup"><span data-stu-id="37176-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="37176-118">[**パブリック名の詳細**] ページで、[**要求の許可**] ドロップダウン リストから [**次に入力したドメイン名**] を選択し、[パブリック名] ボックスに Office Web Apps サーバーの完全修飾名を入力します。</span><span class="sxs-lookup"><span data-stu-id="37176-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="37176-119">この名前は Web サイトへのアクセスに使用される名前である必要があります。</span><span class="sxs-lookup"><span data-stu-id="37176-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="37176-120">たとえば、URL http://officewebapps01.contoso.comを使用してサイトにアクセスする場合は、[**パブリック名**] ボックスに「 **officewebapps01.contoso.com** 」と入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37176-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="37176-121">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-121">Click **Next**.</span></span>

11. <span data-ttu-id="37176-122">[**Web リスナーの選択**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="37176-123">新しい Web リスナーの定義ウィザードで、[**Web リスナー名**] ボックスに新しい Web リスナーの名前 (たとえば、**SSL**) を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="37176-124">[**クライアント接続セキュリティ**] ページで、[**クライアントとの SSL セキュリティ保護接続を必要とする**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="37176-125">[**Web リスナーの IP アドレス**] ページで、[**外部**] を選択し、[**内部**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="37176-126">[**リスナーの SSL 証明書**] ページで、[**この Web リスナーに 1 つの証明書を使う**] を選択し、[**証明書の選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="37176-127">[**証明書の選択**] ダイアログ ボックスで、この Web リスナーで使用する証明書を選択し、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="37176-128">[**リスナーの SSL 証明書**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="37176-129">[**認証の設定**] ページで、[**クライアントが Forefront TMG に資格情報を提供する方法を選択してください**] ドロップダウン リストから [**認証なし**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="37176-130">[**シングル サインオンの設定**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="37176-p105">[**新しい Web リスナー ウィザードの完了**] ページで、選択した構成の概要を確認します。すべて適切に選択されていることを確認できたら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-p105">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made. When ready, click **Finish**.</span></span>

21. <span data-ttu-id="37176-133">[**Web リスナーの選択**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="37176-134">[**認証の委任**] ページで、[**公開された Web サーバーを Forefront TMG が認証する方法を選択してください**] ドロップダウン リストから [**委任できません。クライアントは直接認証できます**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="37176-p106">[**ユーザー セット**] ページで、適切なユーザー セットが表示されていることを確認します。既定のユーザー セットは [**すべてのユーザー**] です。[**追加**] をクリックして他のユーザー セットを追加します (これらのユーザー セットは既に定義されている可能性があります)。操作が終了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-p106">On the **User Sets** page, confirm that the appropriate user sets are listed. By default, this is the **All Users** user set. Click **Add** to add other user sets you may have defined. When complete, click **Next**.</span></span>

24. <span data-ttu-id="37176-139">[**新しい Web 公開ルール ウィザードの完了**] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="37176-p107">[**完了**] をクリックしても、プロセスは完了しません。つまり、新しいルールは自動的に適用されません。また、自動的に有効になりません。新しいルールを適用するには、Forefront TMG ユーザー インターフェイスに表示される [**適用**] ボタンをクリックする必要があります。[**適用**] をクリックすると、[**構成の変更の説明**] ダイアログ ボックスが表示されます。このダイアログ ボックスの [**適用**] をクリックすると、新しい公開ルールが有効になります。</span><span class="sxs-lookup"><span data-stu-id="37176-p107">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule. Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface. When you click **Apply** the **Configuration Change Description** dialog box will appear. Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="37176-144">新しいルールを適用した後で、ユーザーが新しい PowerPoint プレゼンテーション機能を使用できるようにするために、ルールに若干の変更を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="37176-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="37176-145">そのためには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="37176-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="37176-146">Forefront TMG で、新しい公開ルールの名前を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="37176-147">[**プロパティ**] ダイアログ ボックスの [**公開先**] タブで、[[**内部サイト名] フィールドで指定した実際のホストヘッダーの代わりに元のホストヘッダーを、転送する**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="37176-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="37176-148">[**トラフィック**] タブで、[**フィルター**] をクリックし、[**HTTP の構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="37176-149">[**ルールに対する HTTP ポリシーの構成**] ダイアログ ボックスで、[**正規化を検証する**] チェック ボックスをオフにし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="37176-150">[**プロパティ**] ダイアログ ボックスで、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="37176-p109">Forefront TMG で、[**適用**] をクリックして変更を有効にします。[**構成の変更の説明**] ダイアログ ボックスが表示されたら、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="37176-p109">In Forefront TMG, click **Apply** to enable the changes. When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="37176-153">インストールの完了後、「 [Lync server 2013 の Office Web Apps サーバーの構成を検証](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)する」トピックの手順を使用して Office Web apps サーバーをテストできます。</span><span class="sxs-lookup"><span data-stu-id="37176-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

