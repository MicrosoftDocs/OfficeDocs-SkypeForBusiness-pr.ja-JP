---
title: 'Lync Server 2013: (オプション) ダイヤルイン会議の検証'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebfebd5dceff50d7d4b7647c7709bb88b7c1fa8e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530774"
---
# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a>オプションLync Server 2013 でのダイヤルイン会議の確認

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2011-01-21_

ダイヤルイン会議の設定の Web ページとダイヤルイン アクセス番号が正しく動作していることを確認するには、以下を実行する必要があります。

  - 簡単な URL にサインインして、ダイヤルイン会議の設定の Web ページをテストします。

  - この後のスクリプトを実行して、特定のプールでそのアクセス番号が正しく動作することをテストします。 このスクリプトは、アクセス番号への通話をシミュレートします。 このスクリプトを使用するには、特定のプールでホストされている 1 つの統合コミュニケーション (UC) クライアントの SIP アドレスと資格情報が必要です。

このステップはオプションです。

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a>特定のプールのアクセス番号をテストするには

1.  RTCUniversalServerAdmins グループのメンバーか、**Cs-ServerAdministrator** または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    結果レポートに、コマンドの成否と特定の診断情報が表示されます。 –Verbose フラグには、検出されたアクセス番号の数とその詳細に関する情報が、より詳しく表示されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

