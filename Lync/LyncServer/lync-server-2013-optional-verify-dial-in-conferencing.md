---
title: 'Lync Server 2013: (オプション) ダイヤルイン会議の検証'
TOCTitle: (オプション) ダイヤルイン会議の検証
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48271858
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (オプション) Lync Server 2013 でのダイヤルイン会議の検証

 

_**トピックの最終更新日:** 2011-01-21_

ダイヤルイン会議の設定の Web ページとダイヤルイン アクセス番号が正しく動作していることを確認するには、以下を実行する必要があります。

  - 簡易 URL にサインインして、ダイヤルイン会議の設定の Web ページをテストします。

  - この後のスクリプトを実行して、特定のプールでそのアクセス番号が正しく動作することをテストします。 このスクリプトは、アクセス番号への通話をシミュレートします。 このスクリプトを使用するには、特定のプールでホストされている 1 つの統合コミュニケーション (UC) クライアントの SIP アドレスと資格情報が必要です。

このステップはオプションです。

## 特定のプールのアクセス番号をテストするには

1.  RTCUniversalServerAdmins グループのメンバーか、**Cs-ServerAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    結果レポートに、コマンドの成否と特定の診断情報が表示されます。 –Verbose フラグには、検出されたアクセス番号の数とその詳細に関する情報が、より詳しく表示されます。

