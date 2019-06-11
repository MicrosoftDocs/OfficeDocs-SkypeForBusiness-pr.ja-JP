---
title: 'Lync Server 2013: モビリティ展開の確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verifying your mobility deployment
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690024(v=OCS.15)
ms:contentKeyID: 48184477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b38e87a8266763085c74bf7119cc996f793ca93
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-your-mobility-deployment-in-lync-server-2013"></a><span data-ttu-id="4a5c5-102">Lync Server 2013 でのモビリティ展開の確認</span><span class="sxs-lookup"><span data-stu-id="4a5c5-102">Verifying your mobility deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a5c5-103">_**最終更新日:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="4a5c5-103">_**Topic Last Modified:** 2013-02-12_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="4a5c5-104">Lync Server Mobility Service と Lync Server 自動検出サービスを展開した後、テストトランザクションを実行して、展開が正常に動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="4a5c5-104">After you deploy the Lync Server Mobility Service and Lync Server Autodiscover Service, run a test transaction to verify that your deployment works correctly.</span></span> <span data-ttu-id="4a5c5-105">**CsUcwaConference**を実行して、Lync 2013 モバイルクライアントを使用している2人のユーザーが会議での作成、参加、通信を行うことができるかどうかをテストできます。</span><span class="sxs-lookup"><span data-stu-id="4a5c5-105">You can run **Test-CsUcwaConference** to test the ability of two users who are using Lync 2013 Mobile clients to create, join and communicate in a conference.</span></span> <span data-ttu-id="4a5c5-106">このテストトランザクションを使用するには、2つの実際のユーザーを作成するか、ユーザーをテストして、すべての資格情報を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a5c5-106">To use this test transaction, you need two actual users or test users, and their full credentials.</span></span>

<span data-ttu-id="4a5c5-107">Lync 2010 Mobile を使用している2人のユーザー間のインスタントメッセージの送信をテストするには **、CsMcxP2PIM**を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a5c5-107">You use **Test-CsMcxP2PIM** to test sending an instant message between two users who are using Lync 2010 Mobile.</span></span> <span data-ttu-id="4a5c5-108">**CsUcwaConference**と同様に、2つの実際のユーザーまたは2つの定義済みのテストユーザーを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a5c5-108">Similar to **Test-CsUcwaConference**, you use two actual users or two predefined test users.</span></span>

<div>

## <a name="to-test-conferencing-for-lync-2013-mobile-clients"></a><span data-ttu-id="4a5c5-109">Lync 2013 モバイルクライアント用の会議をテストするには</span><span class="sxs-lookup"><span data-stu-id="4a5c5-109">To test conferencing for Lync 2013 Mobile clients</span></span>

1.  <span data-ttu-id="4a5c5-110">Lync Server 管理シェル および Ocscore がインストールされている任意のコンピューターに CsAdministrator の役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="4a5c5-110">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="4a5c5-111">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4a5c5-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4a5c5-112">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="4a5c5-112">At the command line, type:</span></span>
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    <span data-ttu-id="4a5c5-113">スクリプトで資格情報を設定し、テストコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="4a5c5-113">You can set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="4a5c5-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4a5c5-114">For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

</div>

<div>

## <a name="to-test-person-to-person-instant-messaging-im-for-lync-2010-mobile"></a><span data-ttu-id="4a5c5-115">Lync 2010 Mobile のユーザー間のインスタントメッセージング (IM) をテストするには</span><span class="sxs-lookup"><span data-stu-id="4a5c5-115">To test person-to-person instant messaging (IM) for Lync 2010 Mobile</span></span>

1.  <span data-ttu-id="4a5c5-116">Lync Server 管理シェル および Ocscore がインストールされている任意のコンピューターに CsAdministrator の役割のメンバーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="4a5c5-116">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="4a5c5-117">Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="4a5c5-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4a5c5-118">コマンド ラインで次を入力します。</span><span class="sxs-lookup"><span data-stu-id="4a5c5-118">At the command line, type:</span></span>
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    <span data-ttu-id="4a5c5-119">スクリプトで資格情報を設定し、テストコマンドレットに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="4a5c5-119">You can set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="4a5c5-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4a5c5-120">For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4a5c5-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a5c5-121">See Also</span></span>


[<span data-ttu-id="4a5c5-122">テスト-CsMcxP2PIM</span><span class="sxs-lookup"><span data-stu-id="4a5c5-122">Test-CsMcxP2PIM</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)  
[<span data-ttu-id="4a5c5-123">Test-CsUcwaConference</span><span class="sxs-lookup"><span data-stu-id="4a5c5-123">Test-CsUcwaConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

