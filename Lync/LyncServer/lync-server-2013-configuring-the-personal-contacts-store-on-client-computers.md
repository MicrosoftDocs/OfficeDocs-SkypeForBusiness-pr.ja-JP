---
title: 'Lync Server 2013: クライアントコンピューター上の個人用連絡先ストアの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5672619302e169db5e89281323eec4b5d8312c06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a><span data-ttu-id="ec9b7-102">Lync Server 2013 のクライアントコンピューターでの個人用連絡先ストアの構成</span><span class="sxs-lookup"><span data-stu-id="ec9b7-102">Configuring the personal contacts store on client computers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec9b7-103">_**トピックの最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="ec9b7-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="ec9b7-104">Microsoft Lync Server 2013 と Microsoft Exchange Server 2013 を統合する場合は、Microsoft Lync 2010 を実行しているすべてのクライアントコンピューターで個人連絡先ストアを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ec9b7-104">If you are integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 then it is recommended that you configure the personal contact store on any client computers running Microsoft Lync 2010.</span></span> <span data-ttu-id="ec9b7-105">特に、Exchange を個人連絡先ストアとして使用するように Lync を構成し、同時にユーザーがその決定を上書きできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec9b7-105">In particular, you should configure Lync to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="ec9b7-106">これを行うには、各クライアントコンピューターでレジストリ値を作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="ec9b7-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>

<span data-ttu-id="ec9b7-107">これは、Lync 2013 を実行しているコンピューターでは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ec9b7-107">Note that this is not required on computers running Lync 2013.</span></span>

<span data-ttu-id="ec9b7-108">ある 1 台のコンピューターでこの値を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ec9b7-108">To configure this value on a single computer, complete the following procedure:</span></span>

1.  <span data-ttu-id="ec9b7-109">クライアントコンピューターで、[**スタート**] をクリックし、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec9b7-109">On the client computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="ec9b7-110">[**実行**] ダイアログボックスで、「regedit」と入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ec9b7-110">In the **Run** dialog box, type regedit and then press ENTER.</span></span>

3.  <span data-ttu-id="ec9b7-111">レジストリエディターで、[ **HKEY\_LOCAL\_MACHINE**] を展開し、[**ソフトウェア**]、[**ポリシー**]、[ **Microsoft**]、[ **Communicator**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="ec9b7-111">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>

4.  <span data-ttu-id="ec9b7-112">[ **Communicator**] を右クリックし、[**新規**] をポイントして、[ **DWORD (32 ビット)**] の値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec9b7-112">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>

5.  <span data-ttu-id="ec9b7-113">新しい値が作成されたら、「 **」と入力し、** enter キーを押して、値の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="ec9b7-113">After the new value is created, type **PersonalContactStoreOverride** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="ec9b7-114">PersonalContactStoreOverride の値が 0 に設定されていることを確認し、レジストリ エディタを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ec9b7-114">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="ec9b7-115">複数のコンピューターでこれと同じ変更をする必要がある場合は、カスタム グループ ポリシー オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ec9b7-115">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="ec9b7-116">詳細については、「」の[http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543)グループポリシーのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec9b7-116">For details, see the Group Policy documentation at [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

