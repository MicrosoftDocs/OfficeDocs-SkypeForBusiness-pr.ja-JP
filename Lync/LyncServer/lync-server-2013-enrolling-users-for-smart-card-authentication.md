---
title: 'Lync Server 2013: スマートカード認証のユーザーの登録'
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
ms.openlocfilehash: 9a157d5492378771cf40a6438bbf8672efd01412
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="d71aa-102">Lync Server 2013 でのスマートカード認証のユーザーの登録</span><span class="sxs-lookup"><span data-stu-id="d71aa-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d71aa-103">_**トピックの最終更新日:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="d71aa-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="d71aa-104">通常、スマートカード認証のためにユーザーを登録する方法は2つあります。</span><span class="sxs-lookup"><span data-stu-id="d71aa-104">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="d71aa-105">簡単な方法では、ユーザーが web 登録を使用してスマートカード認証を直接登録する必要がありますが、より複雑な方法では登録エージェントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d71aa-105">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="d71aa-106">このトピックでは、スマートカード証明書のセルフ登録に重点を置いて説明します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-106">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="d71aa-107">登録エージェントとしてのユーザーの代理での登録の詳細については、「他のユーザーの[https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367)代理として証明書を登録する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d71aa-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="d71aa-108">スマートカード認証を使用するようにユーザーを登録するには</span><span class="sxs-lookup"><span data-stu-id="d71aa-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="d71aa-109">Lync が有効なユーザーの資格情報を使用して、Windows 8 ワークステーションにログインします。</span><span class="sxs-lookup"><span data-stu-id="d71aa-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="d71aa-110">Internet Explorer を起動します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="d71aa-111">**証明機関の Web 登録**ページに移動しますhttps://MyCA.contoso.com/certsrv)(例:)。</span><span class="sxs-lookup"><span data-stu-id="d71aa-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d71aa-112">Internet Explorer 10 を使用している場合は、この web サイトを互換モードで表示する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="d71aa-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="d71aa-113">[**ようこそ**] ページで、[**証明書の要求**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="d71aa-114">次に、[**要求の詳細設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="d71aa-115">[**この CA への要求を作成し送信**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="d71aa-116">[**証明書テンプレート**] セクションの [**スマートカードユーザー** ] を選択し、次の値を使用して詳細証明書の要求を完了します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="d71aa-117">**キーオプション**次の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="d71aa-118">[**新しいキーセットの作成**] ラジオボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="d71aa-119">**CSP**の場合、[ **Microsoft 基本スマートカード暗号化プロバイダー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="d71aa-120">**キー使用法**については、[ **Exchange** ] を選択します (このオプションは使用できます)。</span><span class="sxs-lookup"><span data-stu-id="d71aa-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="d71aa-121">**キーサイズ**の場合は、 **2048**を入力します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="d71aa-122">**自動キーコンテナー名**が選択されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="d71aa-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="d71aa-123">その他のボックスはオフのままにします。</span><span class="sxs-lookup"><span data-stu-id="d71aa-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="d71aa-124">[**その他のオプション**] で、次の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="d71aa-125">**要求の形式**には、[ **CMC**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="d71aa-126">[**ハッシュアルゴリズム**] で [ **sha1**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="d71aa-127">**フレンドリ名**には、 **Smardcard 証明書**を入力します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="d71aa-128">物理スマートカードリーダーを使用している場合は、デバイスにスマートカードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="d71aa-129">[ **Submit** ] をクリックして証明書要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="d71aa-130">メッセージが表示されたら、仮想スマートカードの作成に使用した PIN を入力します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d71aa-131">既定の仮想スマートカードの PIN の値は ' 12345678 ' です。</span><span class="sxs-lookup"><span data-stu-id="d71aa-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="d71aa-132">証明書が発行されたら、[**この証明書のインストール**] をクリックして登録プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d71aa-133">証明書の要求が失敗し、"この Web ブラウザーは証明書の要求の生成をサポートしていません" というエラーが発生した場合は、次の3つの方法で問題を解決できます。</span><span class="sxs-lookup"><span data-stu-id="d71aa-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="d71aa-134">Internet Explorer で互換表示を有効にする</span><span class="sxs-lookup"><span data-stu-id="d71aa-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="d71aa-135">Internet Explorer で [イントラネット設定を有効にする] オプションを有効にする</span><span class="sxs-lookup"><span data-stu-id="d71aa-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="d71aa-136">Internet Explorer の [オプション] メニューの [セキュリティ] タブで、[すべての領域を既定のレベルにリセットする] 設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="d71aa-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

