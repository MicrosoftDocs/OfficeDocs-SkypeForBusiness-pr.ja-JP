---
title: -Roll を使用した AV および OAuth 証明書のステージング Set-CsCertificate
description: を使用して AV および OAuth 証明書をステージングする-CsCertificate のロール。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3732c4adb4327cc1e4111307ab2d72ed080cf221
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541843"
---
# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>Lync Server 2013 での AV および OAuth 証明書のステージングを使用した Set-CsCertificate

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-13_

音声ビデオ (A/V) 通信は、Microsoft Lync Server 2013 の主要なコンポーネントです。 アプリケーション共有や音声ビデオ会議などの機能は、音声ビデオエッジサービスに割り当てられている証明書、特に音声ビデオ認証サービスに依存します。

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>この新機能は、音声ビデオエッジサービスと <EM>Oauthtokenissuer</EM> 証明書に対して動作するように設計されています。 音声ビデオエッジサービスと OAuth 証明書の種類を使用して、他の証明書の種類をプロビジョニングすることはできますが、音声ビデオエッジサービス証明書による共存の動作からはメリットがありません。</P>
> <LI>
> <P>Microsoft Lync Server 2013 証明書の管理に使用する Lync Server 管理シェルのコマンドレットは、音声ビデオエッジサービス証明書を <EM>Audiovideoauthentication</EM> 証明書の種類として、OAuthServer 証明書の種類が <EM>Oauthtokenissuer</EM>であることを示します。 このトピックの残りの部分では、証明書を一意に識別するために、同じ識別子の種類、 <EM>Audiovideoauthentication</EM> 、および <EM>Oauthtokenissuer</EM>から参照されます。</P></LI></OL>



</div>

音声ビデオ認証サービスは、クライアントとその他の音声ビデオコンシューマーによって使用されるトークンの発行を担当します。 トークンは、証明書の属性から生成され、証明書の有効期限が切れたときに、新しい証明書によって生成された新しいトークンに接続が失われ、再参加するための要件が発生します。 Lync Server 2013 の新機能により、古い証明書を事前に期限切れにして、両方の証明書を一定期間有効にすることができるようになり、この問題が軽減されます。 この機能では、Set-CsCertificate Lync Server 管理シェルコマンドレットで更新された機能を使用します。 新しいパラメーター– Roll は、既存のパラメーター– EffectiveDate を指定して、新しい AudioVideoAuthentication 証明書を証明書ストアに配置します。 以前の AudioVideoAuthentication 証明書は、発行されたトークンを検証するために引き続き残っています。 新しい AudioVideoAuthentication 証明書を適所に配置すると、次の一連のイベントが発生します。

<div>


> [!TIP]
> Lync Server 管理シェルコマンドレットを使用して証明書を管理するには、エッジサーバーの各目的に個別の証明書を要求することができます。 [Lync Server 展開ウィザード] の [証明書ウィザード] を使用すると、証明書を作成できますが、通常は、エッジサーバーのすべての証明書を1つの証明書に結合する <STRONG>既定</STRONG> の種類が使用されます。 ローリング証明書機能を使用する場合は、AudioVideoAuthentication 証明書を他の証明書の用途から切り離すことをお勧めします。 既定の種類の証明書をプロビジョニングおよびステージングすることもできますが、結合された証明書の AudioVideoAuthentication 部分のみがステージングによる恩恵を受けます。 アクセスエッジサービスに関連付けられている新しい証明書を使用するには、証明書の有効期限が切れたときに、インスタントメッセージングの会話をログアウトして再度ログインする必要があるユーザー。 Web 会議エッジサービスを使用して Web 会議に参加しているユーザーに対して同様の現象が発生します。 OAuthTokenIssuer 証明書は、すべてのサーバーの間で共有される特定の種類の証明書です。 1つの場所で証明書を作成して管理すると、その証明書は他のすべてのサーバーの中央管理ストアに格納されます。



</div>

