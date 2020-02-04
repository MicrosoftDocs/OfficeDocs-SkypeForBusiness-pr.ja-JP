---
title: 'Lync Server 2013: モビリティ展開の確認'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying your mobility deployment
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690024(v=OCS.15)
ms:contentKeyID: 48184477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96b6c82478fffe2815e9d69b870b3b434eadb3cf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-your-mobility-deployment-in-lync-server-2013"></a>Lync Server 2013 でのモビリティ展開の確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-12_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server Mobility Service と Lync Server 自動検出サービスを展開した後、テストトランザクションを実行して、展開が正常に動作することを確認します。 **CsUcwaConference**を実行して、Lync 2013 モバイルクライアントを使用している2人のユーザーが会議での作成、参加、通信を行うことができるかどうかをテストできます。 このテストトランザクションを使用するには、2つの実際のユーザーを作成するか、ユーザーをテストして、すべての資格情報を確認する必要があります。

Lync 2010 Mobile を使用している2人のユーザー間のインスタントメッセージの送信をテストするには **、CsMcxP2PIM**を使用します。 **CsUcwaConference**と同様に、2つの実際のユーザーまたは2つの定義済みのテストユーザーを使用します。

<div>

## <a name="to-test-conferencing-for-lync-2013-mobile-clients"></a>Lync 2013 モバイルクライアント用の会議をテストするには

1.  Lync Server 管理シェル および Ocscore がインストールされている任意のコンピューターに CsAdministrator の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  コマンド ラインで次を入力します。
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    スクリプトで資格情報を設定し、テストコマンドレットに渡すことができます。 次に例を示します。
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

</div>

<div>

## <a name="to-test-person-to-person-instant-messaging-im-for-lync-2010-mobile"></a>Lync 2010 Mobile のユーザー間のインスタントメッセージング (IM) をテストするには

1.  Lync Server 管理シェル および Ocscore がインストールされている任意のコンピューターに CsAdministrator の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  コマンド ラインで次を入力します。
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    スクリプトで資格情報を設定し、テストコマンドレットに渡すことができます。 次に例を示します。
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

</div>

<div>

## <a name="see-also"></a>関連項目


[テスト-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)  
[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

