---
title: 'Lync Server 2013: モビリティ展開の確認'
TOCTitle: モビリティ展開の確認
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh690024(v=OCS.15)
ms:contentKeyID: 48272452
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのモビリティ展開の確認

 

_**トピックの最終更新日:** 2013-02-12_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server Mobility Service および Lync Server 自動検出サービスを展開した後、テスト トランザクションを実行して、展開が適切に機能することを確認します。**Test-CsUcwaConference** を実行すると、Lync 2013 モバイル クライアントを使用している 2 人のユーザーが、電話会議を作成、参加、通信できるかテストできます。このテスト トランザクションを使用するには、2 人の実際のユーザーまたはテスト ユーザー、およびそれらのユーザーの完全な資格情報が必要です。

Lync 2010 Mobile を使用している 2 人のユーザーの間でインスタント メッセージの送信をテストするには、**Test-CsMcxP2PIM** を使用します。**Test-CsUcwaConference** 同様に、2 人の実際のユーザー、または 2 人の定義済みのテスト ユーザーを使用します。

## Lync 2013 モバイル クライアントの会議をテストするには

1.  Lync Server 管理シェルおよび Ocscore がインストールされている任意のコンピューターに CsAdministrator の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンドラインで、次のように入力します。
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    スクリプト内に資格情報を設定して、資格情報をテスト コマンドレットに渡すことができます。たとえば、次のようになります。
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

## Lync 2010 Mobile 用に 1 対 1 のインスタント メッセージング (IM) をテストするには

1.  Lync Server 管理シェルおよび Ocscore がインストールされている任意のコンピューターに CsAdministrator の役割のメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンドラインで、次のように入力します。
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    スクリプト内に資格情報を設定して、資格情報をテスト コマンドレットに渡すことができます。たとえば、次のようになります。
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

## 関連項目

#### その他のリソース

[Test-CsMcxP2PIM](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxP2PIM)  
[Test-CsUcwaConference](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference)