Set-CsCertificate コマンドレットを使用するとき、および現在の証明書の有効期限が切れる前にこのコマンドレットを使用して証明書をステージングするときのオプションと要件を十分に理解するには、さらに詳しい説明が必要です。 重要なのは –Roll パラメーターですが、このパラメーターの用途は実質的に 1 つです。 パラメーターとして定義すると、EffectiveDate によって定義された証明書に関する情報 (AudioVideoAuthentication および OAuthTokenIssuer など) についての情報を提供することを Set-CsCertificate に通知されます。

**-ロール:** – Roll パラメーターは必須であり、それと一緒に指定する必要がある依存関係を持っています。 どの証明書が影響を受け、どのように適用されるかを完全に定義するための必須パラメーターです。

**-EffectiveDate:** パラメーター– EffectiveDate は、新しい証明書が現在の証明書と共同で有効になるタイミングを定義します。 – EffectiveDate は、現在の証明書の有効期限に近い場合もあれば、長期間になることもあります。 AudioVideoAuthentication 証明書の EffectiveDate が推奨される最小値は8時間になります。これは、AudioVideoAuthentication 証明書を使用して発行された AV エッジサービストークンの既定のトークンの有効期間です。

OAuthTokenIssuer 証明書をステージングするときは、証明書が有効になるまでのリード タイムの要件が異なります。OAuthTokenIssuer 証明書のリード タイムは、現在の証明書の有効期限が切れる 24 時間以上前に設定する必要があります。共存のリード タイムが長いのは、OAuthTokenIssuer 証明書に依存する他のサーバーの役割 (たとえば Exchange Server) で、証明書によって作成された認証と暗号化キー材料の保有期間が長いためです。

**-Thumbprint:** 拇印は、その証明書に固有の証明書の属性です。 –Thumbprint パラメーターを使用して、Set-CsCertificate コマンドレットの処理によって影響を受ける証明書を識別します。

**-型:** – Type パラメーターは、1つの証明書の使用法の種類、または証明書の使用法の種類のコンマ区切りリストを受け入れることができます。 証明書の種類は、コマンドレットに対して、証明書の目的をサーバーに対して識別するものです。 たとえば、「AudioVideoAuthentication」と入力すると、音声ビデオエッジサービスと AV 認証サービスによって使用されます。 異なる種類の証明書を同時にステージングおよびプロビジョニングする場合は、証明書に対して最も必要な最小のリード時間を考慮する必要があります。 たとえば、AudioVideoAuthentication と OAuthTokenIssuer の種類の証明書をステージングする必要があるとします。 – EffectiveDate は、少なくとも24時間のリードタイムを持つ2つの証明書 (この場合は OAuthTokenIssuer) の方が多い必要があります。 24時間のリードタイムを使用して AudioVideoAuthentication 証明書をステージしない場合は、要件により多くの EffectiveDate を使用して、別のステージを行います。

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>-ロールおよび-EffectiveDate パラメーターを使用して音声ビデオエッジサービス証明書を更新または更新するには

1.  Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2.  音声ビデオエッジサービスの既存の証明書のエクスポート可能な秘密キーを使用して、更新または新しい AudioVideoAuthentication 証明書を要求します。

3.  新しい AudioVideoAuthentication 証明書をエッジサーバーにインポートし、プール内の他のすべてのエッジサーバーにインポートします (プールが展開されている場合)。

4.  インポートした証明書を Set-CsCertificate コマンドレットで構成し、–Roll パラメーターを –EffectiveDate パラメーターと共に使用します。 有効日は、現在の証明書の有効期限 (14:00:00 または 2:00:00 PM) からトークン存続時間 (既定では 8 時間) を引いた値で定義します。 これにより、証明書をアクティブに設定する必要があり、– EffectiveDate \<string\> : "7/22/2012 6:00:00 AM" であることがわかります。
    
    <div>
    

    > [!IMPORTANT]
    > エッジプールの場合は、すべての AudioVideoAuthentication 証明書を展開し、最初の証明書の– EffectiveDate パラメーターで定義された日時によってプロビジョニングされている必要があります。これにより、古い証明書が新しい証明書を使用して更新される前に、以前の証明書の有効期限が切れています。

    
    </div>
    
    –Roll および –EffectiveTime パラメーターを使用する Set-CsCertificate コマンドは次のようになります。
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-CsCertificate コマンドの例を次に示します。
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > EffectiveDate は、サーバーの地域と言語の設定に合った形式にする必要があります。この例で使用している地域と言語の設定は英語 (米国) です。

    
    </div>

