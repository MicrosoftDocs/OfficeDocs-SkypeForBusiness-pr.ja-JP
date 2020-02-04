---
title: 'Lync Server 2013: スマートカード認証のためにユーザーを登録する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750e77b342b48d2c81bf05e160779ca5566f5a2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735447"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="a03dd-102">Lync Server 2013 でスマートカード認証のユーザーを登録する</span><span class="sxs-lookup"><span data-stu-id="a03dd-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a03dd-103">_**最終更新日:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="a03dd-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="a03dd-p101">スマート カードの認証を行うユーザーを登録する方法は、主に 2 つあります。Web 登録を使ってスマート カード認証のユーザーを直接登録する方法がより簡単で、登録エージェントを使う方法はより複雑です。このトピックでは、スマート カードの証明書を自分で登録する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a03dd-p101">There are generally two methods for enrolling users for smart card authentication. The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent. This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="a03dd-107">登録エージェントとしてユーザーの代理として登録する方法について詳しくは、「他のユーザー [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367)の代理で証明書を登録する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a03dd-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="a03dd-108">スマート カードの認証を行うユーザーを登録するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a03dd-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="a03dd-109">Lync 対応ユーザーの資格情報を使用して、Windows 8 ワークステーションにログインします。</span><span class="sxs-lookup"><span data-stu-id="a03dd-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="a03dd-110">Internet Explorer を起動します。</span><span class="sxs-lookup"><span data-stu-id="a03dd-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="a03dd-111">**証明機関の Web 登録**ページを参照しますhttps://MyCA.contoso.com/certsrv)(例:</span><span class="sxs-lookup"><span data-stu-id="a03dd-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a03dd-112">Internet Explorer 10 を使っている場合は、この Web サイトを互換モードで見る必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a03dd-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="a03dd-113">Web サイトの [**ようこそ**] ページで、[**証明書の要求**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a03dd-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="a03dd-114">次に、[**証明書の要求の詳細設定**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a03dd-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="a03dd-115">[**この CA への要求を作成し送信する。**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a03dd-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="a03dd-116">[**証明書のテンプレート**] セクションで [**スマート カード ユーザー**] を選び、[証明書の要求の詳細設定] を次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a03dd-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="a03dd-117">[**キーのオプション**] で次の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="a03dd-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="a03dd-118">[**新しいキー セットを作成する**] ラジオ ボタンを選ぶ</span><span class="sxs-lookup"><span data-stu-id="a03dd-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="a03dd-119">[**CSP**] で、[**Microsoft ベース スマート カード暗号化プロバイダー**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="a03dd-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="a03dd-120">[**キー使用法**] で、[**Exchange**] を選ぶ (このオプションのみ有効)</span><span class="sxs-lookup"><span data-stu-id="a03dd-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="a03dd-121">[**キーのサイズ**] に、**2048** と入力する</span><span class="sxs-lookup"><span data-stu-id="a03dd-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="a03dd-122">[**自動キー コンテナー名**] が選択されている</span><span class="sxs-lookup"><span data-stu-id="a03dd-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="a03dd-123">その他のボックスはオフにします。</span><span class="sxs-lookup"><span data-stu-id="a03dd-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="a03dd-124">[**追加オプション**] で次の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="a03dd-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="a03dd-125">[**要求の形式**] で [**CMC**] を選ぶ。</span><span class="sxs-lookup"><span data-stu-id="a03dd-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="a03dd-126">[**ハッシュ アルゴリズム**] で [**sha1**] を選ぶ。</span><span class="sxs-lookup"><span data-stu-id="a03dd-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="a03dd-127">[**フレンドリ名**] に「**Smardcard Certificate**」と入力する。</span><span class="sxs-lookup"><span data-stu-id="a03dd-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="a03dd-128">物理カード リーダーを使っている場合は、デバイスにスマート カードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="a03dd-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="a03dd-129">[**送信**] をクリックして証明書要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="a03dd-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="a03dd-130">入力を求められたら、仮想スマート カードを作成したときに使った PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="a03dd-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a03dd-131">仮想スマート カードの既定の PIN の値は、「12345678」です。</span><span class="sxs-lookup"><span data-stu-id="a03dd-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="a03dd-132">証明書が発行されたら、[**この証明書のインストール**] をクリックして登録プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="a03dd-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a03dd-133">「証明書の要求の生成はこの Web ブラウザーではサポートされていません。」というエラーが発生して証明書の作成が失敗した場合、解決する方法として次の 3 つが考えられます。</span><span class="sxs-lookup"><span data-stu-id="a03dd-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="a03dd-134">Internet Explorer の [互換表示] を有効にする</span><span class="sxs-lookup"><span data-stu-id="a03dd-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="a03dd-135">Internet Explorer で [イントラネットの設定を有効にする] オプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="a03dd-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="a03dd-136">Internet Explorer の [インターネット オプション] の [セキュリティ] タブで、[すべてのゾーンを既定のレベルにリセットする] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="a03dd-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