コンシューマーが使用中の AudioVideoAuthentication を検証するための既存の証明書をそのまま使用しながら、同時に AudioVideoAuthentication の新しいトークンを発行するための新しい証明書をステージングできるように Set-CsCertificate、-Roll、および –EffectiveDate が使用するプロセスを詳しく理解するには、時系列の図を使う方法が効果的です。

次の例では、管理者は、音声ビデオエッジサービスの証明書の有効期限が07/22/2012 の 2:00:00 PM に設定されていることを確認します。 ユーザーは新しい証明書を要求して受信し、プール内の各エッジサーバーにインポートします。 2012 年 7 月 22 日の午前 2:00 に、管理者は –Roll、新しい証明書の拇印文字列に相当する -Thumbprint、および 2012 年 7 月 22 日の午前 6:00 に設定した –EffectiveTime を使用して、Get-CsCertificate の実行を開始します。 各エッジサーバーでこのコマンドを実行します。

![Roll パラメーターと EffectiveDate パラメーターを使用します。](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Roll パラメーターと EffectiveDate パラメーターを使用します。")

有効時刻 (2012 年 7 月 22 日午前 6:00) になると、新しいトークンはすべて新しい証明書によって発行されます。トークンを検証する場合、トークンはまず新しい証明書に照らして検証されます。検証が失敗した場合は、古い証明書が試されます。新しい証明書を試してから古い証明書にフォールバックするこのプロセスは、古い証明書の有効期限まで続きます。古い証明書の有効期限が切れた後は (2012 年 7 月 22 日午後 2:00)、トークンは新しい証明書のみを使用して検証されます。古い証明書は、次のように Remove-CsCertificate コマンドレットに –Previous パラメーターを指定して安全に削除できます。

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>–Roll および -EffectiveDate パラメーターを使用して OAuthTokenIssuer 証明書の更新または書き換えを行うには

1.  Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2.  音声ビデオエッジサービスの既存の証明書のエクスポート可能な秘密キーを使用して、更新または新しい OAuthTokenIssuer 証明書を要求します。

3.  新しい OAuthTokenIssuer 証明書をプール内のフロントエンドサーバーにインポートします (プールが展開されている場合)。 OAuthTokenIssuer 証明書はグローバルにレプリケートされるので、展開内の任意のサーバーで更新および書き換うだけで十分です。 フロントエンドサーバーは例として使用されます。

4.  インポートした証明書を Set-CsCertificate コマンドレットで構成し、–Roll パラメーターを –EffectiveDate パラメーターと共に使用します。有効日は、現在の証明書の有効期限 (14:00:00 または 2:00:00 PM) から少なくとも 24 時間を引いた値で定義します。
    
    –Roll および –EffectiveTime パラメーターを使用する Set-CsCertificate コマンドは次のようになります。
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Set-CsCertificate コマンドの例を次に示します。
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > EffectiveDate は、サーバーの地域と言語の設定に合った形式にする必要があります。この例で使用している地域と言語の設定は英語 (米国) です。

    
    </div>

有効時刻 (2012 年 7 月 21 日午前 1:00) になると、新しいトークンはすべて新しい証明書によって発行されます。トークンを検証する場合、トークンはまず新しい証明書に照らして検証されます。検証が失敗した場合は、古い証明書が試されます。新しい証明書を試してから古い証明書にフォールバックするこのプロセスは、古い証明書の有効期限まで続きます。古い証明書の有効期限が切れた後は (2012 年 7 月 22 日午後 2:00)、トークンは新しい証明書のみを使用して検証されます。古い証明書は、次のように Remove-CsCertificate コマンドレットに –Previous パラメーターを指定して安全に削除できます。

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でエッジサーバー証明書を計画する](lync-server-2013-plan-for-edge-server-certificates.md)  
[Lync Server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[Lync Server 2013 のエッジ証明書のセットアップ](lync-server-2013-set-up-edge-certificates.md)  
[設定-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))  
[削除-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

